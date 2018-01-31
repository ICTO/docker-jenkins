FROM jenkins/jenkins:lts

USER root
# Install debian package dependencies
RUN apt-get update && apt-get install -y curl php7.0-cli php7.0-curl python-pip python-dev libffi-dev git ruby ruby-dev rubygems build-essential
# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
RUN apt-get install nodejs
USER jenkins
# Install FPM
RUN gem install --user fpm
# Install Ansible + Dependencies
RUN cd ~ && pip install --user pycrypto jinja2 six paramiko httplib2 pyyaml
RUN cd ~ && git clone https://github.com/ansible/ansible.git && cd ansible && git checkout v2.4.2.0-1
# Install Composer
RUN cd ~ && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && mkdir bin && php composer-setup.php --install-dir=bin --filename=composer && rm composer-setup.php
