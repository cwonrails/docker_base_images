FROM ruby:2.4

RUN echo "deb http://apt.gemnasium.com stable main" > /etc/apt/sources.list.d/gemnasium.list \
  && apt-key adv --recv-keys --keyserver keyserver.ubuntu.com E5CEAB0AC5F1CA2A \
  && apt-get update \
  && apt-get upgrade -y \
  && apt-get install -y gemnasium-toolbelt libmysqlclient-dev mysql-client \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* \
  && gem install bundler \
  && gem cleanup \
  && mkdir -p /app/tmp \
  && mkdir /root/.ssh \
  && ssh-keyscan github.com >> /root/.ssh/known_hosts \

WORKDIR /app
