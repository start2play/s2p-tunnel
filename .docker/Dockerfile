FROM ubuntu:latest

COPY . ./

RUN  apt-get update \
  && apt-get install -y wget

RUN  wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-arm64.deb \
  && dpkg -i cloudflared-linux-arm64.deb

CMD cloudflared --config config.yml --origincert .cloudflared/cert.pem tunnel run