# vagrant-openam

<!--
```
openssl req -batch -new -x509 -newkey rsa:2048 -nodes -sha256 \
  -subj /CN=idp.sheepcloud.org/O=self-signed -days 3650 \
  -keyout idp.key \
  -out idp.crt
cat idp.crt idp.key > bundle.crt
openssl pkcs12 -export -in idp.crt -inkey idp.key -out idp.p12 -certfile idp.crt -name "tomcat"

keytool -importkeystore -srckeystore idp.p12 -srcstoretype pkcs12 -srcstorepass "changeit" -srcalias "tomcat" -destalias "tomcat" -destkeystore .keystore -deststoretype jks -deststorepass "changeit" -destalias "tomcat" -noprompt


openssl req -batch -new -x509 -newkey rsa:2048 -nodes -sha256 \
  -subj /CN=sp.sheepcloud.org/O=self-signed -days 3650 \
  -keyout sp.key \
  -out sp.crt
```

```
echo "openam soft nofile 65536" >> /etc/security/limits.conf 
echo "openam hard nofile 131072" >> /etc/security/limits.conf 
```
https://idp1.sheepcloud.org:8443/openam/
https://idp2.sheepcloud.org:8443/openam/



https://idp2.sheepcloud.org/openam/saml2/jsp/exportmetadata.jsp

```
amAdmin
amadmin55
```

サーバー URL:

https://idp.sheepcloud.org:443

Cookieドメイン: 
.sheepcloud.org

```
設定ストアの詳細
ポート：50389
管理者ポート：4444 
JMX ポート：1689
```

-->
