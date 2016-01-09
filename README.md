# Eventex

Sistema de eventos encomendado pela Morena

[![Build Status](https://travis-ci.org/macndesign/wttd.svg?branch=master)](https://travis-ci.org/macndesign/wttd)
[![Code Climate](https://codeclimate.com/github/macndesign/wttd/badges/gpa.svg)](https://codeclimate.com/github/macndesign/wttd)
[![Coverage Status](https://coveralls.io/repos/macndesign/wttd/badge.svg?branch=master&service=github)](https://coveralls.io/github/macndesign/wttd?branch=master)


## Como desenvolver?

1. Clone o repositório.
2. Crie um virtualenv com Python 3.5
3. Ative o virtualenv.
4. Instale as dependências.
5. Configure a instância com .env

```console
git clone git@github.com:macndesign/wttd.git wttd
cd wttd
python -m venv .wttd
source .wttd/bin/activate
pip install -r requirements-dev.txt
cp contrib/env-sample .env
python manage.py test
```


## Como fazer o deploy?

1. Crie uma instância do Heroku.
2. Envie as configurações para o Heroku.
3. Define uma SECRET_KEY segura para a instância.
4. Defina DEBUG=FALSE
5. Configure o serviço de email.
6. Envie o código para o Heroku.

```console
heroku create minhainstancia
heroku config:push
heroku config:set SECRET_KEY=`python contrib/secret_gen.py`
heroku config:set DEBUG=False
# configura o email
git push heroku master --force
```