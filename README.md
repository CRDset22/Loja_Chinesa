# Loja JEN DIAN — Artigos Chineses

Site de página única (one-page) de uma loja fictícia de artigos chineses:
pratos decorativos, vasos, espadas, nunchacus e bules. Feito com **HTML,
CSS e Bootstrap 5**, com carrossel de capa, vitrine de produtos em abas e
formulário de contato com máscara de telefone (jQuery Mask).

> Página fictícia, para fins de prática e estudo de front-end, usando
> imagens de terceiros e textos fantasiosos.

## Tecnologias

- HTML5 e CSS3
- Bootstrap 5.3 e Bootstrap Icons (via CDN)
- jQuery 3.7 + jQuery Mask Plugin (máscara do campo de telefone)
- Google Fonts: Pacifico, Roboto e Open Sans

## Como abrir

Basta abrir o `index.html` no navegador. É preciso estar conectado à
internet, pois Bootstrap, ícones, fontes e jQuery vêm de CDN.

## Estrutura da pasta

```
Loja_Chinesa/
├── index.html                  página única do site
├── main.css                    estilos próprios (sobre o Bootstrap)
├── README.md                   este arquivo
├── erros.txt                   relatório da revisão (estudo)
├── fluxograma.svg              diagrama dos arquivos
├── Fachada loja chinesa.png    imagem da seção "Sobre a Loja"
├── One.png                     imagem da seção "Sobre o espaço"
├── maxresdefault.jpg           imagem da seção "Artes Marciais"
├── Ajuste/                     3 imagens panorâmicas do carrossel de capa
├── Pratos/                     5 fotos de produtos (aba Pratos)
├── Vaso_chines/                5 fotos de produtos (aba Vasos)
├── Espadas/                    5 fotos de produtos (aba Espadas)
├── Nunchacus/                  6 fotos (5 produtos + 1 reserva)
├── Bule_chines/                5 fotos de produtos (aba Bules)
└── jsQueryMask/                jquery.mask.min.js (máscara do telefone)
```

## Padrão de tamanho das imagens

As fotos originais têm proporções muito variadas (de vasos verticais
0,58 a espadas deitadas 2,48). A padronização foi feita por CSS, com uma
proporção fixa para cada contexto e `object-fit` cuidando do
preenchimento sem distorcer:

| Contexto                  | Classe / seletor      | Proporção | Preenchimento |
|---------------------------|-----------------------|-----------|---------------|
| Carrossel de capa         | `.carousel-item img`  | 12:5      | `cover` (corta o excesso) |
| Imagens das seções        | `.img-secao`          | 16:9      | `cover` |
| Fotos de produto          | `.produto-img`        | 1:1       | `contain` (produto inteiro, fundo branco) |

Nos produtos foi usado `contain` de propósito: com `cover`, uma espada
deitada perderia a lâmina no corte. Assim todas as caixas têm o mesmo
tamanho e o produto aparece por completo, como numa vitrine de
e-commerce.

## Aba "Bules" (novidade desta revisão)

A pasta `Bule_chines/` tinha 5 imagens que não eram usadas em lugar
nenhum — a categoria ficou inacabada. A aba **Bules** foi criada seguindo
o padrão das demais. **Os nomes, descrições e preços desses 5 produtos
são sugestões**: edite-os à vontade no bloco `<div class="tab-pane"
id="Bules">` do `index.html`.

## O que foi removido do pacote

- `.git/` — o histórico Git local (o zip é só o site; seu repositório
  original continua intacto no seu computador/GitHub).
- `jQuery-Mask-Plugin-master/` — o repositório completo do plugin
  (testes, Dockerfile etc.). O site só precisa do
  `jsQueryMask/jquery.mask.min.js`, que foi mantido.
- `jquery.validate.min.js` e `messages_pt_PT.min.js` — não eram
  carregados por nenhum `<script>`.
- `Nunchacus/1280px-Nunchaku.jpeg` continua na pasta, mas o carrossel
  agora usa a cópia idêntica de `Ajuste/` (todas as capas na mesma
  pasta). Pode apagar a da pasta Nunchacus se quiser.

A lista completa de erros encontrados e corrigidos está no `erros.txt`.
