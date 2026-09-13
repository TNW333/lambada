# Festival de Lambada em Coroa Vermelha — Landing Page

## Direção visual: "O Sol da Lambada"
A referência enviada (fundo índigo-noturno, destaque dourado, vermelho institucional,
composição praiana ao entardecer) foi traduzida numa identidade própria construída em torno
de um emblema circular de raios dourados — o "Sol da Lambada". Ele aparece no hero, na seção
final e como moldura dos cards de DJ, funcionando como assinatura visual repetida por toda a
página, sem copiar o layout da imagem de referência.

- **Paleta:** índigo-noturno (`--ink-900/800/700`), dourado (`--gold-500/400/700`), coral de
  pôr do sol (`--coral-500/700`) e areia (`--sand-100/200`) para textos claros.
- **Tipografia:** `Anton` (títulos, energia de cartaz de festival), `Manrope` (corpo, leitura
  confortável) e `Caveat` (toques manuscritos pontuais — tagline do hero, chamada de "O Que
  Esperar").
- **Componentes:** botões em pílula, cards com radius 20px e sombras quentes sutis, divisores
  em forma de onda/horizonte entre seções.
- **Imagens:** nenhuma fotografia real ou fictícia foi usada. Toda a composição visual é feita
  em SVG/CSS (emblema solar, palmeira em linha, caminho de dança pontilhado). A galeria, o
  quadro "Sobre" e os cards de DJ têm placeholders prontos para receber fotos oficiais depois.

## Estrutura de arquivos
```
index.html          Marcação semântica de todas as seções
style.css            Sistema de design (tokens em :root) + estilos de todas as seções
script.js            Menu mobile, header com estado de scroll, scroll-reveal, lightbox da galeria
assets/images/       Pasta para as fotografias oficiais (vazia — ver abaixo)
assets/icons/        Pasta reservada para ícones adicionais em SVG
assets/fonts/        Pasta reservada caso queira hospedar as fontes localmente
```

## Como adicionar as fotografias oficiais
1. **Galeria** (`#galeria`): substitua o conteúdo de cada `.gallery-item` (arquivo `index.html`)
   por uma tag `<img>` com `object-fit: cover` — as classes `.gi-1` a `.gi-6` já controlam o
   tamanho de cada bloco no mosaico.
2. **Sobre** (`#sobre`): a `.frame-shape` pode receber uma imagem com `clip-path` usando o
   mesmo `path` do SVG, ou uma `<img>` posicionada com `object-fit: cover` atrás do SVG de
   contorno.
3. **Line-up** (`#lineup`): troque o SVG dentro de `.dj-avatar` por uma `<img>` circular do
   próprio DJ, e o texto "Instagram em breve" pelo link real (`<a href="https://instagram.com/...">`).
4. **Redes sociais** (rodapé): adicione os `href` reais assim que estiverem disponíveis.

## Notas
- Nenhuma informação da programação, datas, locais ou nomes de DJs foi alterada ou inventada.
- O código está organizado em três arquivos separados, sem duplicação de estilos, com todas as
  variáveis de cor, tipografia, espaçamento, radius e sombra centralizadas em `:root`.
- Testado sem overflow horizontal em 375px, 390px, 768px, 1024px e 1440px de largura.
