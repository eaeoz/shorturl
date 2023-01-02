### URL SHORTENER

##### INSTALLATION

`docker run -itd --name shorturl -p 8000:8000 sedate/shorturl:1`

admin page default login information (http://{{ip-address}}:8000/admin)

```
username:admin
password:admin
```

if you use custom domain name you must edit trusted domains in docker shell:
```
docker exec -it shorturl bash
nano /shorturl/urlshortnerprj/settings.py

find CSRF_TRUSTED_ORIGINS and edit your domain name at the list.
```

create new user:

```
docker exec -it shorturl bash
(cd /shorturl && python3 manage.py createsuperuser)
```

##### CODE

`git clone https://github.com/eaeoz/shorturl.git`
