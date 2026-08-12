# Maison Trigo

Site institucional para uma padaria artesanal fictícia, desenvolvido com a proposta de utilizar apenas HTML5 e CSS. O objetivo foi construir um código semanticamente organizado e funcional, incluindo navegação entre seções por âncoras, carrossel de imagens em CSS puro e layout totalmente responsivo.

# Demo
Link para o site publicado <!-- substitua pelo link do GitHub Pages / Vercel -->

# Sobre o projeto

Maison Trigo simula o site de uma padaria de fermentação natural com duas unidades físicas. A proposta técnica do projeto foi um desafio consciente: montar uma experiência de "single page application" com múltiplas seções, navegação, interatividade visual, interface moderna e  sem uma linha de JavaScript, usando somente os recursos nativos do HTML5 e do CSS3.

# Tecnologias

HTML5 semântico

CSS3 puro (sem frameworks, sem pré-processadores)

Font Awesome (ícones, via CDN)

Google Fonts — Cormorant Garamond (títulos) e Plus Jakarta Sans (corpo de texto)

# Funcionalidades e decisões técnicas

Navegação sem JavaScript com :target

Cada seção do site (#home, #sobre, #artesanal, #lojas) fica oculta por padrão (display: none) e só é exibida quando corresponde à âncora ativa na URL, usando a pseudo-classe :target:

main section {
  display: none;
}

main section#home {
  display: block;
}

main section:target {
  display: block;
  animation: fadeIn 0.4s ease-in-out;
}

Isso permite simular uma navegação de SPA (single page application) inteiramente com CSS, incluindo uma animação de fade-in suave ao trocar de seção.

# Carrossel de imagens 100% CSS

O banner principal usa um carrossel automático construído apenas com @keyframes e transform: translateX(), sem nenhuma biblioteca ou script:

.carrossel-slides {
  display: flex;
  width: 500%;
  animation: carrosselAuto 20s infinite ease-in-out;
}

O carrossel também pausa ao passar o mouse (:hover), melhorando a experiência de leitura das imagens.

# Layout com Flexbox e Grid

O projeto combina as duas ferramentas de layout do CSS moderno, cada uma no contexto que faz mais sentido:
Flexbox para alinhamentos em linha: header (logo + navegação), botão flutuante do WhatsApp, ícones de redes sociais no rodapé e os slides do carrossel.
CSS Grid para os cards de produtos e lojas, usando grid-template-columns: repeat(auto-fit, minmax(280px, 1fr), técnica que cria um grid responsivo que se reorganiza sozinho, sem precisar de media queries para definir o número de colunas.

# Responsividade (desktop-first)

O layout foi desenvolvido no modelo desktop-first: o CSS base é pensado para telas grandes, e os ajustes para telas menores são feitos com max-width em dois breakpoints:

@media (max-width: 900px) — tablets e telas médias
@media (max-width: 600px) — celulares

Nesses breakpoints, o header empilha verticalmente, os grids de cards passam para uma única coluna, o carrossel reduz de altura e a tipografia é reajustada para manter a leitura confortável em telas menores.

# Semântica HTML5

A estrutura utiliza tags semânticas (header, nav, main, section, footer) em vez de divs genéricas, o que melhora tanto a acessibilidade quanto a leitura do código por outros desenvolvedores — e a interpretação do conteúdo por mecanismos de busca.

# Acessibilidade

Botão flutuante do WhatsApp com aria-label descritivo

Estado de foco visível customizado (:focus-visible) para navegação por teclado

Imagens com atributos alt descritivos

# Responsividade

O site foi testado e ajustado nos seguintes formatos, com largura de:

Desktop: acima de 900px 

Tablet: até 900px

Celular: até 600px


# Restrição do projeto

Este projeto foi desenvolvido com a restrição proposital de não utilizar nenhum JavaScript, como exercício de aprofundamento em HTML5 e CSS3. Todos os efeitos interativos, tais como navegação entre seções, carrossel de imagens, animações e hover states foram construídos exclusivamente com recursos nativos do CSS.

# Licença
Este é um projeto de portfólio pessoal, desenvolvido para fins de estudo e demonstração de habilidades em front-end.
