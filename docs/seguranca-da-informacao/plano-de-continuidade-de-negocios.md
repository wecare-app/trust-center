---
id: plano-de-continuidade-de-negocios
title: Plano de Continuidade de Negócios
description: Documento oficial com diretrizes de seguranca da informacao da WeCare.
sidebar_position: 5
---

# Plano de Continuidade de Negócios

> Status: Vigente  
> Versao: 1.0  
> Ultima atualizacao: Maio de 2025  
> Responsavel: Seguranca da Informacao


# Propósito {#propósito}

Este plano define ações, responsabilidades e procedimentos para manter as operações críticas da WeCare durante e após eventos que causem interrupções, minimizando impactos para clientes, equipe e parceiros. Abrange eventos tecnológicos e não tecnológicos.

# Características da Empresa {#características-da-empresa}

A WeCare opera 100% de forma remota, com 6 colaboradores distribuídos geograficamente. Toda a operação depende de serviços em nuvem, o que oferece flexibilidade e escalabilidade, mas exige disponibilidade dos fornecedores e estabilidade de conexão dos colaboradores.

### Ferramentas Principais {#ferramentas-principais}

* **Comunicação:** Google Workspace (e-mail), Slack (mensagens), WhatsApp corporativo (alternativo), Figma (colaboração visual), Zendesk (suporte).  
* **Repositório de Código:** GitHub.  
* **Deploy e Integração Contínua:** CircleCI.

### Infraestrutura de Produto: {#infraestrutura-de-produto:}

* Plataforma SaaS de Recursos Humanos hospedada no Salesforce Heroku.  
* Banco de Dados gerenciado pelo Heroku.  
* Armazenamento de arquivos em Amazon S3.  
* Envio de e-mails transacionais via Twilio Sendgrid.  
* Envio de SMS via Comtele.  
* Notificações em WhatsApp via Z-API.  
* Notificações em Slack e Telegram via integrações próprias.

# 

# Contatos de Emergência {#contatos-de-emergência}

Em caso de indisponibilidade ou interrupção dos serviços, os seguintes contatos devem ser acionados:

| Nome | Cargo | Telefone | E-mail | Observações |
| :---- | :---- | :---- | :---- | :---- |
| Deborah Oliveira | CEO | \+55 61 9 8209 3231 | deborah@sejawecare.com.br | Disponível em horário comercial |
| Rafael Fernandes | Líder Técnico | \+55 61 9 8299 3394 | rafael@sejawecare.com.br | Disponível em horário comercial |
| TI \- WeCare | Suporte Técnico Interno | \- | ti@sejawecare.com.br | Prioritário para incidentes técnicos |
| Heroku Suporte | Fornecedor de Infraestrutura | [https://help.heroku.com/](https://help.heroku.com/) | \- | 24x7 (Heroku Premium Support) |
| AWS Suporte | Fornecedor de Storage | [https://aws.amazon.com/contact-us/](https://aws.amazon.com/contact-us/) | \- | \- |
| Google Workspace Suporte | Comunicação e Colaboração | [https://support.google.com/](https://support.google.com/) | \- | 24x7 |

# Procedimento de Acionamento {#procedimento-de-acionamento}

### Identificação do Evento de Interrupção ou Indisponibilidade {#identificação-do-evento-de-interrupção-ou-indisponibilidade}

Sempre que um colaborador identificar falhas no sistema, lentidão, indisponibilidade ou qualquer comportamento fora do normal, deve acionar imediatamente o Líder Técnico.

### Avaliação Técnica e Escalonamento {#avaliação-técnica-e-escalonamento}

O Líder Técnico é responsável por:

* Avaliar a gravidade e o impacto do evento.

* Iniciar as ações de contenção e diagnóstico.

* Acionar o CEO, caso o incidente tenha impacto grave para usuários ou clientes, ou exija tomada de decisão de negócio.

Se o incidente envolver terceiros (Heroku, AWS, etc.), o Líder Técnico deve:

* Abrir chamado diretamente no canal apropriado do fornecedor.

* Avaliar o impacto e seguir o fluxo de escalonamento descrito acima.

# Identificação de Indisponibilidade {#identificação-de-indisponibilidade}

Falhas operacionais ou indisponibilidades nos sistemas da WeCare podem ser percebidas das seguintes formas:

* Alertas de Monitoramento: Notificações automáticas enviadas pelas plataformas (Heroku, Google Workspace ou outros) indicando falha ou degradação de serviço.

* Suporte de Clientes: Relatos recebidos via Zendesk. 

* Observação Interna: Qualquer membro da equipe pode reportar comportamento inesperado ou problemas de acesso. Qualquer identificação de falha deve resultar no acionamento imediato do Líder Técnico (ver seção "Procedimento de Acionamento").

Para o tratamento estruturado de incidentes, incluindo critérios de classificação, responsáveis, registros e respostas, deve-se seguir a Política de Gestão de Incidentes da WeCare.

# Prevenção e Mitigação {#prevenção-e-mitigação}

### Infraestrutura e Ferramentas {#infraestrutura-e-ferramentas}

* Backups automáticos da base de dados realizados diariamente por meio do Heroku Postgres, com retenção garantida durante todo o período contratual do cliente.  
  Responsável: Líder Técnico

* Monitoramento contínuo da aplicação configurado com alertas nativos do Heroku e verificação manual dos indicadores de disponibilidade.  
  Responsável: Desenvolvedores

* Plano de contingência para serviço de e-mail corporativo, com conta de emergência previamente configurada em provedor alternativo (ex: Zoho Mail), para ativação em caso de falha prolongada do Google Workspace.  
  Responsáveis: CEO e Líder Técnico

### Segurança Cibernética {#segurança-cibernética}

* Auditorias de segurança (testes de intrusão) executadas anualmente com ferramenta externa ou consultoria especializada, visando identificar vulnerabilidades críticas.  
  Responsável: Líder Técnico

* Atualizações de segurança aplicadas semanalmente nas dependências do sistema, com suporte das ferramentas automáticas de verificação (ex: GitHub Dependabot).  
  Responsável: Desenvolvedores

* Autenticação de dois fatores (2FA) exigida para todas as contas corporativas em sistemas críticos (Google Workspace, Heroku, GitHub, AWS), com revisão periódica nas movimentações de equipe.  
  Responsável: Líder Técnico

# 

# RTO e RPO {#rto-e-rpo}

Objetivo: Garantir que a recuperação de cada serviço crítico da empresa ocorra dentro dos prazos definidos, minimizando o impacto sobre os negócios e evitando perdas irreparáveis.

*RTO (Recovery Time Objective): tempo máximo para restaurar o serviço.*  
*RPO (Recovery Point Objective): ponto no tempo até onde os dados podem ser recuperados.*

| Sistema/Serviço | RTO | RPO |
| :---- | :---- | :---- |
| Aplicação WeCare \- Código (Github) | Até 2 horas | Imediato (Backup contínuo) |
| Plataforma WeCare (Heroku) | 4 horas | Até o momento da falha (Continuous Protection) |
| Banco de Dados (Heroku) | 4 horas | Até o momento da falha (Continuous Protection) |
| Armazenamento de Arquivos (AWS S3) | 4 horas | Até o momento da última versão salva (Versionamento habilitado) |
| Backups (Google Cloud Storage) | 8 horas | Até 24 horas |
| Cloudflare (DNS/WAF) | 4 horas | Não aplicável |

# Responsáveis e Contatos {#responsáveis-e-contatos}

Os papéis e responsabilidades para a execução do PCN estão claramente definidos, assegurando uma resposta coordenada e eficiente diante de incidentes. A seguir, as responsabilidades de cada ação e os respectivos contatos.

| Ação | Responsável | Contato Principal | Contato Alternativo |
| :---- | :---- | :---- | :---- |
| Identificação de evento de interrupção | Líder técnico | rafael@sejawecare.com.br | \+55 61 9 8299 3394 |
| Comunicação ao time | CEO | deborah@sejawecare.com.br | \+55 62 98209-3231 |
| Comunicação aos clientes | CEO | deborah@sejawecare.com.br | \+55 62 98209-3231 |
| Acionamento dos fornecedores | Líder técnico | rafael@sejawecare.com.br | \+55 61 9 8299 3394 |
| Recuperação da aplicação | Líder técnico | rafael@sejawecare.com.br | \+55 61 9 8299 3394 |
| Recuperação de banco de dados | Líder técnico | rafael@sejawecare.com.br | \+55 61 9 8299 3394 |
| Comunicação de Pós-incidente | CEO | deborah@sejawecare.com.br | \+55 62 98209-3231 |
| Análise e Revisão do PCN | Líder técnico / CEO | rafael@sejawecare.com.br | deborah@sejawecare.com.br |

# 

# Testes e Exercícios {#testes-e-exercícios}

O plano precisa ser testado periodicamente para garantir que funcione na prática. Os testes devem avaliar diferentes aspectos do plano, desde a recuperação de sistemas até a comunicação interna e externa durante a crise. A seguir, estão descritos os tipos de testes que devem ser realizados:

* Testes de Mesa: Simulações de incidentes em um ambiente controlado, onde a equipe discute a resposta e os procedimentos a seguir. Este tipo de teste visa avaliar a capacidade de resposta e a coordenação entre os membros da equipe.

* Testes Técnicos: Verificação prática da capacidade de recuperação dos sistemas, dados e infraestrutura em situações de falha.

* Testes de Comunicação: Simulação de comunicação interna e externa, incluindo a notificação de clientes, fornecedores e stakeholders relevantes.

* Treinamento Continuado: A equipe deve participar regularmente de treinamentos de segurança para garantir que todos os membros saibam como atuar em situações de incidente.

Periodicidade dos Testes:

* Testes de mesa: A cada 6 meses.  
* Testes técnicos: Anualmente.  
* Testes de comunicação: A cada 3 meses.

Documentação e Acompanhamento: Um relatório será gerado após cada teste, com as lições aprendidas e eventuais ajustes necessários no plano. 

# Revisão do Documento {#revisão-do-documento}

O Plano de Continuidade de Negócios (PCN) deve ser revisado e atualizado regularmente para garantir que esteja alinhado com a realidade da empresa e eficaz em caso de incidentes. A periodicidade das atualizações será definida da seguinte forma:

* Revisão Anual: O PCN será revisado e atualizado anualmente para garantir que ele reflita mudanças nos processos de negócios, nas ferramentas utilizadas, na equipe ou nas condições de operação da empresa.

* Mudanças Significativas: O plano será revisado sempre que houver mudanças significativas, como:  
  * Alterações nos fornecedores ou prestadores de serviços críticos.  
  * Mudanças na infraestrutura de TI ou nas ferramentas utilizadas.  
  * Novos processos de negócios ou atualizações legais que possam afetar a continuidade dos serviços.

Processo de Atualização: A responsabilidade pela atualização do PCN será atribuída ao líder técnico e ao CEO. Eles, juntamente com a equipe envolvida, revisarão o plano e farão as modificações necessárias. As atualizações serão documentadas de forma clara, incluindo o histórico de mudanças e as razões para cada alteração.

Feedback dos Testes: Após cada exercício de testes, o feedback obtido será utilizado para revisar o PCN e implementar melhorias. As lições aprendidas serão integradas ao plano para garantir que ele esteja sempre preparado para lidar com novos desafios.

# Avaliação e Melhoria Contínua {#avaliação-e-melhoria-contínua}

O PCN deve ser avaliado regularmente e ajustado com base em eventos reais, testes e feedbacks. A seguir, estão as ações previstas para a avaliação do plano e a incorporação de melhorias.

### Avaliações Regulares {#avaliações-regulares}

* Frequência: O PCN será avaliado a cada semestre para garantir que todas as ações e medidas de contingência estejam atualizadas.

* Método: As avaliações serão realizadas por meio de reuniões de revisão do PCN, onde serão analisados os seguintes pontos:

  * A eficácia das ações de prevenção e mitigação;

  * O desempenho do plano em eventos de interrupção recentes;

  * O feedback dos colaboradores e dos stakeholders sobre os processos adotados.

* Responsável: Líder técnico, CEO e equipe de segurança.

### Incorporação de Feedbacks {#incorporação-de-feedbacks}

* Análise pós-incidente: Após a ocorrência de qualquer incidente, será realizada uma revisão detalhada para identificar falhas no plano, medir o tempo de resposta e avaliar a eficácia das ações de recuperação. As lições aprendidas serão aplicadas diretamente no plano.

* Feedback de stakeholders: Será coletado feedback dos clientes e fornecedores após incidentes significativos para avaliar a percepção de eficácia e comunicar melhorias feitas no plano.

### Ações de Melhoria {#ações-de-melhoria}

* Identificação de falhas e pontos de melhoria: Durante cada avaliação, será feita uma análise detalhada de qualquer falha ou deficiência encontrada. As ações corretivas serão documentadas e atribuídas a responsáveis específicos.

* Implementação de melhorias: A equipe técnica e o CEO garantirão que as melhorias recomendadas sejam implementadas em um prazo máximo de três meses.

* Monitoramento das melhorias: O progresso na implementação das melhorias será monitorado até que todas as ações corretivas sejam concluídas, com acompanhamento em reuniões de status.

# 

# Fluxograma Simplificado {#fluxograma-simplificado}

Este fluxograma apresenta uma visão geral do acionamento do Plano de Continuidade de Negócios (PCN), a partir da identificação de eventos que causem interrupção relevante em serviços críticos da WeCare.

**1. Identificação de Indisponibilidade**:
   Percepção por alertas automáticos, dashboards, relatos de usuários ou equipe.

Responsável: Líder Técnico.  
Referência: Política de Gestão de Incidentes.

**2. Avaliação do Impacto**:
   O Líder Técnico avalia se o incidente impacta diretamente os serviços críticos da empresa. Se sim, o PCN deve ser ativado.  
   Responsável: Líder Técnico.

**3. Acionamento do PCN**:
   O Líder Técnico comunica o CEO, aciona fornecedores e inicia o plano de resposta com os responsáveis definidos.  
   Reunião rápida com os envolvidos para definir os próximos passos com base na matriz RACI.

**4. Comunicação com Clientes e Fornecedores**:
   O CEO comunica aos clientes e fornecedores afetados.  
   Os canais utilizados podem incluir e-mail, WhatsApp ou outro canal disponível.

**5. Restabelecimento dos Serviços**:
   Priorizar a retomada dos serviços críticos: Plataforma SaaS, banco de dados e canais de suporte.  
   Acionamento de fornecedores e equipe interna conforme necessário.  
   Responsáveis: Líder Técnico e equipe de TI.

**6. Encerramento e Pós-Incident Review**:
   Após a normalização, é realizada uma análise do ocorrido.  
   As lições aprendidas são documentadas e o PCN pode ser ajustado.  
   Responsáveis: Líder Técnico, CEO e equipe envolvida.

Observação: Para os procedimentos detalhados de resposta a incidentes, consulte a Política de Gestão de Incidentes da WeCare.

## Histórico de revisões

| Versão | Data | Tipo de alteração | Autor | Revisor | Aprovador |
| :---- | :---- | :---- | :---- | :---- | :---- |
| 1.0 | 01/05/2025 | Criação | [Rafael Fernandes](mailto:rafael@sejawecare.com.br) | Eduardo Fernandes | [Deborah Oliveira](mailto:deborah@sejawecare.com.br) |
