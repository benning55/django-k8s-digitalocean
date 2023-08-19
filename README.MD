pip install -r requirements.txt

# django-k8s-digitalocean

```
docker build -t registry.digitalocean.com/benning-k8s/django-k8s-web:latest -f Dockerfile .

docker push registry.digitalocean.com/benning-k8s/django-k8s-web --all-tags
```

```
Gen secret key that urlk safe

python -c "import secrets;print(secrets.token_urlsafe(32))"

python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"

```

# Build for ARM64 (default)

docker build -t <image-name>:<version>-arm64 .

# Build for ARM64

docker build --platform=linux/arm64 -t <image-name>:<version>-arm64 .

# Build for AMD64

docker build --platform=linux/amd64 -t <image-name>:<version>-amd64 .
