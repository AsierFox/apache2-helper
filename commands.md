# Restart server

```{r, engine='bash', count_lines}
systemctl restart apache2.service
```

# Enable mod_rewrite for .htaccess
Also do not forget to change apache2.conf configuration to AllowOverride All.
```{r, engine='bash', count_lines}
sudo a2enmod rewrite
sudo service apache2 restart
```

# Change default permissions to /var/www/
Also do not forget to change apache2.conf configuration to AllowOverride All.
```{r, engine='bash', count_lines}
sudo chgrp www-data /var/www
sudo chmod 775 /var/www
sudo chmod g+s /var/www
sudo useradd -G www-data [USERNAME]
usermod -a -G www-data [USERNAME]
sudo chown [USERNAME] /var/www/
```

# Change php version

### From php5.6 to php7.0
```{r, engine='bash', count_lines}
sudo a2dismod php5.6 ; sudo a2enmod php7.0 ; sudo service apache2 restart
```

### From php7.0 to php5.6
```{r, engine='bash', count_lines}
sudo a2dismod php7.0 ; sudo a2enmod php5.6 ; sudo service apache2 restart
```
