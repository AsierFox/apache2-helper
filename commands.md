# Restart server

```{r, engine='bash', count_lines}
sudo systemctl restart apache2.service
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
