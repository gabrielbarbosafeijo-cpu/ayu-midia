# ayu-midia

Fotos e legendas do site da Academia AYU. O site lê o arquivo `fotos.json` deste repositório (via GitHub Pages) e monta o Hero, a galeria e os professores sozinho. Para trocar uma foto, **não precisa mexer no código do site**.

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

Todas as fotos estão nas pastas, mas **só aparecem no site as que estão listadas em `estrutura` no `fotos.json`** (hoje, 12 destaques). `MAPA-ORIGINAIS.md` mostra de qual `IMG_xxxx` veio cada arquivo.

## Como mostrar outra foto no site

1. Abra `fotos.json` → ícone do lápis.
2. Na lista `estrutura`, adicione uma linha com o caminho da pasta:
   ```json
   { "arquivo": "musculacao/musculacao-04.jpg", "legenda": "Musculação", "alt": "Descreva o que aparece na foto" }
   ```
3. **Commit changes**. A ordem da lista é a ordem no site; para tirar uma foto, apague a linha. Vírgula entre itens sim, depois do último não.

## Como subir foto nova

Entre na pasta certa → **Add file → Upload files** → **Commit changes**. Depois registre no `fotos.json` como acima.

## Regras das imagens

- JPG, PNG ou WebP (**HEIC não abre na maioria dos navegadores**: converta antes). Nome sem espaços nem acentos.
- Até ~1600 px no lado maior e ~300 KB. Fotos de pessoas só com autorização delas.

## Atenção

- **Repositório público:** tudo o que for enviado fica visível e pode ser baixado. Fotos de celular guardam a localização nos metadados; as deste repositório já foram limpas.
- **Não renomeie nem apague o repositório**: o site depende da URL acima. Se mudar, atualize `MIDIA_BASE` em `js/midia.js` do site.
- Se o repositório sair do ar, o site continua com o conteúdo que está no HTML dele.

## Ativar o GitHub Pages (uma vez)

Settings → Pages → Source: **Deploy from a branch** → Branch: `main` / `(root)` → Save.
