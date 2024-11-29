# Exemplo de load balancer com um hello world de backend e nginx de proxy reverso

1. `kubectl apply -f hello.yaml -n hello`
2. entrar na pasta do nginx e `docker compose up -d`
3. acessar `localhost:8080`
