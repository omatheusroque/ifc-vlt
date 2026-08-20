# Analise da Pagina Master Business (Modelo para VLT)

> Fonte: https://api.taticaleads.com.br/preview/cquKQYPDLRGrXS5NtW98?notrack=true
> Empresa original: AuraFlow Desenvolvimento Humano
> Data da analise: 2026-08-19

---

## 1. Estrutura Geral da Pagina

Pagina single-page (one-page) com scroll vertical. Sem menu de navegacao tradicional. Fluxo linear com 6 secoes:

| # | Secao | Descricao |
|---|-------|-----------|
| 1 | Hero Section | Tela cheia com titulo, subtitulo, badge e CTA |
| 2 | Video | Video de apresentacao (YouTube embed) |
| 3 | Beneficios | 3 cards com os pilares do treinamento |
| 4 | Depoimentos | 3 testimoniais com estrelas |
| 5 | Formulario | Formulario de cadastro/inscricao (iframe TaticaLeads) |
| 6 | Footer | Copyright e nome da empresa |

---

## 2. Header / Topo

- **Logo**: Imagem PNG do "Master Business" (altura: 5rem)
- **Navegacao**: Nao ha menu. Apenas links de ancora internos (#video, #form)
- **Estilo**: Transparente sobre o hero

---

## 3. Hero Section (Tela Cheia)

### Badge / Selo
> "Um dia imersivo de PNL, Vendas, Empreendedorismo e Lideranca."

### Titulo Principal
> "Desperte sua Mentalidade de Sucesso"

### Descricao / Subtitulo
> "Um imersao para desenvolver as mentalidades de Vendas, Empreendedorismo e Lideranca. Aprenda como alinhar comportamento, tecnica e inteligencia emocional usando ferramentas de PNL e lideranca para transformar sua vida profissional e pessoal."

### CTA (Call-to-Action)
- **Texto do botao**: "QUERO MEU LUGAR NO MASTER BUSINESS"
- **Link**: Ancora para #form (formulario de inscricao)
- **Estilo**: Botao com gradiente dourado, hover com elevacao

### Indicador de Scroll
- Circulo animado com seta para baixo (animacao bounce)
- Indica ao usuario para rolar a pagina

### Background
- Gradiente diagonal: preto para cinza escuro
- Overlay escuro sobre o fundo

---

## 4. Secao de Video

### Titulo
> "Conhecendo o Master Business"

### Subtitulo
> "Uma imersao para impulsionar o seu negocio."

### Conteudo
- Embed de video do YouTube (iframe)
- ID do video: `-aWlmfIXJDg`
- Proporcao: 16:9
- Texto complementar: "Assista ao video."

---

## 5. Secao de Beneficios

### Titulo da Secao
> "O que voce ganhara participando do Master Business?"

### Card 1 — Mentalidade de Vendas
- **Icone**: Emoji de dinheiro (pode ser substituido por icone SVG)
- **Titulo**: "Mentalidade de Vendas"
- **Descricao**: "Descubra por que 85% da performance em vendas vem do comportamento e atitude. Explore o modelo DISC, trabalhe crencas e emocoes, aprenda perguntas SPIN e domine tecnicas de persuasao."

### Card 2 — Mentalidade Empreendedora
- **Icone**: Emoji de coroa (pode ser substituido por icone SVG)
- **Titulo**: "Mentalidade Empreendedora"
- **Descricao**: "Torne-se um empreendedor antifragil: identifique oportunidades, avalie riscos, desenvolva a atitude certa e aplique ferramentas praticas para transformar ideias em negocios de sucesso."

### Card 3 — Mentalidade de Lideranca
- **Icone**: Emoji de foguete (pode ser substituido por icone SVG)
- **Titulo**: "Mentalidade de Lideranca"
- **Descricao**: "Aprenda a gerir seu tempo e a tomar decisoes em cenarios complexos. Desenvolva inteligencia emocional, carisma e coaching para inspirar sua equipe e use a roda de lideranca para se autoavaliar."

### Layout dos Cards
- 3 cards lado a lado (desktop)
- Cada card com: icone + titulo + descricao
- Efeito hover: elevacao (translateY) + glow dourado
- Background dos cards: cinza escuro com backdrop-filter blur

---

## 6. Secao de Depoimentos

### Titulo da Secao
> "O que nossos alunos estao dizendo"

### Depoimento 1
- **Nome**: Marcia Nascimento
- **Profissao**: Fisioterapeuta
- **Avatar**: Letra inicial "M" (circulo colorido)
- **Avaliacao**: 5 estrelas
- **Texto**: "O Felipe me transformou como empresaria. Hoje tenho mais garra, mais vontade e sou mais atuante no meu mercado!"

### Depoimento 2
- **Nome**: Adailton Silva
- **Profissao**: Empresario
- **Avatar**: Letra inicial "A" (circulo colorido)
- **Avaliacao**: 5 estrelas
- **Texto**: "Felipe e meu mentor, amigo e parceiro. E o treinamento foi revolucionario, mudando minha forma de pensar a vida e a empresa."

### Depoimento 3
- **Nome**: Marcos Rodrigues
- **Profissao**: Mentor e Empresario
- **Avatar**: Letra inicial "M" (circulo colorido)
- **Avaliacao**: 5 estrelas
- **Texto**: "Minha identidade era bloqueada. Quando conheci o Felipe acessei minha verdadeira identidade e hoje posso contribuir com as pessoas."

### Layout dos Depoimentos
- 3 cards lado a lado (desktop)
- Cada card: avatar circular + estrelas + texto + nome + profissao
- Estilo: cards com fundo escuro e borda sutil

---

## 7. Secao de Formulario (Inscricao)

- **ID da secao**: `#form`
- **Conteudo**: iframe externo da plataforma TaticaLeads
- **ID do formulario**: `rkYo33CblSOrjPXUSDDb`
- **Altura do iframe**: 463px
- **Obs**: Nao ha informacoes de preco, oferta ou bonus visiveis na pagina

---

## 8. Footer

### Conteudo
> "Copyright 2025. Todos os direitos reservados"
> "AuraFlow Desenvolvimento Humano"

### Estilo
- Simples e minimalista
- Texto centralizado
- Sem links adicionais ou redes sociais

---

## 9. Design e Estilo Visual

### Paleta de Cores (CSS Variables)

| Elemento | Cor | HSL |
|----------|-----|-----|
| Background (fundo) | Preto muito escuro | `hsl(0, 0%, 8%)` |
| Foreground (texto) | Bege / Creme claro | `hsl(45, 100%, 85%)` |
| Accent (destaque) | Amarelo ouro | `hsl(45, 100%, 70%)` |
| Card background | Cinza muito escuro | `hsl(0, 0%, 12%)` |
| Bordas | Cinza escuro | `hsl(0, 0%, 20%)` |

### Gradientes
- **Primario (fundo)**: linear-gradient diagonal — preto → cinza escuro → cinza mais claro
- **Accent (botoes/destaques)**: linear-gradient — amarelo ouro → amarelo mais escuro

### Tipografia
- **Familia**: Inter (fallbacks: system-ui, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif)
- **Pesos usados**: 300 (light), 400 (regular), 500 (medium), 600 (semi-bold), 700 (bold), 900 (black)

### Efeitos Visuais
- `backdrop-filter: blur(10px)` nos cards (efeito glass/vidro fosco)
- `box-shadow` com glow na cor accent (dourado)
- Bordas arredondadas: `border-radius: 0.75rem`
- Hover: `translateY` (elevacao) + mudanca de cor
- Animacao bounce no indicador de scroll
- Transicoes suaves: `0.3s cubic-bezier`

### Estilo Geral
- **Modo**: Dark mode premium
- **Acentos**: Dourado / Ouro
- **Abordagem**: Moderno, minimalista, elegante
- **Sensacao**: Premium, exclusivo, sofisticado

---

## 10. Elementos de Prova Social

- Estatistica: "85% da performance em vendas vem do comportamento e atitude"
- 3 depoimentos com nomes reais e profissoes
- Mencao a "Felipe" como instrutor/mentor principal
- Avaliacoes 5 estrelas

---

## 11. Elementos de Urgencia / Escassez

**Nenhum identificado na pagina:**
- Sem timer / contagem regressiva
- Sem limite de vagas mencionado
- Sem mensagens de escassez
- Sem bonus com prazo limitado

---

## 12. Elementos Ausentes (nao presentes na pagina)

- Menu de navegacao
- FAQ (Perguntas Frequentes)
- Secao de precos / oferta detalhada
- Bonus listados
- Garantia
- Secao "Sobre o instrutor"
- Links para redes sociais
- Politica de privacidade / Termos de uso

---

## 13. Mapeamento para o VLT (Vendas e Lideranca Training)

### Adaptacoes sugeridas

| Master Business | VLT (Vendas e Lideranca Training) |
|-----------------|-----------------------------------|
| Logo Master Business | Logo VLT (ja existe em VLT/logo/Logo_VLT.png) |
| "Mentalidade de Sucesso" | Adaptar para foco em Vendas e Lideranca |
| 3 pilares (Vendas, Empreendedorismo, Lideranca) | Redefinir pilares para o VLT |
| AuraFlow Desenvolvimento Humano | IFC — Instituto Felipe Castro |
| Copyright 2025 | Copyright 2026 |
| Formulario TaticaLeads | Manter ou substituir conforme necessidade |
| Depoimentos genericos | Substituir por depoimentos do VLT |
| Video YouTube | Substituir pelo video do VLT |

### Estrutura recomendada para o VLT
1. Hero Section (com logo VLT, titulo, descricao e CTA)
2. Video de apresentacao
3. Beneficios / Pilares do treinamento
4. Depoimentos
5. Formulario de inscricao
6. Footer (IFC — Instituto Felipe Castro)

### Melhorias possiveis
- Adicionar secao "Sobre o Felipe Castro"
- Adicionar FAQ
- Adicionar secao de preco/oferta
- Adicionar countdown / urgencia
- Adicionar links para redes sociais do IFC
- Adicionar garantia
- Usar cores e identidade visual do VLT (manter ou adaptar o dark mode premium)
