# Relação de boas práticas para desenvolvimento NodeJS

## Ferramentas para desenvolvimento

### VSCode

Instalação de plugins e configuração para manter padrão mínimo

## Setup de projeto

### ESLint (airbnb)

Instalar e configurar ESLint para usar padrão desenvolvimento airbnb

### Sucrase

Instalar e configurar sucrase para substituir Babel

### Jest

Instalar e configurar Jest para testes unitários e de integração

### Estrutura diretórios

Para facilitar leitura/codificação, configurar projeto para usar estrutura de
diretórios adequada (frontend/backend).

```
raiz--+
      |
      +--src--+
              |
              |--app--+
              |       |
              |       +--controllers
              |       |
              |       +--middlewares
              |       |
              |       +--models
              |
              +--config
              |
              +--database--+
                           |
                           +--migrations
```

```
raiz => Diretório raiz da aplicação
raiz/src => Diretório onde fica o código-fonte da aplicação
raiz/src/app => Diretório da aplicação em si
raiz/src/app/controllers => Diretório da camada de Controllers da aplicação
raiz/src/app/middlewares => Diretório da camada de Middlewares da aplicação
raiz/src/app/models => Diretório da camada de Models da aplicação
raiz/src/config => Diretório da de arquivos de configuração da aplicação
raiz/src/database => Diretório de conexão com o(s) BD(s) da aplicação
raiz/src/database/migrations => Diretório de migrations da aplicação
```

### Sequelize (orm/migrations/seeds)

Instalar e configurar sequelize para utilizar quando possível migrations e
seeds.

### Yup

Validação de dados no backend e frontend

## Github

### Templates issues/pull request

Criar estrutura diretórios e templates para padronizar criação de issues/pull
requests

### Acompanhamento (project/kanbam)

Acompanhamento de issues/milestones/notas deve ser feito através de aba "Projects"
no Github

### master/develop

Utilizar padrão definido pelo Gitflow para controle de versões com 2 branches
(master e develop)

## Camada de apresentação

### React

Componentes statefull escritos a partir de classes, herdando do React;
Componentes stateless escritos a partir de funções puras.

### CSS puro (não usar framework por enquanto)

Para minimizar a curva de aprendizado e melhorar a técnica com HTML5 e CSS3

### Unform

Usar pacote unform para gerenciamento de formulários

## Deploy

### Automatizar

### Docker
