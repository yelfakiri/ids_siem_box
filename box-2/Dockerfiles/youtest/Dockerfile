# Utiliser Kali Linux comme base
FROM kalilinux/kali-rolling

# Mise à jour et installation des outils essentiels
RUN apt-get update && apt-get install -y \
    nmap \                        
    net-tools \  
    iputils-ping \              
    ftp \                         
    telnet \                      
    curl \                        
    wget \                        
    netcat-openbsd \                  
    openssh-client \              
    default-mysql-client \        
    sqlmap \                      
    metasploit-framework \        
    hydra \                       
    nikto \                       
    john \                        
    && apt-get clean

# Garder le conteneur actif pour les tests interactifs
ENTRYPOINT ["/bin/bash"]