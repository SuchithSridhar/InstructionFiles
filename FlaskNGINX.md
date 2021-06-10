# Setup Flask Application with NGINX and gunicorn

Installation :
- Install dependancies `apt install nginx certbot python3-certbot gunicorn`
- Confirm `gunicorn` support for Python 3 using `gunicorn --version`
- Install Flask `pip install flask` and any other dependancies

NGINX Configuration :
- Create a file `flask` or any name in `/etc/nginx/sites-available`
- Add NGINX setup on this file as :
```
server {
    listen 80;
    server_name YOUR_IP_OR_DOMAIN;

    location / {
        proxy_pass http://localhost:8000;
        include /etc/nginx/proxy_params;
        proxy_redirect off;
    }
}
```
- Ensure "proxy_pass http://localhost:8000" is listening to the port the Flask App will be hosted in.
- Link this to `sites-enabled` using `ln -s /etc/nginx/sites-available/flask /etc/nginx/sites-enabled`
- Start and test NGINX `systemctl enable nginx`, `systemctl start nginx`, `systemctl status nginx`

Running gunicorn :
- `cd` to Project Directory and run `gunicorn -b 0.0.0.0:8001 -w 3 index:app`
- Ensure it binds to port as `0.0.0.0:PORT`

Run `gunicorn` using `&` or `setsid -f` and the website is hosted!
