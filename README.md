# EcoTrack - Rastreador de Consumo de Energia Inteligente

Este repositório foi criado para hospedar e documentar o **Trabalho Final da disciplina de Interação Humano-Computador (IHC)**. 
O projeto consiste em uma proposta de solução interativa focada em **Interação Humano-Dados (IHD)**, desenvolvida sob os princípios de **Lean UX** e **SPEC-Driven Development**, com o objetivo de traduzir dados complexos de consumo elétrico para usuários leigos.

---

## Protótipo Interativo

O protótipo de alta fidelidade, totalmente navegável e com simulação de fluxos reais, foi desenvolvido utilizando o **Figma**.

 **[CLIQUE AQUI PARA ACESSAR O PROTÓTIPO INTERATIVO NO FIGMA](https://www.figma.com/make/ycHauyXsk7yLm3Gv2k38T5/Eco-Friendly-Electricity-Tracker?fullscreen=1&t=WiJvP4IpOj7qNcBI-1&code-node-id=0-9)**

---

## Funcionalidades Projetadas (SPEC-Driven)

Alinhado rigorosamente com o documento de especificação (SPEC) do grupo, o protótipo engloba:
1. **Tela de Login Acessível:** Autenticação limpa com validações visuais e login social.
2. **Dashboard de Consumo:** Exibição clara em Reais (R$) e kWh com filtros temporais interativos (Diário, Mensal, Anual) e gráficos de barras de leitura imediata.
3. **Calculadora Guia (Wizard Pattern):** Fluxo passo a passo para usuários leigos estimarem o gasto mensal real de eletrodomésticos específicos (Ar-condicionado, Chuveiro, Geladeira, etc.).
4. **Personalização de Watts:** Opção avançada e contextualizada para usuários que conhecem a potência exata de seus aparelhos ajustarem o cálculo.
5. **Painel de Impacto Ecológico:** Tradução de métricas técnicas em metáforas do mundo real (ex: equivalência em árvores salvas ou emissão de CO₂ evitada).

---

## Engenharia de Prompts (Uso de IA Generativa)

Em total conformidade com as diretrizes de avaliação do projeto, documentamos abaixo todos os prompts de comando e instruções exatas utilizadas no suporte à criação e estruturação das interfaces através de Inteligência Artificial:

### Prompt 1: Estruturação Inicial das Telas (Inglês)
> *Utilizado para a geração do esqueleto e componentes base das primeiras 3 telas estruturais no motor de design.*
```text
A website design for an eco-friendly Electricity Consumption Tracker tailored for non-technical users. Clean, modern, and accessible UI based on Material Design 3 principles. Friendly color palette using shades of soft green, energy yellow, and clean white. High contrast and highly readable typography. The app contains 3 screens: 1. Dashboard Screen: Main overview showing current electricity bill prominently in BRL (R$) and kWh. A clear segmented control button/tab to filter consumption data by Day, Month, and Year. Simple, easy-to-read bar chart showing consumption trends. Warning cards for high peak hours. 2. Wizard Calculator Screen: A step-by-step interactive form (Wizard design pattern) to calculate appliance energy costs. Includes a grid layout to select a household appliance (e.g., Air Conditioner, Refrigerator, Shower), a smooth slider component to input daily usage hours, and a prominent real-time card showing the estimated monthly cost in BRL (R$). 3. Energy Saving & Eco Impact Screen: Educational cards with quick tips on how to save power. A dedicated section highlighting the environmental impact, showing carbon footprint reduction (CO2 avoided) in a visual, rewarding, and encouraging format. Include a consistent Bottom Navigation Bar across all screens for easy access.
```
### Prompt 2: Refinamento de Usabilidade, Internacionalização e Customização de Componentes de IHD
> *Utilizado para refinar a usabilidade do usuário e traduzir o website.*
```text
Realize o refinamento de alta fidelidade das interfaces do aplicativo sob as diretrizes do Material Design 3, aplicando as seguintes atualizações estruturais e de interação:

Internacionalização e Localização (L10n): Traduza integralmente todos os textos, rótulos (labels) e componentes da interface para o idioma Português do Brasil (pt-BR).

Redução de Carga Cognitiva no Dashboard: Adicione um componente de Tooltip descritivo e informativo. Esse texto explicativo deve ser disparado via gatilho de interação (Hover / passar o ponteiro do mouse) sobre o ícone de informação posicionado dentro do card/retângulo verde principal.

Explicabilidade na Visualização de Dados: Inclua uma legenda clara e de alto contraste no gráfico de consumo, permitindo a imediata identificação e interpretação das variáveis apresentadas.

Flexibilidade e Controle do Usuário (Gráfico Adaptável): Transforme o gráfico de consumo em um componente dinâmico e interativo. O fluxo deve permitir que o usuário gerencie os dados exibidos, adicionando novos eletrodomésticos e customizando a métrica de uso diário individual através de parâmetros de tempo configuráveis em minutos ou horas.
```
### Prompt 3: Modelagem de Parâmetros Temporais Intermitentes para Refinamento de Gráficos de IHD
> *Utilizado para aplicar o princípio de fidelidade de dados e controle do usuário.*
```text
Aperfeiçoe o fluxo interativo e os componentes da calculadora guia (Wizard design pattern), adicionando suporte para cenários de consumo intermitente e não diário dos eletrodomésticos:

Seleção de Frequência Semanal/Mensal: Insira um componente de controle (como seletores de dias ou campos de entrada numéricos) que permita ao usuário definir com exatidão em quantos dias da semana ou do mês aquele eletrodoméstico específico é utilizado de fato.

Modularização do Tempo de Uso Pragmático: Vincule à seleção de dias uma entrada de tempo dinâmica (em minutos ou horas) para especificar a quantidade de uso realizada apenas nos dias selecionados, substituindo a média diária linear fixa.

Atualização Dinâmica do Gráfico de IHD: Garanta que esses novos parâmetros de intermitência recalculem instantaneamente a projeção de consumo, gerando uma curva gráfica mais realista, fidedigna e livre de margens de erro causadas por aparelhos de uso esporádico.
```
### Prompt 4: Expansão de Recursos e Componentes Funcionais
> *Utilizado para detalhar o comportamento interativo, novos eletrodomésticos, a lógica de personalização de Watts e a tela de histórico comparativo.*
```text
Crie a expansão de interface mobile para um aplicativo de rastreamento de consumo de energia elétrica, focado em alta usabilidade (Material Design 3). As telas precisam ser estruturadas de forma funcional com os seguintes componentes e fluxos:

Tela de Login Acessível: Layout limpo com campos de input para e-mail e senha com feedback visual de validação. Incluir botão de login destacado, link para "esqueci a senha" e opção de login social rápido (Google/Apple).

Fluxo do Histórico de Consumo Avançado: Uma tela dedicada que exibe um gráfico de barras comparativo. O usuário deve visualizar filtros interativos de "Mês Atual vs. Meses Anteriores", com uma lista detalhada abaixo mostrando os dias de maior pico de gasto e insights de texto simples traduzindo os dados (ex: "Você gastou 15% a menos que o mês passado").

Calculadora Guia (Wizard) com Mais Eletrodomésticos: Uma listagem expandida em formato de grade (grid) ou lista com ícones modernos para: Ar-condicionado, Geladeira, Chuveiro Elétrico, Máquina de Lavar, Computador, Televisão e Micro-ondas. O fluxo deve permitir selecionar múltiplos aparelhos para o cálculo.

Seção de Personalização de Potência (Watts): Dentro do fluxo da calculadora, ao selecionar um eletrodoméstico, deve abrir um modal ou campo de entrada numérico interativo onde o usuário possa digitar ou ajustar os Watts exatos do seu aparelho (caso ele saiba), com um texto de ajuda explicando a média padrão daquele eletrodoméstico para usuários leigos.

Painel de Informações Ambientais Expandido: Tela com cards educativos e ilustrativos sobre pegada de carbono. Deve conter dados interativos que convertem o consumo de kWh do usuário em equivalentes ecológicos fáceis de entender (ex: "Sua economia este mês equivale a 3 árvores plantadas" ou "X kg de CO2 evitados").

Mantenha uma barra de navegação inferior (Bottom Navigation Bar) fixa para alternar entre as abas de Dashboard, Histórico, Calculadora e Impacto Ambiental.
