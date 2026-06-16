## Nmap

O **Nmap (network Mapper)** é uma ferramenta de código aberto utilizada para descobertas de hosts, mapeamento de redes, etc.

#### Instalação
```bash
sudo apt update
sudo apt install nmap
nmap --version
```

#### Comandos
- Descobrir quais serviços estão acessíveis:  
    ```bash
    nmap 192.168.1.10
    ```
- Identificar dispositivos ativos em uma sub-rede:  
    ```bash
    nmap 192.168.1.0/24
    ```
- Scan de todas as portas  
    ```bash
    nmap -p- 192.168.1.10
    ```
- Scan de portas específicas  
    ```bash
    nmap -p 22,80,443 192.168.1.10
    ```
- Detecção de versão dos serviços  
    ```bash
    nmap -sV 192.168.1.10
    # Resultado
    # 22/tcp open ssh OpenSSH 9.6
    # 80/tcp open http Apache 2.4.58 
    ```
- Detecção de sistema operacional:  
    ```bash
    sudo nmap -O 192.168.1.10  
    ```