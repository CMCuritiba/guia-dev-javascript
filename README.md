# Relação de boas práticas para desenvolvimento NodeJS
Baseado nos padrões definidos no curso da Rocketseat

## Ferramentas para desenvolvimento

### VSCode

[Download](https://code.visualstudio.com/)

settings.json

```
"editor.formatOnSave": true,
"eslint.autoFixOnSave": true,
```

Instalação de plugins e configuração para manter padrão mínimo

[ESLint](https://github.com/Microsoft/vscode-eslint)

.eslintrc.js

```
module.exports = {
  env: {
    browser: true,
    es6: true,
    jest: true,
  },
  extends: ['airbnb', 'prettier', 'prettier/react'],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parser: 'babel-eslint',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  plugins: [
    'react',
    'prettier',
    'prettier/react',
    'jest-dom',
    'testing-library',
    'jsx-a11y',
    'import',
  ],
  rules: {
    'prettier/prettier': 'error',
    'react/jsx-filename-extension': ['warn', { extensions: ['.jsx', '.js'] }],
    'import/prefer-default-export': 'off',
    'no-console': ['error', { allow: ['tron'] }],
    'testing-library/await-async-query': 'error',
    'testing-library/no-await-sync-query': 'error',
    'testing-library/no-debug': 'warn',
  },
};
```

[Prettier](https://github.com/prettier/prettier-vscode)

.prettierrc

```
{
  "singleQuote": true,
  "trailingComma": "es5"
}
```

[Color Highlight](https://github.com/egonyans/vscode-ext-color-highlight)

[VSCode Styled Components](https://github.com/styled-components/vscode-styled-components)

[Editor Config for VSCode](https://github.com/editorconfig/editorconfig-vscode)

.editorconfig

```
root = true

[*]
end_of_line = lf
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```

[Rocketseat ReactJS](https://github.com/Rocketseat/rocketseat-vscode-reactjs-snippets)

## Setup de projeto

### Configurando ESLint, Prettier, EditorConfig e Airbnb airbnb
Seguir os passos do vídeo : https://www.youtube.com/watch?v=TI4v4Y8yRjw

### Sucrase (backend)

Instalar e configurar sucrase para substituir Babel

https://carloslevir.com/es6-node-sucrase/

### Reactotron (frontend)

Instalar e configurar reactotron para fornecer/inspecionar informações do sistema de maneira mais amigável

https://github.com/infinitered/reactotron

### Jest (backend)

Instalar e configurar Jest para testes unitários e de integração

### Estrutura diretórios (backend-express)

Para facilitar leitura/codificação, configurar projeto para usar estrutura de
diretórios adequada (frontend/backend).

```
raiz--+
      |
      |--tests--+
      |         |
      |         +--coverage
      |         |
      |         +--integration
      |         |
      |         +--unit
      |         |
      |         +--util
      |
      |
      +--src--+
              |
              |
              |
              |--app--+
              |       |
              |       +--controllers
              |       |      
              |       +--helpers 
              |       |
              |       +--middlewares
              |       |
              |       +--models
              |       |
              |       +--services
              |       |
              |       +--validators
              |
              +--config
              |
              +--database--+
                           |
                           +--migrations
```

```
raiz => Diretório raiz da aplicação

raiz/__tests__ => Diretórios dos testes da aplicação
raiz/__tests__/coverage => Diretório com relatórios criado automaticamente pelo suite de testes.
raiz/__tests__/integration => Testes de integração
raiz/__tests__/unit => Testes unitários
raiz/__tests__/unit => Arquivos utilitários para a suite de testes

raiz/src => Diretório onde fica o código-fonte da aplicação

raiz/src/app => Diretório da aplicação em si
raiz/src/app/controllers => Diretório da camada de Controllers da aplicação
raiz/src/app/middlewares => Diretório da camada de Middlewares da aplicação
raiz/src/app/models => Diretório da camada de Models da aplicação
raiz/src/app/services => Diretório da camada de Services da aplicação
raiz/src/app/validators => Diretório da camada de Validators da aplicação

raiz/src/config => Diretório da de arquivos de configuração da aplicação

raiz/src/database => Diretório de conexão com o(s) BD(s) da aplicação
raiz/src/database/migrations => Diretório de migrations da aplicação

```

### Estrutura diretórios (backend-Adonis)

A estrutura básica de diretórios utilizando o Adonis pode ser encontrada neste link :
https://adonisjs.com/docs/4.1/folder-structure

Adicionar o diretório ```app/Services``` nesta arquitetura para seguir o padrão definido anteriormente
no contexto do express.


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

### Estrutura diretórios (frontend)

```
raiz--+
      |
      |
      |
      |
      +--src--+
              |
              +--__tests__--+
              |             |
              |             +--components
              |             |
              |             +--store
              |
              +--assets--+
              |          |
              |          +--images
              |
              +--components
              |      
              +--config
              |
              +--helpers
              |
              +--pages--+
              |         |
              |         +--_layouts
              |
              |
              +--routes
              |
              +--services
              |
              +--store--+
              |         |
              |         +--modules     
              |
              +--styles
```

```
raiz => Diretório raiz da aplicação

raiz/src => Diretório onde fica o código-fonte da aplicação

raiz/src/__tests__ => Diretório de testes da aplicação
raiz/src/__tests__/components => Testes de componentes
raiz/src/__tests__/store => Testes de redux/saga

raiz/src/assets => Diretório de arquivos de binários
raiz/src/assets/images => Imagens

raiz/src/components => Diretório de componentes

raiz/src/config => Diretório de configurações

raiz/src/helpers => Diretório de helpers

raiz/src/pages => Diretório de componentes de página
raiz/src/pages/_layouts => layouts comuns das páginas

raiz/src/routes => Diretório de rotas da aplicação

raiz/src/services => Diretório de serviços da aplicação

raiz/src/store => Diretório de stores da aplicação (Redux/Redux Saga)
raiz/src/store/modules => Módulos da aplicação gerenciados pelo Redux/Redux Saga

raiz/src/styles => Diretório de estilos globais da aplicação

```

### CSS puro (styled components)

Não utilizar bibliotecas de componentes tipo bootstrap, material ou qualquer parecida.
Utilizar a Styled components.

### Unform

Usar pacote unform para gerenciamento de formulários

### Prototipação/Wireframe

Utilizar o [figma](https://www.figma.com) para prototipação de telas e definição de componentes puros (react) e (styled components)

## Deploy

### Automatizar

### Docker
https://github.com/CMCuritiba/guia-dev-javascript.git

### Guia de procedimentos
Visiste a wiki e contribua 

https://github.com/CMCuritiba/guia-dev-javascript/wiki


