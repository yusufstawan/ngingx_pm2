VueJS PM2 + Nginx

# /var/www/your_domain.id

## deploy staging
npm install
npm run build
pm2 start npm --name "your_doman.id[8982]" -- run start:staging

## deploy production
npm install
npm run build
pm2 start npm --name "your_doman.id[8982]" -- run start:production

# /etc/nginx/sites-available
## nginx sites-available
use example file your_domain.id in this repo

## create symlink
sudo ln -s /etc/nginx/sites-available/your_domain.id /etc/nginx/sites-enabled

## check nginx config
sudo nginx -t

## restart nginx
sudo service nginx restart

## ssl
sudo certbot --nginx -d your_domain.id

## updat ssl
sudo certbot renew --dry-run
