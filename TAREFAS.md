# TAREFAS DO DESAFIO - API Favoritos AIQFome

## 📋 Resumo do Desafio
Desenvolver uma API RESTful para gerenciar **clientes** e **produtos favoritos**, com integração à API externa [FakeStore API](https://fakestoreapi.com/docs).

---

## 🎯 FUNCIONALIDADES PRINCIPAIS

### 1. **Gestão de Clientes**
- [ ] **Criar cliente** (POST /api/clients)
  - Campos obrigatórios: nome, email
  - Validar email único
- [ ] **Listar clientes** (GET /api/clients)
- [ ] **Visualizar cliente** (GET /api/clients/{id})
- [ ] **Editar cliente** (PUT/PATCH /api/clients/{id})
- [ ] **Remover cliente** (DELETE /api/clients/{id})

### 2. **Gestão de Favoritos**
- [ ] **Adicionar produto aos favoritos** (POST /api/clients/{id}/favorites)
  - Validar produto via FakeStore API
  - Evitar duplicatas por cliente
- [ ] **Listar favoritos do cliente** (GET /api/clients/{id}/favorites)
  - Exibir: ID, título, imagem, preço, review
- [ ] **Remover favorito** (DELETE /api/clients/{id}/favorites/{product_id})

### 3. **Integração com API Externa**
- [ ] **Service para FakeStore API**
  - GET produtos: `https://fakestoreapi.com/products`
  - GET produto por ID: `https://fakestoreapi.com/products/{id}`
- [ ] **Validação de produto existente**
- [ ] **Cache de produtos** (opcional para performance)

---

## 🔧 INFRAESTRUTURA TÉCNICA

### Database & Models
- [ ] **Migration - Tabela `clients`**
  - id, name, email, timestamps
  - Index único em email
- [ ] **Migration - Tabela `client_favorites`**
  - id, client_id, product_id, timestamps
  - Index único (client_id, product_id)
- [ ] **Model Client** com relacionamento favorites
- [ ] **Model ClientFavorite**

### API & Controllers
- [ ] **ClientController**
  - CRUD completo
  - Validações (FormRequest)
- [ ] **FavoriteController**
  - Adicionar/remover/listar favoritos
- [ ] **Rotas API** com middleware de autenticação

### Services & Validations
- [ ] **FakeStoreService** para integração externa
- [ ] **ClientRequest** para validações
- [ ] **FavoriteRequest** para validações
- [ ] **Middleware de autenticação** (Sanctum)

---

## 🔐 SEGURANÇA & AUTENTICAÇÃO

- [ ] **Sistema de autenticação**
  - Login/Register endpoints
  - Token-based (Laravel Sanctum)
- [ ] **Middleware auth:sanctum** nas rotas protegidas
- [ ] **Validação de autorização** (cliente só acessa seus próprios favoritos)
- [ ] **Rate limiting** para APIs externas

---

## 📚 DOCUMENTAÇÃO & TESTES

### Documentação
- [ ] **README.md completo**
  - Instruções de instalação
  - Como rodar o projeto
  - Explicação das escolhas técnicas
- [ ] **Documentação da API**
  - Collection Postman/Insomnia
  - Ou Swagger (opcional)

### Testes
- [ ] **Feature Tests**
  - CRUD clientes
  - Gestão de favoritos
  - Integração FakeStore API
- [ ] **Unit Tests**
  - Services
  - Validações
- [ ] **Garantir 100% dos endpoints funcionando**

---

## 🚀 SETUP & DEPLOY

### Configuração Inicial
- [ ] **Configurar .env**
  - Database (PostgreSQL/MySQL)
  - API URLs
- [ ] **Seeders** para dados de teste
- [ ] **Docker** (opcional mas recomendado)

### Otimizações
- [ ] **Performance**: Cache, eager loading
- [ ] **Escalabilidade**: Queue jobs para APIs externas
- [ ] **Logs estruturados**

---

## ✅ CHECKLIST FINAL

### Correção & Funcionamento (🔥🔥🔥🔥)
- [ ] Todas as rotas funcionando
- [ ] CRUD completo de clientes
- [ ] Sistema de favoritos operacional
- [ ] Integração FakeStore API

### Modelagem de Dados (🔥🔥🔥)
- [ ] Relacionamentos corretos
- [ ] Migrations bem estruturadas
- [ ] Índices para performance

### Validação & Controle (🔥🔥🔥)
- [ ] Email único
- [ ] Produto não duplicado por cliente
- [ ] Validação de produto existente
- [ ] Tratamento de erros

### Documentação (🔥🔥)
- [ ] README com instruções claras
- [ ] Collection/documentação da API

### Segurança (🔥🔥)
- [ ] Autenticação funcionando
- [ ] Autorização de acesso
- [ ] Validações de entrada

---

## 📅 **PRAZO: 5 dias corridos**