**Instânciação em Docker**
```bash
sudo docker run -d \
  --name owasp-zap-web \
  -p 8080:8080 \
  -p 8090:8090 \
  -v /home/mateus/zap:/home/zap/.zap/:rw \
  zaproxy/zap-stable:latest \
  zap-webswing.sh 


# -d - Executa o container em segundo plano
# 8080:8080: Conecta a porta 8080 da sua máquina local à porta 8080 interna do container.
# -p 8090:8090: Adiciona a porta padrão que o ZAP usa internamente como proxy.
# :rw: Dá permissão de read e write para o container
# zap-webswing.sh: O script que inicializa o OWASP ZAP dentro do container.
# -host 0.0.0.0: Obriga o ZAP a escutar em todas as interfaces de rede do container  
# -config api.addrs.addr.name=.*: Libera a API interna para aceitar requisições de qualquer origem na rede.
#-config api.disablekey=true: Desativa temporariamente a obrigatoriedade de uma chave de API para o seu primeiro login na interface Webswing.
```
URL para acesso em rede local: http://192.168.100.11:8080/zap/