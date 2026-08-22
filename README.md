# Céos

Céos é uma plataforma web de apoio ao estudo de Matemática, com ferramentas interativas para funções, análise combinatória e estatística.

## Sobre o Projeto

O objetivo do Céos é tornar a revisão mais prática, reunindo cálculos, fórmulas, explicações de resultados e uma área de autenticação para usuários.

## Funcionalidades

- Área de Matemática com navegação por módulos;
- cálculo de funções de 1º e 2º grau;
- avaliação de função em um ponto e resolução de raízes;
- média, mediana e moda;
- permutação, combinação, arranjo e arranjo com repetição;
- cadastro, login e recuperação de senha;
- FAQ e página institucional;
- histórico de sessão armazenado localmente.

## Tecnologias Utilizadas

- React 19;
- React Router DOM;
- Axios;
- Bootstrap;
- React Icons;
- Framer Motion;
- JWT Decode;
- Create React App.

## Estrutura

```text
CeosB/
├── public/
├── src/
│   ├── domain/
│   │   ├── entities/       # Entidades da aplicação
│   │   ├── repositories/   # Contratos de acesso a dados
│   │   └── usecases/       # Casos de uso matemáticos e de usuário
│   ├── infrastructure/
│   │   └── api/            # Clientes Axios e repositórios HTTP
│   └── presentation/
│       ├── components/     # Navbar, footer e componentes reutilizáveis
│       ├── context/        # Autenticação e carregamento
│       ├── hooks/
│       └── pages/          # Telas da aplicação
└── package.json
```

## Rotas da aplicação

| Rota                               | Descrição                    |
| ---------------------------------- | ---------------------------- |
| `/`                                | Página inicial               |
| `/matematica`                      | Menu dos módulos matemáticos |
| `/matematica/funcao`               | Calculadora de funções       |
| `/matematica/analise-combinatoria` | Calculadora combinatória     |
| `/matematica/estatistica`          | Calculadora estatística      |
| `/faq`                             | Perguntas frequentes         |
| `/login`                           | Login de usuário             |
| `/register`                        | Cadastro de usuário          |

## Configuração das APIs

O frontend usa variáveis de ambiente para definir os serviços externos:

```env
REACT_APP_MATH_API_URL=http://localhost:8080
REACT_APP_API_LOGIN_URL=http://localhost:8081
```

Os nomes devem ser ajustados conforme os backends disponíveis. Sem essas variáveis, as chamadas de cálculo e autenticação podem gerar URLs inválidas.

O token JWT é salvo em `localStorage` com a chave `ceos_token`, e os dados do usuário com a chave `ceos_user`. Requisições autenticadas recebem automaticamente o cabeçalho `Authorization: Bearer ...`.

## Como executar

1. Instale o Node.js e o npm.
2. Instale as dependências com `npm install`.
3. Configure as variáveis `REACT_APP_MATH_API_URL` e `REACT_APP_API_LOGIN_URL` em um arquivo `.env`.
4. Inicie o projeto com `npm start`.

A aplicação será disponibilizada, por padrão, em `http://localhost:3000`.

## Scripts disponíveis

```bash
npm start       # inicia o servidor de desenvolvimento
npm run build   # gera o build de produção em build/
npm test        # executa os testes do Create React App
```

## Autores

Este site foi desenvolvido por:

- Rhuan
- Leonardo
- Mauricio
- Vitor

## Observações

- O frontend depende de serviços externos para login, cadastro, recuperação de senha e cálculos.
- O histórico e a sessão usam `localStorage` no navegador.
- Quando uma resposta autenticada retorna `401`, a aplicação limpa a sessão e redireciona para `/login`.
- As interfaces de Física e Química não possuem rotas implementadas no estado atual do projeto.

## Contato

Email de suporte: ceoscalculadora.suporte@gmail.com

Acesse: [https://ceos-puce.vercel.app/](https://ceos-puce.vercel.app/)
