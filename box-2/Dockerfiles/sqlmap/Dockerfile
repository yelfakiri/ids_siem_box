FROM ubuntu:24.04
RUN apt update && apt upgrade -y
RUN apt install -y git wget python3 python-is-python3 sqlite3
WORKDIR /app
RUN git clone --depth 1 https://github.com/sqlmapproject/sqlmap.git sqlmap
WORKDIR /app/sqlmap
ENTRYPOINT ["tail", "-f", "/dev/null"]