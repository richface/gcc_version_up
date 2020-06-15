## **■ package**
+ x86: CentOS 5, gcc 4.7
+ EL7: CentOS 8, gcc 9.1
+ EL8: CentOS 8, gcc 9.1

## **■ 修正内容**

### **boost containerの代わりに標準container使用**
+ x86: 影響なし
+ EL7
+ EL8
    - imap全体的な動作に関連する
    - compile timeでの互換性を確認

### **□ headerファイルの追加**
+ x86
+ EL7
+ EL8
    - image変換動作に関連
    - compile timeでの互換性を確認

### **□ naming collisions回避**
+ x86: 影響なし
+ EL7
+ EL8
    - maildbfmngの影響、テストは必要ない

### **□ ldapのheaderのpath変更**
+ x86
+ EL7
    - compile timeで適切なheaderファイルを参照していることを確認
+ EL8
    - ldap動作関連
    - openldap versionが変更、 ldapに関する一般的な動作を確認

### **□ readdir_r defrecated (glib 2.24~)**
+ x86
+ EL7
    - 影響なし
+ EL8
    - directory探索する動作、（queue配送、chkmbdbfなど）
    - change readdir_r(thread safe) to readdir(thread unsafe)  
       `In the current POSIX.1 specification (POSIX.1-2008), readdir() is not required to be thread-safe.  However, in modern implementations (including the glibc implementation), concurrent  calls  to
       readdir()  that  specify different directory streams are thread-safe.  In cases where multiple threads must read from the same directory stream, using readdir() with external synchronization is
       still preferable to the use of the deprecated readdir_r(3) function.  It is expected that a future version of POSIX.1 will require that readdir() be thread-safe when  concurrently  employed  on different directory streams.`

### **□ WARNING修正: -Wregister**
+ x86
+ EL7
+ EL8
    - 影響範囲が多い、動作の影響はなし


### **□ WARNING修正: -Wbool-compare**
+ x86
+ EL7
+ EL8
    - メールクォーター関連の影響、動作の影響はなし

### **□ WARNING修正: -Wcatch-value=**
+ x86
+ EL7
+ EL8
    - テンプレートファイルの作成に関連、動作の影響はなし


### **□ WARNING修正: -Wbuiltin-declaration-mismatch**
+ x86
+ EL7
+ EL8
    - mailcreator.cgi 関連、動作の影響はなし


### **□ WARNING修正:  -Wmisleading-indentation**
+ x86
+ EL7
+ EL8
    - 影響範囲が多い、動作の影響はなし

### **□ WARNING修正: -Wswitch**
+ x86
+ EL7
+ EL8
    - smtp, imap 関連、動作の影響はなし

### **□ WARNING修正: -format-truncation, -Wstringop-truncation**
+ x86
+ EL7
+ EL8
    - CGI全体的に関連、動作の影響はなし

### **□ shared library**
+ x86
+ EL7
    - 影響なし
+ EL8
    - liblber.a （ldap)
    - libldap.a （ldap)
    - libsqlite3.a （国 IP)
    - libz.a （backup, restore）
