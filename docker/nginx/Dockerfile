FROM nginx

RUN apt-get update \
  && apt-get install -y unzip vim telnet \
  && rm -rf /var/lib/apt/lists/*

COPY ./entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
COPY ./template/default.ctmpl /templates/default.ctmpl

ADD https://releases.hashicorp.com/consul-template/0.12.2/consul-template_0.12.2_linux_amd64.zip /usr/bin/
RUN unzip /usr/bin/consul-template_0.12.2_linux_amd64.zip -d /usr/local/bin

WORKDIR "/var/www"
EXPOSE 80
ENTRYPOINT ["/entrypoint.sh"]


