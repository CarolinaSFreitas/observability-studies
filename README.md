# 👀 Observability Studies

Repository to centralize my studies on [Zabbix](./Zabbix/), [Grafana](./Grafana/), [Datadog](./Datadog/) and [Dynatrace](./Dynatrace/).

## SLA, SLI e SLO

- **SLA (Service Level Agreement)**
Acordo de Nível de Serviço é um contrato formal entre um provedor de serviço e o cliente que define o nível esperado de serviço. O SLA especifica os requisitos de desempenho e disponibilidade do serviço, bem como as penalidades ou compensações caso o provedor não cumpra esses requisitos. É essencialmente um compromisso público sobre a qualidade do serviço.

- **SLI (Service Level Indicator)**
Indicador de Nível de Serviço é uma métrica específica usada para medir um aspecto do serviço, como a latência, a taxa de erro ou a disponibilidade. Os SLIs são utilizados para monitorar e avaliar o desempenho do serviço em relação aos SLOs e SLAs. Por exemplo, a porcentagem de solicitações HTTP que retornam uma resposta com sucesso dentro de um determinado tempo é um SLI.

- **SLO (Service Level Objective)**
Objetivo de Nível de Serviço é uma meta interna de desempenho que um provedor de serviço define para guiar suas operações e garantir que os SLAs sejam cumpridos. Os SLOs são específicos e mensuráveis, baseando-se nos SLIs para estabelecer metas realistas e atingíveis. Por exemplo, um SLO pode ser que 99,9% das solicitações sejam processadas em menos de 500 ms.

#### Resumo:
**SLI:** Métrica que mede aspectos específicos do serviço (indicador).
**SLO:** Meta interna baseada em SLIs, usada para guiar operações (objetivo).
**SLA:** Contrato formal com o cliente que define expectativas de serviço (acordo).
Em termos de observabilidade, esses conceitos são essenciais para garantir que os sistemas estejam operando dentro dos parâmetros esperados e para identificar rapidamente quando algo não está conforme, permitindo ações corretivas eficazes.

SLI: O que você está medindo?
SLO: Quão bom tem que ser?
SLA: SLO + O que acontece caso não entregue o acordado? 
Error Budget: Equilíbrio entre inovação e estabilidade 

#### Notas: 
- Ferramentas de monitoramento e gerenciamento de desempenho de aplicações (APM, na sigla em inglês).
- Monitoramento de experiência digital (DEM)
