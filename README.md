![logo](./docs/assets/img/logoBanner.png)

# Idiomas da documentação

### [Português](https://github.com/PedroCF87/postman-2-openapi#portug%C3%AAs)

### [English](https://github.com/PedroCF87/postman-2-openapi#english-1)

## Portugês

### Projeto base do pacote: [postman-to-openapi](https://joolfe.github.io/postman-to-openapi/)

🛸 Conversor Postman Collection v2.1/v2.0 para OpenAPI v3.0.

Em resumo, transforme [o formato PostmanCollection_v2.1.json](https://schema.getpostman.com/json/collection/v2.1.0/collection.json) ou [o formato PostmanCollection_v2.0.json](https://schema.getpostman.com/json/collection/v2.0.0/collection.json) para [o formato OpenAPI 3.0](http://spec.openapis.org/oas/v3.0.3.html)

[![build](https://github.com/joolfe/postman-to-openapi/workflows/Build/badge.svg)](https://github.com/PedroCF87/postman-2-openapi/actions)
<!-- [![npm version](https://img.shields.io/npm/v/postman-to-openapi)](https://www.npmjs.com/package/postman-to-openapi) -->
<!-- [![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com) -->

## Instalação

Usando `npm`

```bash
npm i postman2-to-openapi3
```

Usando `yarn`

```bash
yarn add postman2-to-openapi3
```

Para instalar como um `cli` apenas

```bash
npm i postman2-to-openapi3 -g
```

## Utilizando o conversor

### Como uma biblioteca

```js
// Require Package
const postmanToOpenApi = require('postman2-to-openapi3')

// Postman Collection
const postmanCollection = require('./path/to/postman/collection.json')

// Output OpenAPI Path (recurso desativado temporariamente)
// const outputFile = './api/collection.yml'
const outputFile = null

// Async/await
try {
    const result = await postmanToOpenApi(postmanCollection, outputFile, { defaultTag: 'General' })

    console.log(`OpenAPI specs: ${result}`)

    return result

} catch (err) {
    console.log(err)
}

// Promise callback style
const result = postmanToOpenApi(postmanCollection, outputFile, { defaultTag: 'General' })
    .then(result => {
      console.log(`OpenAPI specs: ${result}`)

      return result
    })
    .catch(err => {
      console.log(err)
    })
```

### Por bash / cli

```bash
p2o ./path/to/PostmantoCollection.json -f ./path/to/result.yml -o ./path/to/options.json
```

## Exemplo Cli

![cli demo gif](./docs/assets/img/demo.gif)

## Documentação

Todos os recursos, instruções de uso e ajuda podem ser encontrados na página da [documentação (em inglês)](https://joolfe.github.io/postman-to-openapi/).

## Ambiente

Para executar este projeto são necessários:

- Node.js v10.15.3 ou acima
- Seguir as regras de padronização de código [Standard JS](https://standardjs.com/).
- Testes com [mocha.js](https://mochajs.org/).

Execute os scripts do `package.json`:

- `test:unit`: Execute os teste unitários (mocha).
- `test`: Execute `nyc npm run test:unit-no-only`.
- `lint`: Execute os testes de padronização de códigos (standard lint) para buscar erros nos códigos.
- `lint:fix`: Execute o standard lint e corrija os erros automaticamente.
- `changelog`: Atualize o changelog automaticamente.

Passos para gerar o GIF demo:

- Instale terminalizer: `npm install -g terminalizer`
- Inicie uma gravação, usando: `terminalizer record demo -d 'zsh'`
- Pare a gravação com `Ctrl+D`
- Verifique a gravação com: `terminalizer play demo`
- Ajuste os delays no `demo.yml`, modifique `rows` para 15 (o valor mais alto) e torne a sessão do terminal anônima.
- Crie o gif com: `terminalizer render demo`

[Husky](https://www.npmjs.com/package/husky) está configurado para impedir o envio de conteúdo incorreto para o repositório.

## Tags

`Nodejs` `Javascript` `OpenAPI` `Postman` `Newman` `Collection` `Transform` `Convert`

## Licença

Acesse o arquivo [LICENÇA](LICENSE.txt).

# English

## Package made from: [postman-to-openapi](https://joolfe.github.io/postman-to-openapi/)

🛸 Convert Postman Collection v2.1/v2.0 to OpenAPI v3.0.

Or in other words, transform [this specification](https://schema.getpostman.com/json/collection/v2.1.0/collection.json) and [also this](https://schema.getpostman.com/json/collection/v2.0.0/collection.json) to [this one](http://spec.openapis.org/oas/v3.0.3.html)

[![build](https://github.com/joolfe/postman-to-openapi/workflows/Build/badge.svg)](https://github.com/joolfe/postman-to-openapi/actions)
[![codecov](https://codecov.io/gh/joolfe/postman-to-openapi/branch/master/graph/badge.svg)](https://codecov.io/gh/joolfe/postman-to-openapi)
[![npm version](https://img.shields.io/npm/v/postman-to-openapi
)](https://www.npmjs.com/package/postman-to-openapi)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com)

## Installation

Using `npm`:

```bash
npm i postman2-to-openapi3
```

Using `yarn`:

```bash
yarn add postman2-to-openapi3
```

To install as a `cli` just

```bash
npm i postman2-to-openapi3 -g
```

## Quick Usage

As a library

```js
// Require Package
const postmanToOpenApi = require('postman2-to-openapi3')

// Postman Collection Path
const postmanCollection = './path/to/postman/collection.json'
// Output OpenAPI Path
const outputFile = './api/collection.yml'

// Async/await
try {
    const result = await postmanToOpenApi(postmanCollection, outputFile, { defaultTag: 'General' })
    // Without save the result in a file
    const result2 = await postmanToOpenApi(postmanCollection, null, { defaultTag: 'General' })
    console.log(`OpenAPI specs: ${result}`)
} catch (err) {
    console.log(err)
}

// Promise callback style
postmanToOpenApi(postmanCollection, outputFile, { defaultTag: 'General' })
    .then(result => {
        console.log(`OpenAPI specs: ${result}`)
    })
    .catch(err => {
        console.log(err)
    })
```

As a cli

```bash
p2o ./path/to/PostmantoCollection.json -f ./path/to/result.yml -o ./path/to/options.json
```

## Cli Demo

![cli demo gif](./docs/assets/img/demo.gif)

## Documentation

All features, usage instructions and help can be found in the [Documentation page](https://joolfe.github.io/postman-to-openapi/)

## Development

This project use for development:

- Node.js v10.15.3 or higher
- [Standard JS](https://standardjs.com/) rules to maintain clean code.
- Use [Conventional Commit](https://www.conventionalcommits.org/en/v1.0.0/) for commit messages.
- Test with [mocha.js](https://mochajs.org/).

Use the scripts in `package.json`:

- `test:unit`: Run mocha unit test.
- `test`: Execute `test:lint` plus code coverage.
- `lint`: Execute standard lint to review errors in code.
- `lint:fix`: Execute standard lint and automatically fix errors.
- `changelog`: Update changelog automatically.

Steps to generate the gif demo:

- Install terminalizer `npm install -g terminalizer`
- Start a recording using `terminalizer record demo -d 'zsh'`
- Stop recording with `Ctrl+D`
- Check demo with `terminalizer play demo`
- Adjust delays in `demo.yml`, change `rows` to 15 (is the height) and anonymize terminal session.
- Generate the gif with `terminalizer render demo`

[Husky](https://www.npmjs.com/package/husky) is configured to avoid push incorrect content to git.

## Tags

`Nodejs` `Javascript` `OpenAPI` `Postman` `Newman` `Collection` `Transform` `Convert`

## License

See the [LICENSE](LICENSE.txt) file.
