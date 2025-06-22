# 💬 Chat em Tempo Real - Desafio 03 | Rocketseat

Este projeto é uma solução para o **Desafio 03** do módulo **Comunicação em tempo real com Flask** da trilha da Rocketseat.

A aplicação consiste em um chat em tempo real utilizando **Flask** e **Flask-SocketIO**, com interface web para envio e recepção de mensagens.

---

## 🚀 Tecnologias Utilizadas

- Python 3.11+
- Flask
- Flask-SocketIO
- HTML + Socket.IO Client
- Eventlet (ou gevent) como servidor assíncrono

---

## ⚙️ Funcionalidades

- 💬 Enviar mensagens em tempo real
- 👥 Receber mensagens de outros usuários conectados instantaneamente
- 🧠 Integração via WebSocket usando Flask-SocketIO

---

## 📁 Estrutura do Projeto

```text
.
├── app.py
└── templates/
    └── index.html
```

---

## 🧰 Como executar o projeto

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/flask-realtime-chat.git
cd flask-realtime-chat
```

### 2. Crie e ative um ambiente virtual

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Baixe o HTML de interface

Crie uma pasta chamada `templates` e baixe o seguinte arquivo:

📄 [index.html](https://github.com/rocketseat-education/python-socket-challenge/blob/main/templates/index.html)

Salve dentro da pasta `templates/`.

---

### 5. Execute a aplicação

```bash
python app.py
```

Acesse o navegador em: [http://localhost:5000](http://localhost:5000)

---

## 📌 Exemplo básico de código (app.py)

```python
from flask import Flask, render_template
from flask_socketio import SocketIO, send

app = Flask(__name__)
app.config['SECRET_KEY'] = 'secret!'
socketio = SocketIO(app)

@app.route('/')
def index():
    return render_template('index.html')

@socketio.on('message')
def handle_message(msg):
    print(f'Mensagem recebida: {msg}')
    send(msg, broadcast=True)

if __name__ == '__main__':
    socketio.run(app, debug=True)
```

---

## 📄 requirements.txt

```txt
flask
flask-socketio
eventlet
```

---

## 💭 Aprendizados

Durante este desafio, foram reforçados os seguintes pontos:

- Como criar rotas e renderizar templates com Flask
- Comunicação em tempo real com WebSockets
- Integração do Socket.IO com Python usando Flask-SocketIO
- Criação de aplicações assíncronas com Eventlet

---

## 🧑‍💻 Autor

Feito com 💜 por [Seu Nome](https://github.com/seu-usuario) para o desafio da Rocketseat.

---

## 📬 Entrega

URL do projeto: [https://github.com/seu-usuario/flask-realtime-chat](https://github.com/seu-usuario/flask-realtime-chat)
