# Passo a passo de como eu fiz para configurar o Eslint + Prettier sem conflitos

1. Inicializa as configurações do Eslint

```shell
npm init @eslint/config
```

Irá exibir algumas perguntas para escolher algumas configurações e no final de tudo selecionei para não instalar as dependência. Copiei as dependências e instalei com o bun.

2. Instala as depedências do Eslint

```shell
bun add -D eslint-config-standard-with-typescript@latest @typescript-eslint/eslint-plugin@^6.4.0 eslint@^8.0.1 eslint-plugin-import@^2.25.2 eslint-plugin-n@^15.0.0 || ^16.0.0 eslint-plugin-promise@^6.0.0 typescript@\*
```

3. Após instalação, instalei os plugin no VSCode, Eslint e Prettier.

- O .eslintrc.json é o responsável pelas regras de lint
- O .prettierrc é o responsável pelas regras de prettier

4. Para evitar conflitos entre ESLint e Prettier instalalei a dependência abaixo e coloquei no extends do `.eslintrc.json` o "prettier":

```shell
bun add -D eslint-config-prettier
```

5. Instalei o prettier como dependência para criar um script de fix no package.json
   para rodar o prettier e o eslint.

```shell
bun add -D prettier
```

6.  Por último instalei o husky olhando sua documentação e crei um hook de pré-commit para rodar o script de fix a cada commit.

```shell
bun add -D husky && bunx husky init
```
