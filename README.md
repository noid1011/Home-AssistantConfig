# Adguard Setup

Install nano:
```
opkg update && opkg install nano
```
Backup config: 
```
cp /etc/AdGuardHome/config.yaml /etc/AdGuardHome/config.yaml.back
```
Add user to config.yaml
```
users:
  - name: <User name>
    password: <BCrypt-encrypted password> # https://bcrypt-generator.com/
```

Allow update: 
```
nano /etc/init.d/adguardhome # delete --no-check-update
```

Stop port 3000 redirect:
```
sed -i 's/--glinet//g' /etc/init.d/adguardhome
```
Restart adguard:
```
/etc/init.d/adguardhome restart
```
