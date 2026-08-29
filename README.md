# Angular Coding Standards

Configurações base para manter projetos Angular consistentes entre máquinas, sistemas operacionais e editores.

A ideia deste repositório é guardar arquivos simples de padronização do workspace, sem depender de configurações globais da sua máquina. Você pode copiar estes arquivos para qualquer projeto Angular novo ou existente.

## O que está incluído

- `.editorconfig`: padrão geral de indentação, charset, quebra de linha final e limpeza de espaços.
- `.prettierrc`: regras do Prettier para TypeScript, HTML Angular, CSS, JSON e demais arquivos suportados.
- `.vscode/settings.json`: configura o VS Code para formatar ao salvar usando Prettier.
- `.vscode/extensions.json`: recomenda extensões importantes para o projeto.
- Scripts `npm run format` e `npm run format:check` no `package.json`.

## Extensões recomendadas do VS Code

Instale estas extensões no VS Code:

- Angular Language Service: `angular.ng-template`
- Prettier - Code formatter: `esbenp.prettier-vscode`

Ao abrir o projeto no VS Code, ele deve sugerir automaticamente as extensões listadas em `.vscode/extensions.json`.

## Como usar em outro projeto Angular

Copie estes arquivos para a raiz do outro projeto:

```text
.editorconfig
.prettierrc
.vscode/settings.json
.vscode/extensions.json
```

Depois, adicione estes scripts no `package.json` do projeto:

```json
{
  "scripts": {
    "format": "prettier --write .",
    "format:check": "prettier --check ."
  }
}
```

Se o projeto ainda não tiver o Prettier instalado, instale como dependência de desenvolvimento:

```bash
npm install -D prettier
```

## Comandos úteis

Formatar o projeto inteiro:

```bash
npm run format
```

Verificar formatação sem alterar arquivos:

```bash
npm run format:check
```

## Por que versionar essas configs

Esses arquivos deixam o padrão do projeto junto com o código. Assim, quando você clonar o repositório em outro notebook ou outro sistema operacional, o VS Code, o Prettier e o EditorConfig aplicam as mesmas regras sem depender de configurações manuais globais.

## O que evitar versionar

Evite colocar neste repositório configurações pessoais ou sensíveis, como:

- tokens e credenciais;
- caminhos absolutos da sua máquina;
- preferências globais do VS Code que não pertencem ao projeto;
- arquivos gerados, como `node_modules` e `dist`.
