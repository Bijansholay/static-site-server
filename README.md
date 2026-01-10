# NGINX Static Site Server

A simple guide to deploy static websites using NGINX.

## Quick Setup

1. **Install NGINX**
   ```bash
   sudo apt update
   sudo apt install nginx
   ```

2. **Start Service**
   ```bash
   sudo systemctl start nginx
   sudo systemctl enable nginx
   ```

3. **Configure Site**
   ```bash
   sudo nano /etc/nginx/sites-available/mysite
   ```
   
   Add:
   ```nginx
   server {
       listen 80;
       server_name your-domain.com;
       root /var/www/mysite;
       index index.html;
   }
   ```

4. **Enable Site**
   ```bash
   sudo ln -s /etc/nginx/sites-available/mysite /etc/nginx/sites-enabled/
   sudo nginx -t
   sudo systemctl reload nginx
   ```

5. **Deploy Files**
   ```bash
   sudo mkdir -p /var/www/mysite
   sudo cp -r * /var/www/mysite/
   sudo chown -R www-data:www-data /var/www/mysite
   ```

Your static site is now live!


[l](https://roadmap.sh/projects/static-site-server)
