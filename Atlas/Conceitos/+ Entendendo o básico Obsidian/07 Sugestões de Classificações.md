---
collection: "[[Gestão de Conhecimento]]"
---
# Padrões Específicos para Tipos de Notas em PKM

## Notas de Pessoas

### Sistema de Classificação Hierárquico

As notas de pessoas utilizam três níveis de classificação, do mais amplo ao mais personalizado:

```
peopleType (tipos fundamentais)
  ↓
peopleDomain (áreas de atuação)
  ↓
peopleGroups (agrupamentos pessoais)
```

### `peopleType` — 4 Tipos Fundamentais

Agrupa pessoas em categorias fundamentais baseadas em sua relação com você e o mundo:

1. **Fictício** — Personagens de obras de ficção
2. **Rede** — Contatos pessoais e profissionais diretos
3. **Notável** — Figuras conhecidas em suas áreas (influenciadores, especialistas)
4. **Proeminente** — Figuras históricas ou amplamente reconhecidas

**Exemplo de uso:**

```yaml
peopleType: rede
peopleName: Maria Silva
```

### `peopleDomain` — 10 Áreas de Atuação

Segmenta pessoas em domínios de conhecimento ou atividade profissional:

1. **Artes** — Artistas visuais, músicos, escritores, performers
2. **Negócios** — Empreendedores, executivos, investidores
3. **Humanidades** — Filósofos, historiadores, pensadores sociais
4. **Política** — Líderes políticos, ativistas, diplomatas
5. **Ciência & Tecnologia** — Cientistas, pesquisadores, desenvolvedores
6. **Espiritualidade** — Líderes religiosos, mestres espirituais, teólogos
7. **Esportes** — Atletas, técnicos, comentaristas esportivos
8. **Guerra** — Líderes militares, estrategistas, historiadores militares
9. **Figura Pública** — Celebridades, comunicadores, mídia
10. **Outro** — Pessoas que não se encaixam claramente nas categorias acima

**Exemplo de uso:**

```yaml
peopleType: proeminente
peopleDomain: Humanidades
peopleName: [[Mary Shelley]]
```

### `peopleGroups` — Agrupamentos Personalizados

Crie agrupamentos customizados baseados em suas necessidades específicas:

**Exemplos práticos:**

- "mentores", "colaboradores-frequentes", "autores-favoritos"
- "networking-2024", "conferência-tech", "livro-clube"
- "inspirações-criativas", "referências-técnicas"

### Campos Biográficos e Contextuais

Propriedades adicionais para enriquecer notas de pessoas:

#### Dados Vitais

```yaml
lifespan: 1797-1851
finalAge: 53
birthPlace: Londres, Inglaterra
```

#### Contexto Cultural

```yaml
culturalEra: Período Romântico
culturalMovement: Romantismo Inglês
culturalWorks: 
  - Frankenstein
  - O Último Homem
  - Valperga
```

#### Informações de Contato (para tipo "rede")

```yaml
email: exemplo@email.com
company: [[Nome da Empresa]]
linkedin: url
lastContact: 2024-10-15
```

### Sistema ROAR: Gestão de Relacionamentos

**ROAR** = "Reach-Outs And Replies" (Contatos e Respostas)

Um sistema prático para acompanhar interações com contatos da sua rede profissional e pessoal.

#### Propriedades do ROAR

**`ROAR` — Status da Interação**

- `reach-out` — Você entrou em contato, aguardando resposta
- `reply` — A pessoa respondeu, sua vez de retornar
- `waiting` — Aguardando momento apropriado para contato

**`ROARrank` — Prioridade (1-5)**

- `5` — Contato crítico/urgente
- `4` — Alta prioridade
- `3` — Prioridade média
- `2` — Baixa prioridade
- `1` — Quando houver oportunidade

**`ROARdetails` — Contexto Rápido**

Uma frase resumindo o último ponto de contato ou próxima ação.

#### Exemplo Completo ROAR

```yaml
peopleType: rede
peopleName: João Santos
peopleGroup: networking-2024
ROAR: reply
ROARrank: 4
ROARdetails: Respondeu proposta de parceria, preciso enviar detalhes do projeto
lastContact: 2024-10-20
```

> **💡 Dica:** O sistema ROAR funciona melhor para pessoas com quem você **não** interage diariamente. Para contatos frequentes, use sistemas de CRM ou gestão de tarefas dedicados.

---

## Notas de Ideias

### O Paradoxo da Classificação de Ideias

> **Princípio fundamental:** Ideias devem ser livres para se conectar organicamente, não engessadas em categorias rígidas.

A classificação excessiva de ideias quase sempre falha porque:

1. **Ideias são fluidas** — Uma mesma ideia pode se conectar a múltiplos contextos
2. **Categorias limitam descobertas** — Categorias predefinidas restringem conexões emergentes
3. **Contexto evolui** — O que parece relevante hoje pode mudar amanhã

### O Que NÃO Fazer

❌ **Evite `ideaCategory`**

- Cria falsa sensação de organização
- Restringe o pensamento associativo
- Dificulta conexões inesperadas

❌ **Evite classificações genéricas**

- "importante", "interessante", "revisar" são vagos demais
- Não agregam valor real à recuperação

### O Que FUNCIONA

#### ✅ Opção 1: Pastas Temáticas Amplas

Use pastas para grandes áreas, não micro-categorias:

```
📁 Ideias/
  📁 Filosofia/
  📁 Tecnologia/
  📁 Criatividade/
  📁 Negócios/
```

#### ✅ Opção 2: Sistema de Tags Flexível

Tags descritivas e específicas ao conteúdo:

```yaml
tags:
  - aprendizagem-ativa
  - metacognição
  - sistemas-complexos
```

#### ✅ Opção 3: `ideaGroup` (Apenas se Pessoal)

Use `ideaGroup` **somente** para agrupamentos altamente pessoais e significativos:

**Exemplos válidos:**

```yaml
ideaGroup: conceitos-fundamentais
ideaGroup: insights-2024
ideaGroup: tese-principal
```

**Por que funciona:** São agrupamentos que você cria com critério pessoal específico, não categorias genéricas impostas.

### Recomendação Final

Para ideias, priorize:

1. **Links internos ([[wikilinks]])** — Conexões orgânicas entre conceitos
2. **Tags contextuais** — Descritores específicos e significativos
3. **Mapas de Conteúdo (MOCs)** — Índices manuais que emergem naturalmente
4. **Busca por texto completo** — Deixe o conteúdo falar por si

---

## Notas de Mídia

### Propriedades Temporais Universais

Para qualquer tipo de mídia (livros, filmes, séries, podcasts, artigos):

#### `yearXP` — Ano de Primeira Experiência

Quando você experienciou pela primeira vez.

```yaml
yearXP: 2023
```

#### `yearXPL` — Ano da Última Experiência

Quando você experienciou pela última vez (para releituras, reassistidas).

```yaml
yearXPL: 2024
```

**Por que isso é útil:**

- Rastreia sua evolução e mudança de perspectiva
- Identifica padrões de consumo de mídia ao longo do tempo
- Facilita revisitas programadas

### Exemplo: Livro com Releitura

```yaml
bookTitle: 1984
bookAuthor: [[George Orwell]]
bookType: ficção
bookGenre: Distopia
yearXP: 2015
yearXPL: 2024
bookRating: 5
bookNotes: "Releitura revelou camadas políticas que não percebi na primeira leitura"
```

### Campos Específicos por Tipo de Mídia

#### Para Livros

```yaml
bookPages: 328
bookFormat: físico / digital / audiobook
bookStatus: lendo / lido / abandonado
```

#### Para Filmes/Séries

```yaml
showRuntime: 148 min
showDirector: [[Christopher Nolan]]
showPlatform: Netflix
showSeasons: 4
```

#### Para Podcasts

```yaml
podcastHost: [[Nome do Host]]
podcastEpisode: 42
podcastDuration: 1h 23min
```

---

## Notas de Saída (Outputs)

### O Desafio da Complexidade

Outputs são particularmente complexos de organizar porque envolvem:

- **Múltiplos estados** (rascunho, revisão, publicado, arquivado)
- **Diferentes mídias** (vídeo, texto, áudio, visual)
- **Vários canais** (YouTube, blog, newsletter, redes sociais)
- **Processos iterativos** (versões, edições, atualizações)

### Sistema de Classificação Recomendado

#### `outputMedium` — Canal de Publicação

O meio/plataforma onde o conteúdo será ou foi publicado:

**Exemplos:**

- YouTube
- Newsletter
- Blog
- LinkedIn
- Twitter/X
- Podcast
- Instagram
- TikTok
- Medium

```yaml
outputMedium: YouTube
```

#### `outputMediumStatus` — Estado do Conteúdo

O status atual do output naquele canal específico:

**Estados sugeridos:**

- `ideia` — Conceito inicial, ainda não desenvolvido
- `rascunho` — Em processo de criação
- `revisão` — Pronto para revisão/edição
- `agendado` — Finalizado, aguardando publicação
- `publicado` — Ao vivo e acessível
- `atualizado` — Publicado e posteriormente atualizado
- `arquivado` — Removido ou descontinuado

```yaml
outputMediumStatus: publicado
```

### Exemplo Completo: Vídeo do YouTube

```yaml
outputType: vídeo
outputMedium: YouTube
outputMediumStatus: publicado
outputTitle: "Como Organizar Notas com o Sistema Zettelkasten"
outputDate: 2024-10-20
outputURL: https://youtube.com/watch?v=exemplo
outputViews: 15420
outputDuration: 18min
outputTags:
  - produtividade
  - zettelkasten
  - pkm
outputRelated:
  - [[Artigo sobre Zettelkasten]]
  - [[Thread no Twitter]]
```

### Estratégia Anti-Redundância

> **Problema:** É tentador criar propriedades infinitas para cada combinação de meio e estado.

**❌ Evite:**

```yaml
# NÃO faça isso - redundância explosiva
youtubeStatus: publicado
blogStatus: rascunho
newsletterStatus: agendado
twitterStatus: ideia
```

**✅ Faça:**

```yaml
# Uma nota por output, múltiplas propriedades simples
outputMedium: YouTube
outputMediumStatus: publicado

# Se republica em outro canal, crie nota relacionada ou adicione
outputRepurposed:
  - medium: Blog
    status: rascunho
    link: [[Post no Blog sobre Zettelkasten]]
```

### Campos Adicionais Úteis

#### Métricas e Performance

```yaml
outputViews: 15420
outputEngagement: 8.5%
outputShares: 234
```

#### Planejamento e Processo

```yaml
outputDeadline: 2024-11-01
outputCollaborators:
  - [[Maria Designer]]
  - [[João Editor]]
outputVersion: 2.1
```

#### Contexto e Relacionamento

```yaml
outputSeries: "Série PKM Avançado"
outputEpisode: 3
outputPrevious: [[Vídeo 02 - Links Inteligentes]]
outputNext: [[Vídeo 04 - Mapas de Conteúdo]]
```

---

## Princípios Gerais para Todos os Padrões

### 1. Comece Simples

Adicione complexidade apenas quando houver necessidade comprovada.

### 2. Mantenha Consistência

Escolha um padrão de nomenclatura e siga-o rigorosamente.

### 3. Documente Decisões

Mantenha uma nota de referência explicando suas convenções.

### 4. Revise Periodicamente

Sistemas evoluem. Revise e ajuste padrões a cada 3-6 meses.

### 5. Menos Propriedades, Mais Conexões

Prefira links e associações orgânicas a campos estruturados excessivos.

---

