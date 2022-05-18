## dockerの導入について
以下を参照
> https://zenn.dev/sprout2000/articles/95b125e3359694

## 構築手順
1,projectを作成
```
sudo docker-compose run web python3 -m django startproject {#任意のプロジェクト名} .
```

2,プロジェクトフォルダ内にあるsettings.pyのDATABASESという項目を編集
```
vim settings.py
```
###### settings.pyの中身
```
DATABASES = {
    'default': {
        #'ENGINE': 'django.db.backends.sqlite3',
        'ENGINE': 'django.db.backends.mysql',
        #'NAME': BASE_DIR / 'db.sqlite3',
        'NAME': 'test-db',
        'USER': 'test',
        'PASSWORD': 'password',
        'HOST': 'db',
        'PORT': '3306'
    }
}
```

3,各サービスを起動
```
docker-compose up -d
```

4,起動確認
> http://localhost:8000
に接続して、ウェルカムページが表示されるか確認。
