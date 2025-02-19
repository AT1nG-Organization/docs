---
title: Implantando o GitHub Advanced Security na sua empresa
intro: Aprenda a planejar, preparar e implementar uma abordagem em fases para implantar {% data variables.product.prodname_GH_advanced_security %} (GHAS) na sua empresa.
product: '{% data reusables.gated-features.advanced-security %}'
redirect_from:
- /admin/advanced-security/deploying-github-advanced-security-in-your-enterprise
miniTocMaxHeadingLevel: 3
versions:
  ghes: '*'
  ghec: '*'
type: how_to
topics:
- Advanced Security
- Code scanning
- Enterprise
- Security
ms.openlocfilehash: 7990891fd4b90127ae5f32aa262d6c096d23acab
ms.sourcegitcommit: dc42bb4a4826b414751ffa9eed38962c3e3fea8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2022
ms.locfileid: "147060751"
---
## <a name="overview-of-the-deployment-process"></a>Visão geral do processo de implantação

{% data reusables.security.overview-of-phased-approach-for-ghas-rollout %}

Para obter um resumo de alto nível dessas diferentes fases, confira "[Visão geral da implantação do {% data variables.product.prodname_GH_advanced_security %}](/admin/advanced-security/overview-of-github-advanced-security-deployment)".

Antes de iniciar sua implantação, recomendamos que você revise os pré-requisitos da instalação do GHAS e as melhores práticas de implantação do GHAS em "[Visão geral da implantação do {% data variables.product.prodname_GH_advanced_security %}](/admin/advanced-security/overview-of-github-advanced-security-deployment)".

## <a name="-octicon-milestone-aria-labelthe-milestone-icon--phase-0-planning--kickoff"></a>{% octicon "milestone" aria-label="The milestone icon" %} Fase 0: Planejamento e início

{% note %}

{% octicon "clock" aria-label="Clock" %} **Tempo estimado:** estimamos que a fase 0 dure aproximadamente entre uma e quatro semanas. Esta faixa pode variar dependendo das necessidades da sua versão e quaisquer aprovações necessárias que a sua empresa pode precisar no plano de implantação.

{% endnote %}

O objetivo da fase de planejamento e arranque é garantir que você tenha as suas pessoas, processos e tecnologias configuradoas e prontas para a implantação do GHAS.

Para o ajudar a comprar dinheiro do patrocinador executivo, recomendamos preparar-se e alinhar-se em um plano e objetivos implementados antes de lançar o GHAS na sua empresa.

Como parte de uma estratégia de implementação em fases, recomendamos que você identifique equipes ou aplicativos críticos de alto impacto que devem ser direcionados para se unir-se ao GHAS antes do restante da sua empresa.

Se uma distribuição em fases não funcionar para sua empresa, vá para a [fase do projeto piloto](#--phase-1-pilot-projects).

Se você está trabalhando com {% data variables.product.prodname_professional_services %}, durante esta fase, vocêtambém estabelecerá um plano sobre a forma como as suas equipes irão trabalhar em conjunto durante o processo de implementação. A equipe {% data variables.product.prodname_professional_services_team %} pode apoiar você com a criação do plano de implantação e metas faseadas, conforme necessário.

### <a name="step-1-kickoff-meeting-with--data-variablesproductprodname_professional_services--optional"></a>Passo 1: Reunião inicial com {% data variables.product.prodname_professional_services %} (opcional)

Se você se inscreveu em {% data variables.product.prodname_professional_services %}, você começará o processo de implementação reunindo-se com o representante dos Serviços.

Se você não se inscreveu em {% data variables.product.prodname_professional_services %}, você pode pular para a próxima etapa.

O objetivo desta reunião é alinhar as duas equipes com as informações necessárias para começar a criar um plano de implementação que funcione melhor para sua empresa. Na preparação desta reunião, criamos um estudo que irá nos ajudar a nos preparar melhor para o debate. Seu representante de serviços irá enviar-lhe esta pesquisa.

Para ajudar você a preparar-se para essa reunião inicial, revise esses tópicos.

-  Alinhar sobre como a sua empresa e {% data variables.product.prodname_professional_services %} trabalharão juntos da melhor forma
  - Definindo expectativas sobre como utilizar melhor as horas/dias de serviço adquiridos
  - Planos de comunicação/frequência das reuniões
  - Funções e responsabilidades
- Revise como o GHAS funciona dentro do ciclo de Vida do Desenvolvimento de Software (SDLC). O seu representante de {% data variables.product.prodname_professional_services %} explicará como o GHAS funciona.
- Revisão das melhores práticas para a implantação do GHAS. Isso é oferecido como uma atualização se sua equipe considerar importante ou se a sua empresa não participou do exercício de Prova de Conceito (POC). Esta revisão inclui uma discussão sobre seu programa de Segurança de Aplicativos existente e seu nível de maturidade em comparação com algo como o modelo de maturidade do DevSecOps.
-  Alinhamento nos próximos passos para sua implantação no GHAS. Seu representante de {% data variables.product.prodname_professional_services %} descreverá as suas próximas etapas e o apoio que você pode esperar de sua parceria.

Para ajudar você a planejar sua estratégia de implementação, você também pode esperar discutir essas questões:
  - Quantas equipes serão habilitadas?
  - Qual é a anatomia dos repositórios das equipes? (Stack tecnológico, ferramenta atual, etc.)
    - Parte disto pode já ter sido coberta durante o exercício da Prova de Conceito se a sua empresa participou. Em caso negativo, este é um momento crucial para discutir este assunto.
   - Que nível de adoção esperamos ser orgânico, assistido ou inorgânico?
   - Qual é a aparência da adoção assistida a partir de uma perspectiva de recursos e documentação?
   - Como você vai gerir a adoção inorgânica mais adiante? (Por exemplo, usando aplicação da política ou fluxos de trabalho gerenciada centralmente.)

### <a name="step-2-internal-kickoff-at-your-company"></a>Etapa 2: Início interno na sua empresa

Independentemente de a sua empresa escolher ou não trabalhar com {% data variables.product.prodname_professional_services %}, recomendamos sempre que você realize sua própria reunião de início para alinhar sua(s) própria(s) equipe(s).

Durante essa reunião inicial, é importante garantir que haja uma clara compreensão dos objetivos, expectativas e que esteja em vigor um plano sobre como avançar com a sua implementação.

Além disso, esse é um bom momento para começar a pensar na formação e preparação para a sua equipe, a fim de garantir que disponham das ferramentas e dos conhecimentos adequados para apoiar a implementação do GHAS.

#### <a name="topics-for-your-internal-kickoff-meeting"></a>Tópicos para sua reunião inicial interna

Recomendamos que você cubra estes tópicos na sua reunião inicial interna da sua empresa, caso ainda não tenha coberto esses tópicos com o mesmo grupo na sua reunião inicial com {% data variables.product.prodname_professional_services %}.

- Quais são suas métricas de sucesso de negócios, como você planeja medir e relatar essas medidas?
  - Se estes não foram definidos, defina-os. Caso tenham sido definidos, comunique-os e fale sobre como você planeja fornecer atualizações de progresso orientados por dados.
- Analise como o GHAS funciona dentro do SDLC (Ciclo de Vida e Desenvolvimento do Software) e como isso deve funcionar para sua empresa.
- Revise as práticas recomendadas se a sua empresa não participou do exercício da Prova de Conceito (ou de uma atualização, se sua equipe encontrar valor nesta revisão)
  - Como isso pode ser comparado ou contrastado com seu Programa de Segurança de Aplicativos?
- Discuta e chegue a um acordo sobre como sua equipe interna trabalhará melhor em conjunto durante a distribuição e a implementação.
  - Alinhe nos seus planos de comunicação e frequência de reuniões para sua equipe interna
  - Revise as tarefas de conclusão e execução, definindo funções e responsabilidades. Nós delineamos a maioria das tarefas neste artigo, mas pode haver tarefas adicionais que sua empresa requer que nós não incluímos.
  - Considere estabelecer um "Programa de Campeões" para capacitação escalonada
  - Comece a discutir tempo para concluir as tarefas
- Comece a trabalhar em abordagens de implantação ideais que funcionarão melhor para sua empresa. Isto incluirá compreender alguns pontos importantes:
  - Quantas equipes serão habilitadas? Parte disso já pode ter sido coberta durante o exercício POC (Prova de Conceito), caso a sua empresa tenha participado. Em caso negativo, este é um momento crucial para discutir este assunto.
  - Dos aplicativos essenciais identificados para a implantação inicial, quantos são desenvolvidos com base em uma tecnologia compatível com o GHAS?
  - Em que medida a preparação organizacional é necessária? Para saber mais, confira "[Fase 2](#--phase-2-organizational-buy-in--rollout-preparation)".

### <a name="step-3-prepare-your-rollout--implementation-plan-and-goals"></a>Etapa 3: Preparar seu plano e suas metas de distribuição e implementação

Antes de poder avançar com o(s) projeto(s) piloto(s) para a primeira fase da implementação, é fundamental garantir que um plano de implementação e objetivos de negócios foram estabelecidos sobre como sua empresa planeja prosseguir.

Se você está trabalhando com {% data variables.product.prodname_professional_services %}, ele pode desempenhar um papel significativo na criação deste plano.

Se você estiver trabalhando de forma independente, esta seção define algumas coisas para garantir que sejam incluídas no seu plano enquanto você se prepara para avançar.

Planos de mudança de processo (se necessário) e treinamento para os integrantes da equipe, conforme necessário:
  - As tarefas de equipe documentadas para funções e responsabilidades. Para obter mais informações sobre as permissões necessárias para cada recurso, confira "[Funções de repositório para uma organização](/organizations/managing-access-to-your-organizations-repositories/repository-roles-for-an-organization#access-requirements-for-security-features)".
  - O plano documentado de tarefas e linha do tempo/cronogramas sempre que possível. Isto deve incluir alterações na infraestrutura, mudanças/formação dos processos e todas as fases subsequentes de habilitação do GHAS, permitindo prazos para correções e ajustes de configuração, conforme necessário. Para obter mais informações, confira "[Fase 1: Projetos piloto](/admin/advanced-security/deploying-github-advanced-security-in-your-enterprise#--phase-1-pilot-projects)" abaixo.
  - Plano priorizado para quais projetos/equipes terão o GHAS habilitado primeiro e planos posteriores para quais projetos/equipes estarão nas fases a seguir
  - Métricas de sucesso baseadas em objetivos de negócios. Este será um ponto de referência fundamental após o(s) projeto(s) piloto para obter adesão para a implementação completa.

{% note %}

**Observação:** para garantir que a conscientização, a adesão e a adoção venha de todos os grupos da sua empresa, é importante definir expectativas realistas com relação ao tempo de distribuição e ao impacto na infraestrutura, nos processos e nos fluxos de trabalho gerais de desenvolvimento diários da sua empresa. Para uma implantação mais suave e bem-sucedida, garanta que as suas equipes de segurança e desenvolvimento compreendam o impacto do GHAS.

{% endnote %}

{% ifversion ghes %}

Para os clientes de {% data variables.product.prodname_ghe_server %}, para ajudar a garantir que sua instância possa apoiar a implementação do GHAS, revise o seguinte:

- Embora a atualização para GHES 3.0 não seja obrigatória, você precisa atualizar para o GHES 3.0 ou superior aproveitar as combinações de recursos, como digitalização de código e {% data variables.product.prodname_actions %}. Para obter mais informações, confira "[Como atualizar o {% data variables.product.prodname_ghe_server %}](/admin/enterprise-management/updating-the-virtual-machine-and-physical-resources/upgrading-github-enterprise-server)".

- Na configuração de alta disponibilidade, um appliance do {% data variables.product.prodname_ghe_server %} secundário totalmente redundante é mantido em sincronização com o appliance primário pela replicação de todos os principais armazenamentos de dados. Para obter mais informações sobre como configurar a alta disponibilidade, confira "[Como configurar a alta disponibilidade](/admin/enterprise-management/configuring-high-availability)".

- Para ajudar a apoiar quaisquer discussões sobre possíveis alterações na configuração da sua empresa, você pode revisar a visão geral do sistema de {% data variables.product.prodname_ghe_server %}. Para obter mais informações, confira "[ Visão geral do sistema](/admin/overview/system-overview)".

{% endif %}

### <a name="step-4-establish-a-baseline-of-organizational-insights"></a>Passo 4: Estabeleer uma linha base de ideias organizacionais

À medida que sua empresa se prepara para iniciar seu(s) projeto(s) piloto(s), é fundamental garantir que você definiu uma linha de base para onde sua empresa está hoje e definiu métricas de sucesso claras para medir o progresso com base no(s) seu(s) projeto(s) piloto.

Provavelmente, sua empresa tem principais metas de negócio que precisarão ser medidas, mas existem outras métricas que podemos identificar para ajudar a avaliar o sucesso do piloto.

Como ponto de partida, algumas dessas métricas podem incluir:
  - O tempo médio para correção de vulnerabilidades do GHAS em comparação com as ferramentas e as práticas anteriores que os projetos piloto/as equipes utilizaram.
  - A verificação de código dos resultados da integração para os principais X aplicativos mais essenciais.
  - O número de aplicativos que têm o SAST (teste de segurança estático do aplicativo) integrado em comparação com antes da participação.

Se você participou do exercício POC antes de comprar o GHAS, esses objetivos podem parecer familiares. Este critério de sucesso inclui vários objetivos para as seguintes funções de alto nível:
  - Equipes de implementação e administração
  - Segurança / CISO (Diretor de Segurança da Informação)
  - Equipes de Desenvolvimento de Aplicativos

Caso deseje dar um passo adiante, considere o uso do DSOMM (Modelo de Maturidade) de DevSecOps do OWASP para trabalhar a fim de alcançar uma maturidade de Nível 1. Existem quatro principais critérios de avaliação no DSOMM:

- **Profundidade estática:** o nível de abrangência da verificação de código estático que está sendo executado no pipeline de CI de AppSec
- **Profundidade dinâmica:** o nível de abrangência da verificação dinâmica que está sendo executada no pipeline de CI de AppSec
- **Intensidade:** a frequência de agendamento para as verificações de segurança em execução no pipeline de CI de AppSec
- **Consolidação:** o fluxo de trabalho de correção usado para tratar a integridade das descobertas e dos processos

Para saber mais sobre essa abordagem e como implementá-la no GHAS, baixe nosso white paper "[Como alcançar a maturidade de DevSecOps com o GitHub](https://resources.github.com/whitepapers/achieving-devsecops-maturity-github/)".

Com base nas metas da sua empresa e nos níveis atuais de maturidade do DevSecOps, podemos ajudar você a determinar a melhor forma de medir o progresso e o sucesso do seu piloto.

## <a name="-octicon-milestone-aria-labelthe-milestone-icon---phase-1-pilot-projects"></a>{% octicon "milestone" aria-label="The milestone icon" %}  Fase 1: Projeto(s) piloto

{% note %}

{% octicon "clock" aria-label="Clock" %} **Tempo estimado:** estimamos que a fase 1 dure aproximadamente entre duas e três semanas ou mais. Esse intervalo pode variar em grande parte dependendo da infraestrutura ou complexidade dos sistemas da sua empresa, processos internos para gerenciar/aprovar essas mudanças, bem como se são necessárias maiores mudanças no processo organizacional para avançar com o GHAS.

{% endnote %}

Para começar a habilitar o GHAS em toda a sua empresa, recomendamos começar com alguns projetos de alto impacto ou equipes para criar um piloto de uma distribuição inicial. Isso permitirá que um grupo inicial na empresa se familiarize com o GHAS e crie uma base sólida nele antes da distribuição para o restante da empresa.

Antes de iniciar seu(s) projeto(s), recomendamos que você agende algumas reuniões de verificação para a(s) sua(s) equipe(s), como uma reunião inicial, uma revisão do ponto intermediário e uma sessão de encerramento quando o piloto estiver concluído. Essas reuniões de verificação ajudarão você a fazer todos os ajustes, conforme necessário, e assegurarão que a(s) sua(s) equipe(s) esteja(m) preparad(a) e suportada(s) para concluir o piloto com sucesso.

Essas etapas ajudarão você a habilitar o GHAS na sua empresa, começar a usar as suas funcionalidades e revisar seus resultados.

Se você estiver trabalhando com {% data variables.product.prodname_professional_services %}, ele poderá fornecer assistência adicional por meio desse processo com sessões de integração, oficinas do GHAS e solução de problemas, conforme necessário.

### <a name="step-1-ghas-set-up--installation"></a>Etapa 1: Configuração e instalação do GHAS

{% ifversion ghes %}

Se você ainda não habilitou o GHAS para sua instância do {% data variables.product.prodname_ghe_server %}, confira "[Como habilitar o GitHub Advanced Security para sua empresa](/admin/advanced-security/enabling-github-advanced-security-for-your-enterprise)".

{% endif %}

Você precisa habilitar o GHAS para cada projeto piloto, habilitando o recurso do GHAS para cada repositório ou para todos os repositórios em qualquer organização que participe do projeto. Para obter mais informações, confira "[Como gerenciar as configurações de segurança e análise do seu repositório](/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-security-and-analysis-settings-for-your-repository)" ou "[Como gerenciar as configurações de segurança e análise da sua organização](/organizations/keeping-your-organization-secure/managing-security-and-analysis-settings-for-your-organization)".

A grande maioria dos ajustes e instalação do GHAS está centrada em habilitar e configurar a digitalização do código na sua empresa e nos seus repositórios.

A verificação de código permite que você analise o código em um repositório de {% data variables.product.prodname_dotcom %} para encontrar vulnerabilidades de segurança e erros de codificação. A digitalização de código pode ser usada para encontrar, triar e priorizar correções para problemas existentes no seu código, Além de ajudar a impedir que os desenvolvedores introduzam novos problemas que, de outra forma, poderiam chegar à produção. Para obter mais informações, confira "[Sobre a verificação de código](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning)".

### <a name="step-2-set-up--data-variablesproductprodname_code_scanning_capc-"></a>Etapa 2: Configurar {% data variables.product.prodname_code_scanning_capc %}

{% ifversion ghes %}

Para habilitar a {% data variables.product.prodname_code_scanning %} na sua instância do {% data variables.product.prodname_ghe_server %}, confira "[Como configurar a verificação de código para seu dispositivo](/admin/advanced-security/configuring-code-scanning-for-your-appliance)".

{% endif %}

Para configurar a verificação de código, você precisa decidir se executará a verificação de código com o [{% data variables.product.prodname_actions %}](#using-github-actions-for-code-scanning) ou com o seu [sistema de CI de terceiros](#using-a-third-party-ci-system-with-the-codeql-cli-for-code-scanning).

#### <a name="using--data-variablesproductprodname_actions--for--data-variablesproductprodname_code_scanning-"></a>Usando {% data variables.product.prodname_actions %} para {% data variables.product.prodname_code_scanning %}

{% ifversion ghes %}

Para configurar a verificação de código com o {% data variables.product.prodname_actions %} para o {% data variables.product.prodname_ghe_server %}, você precisará fornecer um ou mais executores auto-hospedados do {% data variables.product.prodname_actions %} no seu ambiente. Para obter mais informações, confira "[Como configurar um executor auto-hospedado](/admin/advanced-security/configuring-code-scanning-for-your-appliance#running-code-scanning-using-github-actions)".

{% endif %}

Para o {% data variables.product.prodname_ghe_cloud %}, você pode começar a criar um fluxo de trabalho do {% data variables.product.prodname_actions %} usando a [ação do CodeQL](https://github.com/github/codeql-action/) para executar a verificação de código em um repositório. A {% data variables.product.prodname_code_scanning_capc %} usa [executores hospedados pelo GitHub](/actions/using-github-hosted-runners/about-github-hosted-runners) por padrão, mas isso pode ser personalizado se você planeja hospedar um executor próprio com suas especificações de hardware. Para obter mais informações, confira "[Sobre os executores auto-hospedados](/actions/hosting-your-own-runners)".

Para mais informações sobre {% data variables.product.prodname_actions %}, consulte:
  - "[Saiba como usar o GitHub Actions](/actions/learn-github-actions)"
  - "[Noções básicas sobre o GitHub Actions](/actions/learn-github-actions/understanding-github-actions)"
  - "[Eventos que disparam fluxos de trabalho](/actions/learn-github-actions/events-that-trigger-workflows)"
  - "[Folha de referências de filtros padrão](/actions/learn-github-actions/workflow-syntax-for-github-actions#filter-pattern-cheat-sheet)"

#### <a name="using-a-third-party-ci-system-with-the-codeql-cli-for--data-variablesproductprodname_code_scanning-"></a>Usando um sistema de CI de terceiros com o a CLI do CodeQL para {% data variables.product.prodname_code_scanning %}

Se você não usar {% data variables.product.prodname_actions %} e tiver o seu próprio sistema de integração contínua, você poderá usar o CLI do CodeQL para executar a digitalização de código do CodeQL em um sistema CI de terceiros.

Para obter mais informações, consulte:
  - "[Sobre a verificação de código do CodeQL no sistema de CI](/code-security/code-scanning/using-codeql-code-scanning-with-your-existing-ci-system/about-codeql-code-scanning-in-your-ci-system)"

### <a name="step-3-enable--data-variablesproductprodname_code_scanning_capc--in-repositories"></a>Etapa 3: Habilitar {% data variables.product.prodname_code_scanning_capc %} nos repositórios

Se você estiver usando uma abordagem faseada para implementar o GHAS, recomendamos habilitar {% data variables.product.prodname_code_scanning %} por repositório como parte do seu plano de implementação. Para obter mais informações, confira "[Como configurar a verificação de código para um repositório](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/setting-up-code-scanning-for-a-repository)".

Se você não estiver planejando uma abordagem de implementação faseada e quiser habilitar a verificação de código para muitos repositórios, você pode fazer o script do processo.

Para ver um exemplo de um script que abre solicitações de pull para adicionar um fluxo de trabalho do {% data variables.product.prodname_actions %} a vários repositórios, confira o repositório [`jhutchings1/Create-ActionsPRs`](https://github.com/jhutchings1/Create-ActionsPRs) para ver um exemplo que usa o PowerShell ou [`nickliffen/ghas-enablement`](https://github.com/NickLiffen/ghas-enablement) para as equipes que não têm o PowerShell e desejam usar o NodeJS.

### <a name="step-4-run-code-scans-and-review-your-results"></a>Etapa 4: Execute digitalizações de código e revise seus resultados

Com a verificação de código habilitada nos repositórios necessários, você está pronto para ajudar suas equipes de desenvolvimento a entender como executar verificações de código e relatórios, ver relatórios e processar os resultados.

#### <a name="-data-variablesproductprodname_code_scanning_capc-"></a>{% data variables.product.prodname_code_scanning_capc %}

Com a verificação de código, você pode encontrar vulnerabilidades e erros no código do seu projeto no GitHub, além de ver, fazer a triagem, entender e resolver os alertas relacionados da {% data variables.product.prodname_code_scanning %}.

Quando a verificação de código identifica um problema em uma solicitação de pull, você pode revisar o código realçado e resolver o alerta. Para obter mais informações, confira "[Como fazer a triagem de alertas da {% data variables.product.prodname_code_scanning %} em solicitações de pull](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/triaging-code-scanning-alerts-in-pull-requests)".

Se você tiver permissão de gravação em um repositório, poderá gerenciar alertas da verificação de código desse repositório. Com a permissão de gravação em um repositório {% ifversion delete-code-scanning-alerts %}, você pode exibir, corrigir, descartar ou excluir alertas {% else %}você pode exibir, corrigir ou descartar alertas{% endif %} para possíveis vulnerabilidades ou erros no código do repositório. Para obter mais informações, confira "[Como gerenciar alertas de verificação de código do seu repositório](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/managing-code-scanning-alerts-for-your-repository)".

#### <a name="generate-reports-of--data-variablesproductprodname_code_scanning--alerts"></a>Gerar relatórios de alertas de {% data variables.product.prodname_code_scanning %}

Se você quiser criar um relatório dos seus alertas de digitalização de código, você poderá usar a API de {% data variables.product.prodname_code_scanning_capc %}. Para obter mais informações, confira a "[API do {% data variables.product.prodname_code_scanning_capc %}](/rest/reference/code-scanning)".

Para ver um exemplo de como usar a API do {% data variables.product.prodname_code_scanning_capc %}, confira o repositório [`get-code-scanning-alerts-in-org-sample`](https://github.com/jhutchings1/get-code-scanning-alerts-in-org-sample).

### <a name="step-5-configure--data-variablesproductprodname_code_scanning_capc--to-fine-tune-your-results"></a>Etapa5: Configure {% data variables.product.prodname_code_scanning_capc %} para ajustar seus resultados

Ao executar a digitalização inicial de código, você pode descobrir que nenhum resultado foi encontrado ou que um número incomum de resultados foi retornado. Você pode querer ajustar o que é sinalizado em futuras digitalizações.

Para obter mais informações, confira "[Como configurar a verificação de código](/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/configuring-code-scanning)".

Se sua empresa quiser usar outras ferramentas de análise de código de terceiros com a digitalização de código do GitHub, você poderá usar ações para executar essas ferramentas dentro do GitHub. Como alternativa, você pode fazer upload de resultados, gerados por ferramentas de terceiros como arquivos SARIF, para a digitalização de código. Para obter mais informações, confira "[Como fazer a integração à verificação de código](/code-security/code-scanning/integrating-with-code-scanning)".

### <a name="step-6-set-up-secret-scanning"></a>Etapa 6: Configurar a digitalização de segredos

O GitHub digitaliza repositórios de tipos conhecidos de segredos, para evitar o uso fraudulento de segredos que foram cometidos acidentalmente.

{% ifversion ghes %}

Para habilitar a verificação de segredos para sua instância do {% data variables.product.prodname_ghe_server %}, confira "[Como configurar a verificação de segredos para seu dispositivo](/admin/advanced-security/configuring-secret-scanning-for-your-appliance)".

{% endif %}

Você precisa habilitar digitalização de segredos para cada projeto piloto, habilitando o recurso para cada repositório ou para todos os repositórios de qualquer organização que participe do projeto. Para obter mais informações, confira "[Como gerenciar as configurações de segurança e análise do seu repositório](/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-security-and-analysis-settings-for-your-repository)" ou "[Como gerenciar as configurações de segurança e análise da sua organização](/organizations/keeping-your-organization-secure/managing-security-and-analysis-settings-for-your-organization)".

Para saber como ver e fechar alertas de segredos com check-in no seu repositório, confira "[Como gerenciar alertas da verificação de segredos](/code-security/secret-scanning/managing-alerts-from-secret-scanning)".

### <a name="step-7-set-up-dependency-management"></a>Etapa 7: Configurar gestão de dependências

O GitHub ajuda você a evitar o uso de software de terceiros que contém vulnerabilidades conhecidas. Fornecemos as ferramentas a seguir para atualizar dependências vulneráveis{% ifversion GH-advisory-db-supports-malware %} e remover malware{% endif %}.

| Ferramenta Gerenciamento de Dependência | Descrição |
|----|----|
| Alertas de Dependabot | Você pode acompanhar as dependências do seu repositório e receber alertas de dependências do Dependabot quando sua empresa detectar dependências inseguras. Para obter mais informações, confira "[Sobre os {% data variables.product.prodname_dependabot_alerts %}](/code-security/supply-chain-security/managing-vulnerabilities-in-your-projects-dependencies/about-alerts-for-vulnerable-dependencies)". |
| Gráfico de Dependência | O gráfico de dependências é um resumo do manifesto e bloqueia arquivos armazenados em um repositório. Ele mostra os ecossistemas e pacotes dos quais a sua base de código depende (suas dependências) e os repositórios e pacotes que dependem do seu projeto (suas dependências). Para obter mais informações, confira "[Sobre o grafo de dependência](/code-security/supply-chain-security/understanding-your-software-supply-chain/about-the-dependency-graph)". |{% ifversion ghes or ghec %}
| Revisão de Dependência | Se um pull request tiver alterações nas dependências, você poderá ver um resumo do que alterou e se há vulnerabilidades conhecidas em qualquer uma das dependências. Para obter mais informações, confira "[Sobre a revisão de dependência](/code-security/supply-chain-security/understanding-your-software-supply-chain/about-dependency-review)" ou "[Como revisar as alterações de dependência em uma solicitação pull](/github/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-dependency-changes-in-a-pull-request)". | {% endif %} {% ifversion ghec or ghes > 3.2 %}
| Atualizações de segurança do Dependabot | O dependabot pode corrigir dependências vulneráveis levantando pull requests com atualizações de segurança. Para obter mais informações, confira "[Sobre as atualizações de segurança do Dependabot](/code-security/supply-chain-security/managing-vulnerabilities-in-your-projects-dependencies/about-dependabot-security-updates)". |
| Atualizações da versão do Dependabot | O dependabot pode ser usado para manter os pacotes que você usa atualizados para as últimas versões. Para obter mais informações, confira "[Sobre as atualizações de versão do Dependabot](/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/about-dependabot-version-updates)". | {% endif %}

{% data reusables.dependabot.beta-security-and-version-updates-onboarding %}

### <a name="step-8-establish-a-remediation-process"></a>Etapa 8: Estabelecer um processo de correção

Uma vez que sua(s) equipe(s) puderam de realizar verificações, identificar vulnerabilidades e dependências e puderem consumir os resultados de cada recurso de segurança, o próximo passo é garantir que possam corrigir as vulnerabilidades identificadas em seus processos de desenvolvimento normais sem envolver sua equipe de segurança.

Isto significa que as equipes de desenvolvimento entendem como utilizar as funcionalidades do GHAS durante todo o processo de desenvolvimento, podem executar digitalizações, ler relatórios, usar os resultados e remediar vulnerabilidades dentro de seus fluxos de trabalho normais de desenvolvimento, sem precisar ter uma fase de segurança separada no final do desenvolvimento, ou ter necessidade de envolver sua equipe de segurança para entender relatórios/resultados.

### <a name="step-9-set-up-custom-analysis-if-needed"></a>Etapa 9: Configurar análise personalizada, se necessário

Análise personalizada é um uso opcional mais profundo da varredura de código quando consultas do CodeQL personalizadas são necessárias além do conjunto padrão (e comunidade) disponível de consultas. A necessidade de consultas personalizadas é rara.

As consultas personalizadas são usadas para identificar alertas personalizados de segurança ou ajudar os desenvolvedores a seguir os padrões de codificação, detectando certos padrões de código.

Se sua empresa estiver interessada em escrever consultas personalizadas do CodeQL, existem certos requisitos que sua empresa deve cumprir.

Se sua equipe puder fornecer alguns exemplos de vulnerabilidades existentes que você gostaria de encontrar via CodeQL, avise a equipe do GitHub e nós poderemos agendar uma sessão introdutória para revisar os fundamentos da linguagem e discutir como resolver um dos seus problemas. Se você quiser cobrir o CodeQL com mais profundidade, oferecemos opções adicionais de envolvimento para cobrir mais tópicos para permitir que a sua equipe crie as suas próprias consultas.

Saiba mais sobre as [consultas CodeQL](https://codeql.github.com/docs/writing-codeql-queries/codeql-queries/) em nossa [documentação do CodeQL](https://codeql.github.com/docs/codeql-overview/) ou entre em contato com o representante de vendas ou de equipe do {% data variables.product.prodname_professional_services %}.

### <a name="step-10-create--maintain-documentation"></a>Passo 10: Criar e manter a documentação

Em toda a fase piloto, é fundamental criar e manter uma documentação interna de alta qualidade da infraestrutura e processar alterações feitas dentro da sua empresa, bem como o que foi aprendido com o processo piloto e as alterações na configuração feitas conforme o progresso da(s) sua(s) equipe(s) ao longo da implementação.

Ter uma documentação completa e completa ajuda a fazer das etapas restantes da sua implementação mais de um processo reproduzível.
Uma boa documentação também garante que as novas equipes possam ser integradas de forma consistente ao longo do processo de implementação e, uma vez que que novos integrantes da equipe se unem à(s) equipe(s).

A documentação boa não termina quando a implementação é concluída. A documentação mais útil é atualizada e evolui ativamente à medida que suas equipes expandem sua experiência usando o GHAS e suas necessidades aumentam.

Além da sua documentação, recomendamos que sua empresa forneça canais claros para a(s) sua(s) equipe(s) para suporte e orientação tudo durante e após a implementação. Dependendo do nível de mudança, a sua empresa precisa assumir para apoiar a implementação do GHAS. Ter equipes bem respaldadas ajudará a garantir uma adesão bem-sucedida no fluxo de trabalho diário das suas equipes de desenvolvimento.

## <a name="-octicon-milestone-aria-labelthe-milestone-icon---phase-2-organizational-buy-in--rollout-preparation"></a>{% octicon "milestone" aria-label="The milestone icon" %} Fase 2: Adesão organizacional e preparação para distribuição

{% note %}

{% octicon "clock" aria-label="Clock" %} **Tempo estimado:** estimamos que a fase 2 dure aproximadamente entre uma semana e um mês. Esse intervalo pode variar em grande medida dependendo dos processos internos de aprovação da sua empresa.

{% endnote %}

Um dos principais objetivos desta fase é garantir que você tenha a adesão da organização para fazer com que toda a implantação do GHAS seja bem-sucedida.

Durante essa fase, a sua empresa analisa os resultados do(s) projeto(s) piloto para determinar se o piloto teve sucesso, que qjustes poderão ser necessários e se a empresa está disposta a prosseguir com a implantação.

Dependendo do processo de aprovação da sua empresa, poderá ser necessário continuar com a adesão da organização do seu patrocinador executivo. Na maioria dos casos, a adesão da(s) sua(s) equipe(s) organizacionais é necessária para começar a utilizar o valor do GHAS para a sua empresa.

Antes de passar para a próxima fase de implementação do GHAS em toda a sua empresa, as modificações são frequentemente feitas no plano original de implementação, com base no que aprendermos com o piloto.

Todas as alterações que possam ter impacto na documentação deverão também ser introduzidas para assegurar a sua implantação contínua.

Também recomendamos que você considere seu plano de treinar todas as equipes ou integrantes da equipe que serão apresentados ao GHAS nas próximas fases da sua implementação, se você ainda não o fez.

### <a name="step-1-organize-results"></a>Etapa 1: Organizar resultados

Na conclusão da fase 1, sua(s) equipe(s) deve(m) ter {% ifversion ghes %} o GHAS habilitado na instância de {% data variables.product.prodname_ghe_server %} e{% endif %} poder ter usado todos os principais recursos do GHAS com sucesso, potencialmente com algumas alterações de configuração para otimizar os resultados. Se a sua empresa definiu claramente métricas de sucesso na Fase 0, você poderá medir com base nessas métricas para determinar o sucesso do seu piloto.

É importante revisitar suas métricas de linha de base ao preparar seus resultados para garantir que o progresso adicional possa ser demonstrado com base em métricas coletadas do piloto com base nas metas originais do seu negócio. Se você precisar de ajuda com estas informações, o GitHub pode ajudar, garantindo que sua empresa tenha as métricas certas com base nas quais o seu progresso será medido. Para obter mais informações sobre a ajuda disponível, confira "[Serviços e suporte do GitHub](/admin/advanced-security/overview-of-github-advanced-security-deployment#github-services-and-support)".

### <a name="step-2-secure-organizational-buy-in"></a>Etapa 2: Adesão segura pela organização

A adesão organizacional irá variar com base em uma série de fatores, incluindo o tamanho da sua empresa, processo de aprovação, ou nível de mudança necessário para implantar o GHAS, para citar alguns exemplos.

Para algumas empresas, garantir a adesão é uma reunião única, mas, para outras, este processo pode levar algum tempo (possivelmente semanas ou meses). A adesão poderá exigir a aprovação do seu patrocinador executivo ou exigir a adoção do GHAS nos fluxos diários das suas equipes.

A duração desta fase depende inteiramente da sua empresa e da rapidez com que você gostaria de prosseguir. Recomendamos buscar suporte ou serviços a partir do GitHub sempre que possível para ajudar a responder a perguntas e fornecer todas recomendações que possam ser necessárias para ajudar a apoiar este processo. Para obter mais informações sobre a ajuda disponível, confira "[Serviços e suporte do GitHub](/admin/advanced-security/overview-of-github-advanced-security-deployment#github-services-and-support)".

### <a name="step-3-revise-and-update-documentation"></a>Passo 3: Revisar e atualizar a documentação

Analise os resultados e conclusões de seu projeto piloto e as necessidades dos das equipes restantes da sua empresa. Com base nos seus resultados e análises de necessidades, atualize e revise a sua documentação.

Descobrimos que é essencial garantir que a sua documentação esteja atualizada antes de continuar a implantação para os demais negócios da sua empresa.

### <a name="step-4-prepare-a-full-rollout-plan-for-your-company"></a>Passo 4: Prepare um plano de implantação completo para sua empresa

Com base no que você aprendeu com o(s) seu(s) projeto(s) piloto, atualize o plano de implantação que você projetou na fase 0. Para se preparar para a implementação na sua empresa, considere todos os treinamentos que suas equipes precisarem como, por exemplo, o treinamento sobre o uso do GHAS, mudanças de processo ou treinamento de migração se seu negócio estiver fazendo a migração para o GitHub.

## <a name="-octicon-milestone-aria-labelthe-milestone-icon---phase-3-full-organizational-rollout--change-management"></a>{% octicon "milestone" aria-label="The milestone icon" %} Fase 3: Distribuição organizacional completa e gerenciamento de alterações

{% note %}

{% octicon "clock" aria-label="Clock" %} **Tempo estimado:** estimamos que a fase 3 dure aproximadamente entre duas semanas e vários meses. Esse intervalo pode variar bastante, dependendo do tamanho da sua empresa, do número de repositórios/equipes, do nível de alteração que a distribuição do GHAS representará para sua empresa etc.

{% endnote %}

Assim que sua empresa estiver alinhada com os resultados e conclusões do(s) seu(s) projeto(s) piloto e todas as etapas de preparação forem concluídas a partir da Fase 2, você pode seguir em frente com a implementação completa para sua empresa com base no seu plano.

### <a name="step-1-evaluate-your-rollout-as-you-go"></a>Etapa 1: Avalie sua implantação à medida que você avança

Se você está usando uma abordagem faseada para implementar o GHAS, recomendamos que você faça uma breve pausa e realize uma curta avaliação depois de implementar o GHAS em um segmento diferente da sua empresa para garantir que a implantação avance sem problemas. Sua avaliação pode garantir que as equipes sejam habilitadas e treinadas adequadamente, que todas as necessidades únicas de configuração do GHAS foram atendidas e que os planos e a documentação podem ser ajustados conforme necessário.

### <a name="step-2-set-up-any-needed-training"></a>Passo 2: Configure todos os treinamentos necessários

Ao implementar o GHAS em qualquer equipe além da sua equipe de projeto(s) piloto(s), é importante garantir que as equipes sejam treinadas ou que existam recursos de treinamento disponíveis para fornecer suporte adicional quando necessário.

Estas são as principais áreas em que vemos que as empresas necessitam de suporte adicional:
  - treinamento no GHAS
  - treinamento para clientes novos no GitHub
  - treinamento sobre como migrar para o GitHub

Nossa equipe de {% data variables.product.prodname_professional_services_team %} fornece uma série de serviços de treinamento, bootcamps e apenas aconselhamento geral para ajudar a(s) sua(s) equipe(s) durante todo o processo de implementação. Para obter mais informações, confira "[Serviços e suporte do GitHub](/admin/advanced-security/overview-of-github-advanced-security-deployment#github-services-and-support)".

Para ajudar as suas equipes, aqui está um resumo da documentação relevante do GitHub.

Para conhecer a documentação sobre como habilitar o GHAS, consulte:
  - "[Como habilitar recursos do Advanced Security](/get-started/learning-about-github/about-github-advanced-security)"
  - "[Como gerenciar as configurações de segurança e análise da sua organização](/organizations/keeping-your-organization-secure/managing-security-and-analysis-settings-for-your-organization)"
  - "[Como gerenciar as configurações de segurança e análise do seu repositório](/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-security-and-analysis-settings-for-your-repository)"

Para conhecer a documentação sobre como migrar para o GitHub, consulte:
  - "[Como importar o código-fonte para o GitHub](/github/importing-your-projects-to-github/importing-source-code-to-github)"

Para ler a documentação sobre como começar a usar o GitHub, consulte:
  - "[Introdução](/get-started)"

### <a name="step-3-help-your-company-manage-change"></a>Etapa 3: Ajude a sua empresa a gerenciar as alterações

Na etapa 4 da segunda fase, recomendamos que você atualize o plano inicial de implementação com base nos seus aprendizados do(s) projeto(s) piloto. Certifique-se de que você continue atualizando seu plano à medida que implementa quaisquer alterações organizacionais necessárias para implementar o GHAS com sucesso na sua empresa.

A implementação bem-sucedida do GHAS e a adoção das práticas recomendadas nos fluxos de trabalho diários dependem de garantir que suas equipes entendem por que é necessário incluir a segurança em seu trabalho.

### <a name="step-4-continued-customization"></a>Passo 4: Personalização contínua

A configuração e personalização do GHAS não estão completas até que sejam implementadas em toda a sua empresa. Outras alterações na configuração personalizada devem continuar a ser feitas ao longo do tempo para garantir que o GHAS continue a apoiar as necessidades de alteração da sua empresa.

À medida que a sua equipe torna-se mais experiente e qualificada com GHAS ao longo do tempo, isso criará oportunidades adicionais para uma melhor personalização.
