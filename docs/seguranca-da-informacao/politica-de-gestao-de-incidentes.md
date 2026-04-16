---
id: plano-de-gestao-de-incidentes
title: Política de Gestão de Incidentes
description: Documento oficial com diretrizes de seguranca da informacao da WeCare.
sidebar_position: 8
---

# Política de Gestão de Incidentes

> Status: Vigente  
> Versao: 1.0  
> Ultima atualizacao: Março de 2025  
> Responsavel: Seguranca da Informacao

# Propósito {#propósito}

Esta política tem como finalidade estabelecer diretrizes claras e estruturadas para a gestão de incidentes na WeCare, abrangendo eventos que afetem a segurança da informação, a continuidade das operações, a privacidade dos dados pessoais e o funcionamento de sistemas e serviços críticos.

Seu objetivo é garantir que todos os incidentes relevantes sejam prontamente identificados, classificados, tratados e registrados, promovendo a contenção de impactos, a rápida recuperação dos serviços e o aprendizado contínuo para prevenção de recorrências.

# Governança e Responsabilidade {#governança-e-responsabilidade}

A equipe de Segurança da Informação (Infosec) é responsável pela elaboração, manutenção e revisão periódica desta política, garantindo sua atualização constante e o alinhamento às melhores práticas e normas técnicas aplicáveis. Cabe ao CISO assegurar o cumprimento das diretrizes aqui estabelecidas e supervisionar as ações estratégicas relacionadas à gestão de incidentes.

A equipe técnica, sob a liderança do Tech Lead, é responsável por implementar e seguir rigorosamente as diretrizes desta política em todas as etapas operacionais, desde a identificação inicial até a recuperação e análise pós-incidente, garantindo uma atuação coordenada e eficaz diante de incidentes de segurança da informação.

# Conformidade Legal e Regulatória {#conformidade-legal-e-regulatória}

Esta política está alinhada aos requisitos da ISO/IEC 27001 e fundamenta-se nos princípios e processos definidos pela ISO/IEC 27035-1, que estabelece diretrizes para a prevenção, detecção, resposta e análise pós-incidente.

Além disso, a WeCare garante conformidade com a LGPD (Lei Geral de Proteção de Dados – Lei nº 13.709/2018), adotando medidas para notificação de titulares e autoridades competentes em casos de incidentes que envolvam dados pessoais, bem como com outras regulamentações e contratos aplicáveis aos serviços prestados.

# Público-alvo {#público-alvo}

Esta política se aplica a todos os colaboradores da WeCare, incluindo equipes internas, prestadores de serviço terceirizados e parceiros que atuem, direta ou indiretamente, na operação, suporte, segurança ou manutenção de sistemas, dados e infraestrutura tecnológica. Todos os envolvidos devem conhecer e cumprir as diretrizes estabelecidas neste documento no tratamento de incidentes de segurança da informação.

# Descrição da Política {#descrição-da-política}

### Partes Terceiras {#partes-terceiras}

Todos os fornecedores, parceiros ou terceiros que prestam serviços ou possuem acesso aos sistemas e informações da WeCare devem aderir a esta política. Caso um incidente seja identificado por parte dessas entidades, é obrigatória a comunicação imediata para o ponto de contato definido pela WeCare, detalhando a natureza, extensão e ações iniciais já tomadas.

### 

### Responsabilidades {#responsabilidades}

A WeCare atribui responsabilidades específicas para cada função envolvida na gestão de incidentes de segurança da informação. Essas responsabilidades asseguram a atuação eficiente, coordenada e estruturada em todas as etapas do processo, desde a identificação até a comunicação pós-incidente.

A definição das funções e suas respectivas responsabilidades é descrita abaixo:

* CISO (Chief Information Security Officer): Deve assegurar a governança e conformidade geral do processo de gestão de incidentes, estabelecendo e supervisionando a execução das políticas internas, alinhadas às melhores práticas e exigências regulatórias.  
* Tech Lead: Deve coordenar diretamente as atividades técnicas operacionais relacionadas aos incidentes, incluindo a validação inicial, o escalonamento adequado e a execução das ações técnicas de resposta e recuperação.  
* DPO (Data Protection Officer): Deve assegurar o cumprimento das obrigações legais relacionadas à proteção e privacidade dos dados pessoais envolvidos nos incidentes, conduzindo comunicações internas e externas necessárias conforme legislação vigente.  
* Colaboradores: Devem reportar imediatamente quaisquer suspeitas ou identificação de incidentes para a equipe responsável pela segurança da informação, colaborando diretamente para a rápida identificação, análise e contenção dos eventos.

### Treinamento e Conscientização {#treinamento-e-conscientização}

A WeCare deve promover treinamentos periódicos sobre gestão de incidentes de segurança da informação para todas as equipes envolvidas, com o objetivo de assegurar o entendimento prático dos papéis, responsabilidades e procedimentos definidos nesta política.

A responsabilidade pela organização, atualização e aplicação dos treinamentos é da equipe de Segurança da Informação (Infosec), que deve coordenar as ações em conjunto com as lideranças das áreas envolvidas.

A participação nos treinamentos é obrigatória para todos os novos colaboradores com atuação em áreas críticas, e deve ser renovada anualmente para os demais públicos-alvo, como parte do ciclo de conscientização contínua em segurança da informação.

### Processo de Gestão de Incidentes {#processo-de-gestão-de-incidentes}

A WeCare realiza a gestão de incidentes de segurança da informação seguindo um conjunto estruturado de etapas, garantindo resposta rápida, efetiva e coordenada aos incidentes identificados. As etapas são descritas detalhadamente abaixo:

##### **MONITORAMENTO** {#monitoramento}

A WeCare deve manter o monitoramento contínuo de seus ambientes tecnológicos, com foco na detecção de eventos que possam representar riscos à segurança da informação. Esse monitoramento inclui, mas não se limita a:

* Disponibilidade e desempenho de serviços críticos (ex: APIs, plataforma web);  
* Logs de acesso e autenticação;  
* Alertas de falhas ou comportamentos anômalos em infraestrutura e aplicações;  
* Indicadores de segurança fornecidos por serviços de terceiros como Cloudflare, Heroku, Zendesk e Google Workspace.

Atualmente, o monitoramento é realizado pela equipe de desenvolvimento, que deve garantir a configuração adequada das ferramentas de observabilidade, bem como responder a alertas gerados automaticamente. Cabe à equipe de Segurança da Informação (Infosec) supervisionar esse processo, definindo critérios mínimos e revisando periodicamente os procedimentos e as métricas monitoradas.

##### **IDENTIFICAÇÃO DO INCIDENTE** {#identificação-do-incidente}

Eventos suspeitos identificados durante o monitoramento ou reportados por colaboradores, parceiros ou usuários da plataforma devem ser imediatamente comunicados à equipe de Segurança da Informação (Infosec) ou ao ponto focal designado.

A análise e validação inicial do evento como um incidente de segurança é de responsabilidade da equipe de Infosec, em conjunto com os times técnicos envolvidos, conforme a natureza do incidente.

Todos os eventos confirmados como incidentes devem ser registrados no sistema oficial de gestão de incidentes da WeCare, garantindo rastreabilidade, evidências e integridade das informações para fins de acompanhamento, análise posterior e auditoria.

##### **CLASSIFICAÇÃO E PRIORIZAÇÃO** {#classificação-e-priorização}

Incidentes validados devem ser classificados segundo seu nível de gravidade e impacto operacional, o que determina a prioridade de resposta e o tempo máximo aceitável para resolução. Essa classificação é essencial para orientar a alocação de recursos, o escalonamento interno e a comunicação com partes interessadas.

A WeCare deve classificar e priorizar os incidentes de segurança da informação com base no nível de impacto e criticidade, conforme o esquema a seguir:

P1 – Crítico: Interrupção completa de serviços essenciais ou risco imediato à segurança da informação. Requer resposta imediata e atuação contínua até a completa resolução.

P2 – Alto: Comprometimento severo de áreas-chave ou sistemas sensíveis, com impacto significativo, porém parcial, na operação. Requer resposta rápida, com resolução em até 48 horas úteis.

P3 – Médio: Impacto moderado, com interrupção parcial ou degradação perceptível dos serviços. Deve ser tratado em até 72 horas úteis, conforme planejamento da equipe responsável.

P4 – Baixo: Incidentes pontuais, controláveis e com impacto limitado, sem afetar diretamente a operação. São monitorados e resolvidos em tempo oportuno, conforme priorização da área técnica.

| Nível | Descrição | Prioridade | Ação esperada |
| :---- | :---- | :---- | :---- |
| Crítico | Impacto extenso com interrupção completa das operações essenciais ou alto risco imediato à segurança da informação. | P1 | Intervenção imediata com recursos dedicados até resolução. |
| Alto | Impacto significativo em áreas críticas, com comprometimento severo, porém parcial, das operações essenciais ou segurança dos dados. | P2 | Resposta rápida e resolução em até 48 horas úteis. |
| Médio | Impacto moderado com indisponibilidade parcial ou lentidão dos sistemas, sem afetar severamente a continuidade operacional. | P3 | Resolução programada e planejada em até 72 horas úteis. |
| Baixo | Impacto limitado, pontual e controlável, com pouco ou nenhum efeito perceptível nas operações gerais da WeCare. | P4 | Monitoramento contínuo e resolução em prazo oportuno. |

##### **CATEGORIAS DE INCIDENTE** {#categorias-de-incidente}

Para fins de padronização, registro e tratamento adequado, a WeCare classifica os incidentes de segurança da informação em categorias, com base na natureza do evento e seu modo de ocorrência. Essa categorização auxilia na identificação de padrões recorrentes, definição de planos de resposta específicos e análise estatística para melhoria contínua.

As categorias adotadas são:

| Categoria | Exemplos |
| :---- | :---- |
| Acesso não autorizado | Uso indevido de credenciais, escalonamento de privilégios, acesso indevido a sistemas ou dados restritos. |
| Vazamento de dados | Divulgação acidental ou indevida de informações sensíveis ou pessoais, envio incorreto de documentos, exposição pública de dados. |
| Malware | Infecções por ransomware, trojans, worms, spyware ou qualquer software malicioso. |
| Negação de Serviço (DoS/DDoS) | Ataques que visam tornar sistemas ou serviços indisponíveis por sobrecarga ou exploração de falhas. |
| Engenharia social | Phishing, vishing, manipulação de colaboradores ou parceiros para obtenção de informações ou acesso. |
| Incidente físico | Perda, roubo ou acesso indevido a dispositivos físicos contendo dados sensíveis. |
| Violação de políticas | Quebra de diretrizes internas de segurança, uso não autorizado de recursos, bypass de controles. |

##### **ESCALONAMENTO** {#escalonamento}

Uma vez classificado, o incidente deve ser escalonado internamente conforme a matriz de responsabilidades (RACI) estabelecida, assegurando que os responsáveis adequados sejam acionados para realizar ações necessárias em cada nível de prioridade.

##### **CONTENÇÃO** {#contenção}

Medidas imediatas de contenção devem ser implementadas para limitar ou interromper rapidamente os danos causados pelo incidente. Isso inclui, mas não se limita a: isolamento de sistemas, bloqueio temporário de usuários ou acessos, suspensão de serviços ou aplicações específicas e outras medidas necessárias para a proteção imediata dos ativos de informação da WeCare.

##### **ERRADICAÇÃO** {#erradicação}

Após a contenção, deve-se proceder à identificação e eliminação da causa raiz do incidente. A equipe técnica deve aplicar medidas corretivas e preventivas para assegurar que as vulnerabilidades ou falhas que levaram ao incidente sejam totalmente solucionadas.

##### **RECUPERAÇÃO**  {#recuperação}

A WeCare deve restaurar os serviços afetados de forma estruturada e priorizada, dando precedência às operações classificadas como críticas para a continuidade dos negócios, tais como: plataforma SaaS, bancos de dados principais e canais essenciais de comunicação com clientes. Caso a origem do incidente envolva infraestrutura terceirizada (Cloudflare, Heroku, AWS, Google Cloud), o fornecedor responsável deve ser imediatamente acionado pelos canais oficiais de suporte.

##### **ANÁLISE PÓS-INCIDENTE E LIÇÕES APRENDIDAS** {#análise-pós-incidente-e-lições-aprendidas}

Após o encerramento do incidente, uma análise detalhada deve ser conduzida para entender claramente o ocorrido. Um relatório formal deve ser elaborado contendo:

* Linha do tempo dos eventos desde a identificação até a resolução.  
* Determinação da causa raiz.  
* Avaliação das ações tomadas e sua eficácia.  
* Recomendações e definição de ações preventivas para evitar reincidências.  
* Lições aprendidas para aprimorar continuamente a gestão de incidentes.

Todos os incidentes devem ser registrados formalmente em sistema próprio da WeCare, com informações completas, como: data/hora, descrição, classificação, ações executadas, responsáveis e desdobramentos. Os registros devem ser auditáveis e utilizados como base para lições aprendidas, auditorias internas e análise de recorrência.

##### **COMUNICAÇÃO** {#comunicação}

A comunicação sobre incidentes deve seguir rigorosamente os processos estabelecidos, incluindo:

* Comunicação Interna: Acionamento imediato da equipe envolvida e reuniões emergenciais, quando necessárias, utilizando canais internos como Slack para garantir coordenação clara e eficaz.

* Comunicação Externa: Notificação clara, objetiva e transparente aos clientes e parceiros afetados, utilizando preferencialmente e-mail ou WhatsApp corporativo, além da página de status do serviço. ([status.wecare.app.br](http://status.wecare.app.br)). Deve-se atualizar periódicamente as informações sobre o incidente.

	*Prezado cliente,*

*Identificamos um incidente que está causando \[breve descrição do impacto\]. Nossa equipe está trabalhando continuamente para resolver a situação o mais rápido possível. Manteremos você atualizado sobre o andamento da resolução. Agradecemos pela sua compreensão e pedimos desculpas por qualquer transtorno causado.*

*Equipe WeCare*

# 

# Fluxograma do Processo {#fluxograma-do-processo}

O processo de gestão de incidentes da WeCare é estruturado em etapas sequenciais e interdependentes, que visam assegurar uma resposta ágil, coordenada e eficaz a qualquer incidente de segurança da informação. O fluxo abaixo representa, em alto nível, as fases adotadas pela organização desde a identificação até a análise pós-incidente:

Monitoramento Contínuo e Alertas Automáticos  
             |  
             v  
Identificação e Registro Inicial do Incidente  
             |  
             v  
Classificação e Priorização (Crítico, Alto, Médio, Baixo)  
             |  
             v  
Comunicação Interna e Escalonamento (Matriz RACI)  
             |  
             v  
Contenção Imediata do Incidente  
             |  
             v  
Erradicação da Causa Raiz  
             |  
             v  
Recuperação dos Serviços Afetados  
             |  
             v  
Comunicação Externa (Clientes/Parceiros)  
             |  
             v  
Análise Pós-incidente e Documentação das Lições Aprendidas

# 

# Processos Relacionados {#processos-relacionados}

A gestão de incidentes de segurança da informação na WeCare está diretamente conectada a outros processos organizacionais fundamentais, garantindo uma abordagem integrada e eficiente na resposta a eventos críticos.

Entre os principais processos relacionados, destacam-se:

* Continuidade de Negócios  
* Gestão de Mudanças  
* Gestão de Riscos

A integração entre esses processos é essencial para assegurar a resiliência da operação, mitigar riscos recorrentes, garantir conformidade legal e regulatória, e preservar a confiança de clientes, parceiros e colaboradores. Sempre que um incidente gerar impacto em qualquer uma dessas frentes, os processos correspondentes devem ser imediatamente acionados, seguindo os fluxos definidos pela WeCare.

# Exceções {#exceções}

Qualquer pedido de exceção a esta política deve ser submetido por escrito e será avaliado caso a caso. Exceções serão permitidas apenas após aprovações documentadas do CISO (Chief Information Security Officer) ou do Comitê de Direção.

# Revisão do Documento {#revisão-do-documento}

Este documento de política e procedimento será revisado quanto a atualizações e alterações, no mínimo, uma vez por ano pela área de InfoSec (Segurança da Informação).
