## dockerの導入について
以下を参照
> https://zenn.dev/sprout2000/articles/95b125e3359694

## 構築手順
1,docker-composeを使用してbuild
```
docker-compose build
```

2,projectを作成
```
sudo docker-compose run web python3 -m django startproject {#任意のプロジェクト名} .
```

3,プロジェクトフォルダ内にあるsettings.pyのDATABASESという項目を編集
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

4,各サービスを起動
```
docker-compose up -d
```
