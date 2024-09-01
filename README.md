# Adguard Setup

backup: cp /etc/AdGuardHome/config.yaml /etc/AdGuardHome/config.yaml.back
add user to config.yaml
```
users:
  - name: <User name>
    password: <BCrypt-encrypted password> # https://bcrypt-generator.com/
```

allow update: /etc/init.d/adguardhome and delete --no-check-update

stop port 3000 redirect:
```
sed -i 's/--glinet//g' /etc/init.d/adguardhome
/etc/init.d/adguardhome restart
```
