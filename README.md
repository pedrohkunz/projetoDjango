# 🚀 Template de Projeto Django com Docker

Este guia descreve o passo a passo para configurar e executar o template do projeto Django utilizando Docker.

---

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter instalado:

* Docker

---

## 📥 Clonar o repositório

Clone o repositório do projeto para sua máquina:

```bash
git clone https://github.com/pedrohkunz/projetoDjango.git
```

---

## 🐳 Subir os containers

Execute os comandos abaixo para buildar e subir os containers:

```bash
docker compose build --no-cache
docker compose up -d
```

---

## ⚙️ Configurar variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto e preencha com base no modelo abaixo:

```env
SECRET_KEY=django-insecure-f7d6%6u4pl2d&+5+yl0(7z)hk#*dre2=27bgju8onu8^=oe)tf
DEBUG=True
DB_NAME=
DB_USER=
DB_PASSWORD=
```

---

## 💻 Acessar o container Django

Execute o comando abaixo para acessar o terminal do container:

```bash
docker compose exec django sh
```

---

## 🗄️ Executar migrations

Dentro do container, rode o comando:

```bash
python3 manage.py migrate
```

---

## 👤 Criar superusuário

Ainda no terminal do container, execute:

```bash
python3 manage.py createsuperuser
```

Siga as instruções para criar seu usuário administrador.

---

## 🌐 Acessar a aplicação

Após finalizar os passos anteriores, acesse no navegador:

```
http://localhost:8000
```

Se tudo estiver correto, você deverá ver a mensagem:

✅ **Funcionou!**

---

## 🧩 Observações

* Caso faça alterações no código, dependendo da configuração do projeto, pode ser necessário reiniciar os containers.
* Certifique-se de que as portas necessárias não estão sendo utilizadas por outros serviços.
