<div align="center">
  <h1>🎬 CineAi-API</h1>
  <p>Uma API RESTful inteligente para descoberta, recomendação e avaliação de filmes, potencializada por IA generativa.</p>
</div>

---

## 📋 Sobre o Projeto

**CineAi-API** é uma aplicação completa desenvolvida em Python (Flask) que oferece endpoints interativos para explorar um vasto catálogo de filmes, processar avaliações de usuários e fornecer recomendações ultracontextuais. A API utiliza **LangChain** e **Groq** para enriquecer a experiência, trazendo análises complexas sobre filmes diretamente ao alcance de sua aplicação frontend.

---

## 🎯 Principais Funcionalidades

- **🧠 Recomendações Baseadas em IA**: Integração com Groq e LangChain para sugestão inteligente de filmes.
- **🎬 Catálogo Extenso**: Busca avançada por filmes, gêneros e títulos.
- **👥 Gestão de Usuários**: Sistema seguro de registro e autenticação de usuários (Login/Token).
- **⭐ Avaliações e Preferências**: Endpoints para usuários avaliarem filmes e cadastrarem gêneros preferenciais.
- **📄 Documentação Automática**: Interface interativa via **Swagger UI** para explorar e testar a API facilmente.
- **🚀 Preparado para Deploy**: Arquivos de configuração otimizados (`render.yaml`, `Gunicorn`) para a nuvem.

---

## 🛠️ Tecnologias Utilizadas

**Backend & Web**
- [Flask](https://flask.palletsprojects.com/) - Framework web principal.
- [Flask-CORS](https://flask-cors.readthedocs.io/) - Habilitar requisições Cross-Origin.
- [Flask-Swagger-UI](https://pypi.org/project/flask-swagger-ui/) - Documentação OpenAPI.

**Inteligência Artificial & Machine Learning**
- [LangChain](https://python.langchain.com/) - Orquestração de prompts e IA generativa.
- [Groq](https://groq.com/) - LLM de alta performance.
- [Scikit-learn](https://scikit-learn.org/) - Empregado para busca de filmes similares (Cosine Similarity).
- [Pandas](https://pandas.pydata.org/) & [NumPy](https://numpy.org/) - Manipulação eficiente de dados.

**Banco de Dados & Servidor**
- [SQLite](https://www.sqlite.org/) - Persistência rápida com base local (`filmes.db`).
- [SQLAlchemy](https://www.sqlalchemy.org/) - Mapeamento Objeto-Relacional (ORM).
- [Gunicorn](https://gunicorn.org/) - Servidor escalável para produção.

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
Certifique-se de ter o [Python 3.8+](https://www.python.org/downloads/) instalado e a chave da API necessárias para os serviços do Groq configuradas como variáveis de ambiente, caso aplicável.

### 1. Clonar o Repositório
```bash
git clone https://github.com/seu-usuario/CineAi-API.git
cd CineAi-API
```

### 2. Criar e Ativar Ambiente Virtual
```bash
python -m venv venv
# No Windows:
venv\Scripts\activate
# No Mac/Linux:
source venv/bin/activate
```

### 3. Instalar Dependências
As ferramentas e bibliotecas estão em `requirements.txt`.
```bash
pip install -r requirements.txt
```

### 4. Iniciar a API
```bash
python app.py
```
A API estará rodando por padrão em `http://localhost:5000`.

---

## 📖 Documentação dos Endpoints (Swagger)

A API conta com o **Swagger** para testes automáticos ou análise dos endpoints na web.
- Acesse a rota: `http://localhost:5000/swagger`

### Resumo das Rotas Disponíveis

**Filmes & Gêneros**
- `GET /movies` - Lista todos os filmes (suporta paginação com `limit`).
- `GET /movies/<id>` - Encontra um filme específico por ID.
- `GET /movies/name/<name>` - Pesquisa de filmes pelo nome ou trecho.
- `GET /genres` - Retorna a lista de todos os gêneros disponíveis.
- `GET /movies/genre/<genre_id>` - Retorna filmes de acordo com o gênero especificado.
- `GET /movies/<id>/similar` - Recomendações extraídas com IA de títulos similares.

**Usuários & Avaliações**
- `POST /usuarios/registrar` - Cria uma nova conta na API.
- `POST /usuarios/login` - Autentica o usuário e fornece acesso contínuo.
- `POST /movies/<id>/avaliar` - Realiza a avaliação ou comentário sobre uma visualização de filme.
- `GET /usuarios/<user_id>/avaliacoes` - Puxa todo o repositório de avaliações daquele usuário.

**Preferências**
- `POST /movies/preferencia` - Informar um filme de gosto pontual do usuário.
- `POST /movies/genero/preferencia` - Registrar um gênero favorito/preferencial.

---

## 📁 Estrutura do Projeto

```text
CineAi-API/
├── api/
│   ├── controllers/   # Lógica com integração de ML, LLM e banco de dados
│   ├── database/      # Conexão e drivers do SQLite
│   ├── models/        # Entidades em Classes para as tabelas
│   └── routes/        # Rotas da Web (Flask Blueprints)
├── static/            # Swagger.yaml e Assets da API
├── app.py             # Script bootstrap para rodar aplicação
├── filmes.db          # Arquivo do banco de dados relacional (Mapeado)
├── render.yaml        # Configurações otimizadas para Infra na Cloud via Render
└── requirements.txt   # Módulo instalador do Python com versões específicas
```

---
<div align="center">
  Reinventando a forma como escolhemos filmes com Inteligência Artificial 🍿
</div>
