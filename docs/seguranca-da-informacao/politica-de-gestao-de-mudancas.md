---
id: politica-de-gestao-de-mudancas
title: Política de Gestão de Mudanças
description: Documento oficial com diretrizes de seguranca da informacao da WeCare.
sidebar_position: 4
---

# Política de Gestão de Mudanças

> Status: Vigente  
> Versao: 1.1  
> Ultima atualizacao: Março de 2026  
> Responsavel: Seguranca da Informacao

# Propósito {#propósito}

Esta política tem como finalidade estabelecer diretrizes para registrar, revisar, aprovar, implementar e documentar mudanças realizadas na plataforma da WeCare, de forma proporcional ao porte da empresa, assegurando rastreabilidade, redução de riscos e continuidade dos serviços. Esta política aplica-se a mudanças em código, infraestrutura, configurações, integrações e serviços associados.

# Governança e Responsabilidade {#governança-e-responsabilidade}

A diretoria da WeCare designará um responsável pela segurança da informação, que será encarregado de manter esta política atualizada e apoiar a avaliação de riscos e exceções.

A equipe de desenvolvimento é responsável por aplicar o processo de gestão de mudanças descrito neste documento.

As áreas envolvidas, incluindo Sucesso do Cliente quando aplicável, devem colaborar na validação, priorização e comunicação das mudanças conforme sua natureza e impacto.

# Conformidade Legal e Regulatória {#conformidade-legal-e-regulatória}

Esta política foi elaborada com base em boas práticas de segurança da informação, rastreabilidade e controle de mudanças, considerando requisitos de conformidade adotados pela WeCare e legislações aplicáveis, como a LGPD.

# Público-alvo {#público-alvo}

Esta política aplica-se a colaboradores, prestadores de serviço e terceiros autorizados que participem da solicitação, análise, desenvolvimento, aprovação, implantação, validação ou comunicação de mudanças na WeCare.

# Descrição da Política {#descrição-da-política}

### Definições {#definições}

* **Mudança**: qualquer alteração nos componentes técnicos ou processos que podem impactar a operação da plataforma;

* **Mudança de Melhoria**: alterações planejadas que seguem o fluxo descrito nesta política;

* **Mudança de Correção**: alterações não planejadas, mas não críticas, que seguem o fluxo descrito nesta política;

* **Mudança Emergencial**: alterações críticas que não podem seguir o processo completo devido à urgência;

* **Mudança de Infraestrutura**: alterações nos componentes de infraestrutura, como servidores, configurações de rede, serviços de cloud ou ajustes de configurações de ambiente;

* **Pull Request (PR)**: registro técnico utilizado para revisão, aprovação, rastreabilidade e documentação de alterações no código, podendo também conter referências à demanda de origem, item do Listas e ticket do Zendesk, quando aplicável.

### 

### Registro da Mudança {#registro-da-mudança}

* Toda mudança deve possuir registro suficiente para garantir rastreabilidade, incluindo, conforme aplicável, descrição da alteração, justificativa, impacto esperado, risco, plano de rollback e referências relacionadas;

* Mudanças no código devem ser registradas tecnicamente por meio de Pull Request (PR);

* Mudanças planejadas, correções e alterações operacionais devem ser organizadas em item do Listas no Slack, que poderá referenciar o respectivo PR;

* Quando a mudança decorrer de solicitação feita por colaboradores dos clientes, deverá haver ticket no Zendesk, e o PR deverá conter a referência ao ticket correspondente;

* Sempre que houver item no Listas e PR relacionados à mesma mudança, deve haver referência cruzada entre ambos para facilitar rastreabilidade;

* Mudanças de infraestrutura devem ser registradas em item do Listas no Slack e, quando houver automação, script, ajuste versionado ou artefato técnico associado, a referência correspondente também deve ser incluída;

* A participação da área de Sucesso do Cliente na aprovação ou validação ocorrerá quando a mudança impactar cliente, fluxo operacional ou requisito funcional sob sua responsabilidade.

* Quando aplicável, a mudança deverá ser revisada e validada pelas áreas envolvidas antes da implantação, especialmente quando houver impacto para clientes, operação ou fluxos internos.

Na WeCare, a rastreabilidade da mudança pode ser mantida por meio da combinação entre Pull Request no GitHub, item do Listas no Slack e ticket no Zendesk, quando aplicável. Para mudanças solicitadas por colaboradores dos clientes, o ticket no Zendesk representa a origem da demanda. O item do Listas organiza o acompanhamento operacional da mudança. O Pull Request documenta tecnicamente a implementação. Sempre que mais de um desses registros existir para a mesma mudança, deve haver referência cruzada entre eles.

### Execução da Mudança {#execução-da-mudança}

* Mudanças no código devem ser desenvolvidas em branch dedicado e submetidas via Pull Request;

* O PR deve conter descrição suficiente da alteração e, quando aplicável, referência ao item correspondente no Listas e ao ticket do Zendesk;

* O item do Listas deve conter referência ao PR relacionado, quando houver;

* Mudanças na infraestrutura devem ser planejadas com antecedência compatível com o risco e registradas no item correspondente do Listas, com documentação mínima da alteração, impacto esperado e plano de reversão, quando aplicável.

### Revisão e Aprovação {#revisão-e-aprovação}

* Mudanças no código devem passar, sempre que possível, por revisão por outro desenvolvedor antes da implantação;

* Quando houver impacto funcional relevante para clientes ou operação, a mudança deve ser validada em homologação pelas áreas envolvidas, incluindo Sucesso do Cliente quando aplicável;

* Mudanças significativas de infraestrutura devem ser revisadas por pessoas com conhecimento técnico compatível, observada a estrutura enxuta da WeCare.

### Testes e Validação {#testes-e-validação}

* Mudanças no código devem ser testadas de forma compatível com o risco e a criticidade da alteração, preferencialmente com registro no PR;

* Sempre que houver ambiente de homologação e a natureza da mudança justificar, a validação deve ocorrer antes da implantação em produção;

* Quando a mudança impactar clientes, fluxos operacionais ou requisitos funcionais, a validação poderá envolver Sucesso do Cliente ou a área responsável;

* Ajustes identificados durante testes ou validação devem ser registrados e tratados de forma rastreável.

* A área de Sucesso do Cliente, quando envolvida, deverá validar principalmente os aspectos funcionais e operacionais da mudança sob sua responsabilidade.

### Implantação e Monitoramento {#implantação-e-monitoramento}

* Após aprovação e testes aplicáveis, o código poderá ser integrado à branch principal e implantado conforme o processo técnico adotado pela WeCare;

* O ambiente de produção deve ser acompanhado após implantações relevantes, com atenção a erros, alertas, comportamento inesperado e impacto para clientes ou operação.

* Mudanças na Infraestrutura:  a infraestrutura deve ser monitorada após qualquer alteração, com foco no desempenho do sistema e na identificação de possíveis falhas ou erros da mudança implementada.

### Mudanças Emergenciais {#mudanças-emergenciais}

Mudanças emergenciais são alterações críticas que não podem seguir o processo completo de gestão de mudanças devido à urgência. Elas visam corrigir falhas que impactam diretamente a operação da plataforma ou a experiência do cliente.

**Registro:**

* O registro da mudança emergencial deve ser feito assim que possível após sua execução, no mecanismo aplicável ao caso, como PR, item do Listas no Slack e, quando houver solicitação de cliente associada, ticket no Zendesk, contendo ao menos:  
  * Descrição da mudança;  
  * Justificativa da urgência;  
  * Impacto potencial;  
  * Plano de rollback ou mitigação, quando aplicável.

**Revisão e Aprovação:**

* Podem ser aprovadas sem validação prévia da área do Sucesso do Cliente;  
* O desenvolvedor deve:  
  * Realizar testes automatizados localmente;  
  * Fazer a revisão por pares do código antes da implantação.

**Execução:**

* Sempre que tecnicamente viável, a alteração emergencial deve ser registrada em Pull Request;  
* Quando houver item do Listas e ticket do Zendesk relacionados, as referências entre PR, Listas e Zendesk devem ser incluídas posteriormente para recompor a rastreabilidade da mudança.

**Validação e Monitoramento:**

* A equipe de desenvolvimento deve monitorar a produção durante e após a implantação para garantir estabilidade;  
* Caso sejam necessários ajustes após a mudança emergencial, estes devem ser documentados e os desenvolvedores notificados.

### Documentação e Comunicação {#documentação-e-comunicação}

As mudanças que impactem diretamente a operação, fluxos internos ou clientes devem ser comunicadas de forma clara e oportuna às partes envolvidas. Para fins de rastreabilidade, a documentação da mudança poderá estar distribuída entre Pull Request, item do Listas no Slack e ticket no Zendesk, desde que haja referência cruzada entre esses registros quando aplicável.

# Exceções {#exceções}

Qualquer pedido de exceção a esta política deve ser submetido por escrito e será analisado com base em risco. Exceções somente poderão ser concedidas mediante aprovação documentada da diretoria da WeCare ou do responsável formalmente designado pela segurança da informação.

# Revisão do Documento {#revisão-do-documento}

Este documento será revisado, no mínimo, uma vez por ano, ou sempre que houver mudanças relevantes no processo de desenvolvimento, infraestrutura, ferramentas utilizadas ou forma de registro e controle das mudanças na WeCare.

## Histórico de revisões

| Versão | Data | Tipo de alteração | Autor | Revisor | Aprovador |
| :---- | :---- | :---- | :---- | :---- | :---- |
| 1.1 | 01/03/2026 | Revisão e simplificação da política; adequação da governança, rastreabilidade e processo de gestão de mudanças ao modelo operacional da WeCare com uso de PR no GitHub, itens no Listas do Slack e tickets no Zendesk quando aplicável | Rafael Fernandes |  |  |
| 1.0 | 19/11/2024 | Criação | [Rafael Fernandes](mailto:rafael@sejawecare.com.br) | Eduardo Fernandes | [Deborah Oliveira](mailto:deborah@sejawecare.com.br) |
