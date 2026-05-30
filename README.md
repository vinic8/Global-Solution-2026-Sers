# ÓRION-7 — Painel de Controle de Missão

> Sistema inteligente de monitoramento energético para uma missão espacial experimental.
> **Desafio:** Soluções em Energias Renováveis e Sustentáveis.

---

## Sobre o projeto

O **ÓRION-7** é uma central de controle de missão que **recebe, interpreta e exibe** dados simulados das condições operacionais de uma nave — temperatura, comunicação, energia e status dos módulos — **gera alertas automáticos** diante de condições críticas e **toma decisões sozinho** (inteligência artificial introdutória) para manter a operação segura, eficiente e sustentável.

O tema central são **energias renováveis e sustentabilidade**: a fonte principal da nave são painéis solares, a energia é medida em potência (kW) e armazenada em baterias (kWh), e o sistema calcula um **índice de sustentabilidade** em tempo real.

## Funcionalidades

- **Monitoramento em tempo real** de geração e consumo de energia, carga das baterias, temperatura, comunicação e status de 6 módulos operacionais.
- **Gráfico de balanço de potência** (geração × consumo × bateria) desenhado do zero, sem bibliotecas.
- **Central de Alertas** automáticos, classificados por gravidade.
- **Decisões Automatizadas (IA)** — motor de regras que reage às situações críticas (modo de economia de energia, termostato com histerese, realinhamento de antena, carga solar, etc.).
- **Índice de Sustentabilidade** que combina uso de energia renovável, reserva das baterias e eficiência dos painéis.
- **Console do Operador** para injetar dados e simular anomalias, demonstrando o sistema ao vivo.

## Como atende ao desafio

| Requisito técnico | Como é atendido |
| --- | --- |
| Monitoramento de dados simulados | Telemetria recebida, interpretada por limiares e exibida em KPIs, gráfico, cartões e vitais |
| Geração de alertas | Central de Alertas automática (dispara na mudança de gravidade) |
| Tomada de decisão básica | Motor de decisão com respostas automatizadas registradas no feed da IA |
| Visualização dos dados | Layout organizado e código de cores (verde / âmbar / vermelho) |

 Explicação detalhada e roteiro de apresentação em [`docs/guia-de-apresentacao.md`](docs/guia-de-apresentacao.md).

##  Tecnologias

- **HTML5, CSS3 e JavaScript (Vanilla)** — sem frameworks nem bibliotecas externas
- Gráficos renderizados manualmente em `<canvas>`
- Aplicação **autossuficiente em um único arquivo**, funciona offline

##  Como executar

**Localmente:** baixe ou clone o repositório e abra o arquivo `index.html` no navegador.

```bash
git clone https://github.com/SEU-USUARIO/orion-7.git
cd orion-7
# abra index.html no navegador
```

**Online:** acesse o link da demonstração ao vivo.

##  Estrutura do repositório

```
orion-7/
├── index.html          # O painel completo 
├── README.md           # Este arquivo
├── LICENSE             # Licença do projeto
├── .gitignore
└── docs/
    ├── guia-de-apresentacao.md   # Explicação + roteiro de vídeo
    └── screenshot.png            # Imagem do painel 
```

## Equipe

- Nome do(a) integrante 1
- Nome do(a) integrante 2

Projeto desenvolvido para o desafio *Soluções em Energias Renováveis e Sustentáveis*.

## Licença

Distribuído sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
