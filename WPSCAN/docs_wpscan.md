## WPScan

O WPScan é uma ferramenta de segurança especializada em identificar informações e possíveis vulnerabilidades em sites WordPress. Ela realiza enumeração de usuários, plugins, temas, versões do WordPress e consulta uma base de dados de **vulnerabilidades conhecidas**  

### Instalação  
```bash
sudo apt update
sudo apt install ruby ruby-dev build-essential
sudo apt install wpscan
```  
### Comandos  
```bash
# Analise basica do ambiente Wordpress
wpscan --url https://site.com
# Retorno: Versão, tema ativo, plugins detectados, headers HTTP, diretórios acessíveis e arquivos expostos

# Enumeração de usuarios
wpscan --url https://site.com --enumerate u

# Enumeracao de plugins
wpscan --url https://site.com --enumerate p

# Enumeracao de temas
wpscan --url https://site.com --enumerate t
```

### Utilizando a API do WPScan  
O WPScan possui uma base de vulnerabilidades própria. Para usa-la é necessário criar uma conta no site [wpscan.com](https://wpscan.com/?utm_source=chatgpt.com)

```bash
# Com a API ativada, a ferramenta consegue informar:
# - CVEs conhecidos
# - Vulnerabilidades de plugins
# - Vulnerabilidades de temas
# - Severidade dos problemas

wpscan --url https://site.com --api-token SUA_API_KEY

# Detectar plugins vulneraveis
wpscan --url https://site.com \
--enumerate vp \
--api-token SUA_API_KEY

# Modo de agressividade: misto
wpscan --url https://site.com --plugins-detection mixed

# Modo de agressividade: aggressive
wpscan --url https://site.com --plugins-detection aggressive
```

### Modos disponíveis  
| Modo       | Descrição                            |
| ---------- | ------------------------------------ |
| passive    | Apenas coleta passiva                |
| mixed      | Passivo + algumas requisições extras |
| aggressive | Busca ativa de plugins e temas       |
