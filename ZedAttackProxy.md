## Zed Attack Proxy (ZAP)

O Zed Attack Proxy (ZAP) é uma ferramenta gratuita e de código aberto desenvolvida para encontrar vulnerabilidades de segurança em aplicações web durante as fases de desenvolvimento e testes.

#### Principais funcionalidades  
- **Proxy Intermediário**: Posiciona-se entre o navegador do usuário e o servidor web. Ele intercepta, inspeciona e permite alterar requisições e respostas HTTP/HTTPS em tempo real.  
- **Spider (Rastreador)**: Rastreia links automaticamente para criar um mapa completo de toda a estrutura da aplicação.  
- **Varredura Passiva**: Analisa o tráfego de forma silenciosa em segundo plano. Ela busca falhas aparentes como cabeçalhos inseguros sem realizar alterações ou injetar dados.  
- **Automação (CI/CD)**: Pode funcionar de forma automatizada via linha de comando ou API integrada.  

```bash
sudo docker run -d \
  --name owasp-zap-web \
  -p 8070:8070 \
  -p 8090:8090 \
  -v /home/mateus/zap:/home/zap/.zap/:rw \
  ghcr.io/zaproxy/zap-stable:2.17.0 \
  zap-webswing.sh 


# -d - Executa o container em segundo plano
# 8080:8080: Conecta a porta 8080 da sua máquina local à porta 8080 interna do container.
# -p 8090:8090: Adiciona a porta padrão que o ZAP usa internamente como proxy.
# :rw: Dá permissão de leitura e escrita (read and write) para o container
# zap-webswing.sh: O script que inicializa o OWASP ZAP dentro do container.
# -host 0.0.0.0: Obriga o ZAP a escutar em todas as interfaces de rede do container  
# -config api.addrs.addr.name=.*: Libera a API interna para aceitar requisições de qualquer origem na rede.
#-config api.disablekey=true: Desativa temporariamente a obrigatoriedade de uma chave de API para o seu primeiro login na interface Webswing.

```

### Referências
- [Documentação oficial](https://www.zaproxy.org/getting-started/)