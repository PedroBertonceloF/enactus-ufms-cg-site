# Molde do site da Enactus UFMS Campo Grande

> **Isto é um molde, uma proposta para o time aprovar. Não é o site oficial.**
> A página tem um selo "Molde" no canto inferior esquerdo e está bloqueada para buscadores (`noindex`).
> Quando o time aprovar e o conteúdo real entrar, apague os blocos marcados com `MOLDE` no `index.html`.

Landing page de uma página só, em **um arquivo** (`index.html`) mais a pasta `assets/`.
Não precisa instalar nada: abra o `index.html` no navegador.

## O que precisa ser preenchido

Tudo que falta aparece **com borda tracejada laranja** na tela e com a etiqueta `EDITAR`.
No código, procure por `EDITAR`.

| Onde | O que colocar |
|---|---|
| Hero | Foto principal do time (`assets/time-capa.jpg`, ideal ≥ 1400 px de largura) |
| Impacto | Número real de **vidas impactadas**. Confira também os outros 3 (`data-alvo="..."`) |
| Cards de projeto | Confirme os **ODS** de cada projeto. As etiquetas ODS 8/12/15, 5 e 2/3 são sugestões, não vieram de um documento oficial |
| O time | Nomes da presidência e da vice-presidência do ciclo |
| Depoimentos | 3 depoimentos reais, **com autorização de uso** (1 da comunidade, 1 de membro, 1 do professor conselheiro) |
| Parceiros | Logos oficiais em PNG transparente, no lugar dos nomes em texto |
| Seja Enactor | Link do formulário do processo seletivo + período de inscrições |
| Newsletter | Ligar a um serviço de e-mail (veja abaixo) + link da política de privacidade |
| Rodapé | Bloco e sala onde o time se reúne |

## Como ligar a newsletter

Hoje o formulário só **mostra a mensagem de sucesso**: ele não salva o e-mail em lugar nenhum.
Para funcionar de verdade, escolha um serviço gratuito:

- **Brevo** ou **MailerLite**: criam o formulário e mandam a newsletter. São os mais completos.
- **Formspree**: só recebe os e-mails no Gmail do time. É o mais simples.

Depois, troque `action="#"` no `<form id="form-news">` pela URL que o serviço fornecer e
apague o `ev.preventDefault();` no `<script>` do final do arquivo.

> **LGPD:** a caixinha de consentimento é obrigatória. Não a remova. A política de privacidade
> precisa dizer o que é coletado (nome e e-mail), para quê (newsletter) e como cancelar.

## De onde veio cada ideia

Este molde junta o melhor da análise em [`enactus-analise-design/ANALISE_DESIGN_ENACTUS.md`](enactus-analise-design/ANALISE_DESIGN_ENACTUS.md):

| Elemento | Inspiração |
|---|---|
| Hero **En · Act · Us** | Enactus Unicamp + o "Entrepreneurial Action Us" do Manual do Membro |
| Foto recortada em **seta com borda amarela** | Enactus UFPA (lembra o origami do símbolo) |
| **Divisores ondulados**, painéis de diretorias com linhas, contadores com barra amarela, depoimentos | Enactus UFMG |
| Números grandes de impacto | Enactus ESALQ |
| Newsletter numa faixa de cor antes do rodapé | UFPA, mas com e-mail **dentro da página**, e não um link para o Google Forms |
| Seção **Seja Enactor** | Não existe em nenhum dos 4 sites. É o diferencial |
| Cores (amarelo `#FFC222` + verde-mata `#1E3D2A` + creme), capivara | Manual do Membro 2026 e artes do time |
| Hexágonos de mel, serifa itálica em palavras-chave | Posts do Instagram do PantaMel (`FotosPosts/`) |

## Animação do arco e flecha (hero)

No lugar da foto do time aparece o **símbolo Enactus fechado**: o origami com o arco e a flecha.
Quando a pessoa rola a página, a corda é puxada, a flecha é solta e o origami se desdobra,
**abrindo a foto do time**. A capivara e o selo entram em seguida. Voltando o scroll, tudo se fecha de novo.

- **Computador:** o hero inteiro fica parado na tela enquanto a animação roda.
- **Celular:** o texto sobe normalmente e só o bloco da foto fica parado no meio da tela durante a animação.
- **"Reduzir movimento" ligado ou sem JavaScript:** a foto aparece aberta direto.

Para ajustar, procure por `ARCO FECHADO` no `index.html`:
- duração no computador: `--palco:130vh` (mais vh = animação mais longa)
- duração no celular: `140svh` em `.js-arco .hero__palco`
- ordem e tempo de cada fase: objeto `T` no JS (`puxa`, `voa`, `abre`, `capi`, `selo`, de 0 a 1)

## Cores e fontes

As cores ficam no topo do `<style>`, em `:root`. Para trocar a paleta, mude só ali.

- Títulos: **Bricolage Grotesque** (800)
- Destaques em itálico: **Instrument Serif**
- Texto: **Figtree**

## Imagens em `assets/`

Os logos e as capivaras foram extraídos do *Manual do Membro 26/27*. As fotos do PantaMel vieram de
`../fotos/` (autorização de imagem já confirmada, segundo o LEIA-ME de lá).
As fotos do banco de imagens (`banco-de-imagens-nao-usar/`) **não** foram usadas.
