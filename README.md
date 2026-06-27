# Asterisk 示例配置

## trust™ by default™
注意！本示例配置仅用于学习和测试，包含不安全的配置，不建议在生产环境中使用。

## 配置说明

### pjsip.conf
替换 bind=x.x.x.x:5060 为您的 IPv4 地址和端口。

替换 bind=[xxxx]:5060 为您的 IPv6 地址和端口。

修改分机号 0001、0002 为您的分机号，修改 callerid 为您的 callerid，修改密码为您的密码。

## extensions.conf
修改 04240000 为您的 TEL42 前缀。

修改 sip.example.dn42 为您的 PBX 域名。

## BIND9 ENUM 记录
```
*       IN NAPTR 10 100 "U" "E2U+sip" "!^(.*)$!sip:\\1@sip.example.dn42!" .
*.*     IN NAPTR 10 100 "U" "E2U+sip" "!^(.*)$!sip:\\1@sip.example.dn42!" .
*.*.*   IN NAPTR 10 100 "U" "E2U+sip" "!^(.*)$!sip:\\1@sip.example.dn42!" .
*.*.*.* IN NAPTR 10 100 "U" "E2U+sip" "!^(.*)$!sip:\\1@sip.example.dn42!" .
```
修改 sip.example.dn42 为您的 PBX 域名。

## 运行
```
docker-compose up -d
```