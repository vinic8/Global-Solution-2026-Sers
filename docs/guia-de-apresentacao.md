# ÓRION-7 — Guia de Apresentação do Projeto
### Sistema Inteligente de Monitoramento Energético para Missão Espacial Experimental

---

## 1. O que é o painel ÓRION-7

O ÓRION-7 é uma central de controle de missão (um *dashboard*) que monitora, interpreta e responde, em tempo real, às condições energéticas de uma missão espacial experimental. Ele recebe dados simulados de telemetria — geração e consumo de energia, temperatura, comunicação e o estado de cada módulo da nave — e os transforma em informação clara, com alertas automáticos e decisões tomadas pelo próprio sistema diante de situações críticas.

O tema do desafio é **energias renováveis e sustentabilidade**, e isso está no coração do projeto: a fonte de energia principal da nave são painéis solares (energia renovável), a energia é medida em potência (kW) e armazenada em baterias (kWh), e o painel calcula um índice que mede o quão sustentável a operação está em cada instante.

Tudo roda em uma única página, feita em **HTML, CSS e JavaScript puro**, sem depender de bibliotecas externas — inclusive os gráficos, que são desenhados manualmente. Isso mostra domínio de programação, algoritmos, pensamento computacional e inteligência artificial introdutória aplicados a um problema real da indústria espacial moderna.

---

## 2. As funcionalidades do painel

**Cabeçalho e status global.** No topo ficam o Tempo de Missão (MET — um cronômetro T+dias:horas:minutos:segundos), o horário UTC e um selo de Status Global que resume o estado da nave como NOMINAL, ATENÇÃO ou CRÍTICO. Esse selo é calculado automaticamente a partir do pior status entre todos os módulos.

**Indicadores principais (KPIs).** Quatro cartões de destaque mostram os números mais importantes: a Geração solar (kW), o Consumo total (kW), a Carga do banco de baterias (%) e o Índice de Sustentabilidade (0–100). Cada cartão traz um mini-gráfico de tendência e uma seta indicando se o valor está subindo, caindo ou estável.

**Gráfico de balanço de potência.** Um gráfico de linha em tempo real compara, lado a lado, a energia gerada pelos painéis (verde), o consumo da nave (âmbar) e a carga da bateria (azul). É a forma mais direta de enxergar se a missão está gerando mais energia do que gasta.

**Status dos módulos operacionais.** Seis cartões acompanham os módulos da operação — Painéis Solares, Banco de Baterias, Suporte de Vida, Comunicação, Propulsão e Controle Térmico. Cada um exibe seu estado (verde/âmbar/vermelho), duas métricas-chave e uma barra de nível, deixando claro qual módulo precisa de atenção.

**Índice de sustentabilidade e fontes de energia.** Um medidor circular mostra o índice geral, detalhado em três fatores: percentual de energia renovável, reserva das baterias e eficiência dos painéis. Logo abaixo, uma barra mostra de onde a energia está vindo neste exato momento — quanto vem do Sol e quanto vem das baterias.

**Vitais da nave.** Aqui acompanhamos a Comunicação (intensidade do sinal com a Terra e a latência em milissegundos) e a Temperatura da cabine (em um termômetro com faixa de cor).

**Central de Alertas.** Um feed que registra automaticamente os eventos críticos, classificados por gravidade (crítico, atenção, informação, recuperação), com módulo de origem e horário. Ele atualiza sem "piscar" e congela quando você passa o mouse, para conseguir ler com calma.

**Decisões Automatizadas (IA).** Um segundo feed mostra as respostas que o sistema toma sozinho diante de cada situação — é a parte de inteligência artificial introdutória do projeto.

**Console do Operador.** A ferramenta de demonstração: permite *injetar dados* manualmente para forçar respostas e ver o sistema funcionando. Tem barras deslizantes para temperatura, sinal, geração, consumo e bateria; botões de cenários de anomalia (superaquecimento, perda de sinal, eclipse, pico de consumo, tempestade solar, esvaziar bateria); botões para forçar a falha de cada módulo; um botão para restaurar tudo ao normal; e a opção de pausar as anomalias automáticas. Ao clicar em qualquer ação, a barra correspondente se move para mostrar exatamente o que mudou.

---

## 3. Como o painel atende cada requisito técnico

**Requisito 1 — Monitoramento de dados simulados (receber, interpretar e exibir).**
O motor de simulação gera continuamente dados de temperatura, comunicação, energia e status dos módulos. O painel *recebe* esses dados, *interpreta* (classificando cada valor em normal, atenção ou crítico por meio de limiares e calculando o índice de sustentabilidade) e *exibe* tudo nos KPIs, no gráfico, nos cartões de módulo e nos vitais. O Console do Operador reforça esse requisito ao permitir inserir dados manualmente e ver o ciclo completo de recebimento e interpretação.

**Requisito 2 — Geração de alertas.**
A Central de Alertas dispara avisos automaticamente sempre que uma condição cruza um limite crítico (bateria baixa, superaquecimento, sinal fraco, geração insuficiente). Os alertas só são gerados na *mudança* de gravidade, evitando repetição, e indicam claramente o módulo afetado e o horário.

**Requisito 3 — Tomada de decisão básica.**
O motor de decisão usa estruturas lógicas (condições, histerese, cooldowns) para responder sozinho às situações críticas e registra cada ação no feed de Decisões. Exemplos: ativar o modo de economia de energia quando a bateria fica baixa e restaurá-lo quando recupera; rotear o excedente solar para carregar as baterias; acionar a refrigeração quando a cabine passa de 32 °C e desligá-la quando baixa de 27 °C (uma vez cada, com histerese); realinhar a antena quando o sinal cai; e reduzir a exposição dos painéis quando superaquecem.

**Requisito 4 — Visualização dos dados.**
A informação é apresentada de forma organizada e hierárquica: os números mais importantes em destaque, o gráfico para enxergar tendências, os cartões para o estado de cada módulo e um código de cores consistente (verde = nominal, âmbar = atenção, vermelho = crítico) que comunica o estado num relance.

---

## 4. Como o painel atende cada critério de avaliação

**Técnica (60 pontos).**
A implementação é robusta e o código é organizado em seções comentadas e separadas por função (configuração, estado, simulação, alertas, motor de decisão, renderização, gráficos). Os alertas são claros e classificados por gravidade. Os gráficos são desenhados do zero, sem bibliotecas, o que demonstra domínio real de algoritmos e da lógica de renderização.

**Inovação (30 pontos).**
Os destaques são o Console do Operador (injeção de dados para testar o sistema em tempo real), o motor de decisão automatizado que age sozinho como uma IA introdutória (com destaque para o termostato inteligente de histerese e o modo de economia de energia) e o índice de sustentabilidade composto, que traduz vários dados em um único número de impacto.

**Usabilidade (10 pontos).**
O painel é autoexplicativo: código de cores intuitivo, rótulos em português, o resumo de status global, os feeds que pausam ao passar o mouse para facilitar a leitura e as barras do console que respondem visualmente a cada ação. O layout também se adapta a telas menores.

**Apresentação.**
O Console transforma o painel em uma demonstração ao vivo — dá para provocar uma situação crítica e mostrar, na hora, o alerta e a decisão automática acontecendo. As etiquetas no rodapé (Energia, Potência, Energias Renováveis, Sustentabilidade) reforçam, de forma objetiva, os conceitos aplicados.

---

## 5. Roteiro de Vídeo — 3 minutos

> **Dica de gravação:** fale em ritmo calmo e deixe pequenas pausas durante a demonstração (cliques e alertas aparecendo) — elas ajudam a preencher o tempo naturalmente. Tenha o painel já aberto e em "Operação Automática" antes de começar.

---

**[0:00 – 0:20] Abertura**
🎬 *Tela: painel completo, telemetria rodando.*
🎙 "Em uma missão espacial, a energia é literalmente questão de sobrevivência. Um único módulo sem controle pode comprometer toda a operação. Foi pensando nisso que desenvolvemos o ÓRION-7: um sistema inteligente que monitora, interpreta e responde, em tempo real, às condições energéticas de uma missão experimental."

**[0:20 – 0:45] Visão geral**
🎬 *Tela: apontar para o topo e os quatro indicadores.*
🎙 "Esta é a central de controle do ÓRION-7. No topo, o tempo de missão e o status global da nave. Logo abaixo, os indicadores principais: a geração de energia solar, o consumo total, a carga das baterias e o índice de sustentabilidade — todos atualizando automaticamente a cada segundo."

**[0:45 – 1:25] Monitoramento dos dados**
🎬 *Tela: gráfico de potência → cartões dos módulos → vitais.*
🎙 "No centro, o gráfico de balanço de potência mostra, lado a lado, quanta energia os painéis solares geram e quanto a nave consome. Ao lado, acompanhamos os seis módulos operacionais — painéis, baterias, suporte de vida, comunicação, propulsão e controle térmico — cada um com seu status colorido. E nos vitais da nave monitoramos a temperatura da cabine e a qualidade do sinal de comunicação com a Terra."

**[1:25 – 2:20] Demonstração ao vivo: alertas e decisão automática**
🎬 *Tela: Console do Operador. Clicar em "🔥 Superaquecimento" e mostrar o painel reagindo.*
🎙 "Mas o grande diferencial está aqui: o Console do Operador. Com ele, conseguimos injetar dados e simular situações críticas para ver o sistema reagir. Vou simular um superaquecimento na cabine."
*(clica e aguarda 2–3 segundos)*
🎙 "Veja o que acontece: a temperatura dispara, o módulo térmico fica vermelho e um alerta crítico é gerado na hora. E o mais importante — o sistema decide sozinho: o termostato inteligente aciona a refrigeração automaticamente, e essa decisão fica registrada no painel da IA. É monitoramento inteligente de verdade: ele não só mostra o problema, ele responde."

**[2:20 – 2:45] Sustentabilidade**
🎬 *Tela: medidor de sustentabilidade e a barra de fontes de energia.*
🎙 "Como o tema do desafio é energia renovável e sustentabilidade, o painel calcula um índice de sustentabilidade que combina o uso de energia solar, a reserva das baterias e a eficiência dos painéis. Quanto mais a missão se apoia em energia limpa, maior o índice — e o sistema ainda roteia o excedente solar para carregar as baterias."

**[2:45 – 3:00] Fechamento**
🎬 *Tela: voltar para a visão geral do painel.*
🎙 "O ÓRION-7 une programação, lógica e inteligência artificial para tornar uma missão mais segura, eficiente e sustentável. Ele recebe, interpreta, alerta e decide — tudo em tempo real. Essa é a nossa solução. Obrigado!"

---

### Resumo de uma frase (para abrir ou fechar a apresentação)
*"ÓRION-7: o sistema que vê, entende e age para manter uma missão espacial energeticamente segura e sustentável."*
