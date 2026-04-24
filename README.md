# matheusdcunha.dev

Meu pedaço na internet

## Stack

- Hugo `extended` `v0.157.0`
- Go
- Tema base: `github.com/michenriksen/hugo-theme-til`
- Deploy automatizado via GitHub Actions

## Requisitos

- Hugo Extended instalado
- Go instalado

Versoes usadas no projeto:

- Hugo: `0.157.0`
- Go: `1.26.1` em [`go.mod`](./go.mod)

## Desenvolvimento local

Instale os modulos do Hugo:

```bash
hugo mod get
```

Suba o servidor local:

```bash
hugo server -D
```

O site ficara disponivel em `http://localhost:1313`.

## Build de producao

```bash
hugo --minify --gc
```

O output gerado vai para `public/`. Esse diretorio e build artefactual e nao e a fonte de verdade do projeto.

## Estrutura

- `content/`: paginas e posts em Markdown
- `layouts/`: sobrescritas e customizacoes do tema
- `assets/`: scripts e assets processados pelo Hugo
- `static/`: arquivos copiados como estaticos para o build final
- `.github/workflows/deploy.yml`: pipeline de deploy no GitHub Pages
- `hugo.toml`: configuracao principal do site

## Conteudo

Paginas e secoes atuais:

- `content/_index.md`: home
- `content/sobre.md`: pagina Sobre
- `content/posts/_index.md`: listagem de posts
- `content/posts/`: posts do blog

Para criar um novo post, adicione um arquivo Markdown em `content/posts/`.

## Deploy

O deploy acontece automaticamente a cada push para `main` via [`deploy.yml`](./.github/workflows/deploy.yml).

Fluxo do deploy:

1. Faz checkout do repositorio
2. Instala Hugo Extended
3. Resolve os modulos do Hugo
4. Executa `hugo --minify --gc`
5. Publica `public/` no GitHub Pages

O dominio customizado e mantido por `static/CNAME`.