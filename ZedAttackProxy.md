```bash
docker run -d \
  --name owasp-zap-daemon \
  -p 8080:8080 \
  -v /home/mateus/zap:/home/zap/.zap/:rw \
  zaproxy/zap-stable:2.17.0 \
  zap.sh -daemon -host 0.0.0.0 -port 8080 -config api.disablekey=true
```