# ayu-midia

Fotos e legendas do site da Academia AYU. O site lê o arquivo `fotos.json` deste repositório (via GitHub Pages) e monta o logo, o Hero, a galeria por áreas e os professores sozinho. Para trocar uma foto, **não precisa mexer no código do site**.

**URL da "API":** `https://gabrielbarbosafeijo-cpu.github.io/ayu-midia/fotos.json`

## Pastas

| Pasta | Conteúdo |
|---|---|
| `geral/` | `hero.jpg` (foto principal, horizontal) e `logo-ayu.png` (logo circular) |
| `estrutura/fachada/` | frente da academia |
| `estrutura/recepcao/` | recepção |
| `estrutura/musculacao/` | salão de musculação e halteres |
| `estrutura/cardio/` | esteiras |
| `estrutura/descanso-massagem/` | cadeira de massagem |
| `estrutura/biblioteca/` | estantes de livros |
| `estrutura/lounge/` | sofá e café |
| `estrutura/apoio/` | toalhas e bebidas |
| `estrutura/banheiros/` | banheiros |
| `estrutura/salas/` | salas |
| `professores/` | fotos da equipe |

As 28 fotos das pastas estão no `fotos.json` e aparecem no site. `MAPA-ORIGINAIS.md` mostra de qual `IMG_xxxx` veio cada arquivo.

## Como o site monta a galeria

O `fotos.json` tem a lista `albuns`: cada **álbum** é uma área (Musculação, Cardio, Biblioteca…) e vira uma **aba** na galeria do site, com a etiqueta da área em cada foto. A aba "Todas" junta tudo automaticamente. A ordem dos álbuns e das fotos no arquivo é a ordem no site.

## Como adicionar uma foto a uma área

1. Suba a imagem na pasta da área (ex.: `estrutura/musculacao/`) → **Add file → Upload files** → **Commit changes**.
2. Abra `fotos.json` → ícone do lápis e, dentro do álbum certo, em `fotos`, adicione uma linha:
   ```json
   { "arquivo": "musculacao/musculacao-10.jpg", "alt": "Descreva o que aparece na foto" }
   ```
3. **Commit changes**. Em alguns minutos aparece no site.

## Como criar uma área nova (ex.: Spa)

Crie a pasta `estrutura/spa/`, suba as fotos e adicione um álbum no `fotos.json`:

```json
{ "id": "spa", "titulo": "Spa", "fotos": [ { "arquivo": "spa/spa-01.jpg", "alt": "Descreva a foto" } ] }
```

O `id` só aceita letras minúsculas, números e hífen. Para tirar uma foto ou área do site, apague a linha (a imagem pode continuar na pasta). Vírgula entre itens sim, depois do último não.

## Regras das imagens

- JPG, PNG ou WebP (**HEIC não abre na maioria dos navegadores**: converta antes). Nome sem espaços nem acentos.
- Até ~1600 px no lado maior e ~300 KB. Fotos de pessoas só com autorização delas.

## Atenção

- **Repositório público:** tudo o que for enviado fica visível e pode ser baixado. Fotos de celular guardam a localização nos metadados; as deste repositório já foram limpas.
- **Não renomeie nem apague o repositório**: o site depende da URL acima. Se mudar, atualize `MIDIA_BASE` em `js/midia.js` do site.
- Se o repositório sair do ar, o site continua com o conteúdo que está no HTML dele.

## Ativar o GitHub Pages (uma vez)

Settings → Pages → Source: **Deploy from a branch** → Branch: `main` / `(root)` → Save.
