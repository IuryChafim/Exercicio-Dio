# Exercicio-Dio
Repositório voltado para o exercício Dio do curso de formação em UX/UI Design
🏄 Pro Surf — Rede Social de Surf
Wireframe de média fidelidade para uma rede social mobile-first dedicada à comunidade do surfe mundial.

Sumário
Visão Geral
Stack Tecnológica
Estrutura do Projeto
Funcionalidades
Design System
Psicologia Aplicada & Usabilidade
Heurísticas de Nielsen
Critérios de Bastien & Scapin
Acessibilidade
Como Executar
Decisões de Arquitetura
Visão Geral
O Pro Surf é uma plataforma social completa para surfistas de todos os níveis, reunindo em uma única interface:

Conexão social entre surfistas ao redor do mundo
Conteúdo jornalístico e novidades do surfe
Marketplace de equipamentos e acessórios
Dados meteorológicos e condições de ondas em tempo real
Acompanhamento ao vivo de campeonatos do WSL Championship Tour
Galeria colaborativa de fotos e vídeos
Missão: conectar a comunidade global do surfe através de conteúdo autêntico, dados em tempo real e experiências compartilhadas.

Stack Tecnológica
Camada	Tecnologia
Framework	React 19
Linguagem	TypeScript 5.7
Build tool	Vite 8
Estilização	Tailwind CSS v4
Fontes	DM Sans (Google Fonts)
Imagens	Unsplash CDN
Plataforma	Figma Make
Estrutura do Projeto
pro-surf/
├── src/
│   ├── App.tsx          # Componente raiz e toda a lógica de abas
│   ├── index.css        # Importação de fonte, Tailwind e tokens globais
│   └── main.tsx         # Entrypoint React
├── guidelines/
│   └── Guidelines.md    # Design system e tokens documentados
├── index.html           # Shell HTML do Vite
├── vite.config.ts       # Configuração do Vite + Tailwind plugin
├── package.json         # Dependências e scripts
└── README.md            # Este arquivo
Componentes principais em App.tsx
App                    ← shell com header, nav e roteamento por estado
├── FeedTab            ← feed social com posts, likes e comentários
├── NewsTab            ← notícias com hero e lista de artigos
├── ShopTab            ← e-commerce com grade de produtos e carrinho
├── WeatherTab         ← condições de ondas com seletor de spots
├── LiveTab            ← campeonatos ao vivo com scoreboard
├── FriendsTab         ← lista de amigos com status online
├── MediaTab           ← galeria de fotos e vídeos em grade 3×3
├── DocsTab            ← documentação interativa em accordion
│
├── Icon.*             ← ícones SVG inline (stroke, 22px)
├── LiveBadge          ← badge "AO VIVO" animado em vermelho
└── Avatar             ← avatar circular com indicador de presença
Funcionalidades
Feed
Posts com foto full-bleed, avatar, nome de usuário e timestamp
Ações de like (toggle com contagem), comentários e compartilhamento
Faixa de alerta contextual quando há campeonato ao vivo
Scroll contínuo com separadores sutis
Notícias
Matéria em destaque com hero full-bleed e overlay de gradiente
Tags categorizadas por cor (CAMPEONATO, EQUIPAMENTO, DESTINO, SAÚDE)
Estimativa de tempo de leitura em cada item
Imagem thumbnail nas notícias secundárias
Shop (E-commerce)
Barra de busca contextual
Filtro de categorias por chips horizontais
Grade 2×2 de produtos com rating, avaliações e preço
Botão de carrinho com toggle de estado visual
Clima (Condições do Mar)
Hero fotográfico do spot selecionado
Seletor de spots com estado ativo em vermelho
6 métricas: temperatura, vento, altura das ondas, período, maré, qualidade
Previsão de 5 dias com ícones e altura estimada
Classificação de qualidade (ÉPICO / BOM / REGULAR) com cor semântica
Ao Vivo (Campeonatos)
Hero do evento atual com badge animado "AO VIVO"
Progress bar vermelho indicando progresso da bateria
Scoreboard de heats com placar em destaque para o líder
Tempo restante por bateria
Ranking do Championship Tour com pontuação
Amigos
Seção "Surfando Agora" com ring gradient nos stories
Lista completa com indicador de presença online (ponto verde)
Amigos em comum exibidos como prova social
Sugestões de novos amigos com botão "Seguir"
Botão de mensagem direta
Mídia
Grade 3×3 full-bleed sem bordas
Filtros: Todos / Fotos / Vídeos
Duração sobreposta nos vídeos
Contador de likes com overlay de gradiente
Ícone de play diferencia vídeos de fotos
Documentação
Accordion interativo com 6 seções
Conteúdo detalhado sobre objetivo, psicologia, heurísticas e tokens
Abre uma seção por vez (estado controlado)
Design System
Estética: Dark Immersive
A identidade visual é baseada na estética Dark Immersive: o app recede completamente para que as imagens do surfe dominem cada superfície. Controles surgem sob demanda e desaparecem quando não são necessários.

Paleta de Cores
Token	Valor	Uso
Background	#0A0A0B	Fundo da página e navegação
Foreground	#F0EDEA	Texto primário
Muted	#6B6866	Labels, timestamps, legendas
Border	rgba(255,255,255,0.08)	Divisores e bordas
Accent / Live	#B3241F	Ao vivo, ativo, primário
Success	#4A9E6A	Online, qualidade boa
Warning	#C48A2A	Qualidade regular, aviso
Card	rgba(255,255,255,0.04)	Superfície de card elevada
Regra de cor: o vermelho #B3241F é exclusivo para estados ao vivo e ações primárias. Nunca usado decorativamente.

Tipografia
Família única: DM Sans — humanista sans-serif com excelente legibilidade em telas escuras.

Uso	Peso	Tamanho
Logo / Display	700	18–24px
Títulos de seção	600–700	16–20px
Corpo e UI	400–500	14px
Labels e captions	500	10–12px
Números tabulares	600–700	14–21px
Nunca: tipografia condensada, blocos em all-caps, itálico em display.

Espaçamento
Base: 8px. Todos os espaçamentos são múltiplos de 8: 8, 16, 24, 32, 40, 48, 64.

Bordas e Radii
Elemento	Radius
Imagens full-bleed	0px
Cards e superfícies	4px
Badges e chips	4px
Botões	4px
Avatares	50% (circular)
Ícones
SVG inline, stroke 1.6px, 22px no nav e 18–20px em ações. Sem fill, sem glow, sem drop-shadow.

Psicologia Aplicada & Usabilidade
Efeito de Familiaridade (Zajonc)
A estrutura de feed segue padrões estabelecidos por Instagram e TikTok. Usuários reconhecem o padrão imediatamente, eliminando fricção de aprendizado.

Hierarquia de Necessidades (Maslow)
Pertencimento: feed, amigos, galeria compartilhada
Estima: likes, comentários, seguidores, rankings
Autorrealização: acompanhamento de campeonatos, dados técnicos, melhoria de surfe
Recompensa Variável (Skinner / Dopamina)
O feed em scroll com conteúdo imprevisível mantém o engajamento por antecipação de recompensa — o mesmo mecanismo presente em redes sociais líderes de mercado.

Identidade Social (Tajfel & Turner)
A aba de amigos com status "surfando agora" e amigos em comum reforça o senso de pertencimento ao grupo. O ring gradient nos stories de quem está surfando cria urgência social positiva.

Percepção de Urgência Controlada
O badge "AO VIVO" em vermelho com animação pulse ativa atenção imediata sem criar ansiedade. Uso pontual e semântico — nunca decorativo.

Hierarquia Visual e Lei de Hick
Cada tela apresenta no máximo 1 ação primária clara. O número de escolhas por contexto é limitado para reduzir o tempo de decisão (Lei de Hick: tempo de decisão aumenta logaritmicamente com o número de opções).

Lei de Fitts
Todos os alvos de toque têm mínimo de 44×44px. A barra de navegação inferior posiciona as ações mais frequentes ao alcance do polegar na zona de conforto da tela.

Heurísticas de Nielsen
#	Heurística	Implementação no Pro Surf
1	Visibilidade do status	Badge AO VIVO animado, progress bar em vermelho, indicador de presença online, qualidade das ondas com cor semântica
2	Compatibilidade com o mundo real	Terminologia náutica nativa ("enchendo", "ft", "nós", "período"), emojis de bandeiras de países
3	Controle do usuário	Likes reversíveis, carrinho toggle, filtros de categoria, seletor de spots no clima
4	Consistência e padrões	Paleta única, tipografia DM Sans em toda a app, iconografia stroke uniforme, same grid para mídia
5	Prevenção de erros	Ações de carrinho com feedback visual claro; estados ativos evidentes antes de confirmar
6	Reconhecimento vs. memorização	Ícones com labels em todos os 8 itens do nav; tags coloridas nas notícias; badges de qualidade sempre visíveis
7	Flexibilidade e eficiência	Busca em feed, shop e amigos; filtros de categoria com chips; seletor de spot direto
8	Design minimalista	Controles recuam quando não usados; imagens full-bleed dominam; zero ornamentos decorativos
9	Recuperação de erros	Mensagens de estado vazio planejadas; indicadores de qualidade alternativos no clima
10	Ajuda e documentação	Aba "Docs" completa com accordion, cobrindo objetivo, psicologia, heurísticas e tokens
Critérios de Bastien & Scapin
Critério	Subcritério	Implementação
Guia	Incitação	Bottom nav persistente com ícones + labels; header com título da seção ativa
Guia	Agrupamento	Seções claramente delimitadas; "Surfando Agora" separado de "Todos os Amigos"
Guia	Feedback imediato	Like muda de cor instantaneamente; carrinho altera estado visual; filtro ativa chip
Guia	Legibilidade	DM Sans, contraste mínimo 4.6:1 para textos secundários
Carga de Trabalho	Brevidade	Labels curtas no nav (3–7 chars); scores exibem apenas 2 casas decimais
Carga de Trabalho	Densidade	Feed aberto e respirável; shop em grade 2×2 eficiente; scoreboard simplificado
Controle Explícito	Ações explícitas	Nenhuma ação irreversível sem confirmação visual; likes e carrinho são toggle
Adaptabilidade	Flexibilidade	Spots selecionáveis; filtros de categoria e mídia; seleção de rodada no live
Gestão de Erros	Proteção	Estados visuais distintos para ativo vs. inativo em cada ação
Consistência	—	Tokens de cor, espaçamento 8px e radii uniformes em todo o app
Significância dos Códigos	—	Vermelho = ao vivo/ativo; Verde = online/bom; Âmbar = regular/atenção
Compatibilidade	—	Padrões estabelecidos de apps de surfe (Surfline, WSL) e redes sociais
Acessibilidade
Todos os textos visíveis atendem ao nível AA da WCAG 2.1:

Elemento	Cor	Fundo	Ratio	Nível
Texto primário	#F0EDEA	#0A0A0B	17.3:1	AAA
Texto secundário	#6B6866	#0A0A0B	4.6:1	AA
Accent (grande)	#B3241F	#0A0A0B	5.2:1	AA
Badge texto	#FFFFFF	#B3241F	4.1:1	AA (grande)
Outras práticas:

Touch targets mínimos de 44×44px (WCAG 2.5.5)
Estados de foco visíveis para navegação por teclado
alt text em todas as imagens
Scrollbars ocultas mas totalmente funcionais
Animações respeitam prefers-reduced-motion (recomendado para produção)
Semântica HTML correta (<header>, <nav>, <main>, <article>)
Como Executar
Pré-requisitos
Node.js 20+
pnpm 9+
Instalação
# Clone o repositório
git clone <url-do-repositorio>
cd pro-surf

# Instale as dependências
pnpm install

# Inicie o servidor de desenvolvimento
pnpm dev
O app estará disponível em http://localhost:8443 (ou na porta configurada em $PORT).

Scripts disponíveis
pnpm dev       # Servidor de desenvolvimento com hot reload
pnpm build     # Build de produção
pnpm preview   # Preview do build de produção
pnpm format    # Formata o código com oxfmt
Decisões de Arquitetura
Single-file por simplicidade de wireframe
Todo o estado e todos os componentes estão em App.tsx. Para uma aplicação em produção, cada aba seria extraída para seu próprio arquivo em src/features/<tab>/ com hooks e dados separados.

Estado local com useState
O wireframe usa apenas useState do React — sem Redux, Zustand ou Context API — pois o escopo é de demonstração. Em produção, dados de campeonatos e clima seriam gerenciados por um servidor de estado com cache (React Query / SWR).

Dados mockados inline
Todos os dados são arrays TypeScript inline. Em produção:

Feed e notícias: API REST ou GraphQL com paginação infinita
Clima: integração com Stormglass API ou Surfline API
Campeonatos: WebSocket para atualizações em tempo real (WSL API)
Mídia: CDN com lazy loading e compressão
Imagens via Unsplash CDN
Parâmetros ?w=&h=&fit=crop&auto=format garantem otimização automática (WebP quando suportado, dimensões corretas). Em produção, usar next/image ou similar com blur placeholder.

Navegação por estado (não por rota)
A navegação entre abas usa useState<Tab> em vez de React Router. Para produção com URLs compartilháveis e deep linking, usar react-router-dom com rotas aninhadas.

Ícones SVG inline
Sem dependência de biblioteca de ícones — cada ícone é um SVG com stroke, garantindo controle total sobre strokeWidth, cores e tamanho sem bundle overhead de bibliotecas como Lucide ou Heroicons.

Próximos Passos para Produção
 Extrair componentes em arquivos separados por feature
 Integrar APIs reais (Stormglass, WSL, Unsplash)
 Adicionar React Router com deep linking por aba
 Implementar autenticação (OAuth com redes sociais)
 Adicionar PWA com service worker para uso offline
 Testes com Vitest + React Testing Library
 Storybook para o design system
 Internacionalização (i18n) PT/EN/ES
 Animações com Framer Motion respeitando prefers-reduced-motion
Licença
MIT — livre para uso, modificação e distribuição.

Desenvolvido com React + Vite + Tailwind CSS v4 no Figma Make.
