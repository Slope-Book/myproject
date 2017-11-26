# myproject
学習のため、初めてCMSフレームワークに触れてみました。<p>

### mezzanineインストール
$ pip install mezzanine    

### プロジェクト作成
mezzanine-project myproject    

### 開発用のDB作成
$ cd myproject
$ python manage.py createdb    

### 画面の確認
$ python manage.py runserver<p>
デフォルトであれば、 http://localhost:8000 にアクセスすれば画面の確認が出来ます。    

### テンプレートの複製
$ python manage.py collecttemplates    

### テーマの変更
私は http://thecodinghouse.in/themes/moderna/ からダウンロードしてきたmodernaを使用しました。
プロジェクトディレクトリの下にDjangoアプリ（モジュール）として配置します。  

次にコピーしたテーマをDjangoアプリケーションとして設定するために、
myproject/settings.py の INSTALLED_APPS の最後、および TEMPLATES/DIRS の先頭に追加します。  

TEMPLATES = [
    {
        "BACKEND": "django.template.backends.django.DjangoTemplates",<p>
        "DIRS": [<p>
            os.path.join(PROJECT_ROOT, "moderna/templates"),<p>
            os.path.join(PROJECT_ROOT, "templates")<p>
        ],<p>
        "APP_DIRS": True,<p>
        ・<p>
        ・<p>
]<p>
<p>
INSTALLED_APPS = (<p>
    ・<p>
    ・<p>
    "mezzanine.twitter",<p>
    # "mezzanine.accounts",<p>
    # "mezzanine.mobile",<p>
    "moderna",<p>
)<p>

