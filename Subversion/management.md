

## Subversionの保守

### リポジトリの作成

リポジトリの作成は、svnadmin コマンドを使って作成する。

### リポジトリの削除

リポジトリの削除については、リポジトリの当該ディレクトリを削除することで削除ができる。
特にSVNコマンドが用意されているわけではありません。

### バックアップ/リストア

#### バックアップ

SVNのバックアップは dvnadmin dumpコマンドでダンプすることで、履歴を含めたバックアップを行うことができます。

```
svnadmin dump [リポジトリのディレクトリ] > [ダンプファイル名]
```
例: sunadmin dump c:\svn\repository\sampleproject > sampleproject.dmp 

#### リストア

SVNのリストアは dvnadmin loadコマンドで、バックアップしたダンプファイルをリストアすることできます。

```
svnadmin load [リポジトリのディレクトリ] < [ダンプファイル名]
```
例: sunadmin load c:\svn\repository\sampleproject < sampleproject.dmp 

### 権限設定方法

リポジトリの権限は、SVNサーバのauthzファイルを編集することで権限設定を行うことができます。