# Eventex

Sistema de Eventos encomendado pela Morena.

[![Build Status](https://travis-ci.org/williangd/wttd.svg?branch=master)](https://travis-ci.org/williangd/wttd)

## Como desenvolver?

1. Clone o repositório.
2. Crie um virtualenv com Python 3.5.
3. Ative o virtualenv.
4. Instale as dependências.
5. Configure a instância com o .env.
6. Execute os testes.

```console
git clone https://github.com/williangd/wttd.git wttd
cd wttd
python -m venv .wttd
source .wttd/bin/activate
pip install -r requirements-dev.txt
cp contrib/env-sample .env
python manage.py test
```

## Como fazer o deploy?

1. Crie uma instância no heroku.
2. Envie as configurações para o heroku.
3. Defina uma SECRET_KEY segura para instância.
4. Defina DEBUG=False   
5. Configure o seriço de e-mail.
6. Envie o código para o heroku.

```console
heroku create minha_instancia
heroku config:push
heroku config:set SECRET_KEY=`python contrib/secret_gen.py`
heroku config:set DEBUG=False
# Configurar e-mail
git push heroku master --force
```