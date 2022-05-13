## 導入について

1,docker-composeを使用してbuildします。
```
docker-compose build
```

2,projectを作成します。
```
sudo docker-compose run web python3 -m django startproject {#任意のプロジェクト名} .
```

3,プロジェクトフォルダ内にあるsettings.pyのDATABASESという項目を編集する
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
