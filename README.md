openssl req -nodes -new -x509 -out ca.crt -keyout ca.key -config req.conf -extensions 'v3_req'

curl --proxy https://proxy:443 https://google.com