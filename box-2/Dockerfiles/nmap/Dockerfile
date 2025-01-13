# Utiliser une image Alpine légère comme base
FROM alpine:3.12

# Installer les dépendances strictement nécessaires pour exécuter Nmap
RUN apk add --update --no-cache \
    nmap \
    libpcap \
    ca-certificates \
 && update-ca-certificates

# Définir le point d'entrée pour exécuter Nmap
ENTRYPOINT ["/bin/sh", "-c", "tail -f /dev/null"]