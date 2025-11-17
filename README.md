📘 MyWebServiceDemo
Web Service minimalista em Flask publicado no Render

Este repositório contém um exemplo simples de um Web Service desenvolvido em Flask, preparado para execução em produção através de Gunicorn e publicado na plataforma Render. O objetivo é demonstrar, de forma clara e prática, como estruturar e disponibilizar um serviço Web mínimo.

🔗 Serviço online:
https://mywebservicedemo-1ghw.onrender.com

🚀 Objetivo

Criar e disponibilizar um Web Service do tipo Hello World, adequado para fins pedagógicos, demonstrações rápidas, testes de integração contínua ou como ponto de partida para serviços Web mais completos.

🧩 Estrutura do Projeto
MyWebServiceDemo/
│
├── app.py
├── requirements.txt
└── README.md

🧪 Executar Localmente
1. (Opcional) Criar ambiente virtual
python3 -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows

2. Instalar dependências
pip install -r requirements.txt

3. Executar o servidor Flask
python app.py


Depois, aceder a:
👉 http://localhost:5000/

🌐 Deployment no Render

O serviço está configurado para iniciar em produção com:

gunicorn app:app


O Render deteta automaticamente o ambiente Python a partir do ficheiro requirements.txt.
Este projeto foi publicado no plano gratuito da plataforma.

📄 Ficheiros Principais
✔️ app.py
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
    return "Hello, World! by AMSS"

if __name__ == "__main__":
    import os
    port = int(os.environ.get("PORT", 5000))
    app.run(host="0.0.0.0", port=port)

✔️ requirements.txt
Flask==2.2.5
gunicorn==20.1.0

📚 Licença

Projeto de carácter demonstrativo para fins académicos.
Sem licença comercial atribuída.
