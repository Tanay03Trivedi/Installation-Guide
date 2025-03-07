# Apache Configuration

## Set Permissions for Web Directory
```sh
sudo chmod 775 -R /home//username/www
sudo chown -R username:www-data /home/username/www
```

## Update Virtual Host Configuration
Edit the default site configuration:
```sh
sudo nano /etc/apache2/sites-available/000-default.conf
```
Ensure the document root is set correctly:
```
DocumentRoot /home/username/www
```

## Update Apache Configuration
Edit the Apache main configuration file:
```sh
sudo nano /etc/apache2/apache2.conf
```
If there are any `Require all denied` directives, replace them with `Require all granted`.

### Ensure Proper Directory Access
Add or modify the following block in `apache2.conf`:
```apache
<Directory /home/username/www>
    Options Indexes FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>
```

## Restart Apache to Apply Changes
```sh
sudo systemctl restart apache2
