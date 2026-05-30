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
