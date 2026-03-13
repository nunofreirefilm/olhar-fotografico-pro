# Layout Specification - Olhar Fotográfico

Este documento detalha a estrutura, design e interatividade de cada seção da landing page, servindo como guia mestre para o desenvolvimento.

---

## Identidade Visual Consolidada
- **Paleta de Cores:**
  - Background: `#0a0a0a` (Deep Dark)
  - Accent Principal: `#e60000` (Red)
  - Texto Primário: `#ffffff`
  - Texto Secundário (Muted): `#a0a0a0`
  - Glass: `rgba(255, 255, 255, 0.05)` com border `rgba(255, 255, 255, 0.1)`
- **Tipografia:**
  - Heading: `Unbounded` (700, 900)
  - Body: `Sora` (300, 400, 600)
  - Accent/Micro-copy: `Space Mono` (400)

---

## Seção 1: Hero (Status: Aprovado/Existente)
- **Arquetipo:** Hero Dominante
- **Constraints:** Video/Image Fullbleed, Glassmorphism
- **Nota:** Já implementado no code base atual. Focar em polir micro-interações.

---

## Seção 2: O Problema (Status: Aprovado/Existente)
- **Arquetipo:** Split Vertical (60/40)
- **Constraints:** Text Highlight, Graphic Elements (Visual Card)
- **Nota:** Já implementado. Manter a estética de "laboratório técnico/cinema".

---

## Seção 3: A Solução
### Arquetipo e Constraints
- **Arquetipo:** Bento Box
- **Constraints:** Glassmorphism, High Contrast, Stagger
- **Justificativa:** Organizar os três pilares (Luz, Ângulo, Composição) como células de uma caixa bento cria uma percepção de "kit de ferramentas" essencial, facilitando a digestão do conteúdo.

### Conteúdo
- **Título:** A Grande Virada no Seu Audiovisual
- **Texto:** 90% da qualidade de um vídeo está em três pilares: Iluminação, Ângulo de Filmagem e Composição Visual...
- **Pilares:** Iluminação, Ângulo de Filmagem, Composição Visual.

### Layout
- Grid de 3 colunas em desktop, transformando-se em stack vertical no mobile.
- Cards com `aspect-ratio: 16/9` ou `1/1` dependendo da densidade do conteúdo.
- Padding interno dos cards: `2.5rem`.

### Cores & Estilo
- Cards com `background: var(--glass-bg)` e `border: 1px solid var(--glass-border)`.
- No hover de cada card, a borda muda para `var(--accent-red)`.

### Animações
- `data-aos="fade-up"` com `stagger` de 100ms entre os cards do grid.

---

## Seção 4: Módulos (O Que Você Vai Aprender)
### Arquetipo e Constraints
- **Arquetipo:** Scroll Cinematico (Vertical Storytelling)
- **Constraints:** Video Masked, Clip Reveal, Sticky Element
- **Justificativa:** Como o curso é sobre olhar e cinema, a navegação deve emular a troca de planos de um filme.

### Conteúdo
- Detalhamento dos Módulos 1, 2 e 3 (Iluminação, Ângulos, Composição).
- Lista de tópicos e bônus para cada um.

### Layout
- Cada módulo ocupa `100vh`.
- O título do módulo fica `sticky` no centro enquanto o conteúdo (tópicos) desliza por cima ou ao lado.
- Uso de `clip-path` para revelar imagens de "olhar técnico" conforme o scroll entra na seção.

### Elementos Visuais
- Background de cada módulo com um vídeo em low-opacity (10-20%) ou imagem de alta qualidade tratada com `grayscale(1)`.
- Molduras que lembram o visor de uma câmera (recortes de canto).

### Interatividade
- Ao passar o mouse nos tópicos, um "glow red" sutil aparece atrás do texto.

---

## Seção 5: Público-alvo
### Arquetipo e Constraints
- **Arquetipo:** Modular
- **Constraints:** Image Duotone, Layered, Asymmetric Padding
- **Justificativa:** Destacar os perfis (Filmmakers, Influencers, Pros) de forma moderna e não apenas uma lista de bullets.

### Layout
- Grid assimétrico onde as imagens dos perfis se sobrepõem ligeiramente ao texto.
- Margens negativas para criar profundidade.

### Cores
- Filtro `duotone` nas imagens (Red & Black) para manter a coesão visual.

---

## Seção 6: Resultados
### Arquetipo e Constraints
- **Arquetipo:** Before/After (Comparação Visual)
- **Constraints:** Split Vertical, Mask Reveal, Slider Before/After
- **Justificativa:** Nada prova melhor a eficiência de um curso de "olhar" do que mostrar a diferença entre uma cena comum e uma cena com técnica.

### Interatividade
- Slider interativo onde o usuário arrasta para ver o "Antes" (amador) e "Depois" (cinematográfico).

---

## Seção 7: Oferta e Bônus
### Arquetipo e Constraints
- **Arquetipo:** Feature Comparison (Stack de Valor)
- **Constraints:** Neon Colors (Glow), High Contrast, Pulse Loop
- **Justificativa:** Reestruturar os bônus como "camadas" de valor que se empilham até o preço final impactante.

### Layout
- Box centralizado com borda `glow red`.
- Bônus listados com tipografia `Space Mono` para parecer um "manifesto" ou "fatura profissional".
- Preço `R$27,90` com tamanho massivo (`font-size: 5rem`).

---

## Seção 8: FAQ & Objeções
### Arquetipo e Constraints
- **Arquetipo:** Editorial
- **Constraints:** Low Contrast, Hover Lift
- **Justificativa:** Seção limpa e direta para remover fricção de compra.

### Layout
- Acordeões customizados com linhas finas separadoras (0.5px opacity 0.2).
- Ícone de expansão: um "+" que rotaciona 45 graus (X) ao abrir.

---

## Seção 9: CTA Final
### Arquetipo e Constraints
- **Arquetipo:** Type Hero
- **Constraints:** Headline >150px, Text with Gradient, Noise Texture
- **Justificativa:** Terminar com um impacto tipográfico que reforça a autoridade da marca.

### Conteúdo
- "GARANTIR MEU ACESSO AO CURSO"
- "Câmeras caras não criam grandes vídeos. Olhar treinado cria."

### Visual
- Gradiente de fundo escuro para vermelho profundo no bottom.
- Texto "Olhar treinado" com `text-stroke` ou `outer-glow`.

---

## Elementos Encantadores (Global)
1. **Cursor Customizado:** Um círculo com "crosshair" (mira de câmera) que aumenta ao passar sobre botões.
2. **Noise Overlay:** Uma camada de granulação de filme constante (já no `index.html`).
3. **Smooth Scroll:** Implementar scroll suave para melhorar a experiência narrativa.
4. **Micro-interações de Botão:** Botões com efeito de "varredura de luz" (já no CSS).
