# Análise de Design — Landing Pages de Times Enactus

> Scraping feito em 04/11/2026 com Firecrawl (conteúdo + branding extraído do CSS + screenshot de página inteira).
> Screenshots completos em [`screenshots/`](screenshots/).

| Time | URL | Plataforma |
|---|---|---|
| Enactus UFPA | https://www.enactusufpa.com/home | Google Sites |
| Enactus UFMG | https://enactusufmg.com.br/ | WordPress 6.7 + Elementor 3.30 |
| Enactus Unicamp Campinas | https://www.enactusunicamp.com/ | Wix |
| Enactus ESALQ-USP | https://sites.usp.br/enactus/ | WordPress (USP) + Elementor 3.31 |

---

## 1. Newsletter: o que cada site tem de verdade

Só **um dos quatro** tem uma newsletter com inscrição. Os outros têm uma área de notícias ou blog com nome parecido.

| Time | Newsletter? | Como funciona | Observações |
|---|---|---|---|
| **UFPA** | ✅ **Sim, com inscrição** | Seção "**Assine nossa Newsletter**" no fim da home, com fundo vinho, título branco, uma linha de descrição e botão branco "**Assine aqui!**" que leva a um **Google Forms** | Promete: "atualizações sobre o time, acompanhamento de ações dos negócios, depoimentos de membros e alumnis". Não tem campo de e-mail na página, só o link para o formulário. |
| **ESALQ-USP** | ⚠️ Só no nome | Item "**Newsletter**" no menu leva a `/newsletter/`, que é um **carrossel de posts** (foto de fundo, título branco, botão "Confira") | Não tem inscrição. É um blog com nome de newsletter. Posts mais recentes: 2021–2022 (abandonado). |
| **Unicamp Campinas** | ⚠️ Blog "News" | Seção "**News**" na home com 3 cards (imagem, título, resumo) e página `/news` | Não tem inscrição. Último post: **jun/2021**. |
| **UFMG** | ❌ Não | Existe um arquivo `News-Maio-2026` no topo da página, mas é só o **logo** (provavelmente sobra do cabeçalho de uma newsletter por e-mail) | Não tem bloco de inscrição nem página de notícias. |

**O que isso significa para o nosso site:**
- Ter uma newsletter com inscrição **de verdade** (campo de e-mail na própria página) já põe o site à frente dos quatro.
- O modelo da UFPA (uma faixa colorida de largura total no fim da página, com título, uma linha de promessa e CTA) é bom. Trocar o link para o Google Forms por um **input de e-mail inline** reduz o atrito.
- Um blog só funciona se for atualizado. Unicamp e ESALQ mostram como um "News" parado desde 2021 passa impressão de time inativo. Se não tiver gente para manter, é melhor mostrar o **feed do Instagram** ou só a newsletter.
- **LGPD:** coletar e-mail exige checkbox de consentimento e link para a política de privacidade, como faz a Enactus Brasil no rodapé.

---

## 2. Identidade visual (extraída do CSS)

### Paleta de cores

| Time | Primária | Secundária | Destaque | Fundo | Texto |
|---|---|---|---|---|---|
| UFPA | `#FBC22C` amarelo | `#751040` vinho | `#FF8806` laranja | `#F2F2F2` | `#741240` vinho |
| UFMG | `#FDC234` amarelo | `#520F93` roxo (botões) | `#D05C28` laranja queimado | `#E8EAE2` off-white quente | `#30333C` grafite |
| Unicamp | `#FFC222` amarelo | `#011C66` azul-marinho | `#FFC222` | `#FFFFFF` | `#515356` cinza |
| ESALQ | `#FFCC21` amarelo | `#61CE70` verde | `#FFCC21` | `#FFFFFF` | `#7A7A7A` cinza claro |

**O que se repete:** todos usam o **amarelo oficial Enactus** (`#FFC222`, entre `#FBC22C` e `#FFCC21`) como primária. O que diferencia cada time é a **cor secundária**:
- UFPA → vinho + laranja (calor, Amazônia)
- UFMG → paleta multicolor terrosa (verde-petróleo, laranja, coral, roxo)
- Unicamp → azul-marinho (sóbrio, institucional)
- ESALQ → verde (agro/ESALQ), mas usado pouco

### Tipografia

| Time | Títulos | Corpo | Caráter |
|---|---|---|---|
| UFPA | **Montserrat** (h1 ≈ 45px, h2 24px) | Montserrat | Geométrica, moderna, pesada |
| UFMG | **Merriweather** serifada (h1 36px, h2 40px), títulos com *letter-spacing* largo em caixa alta | Roboto | Editorial, elegante |
| Unicamp | Avenir Light / Futura / Lulo Clean (display) | Source Sans Pro 18px | Limpa, com títulos espaçados ("Q U E M  S O M O S") |
| ESALQ | **Libre Franklin** | Roboto | Neutra, padrão Elementor |

### Botões e cantos

| Time | Botão primário | Raio | Sombra |
|---|---|---|---|
| UFPA | Branco, largura total, texto vinho | 0px (quadrado) | nenhuma |
| UFMG | `#D05C28` laranja, texto branco / secundário roxo `#520F93` | **20px (pill)** | forte (`10px 6px 10px rgba(0,0,0,.5)`) |
| Unicamp | Não tem botões, só links | 0px | nenhuma |
| ESALQ | Amarelo `#FFCC21`, texto branco | 3px | nenhuma |

---

## 3. Estrutura da página (ordem das seções)

### UFPA (Google Sites) — *storytelling institucional*
1. **Hero:** foto do time comemorando com overlay escuro, nome "Enactus UFPA" e tagline centralizados. Menu transparente sobre a foto (Home, Nossa História, Portal de Notícias, Blog).
2. Linha laranja fina separando do resto
3. **Sobre nós:** faixa vinho com título, depois texto à esquerda e foto recortada em **forma de seta/losango com borda amarela** à direita (é o elemento mais marcante do site)
4. **Missão:** faixa laranja de largura total
5. **Visão:** faixa vinho de largura total
6. **Depoimento do professor conselheiro:** foto em recorte de seta, nome, cargo e texto longo
7. **Parceiros:** faixa laranja com carrossel de logos (7 slides)
8. **Negócios vigentes:** vídeo do Google Drive ao lado da descrição (Biolume, Aruanas)
9. **Newsletter:** faixa vinho com CTA
10. **Rodapé:** tagline grande em vinho, logo, e-mail e ícones sociais coloridos

**Ritmo:** alterna faixas coloridas (vinho → laranja → vinho → laranja → vinho), o que dá energia. O ponto fraco são os vídeos do Drive: no screenshot aparecem como **áreas em branco**, e players do Google Drive são pesados e quebram com facilidade.

### UFMG (WordPress/Elementor) — *o mais completo e polido*
1. Logo centralizado sobre fundo off-white
2. **Hero:** foto de camiseta Enactus com o título serifado amarelo alinhado à direita, subtítulo branco e botão pill "Fale Conosco!"
3. **O que é Enactus?:** texto e **4 estatísticas com ícones amarelos** (37 países, 550 parceiros, 1.730 instituições, 72.000 estudantes) ao lado de um vídeo do YouTube
4. **Nossos projetos atuais:** faixa amarela com **borda ondulada** (wave divider), cards brancos com sombra, imagem, avatar circular, nome em caixa alta, área e botão "Saiba mais"
5. **Conheça nossas bases:** faixa verde-água ondulada, **4 painéis coloridos com linhas orgânicas brancas** (RIF, COM, RH, Presidência), com label branco sobreposto
6. **A Enactus UFMG:** lista com checkmarks amarelos e foto do time com cantos arredondados
7. **Nosso impacto:** fundo cinza ondulado, **4 contadores** com barra amarela vertical à esquerda (R$ 52.000 de renda gerada · 250 impactados · 82 membros · 10 ODS)
8. **Depoimentos:** 4 cards com aspas amarelas, foto circular, nome e cargo
9. **Rodapé:** grafite com 4 colunas (logo + frase, Contato, Endereço, Apoiador)

**Destaques:** os **divisores ondulados** e a seção de **bases/diretorias** com arte própria dão personalidade. É o único site que mostra **impacto em números** e **depoimentos de membros**. Os pontos fracos são o texto pequeno demais nos cards e erros de conteúdo ("emponderar", dois depoimentos assinados como "Bella").

### Unicamp Campinas (Wix) — *conceito forte, execução datada*
1. **Menu azul-marinho fixo** com logo num círculo que "vaza" para baixo do menu (Home, Worldwide, Enactus Unicamp, Projetos, News, Fale Conosco)
2. **Hero tipográfico:** decompõe o nome **"En / Act / Us"** em amarelo ao lado de "Empreendedorismo / Ação / Nós" em branco, sobre fundo escuro desfocado. **É a ideia mais criativa dos quatro.**
3. **Quem somos:** caixa cinza com foto da bandeira e texto justificado
4. **News:** 3 cards
5. **O que fazemos:** bloco azul-marinho com texto branco e **palavras-chave destacadas em amarelo** (oportunidades, empoderam, autonomia...), foto ao lado
6. Galeria/slideshow (12 fotos) com legenda
7. **Rodapé:** cinza com divisor vertical tracejado amarelo, e-mail e endereço com ícones amarelos, links para projetos e Enactus Brasil

**Ponto fraco:** o conteúdo fica numa coluna estreita (~620px) sobre um fundo escuro fixo, com cara de 2018 (o rodapé mostra "© 2018"). O texto justificado cria buracos e a meta description cita projetos diferentes dos que aparecem na página.

### ESALQ-USP (WordPress/Elementor) — *simples e limpo, mas genérico*
1. Logo pequeno à esquerda, ícones sociais amarelos circulares à direita, menu centralizado com **sublinhado verde** no item ativo (Início, Sobre, Time, Projetos, Newsletter, Contato)
2. **Hero:** foto aérea do campus ESALQ (bonita, mas é do prédio e não das pessoas)
3. **Contadores gigantes em amarelo:** +10 projetos · +500 vidas impactadas
4. **Missão / Visão / Valores:** 3 colunas com ícones amarelos grandes (bússola, olho, balança)
5. **Notícias:** 3 colunas (título amarelo, foto, data e resumo em caixa alta espaçada, botão amarelo "Leia mais")
6. Vídeo institucional da Enactus Brasil em largura total
7. **Rodapé:** cinza médio com endereço, menu repetido, busca e ícones sociais
8. ⚠️ Sobrou um placeholder do Elementor visível: "*Adicione o texto do seu título aqui*"

**Ponto fraco:** amarelo sobre branco tem **contraste ruim** (os títulos "Missão", "Renascer Solidário" etc. ficam difíceis de ler). Não mostra nenhum projeto atual, e as notícias são de 2020–2023.

---

## 4. Padrões que se repetem (o "esqueleto" de uma landing Enactus)

| Seção | UFPA | UFMG | Unicamp | ESALQ | Recomendação |
|---|:-:|:-:|:-:|:-:|---|
| Hero com foto do time + tagline | ✅ | ✅ | ✅ (tipográfico) | ⚠️ (campus) | **Obrigatório.** Usar foto de **pessoas** |
| O que é Enactus (rede global) | ✅ | ✅ | ✅ | via vídeo | Curto, 2–3 linhas |
| Missão / Visão / Valores | ✅ | — | — | ✅ | Opcional, cabe em 3 colunas |
| Projetos atuais (cards) | ✅ | ✅ | — | — | **Obrigatório** |
| Impacto em números | — | ✅ | — | ✅ | **Obrigatório.** É o que convence parceiros |
| Estrutura / diretorias | — | ✅ | — | — | Bom para recrutamento |
| Depoimentos | ✅ (prof.) | ✅ (membros) | — | — | Recomendado |
| Parceiros / apoiadores (logos) | ✅ | ✅ | — | — | **Obrigatório** se houver patrocínio |
| Notícias / blog | — | — | ✅ | ✅ | Só se for atualizado |
| **Newsletter com inscrição** | ✅ | — | — | — | **Diferencial** |
| Vídeo institucional | ✅ (Drive) | ✅ (YouTube) | — | ✅ (YouTube) | YouTube *lite embed*, nunca Drive |
| CTA "Seja Enactor" / processo seletivo | — | — | — | — | ⭐ **Nenhum tem.** É a maior lacuna |
| Rodapé com contato + endereço + redes | ✅ | ✅ | ✅ | ✅ | Padrão |

---

## 5. Melhores ideias para aproveitar

1. **Hero "En · Act · Us" (Unicamp):** explicar o nome com tipografia é memorável. Dá para modernizar com animação de entrada palavra por palavra.
2. **Recortes de foto em forma de seta com borda amarela (UFPA):** remetem ao símbolo da Enactus (a "seta/origami" do logo). É identidade forte sem custo.
3. **Divisores ondulados e painéis de diretorias com linhas orgânicas (UFMG):** quebram a monotonia das faixas retas.
4. **Contadores de impacto com barra lateral amarela (UFMG)** + **números gigantes (ESALQ)**: animar a contagem quando entram na tela.
5. **Palavras-chave em amarelo dentro do texto corrido (Unicamp):** ajuda a leitura rápida.
6. **Faixas de cor alternadas (UFPA):** dão ritmo a um site de uma página só.
7. **Newsletter em faixa de largura total antes do rodapé (UFPA):** mas com input de e-mail inline.

## 6. Erros para não repetir

- ❌ Conteúdo desatualizado (Unicamp 2021, ESALQ 2023, "© 2018") passa a impressão de time inativo
- ❌ Amarelo sobre branco em texto (ESALQ): falha WCAG. Usar amarelo como **fundo** ou **detalhe**, nunca como cor de texto pequeno
- ❌ Vídeos do Google Drive embutidos (UFPA): pesados e aparecem em branco
- ❌ Placeholders esquecidos ("Adicione o texto do seu título aqui")
- ❌ Coluna estreita sobre fundo fixo (Unicamp): desperdiça tela e fica ruim no celular
- ❌ Texto justificado e corpo de 10–12px (Unicamp, UFMG)
- ❌ Newsletter que é só um link externo (UFPA) ou que é só um blog (ESALQ)
- ❌ Nenhum dos quatro tem um **CTA de recrutamento** claro ("Seja Enactor", data do próximo processo seletivo)

---

## 7. Proposta de estrutura para a landing page (síntese)

```
[Nav fixa: logo · Sobre · Projetos · Impacto · Time · Newsletter · [Seja Enactor]]
[Hero: foto do time + "En·Act·Us" animado + tagline + CTA duplo (Seja Enactor / Seja parceiro)]
[O que é Enactus: 2 linhas + 4 stats globais]
[Projetos atuais: cards com ODS, área e "Saiba mais"]
[Impacto em números: contadores animados]
[Nossas diretorias: painéis coloridos]
[Depoimentos: membros + professor conselheiro]
[Parceiros: faixa de logos]
[Newsletter: faixa de cor, input de e-mail + checkbox LGPD]
[Rodapé: contato · endereço do câmpus · redes · link Enactus Brasil]
```

**Paleta sugerida:** amarelo Enactus `#FFC222` (primária) + uma secundária própria do time, escura e de bom contraste com o amarelo (ex.: um verde-pantanal ou azul-escuro para a UFMS) + off-white quente `#F4F1EA` de fundo + grafite `#2B2D33` para texto.
**Tipografia sugerida:** uma display geométrica para títulos (Montserrat / Poppins / Sora) + uma sans legível no corpo (Inter / Source Sans 3) com 16–18px.
