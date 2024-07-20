# Tradingview Charts Save and Load Storage 

## Updstrem submodule

```sh
cd saveload_backend
git pull origin master
## updated
cd ..
git add saveload_backend
git commit -m "Update saveload_backend submodule"
```

## generate secret key via docker image

```sh
docker pull python:3.9
docker run --rm -it -v $(pwd)/saveload_backend:/app python:3.9 bash
cd /app
pip install -r requirements.txt
python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'
# copy the secret key paste to docker-compose.yaml
exit
```

## Docker

```sh
docker-compose up -d
```