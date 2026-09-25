# 2ª Parte – Prática

## 1. Execução no Killercoda

### Criação do arquivo `index.html`

```bash
cat > index.html <<'EOF'
<!DOCTYPE html>
<html lang="pt-BR">
<head>
 <meta charset="UTF-8">
 <title>Comunicado interno</title>
</head>
<body>
 <h1>Comunicado interno disponível</h1>
</body>
</html>
EOF
```

### Criação do contêiner Nginx

```bash
docker run -d --name comunicado -p 8090:80 nginx:alpine
```

### Cópia do arquivo para o contêiner

```bash
docker cp index.html comunicado:/usr/share/nginx/html/index.html
```

### Verificação do contêiner

```bash
docker ps
```

### Teste da página

```bash
curl http://localhost:8090
```

---

## 2. Evidência

Foi realizado o teste no Killercoda, comprovando que o contêiner Nginx está funcionando e que a página responde pela porta 8090.

**Print da execução no Killercoda:**

> Inserir aqui o print do terminal.

---

## 3. Respostas

### 1. Qual a diferença entre `nginx:alpine` e o contêiner `comunicado`?

`nginx:alpine` é a imagem usada para criar o contêiner. `comunicado` é o nome do contêiner criado a partir dessa imagem.

### 2. O que significa o mapeamento `8090:80`?

Significa que a porta 8090 do ambiente externo está direcionada para a porta 80 dentro do contêiner, onde o Nginx está funcionando.

### 3. Qual saída comprova que a página solicitada respondeu?

A saída do comando `curl http://localhost:8090`, que apresentou a página com a mensagem **“Comunicado interno disponível”**, comprova que a página respondeu corretamente pela porta 8090.
