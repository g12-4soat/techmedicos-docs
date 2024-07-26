<p dir="auto"><img src="https://github.com/g12-4soat/techmedicos-iac/blob/main/docs/Imagem/logo-techmedicos.png" alt="TECHMEDICOS" title="TECHMEDICOS" align="right" height="60" style="max-width: 100%;"></p>

# Tech Medicos Docs
Projeto Hackaton

Repositório dedicado às documentações do Hackaton da FIAP - Turma 4SOAT.

## Problema

A Health&Med, uma startup inovadora no setor de saúde, está desenvolvendo um novo sistema que irá revolucionar a Telemedicina no país. Atualmente, a startup oferece a possibilidade de agendamento de consultas e realização de consultas online (Telemedicina) por meio de sistemas terceiros como Google Agenda e Google Meetings. 

Recentemente, a empresa recebeu um aporte e decidiu investir no desenvolvimento de um sistema proprietário, visando proporcionar um serviço de maior qualidade, segurança dos dados dos pacientes e redução de custos. O objetivo é criar um sistema robusto, escalável e seguro que permita o gerenciamento eficiente desses agendamentos e consultas. Além de conter as funcionalidades de agendamento e realização de consultas online, o sistema terá o diferencial de uma nova funcionalidade: o Prontuário Eletrônico. 

O Prontuário Eletrônico permitirá o armazenamento e compartilhamento de documentos, exames, cartão de vacinas, e outros registros médicos entre as partes envolvidas, garantindo maior assertividade nos diagnósticos.
Para viabilizar o desenvolvimento de um sistema que esteja em conformidade com as melhores práticas de qualidade e arquitetura de software, a Health&Med contratou os alunos do curso (SOAT) para fazer a análise do projeto e a arquitetura do software.

<p dir="auto">Fonte: <a href="https://www.fiap.com.br/" rel="nofollow">FIAP</a></p>

## Proposta

A proposta é desenvolver um sistema de Telemedicina robusto e escalável, integrando funcionalidades de agendamento de consultas, realização de consultas online e um Prontuário Eletrônico seguro. O sistema será desenhado para garantir qualidade no serviço, segurança dos dados dos pacientes, redução de custos operacionais  e uma nova forma de revolucionar a telemedicina. O grupo G12 da turma 4SOAT da Pós Tech em Software Architecture foi contratado para desenvolver uma solução robusta que atenda as demandas do mercado de telemedicina.

# Documentação

<details>
  <summary>Requisitos Funcionais</summary>

  ## Entregáveis

1. <b>Autenticação do Usuário (Médico)</b>:
    - O sistema deve permitir que o médico faça login usando o número de CRM e uma senha.
2. <b>Cadastro/Edição de Horários Disponíveis (Médico)</b>:
    - O sistema deve permitir que o médico faça login usando o número de CRM e uma senha.
3. <b>Aceite ou Recusa de Consultas Médicas (Médico)</b>:
    - O médico deve poder aceitar ou recusar consultas médicas agendadas.
4. <b>Autenticação do Usuário (Paciente)</b>:
    - O sistema deve permitir que o paciente faça login usando um e-mail, CPF e uma senha.
5. <b>Busca por Médicos (Paciente)</b>:
    - O sistema deve permitir que o paciente visualize a lista de médicos disponíveis, utilizando filtros como especialidade, distância (em kms) e avaliação.
6. <b>Agendamento de Consultas (Paciente)</b>:
    - Após selecionar o médico, o paciente deve poder visualizar a agenda do médico e o valor da consulta, e efetuar o agendamento.
    - O usuário paciente poderá cancelar a consulta mediante justificativa.
7. <b>Teleconsulta</b>:
    - A consulta agendada deve criar um link de reunião online de duração padrão de 50 minutos que será utilizado pelo usuário e pelo médico no dia da consulta.
8. <b>Prontuário Eletrônico</b>
    - <b>Acesso e Upload</b>:
      - O paciente deve poder acessar seu prontuário eletrônico e fazer o upload de arquivos, como exames e laudos médicos.
    - <b>Gestão de Compartilhamento</b>:
      - O paciente deve poder compartilhar seu prontuário com médicos, definindo quais arquivos ou grupos de arquivos serão acessíveis e por quanto tempo.

<p dir="auto">Fonte: <a href="https://www.fiap.com.br/" rel="nofollow">FIAP</a></p>
</details>

<details>
  <summary>Requisitos Não Funcionais</summary>

   ## Entregáveis
- <b>Alta Disponibilidade</b>:
  - O sistema deve estar disponível 24/7 devido à sua natureza crítica no setor de saúde.
- <b>Escalabilidade</b>:
  - O sistema deve ser capaz de lidar com alta demanda, especialmente para profissionais muito procurados.
  - O sistema deve suportar até 20.000 usuários simultâneos em horários de pico.
- <b>Segurança</b>:
  - O prontuário eletrônico deve possuir alta camada de segurança para prevenir falhas no compartilhamento de documentos.
  - A proteção dos dados sensíveis dos pacientes deve seguir as melhores práticas de segurança da informação.

<p dir="auto">Fonte: <a href="https://www.fiap.com.br/" rel="nofollow">FIAP</a></p>
</details>

<details>
  <summary>Entregáveis Mínimos</summary>
  
  ## Requisitos
  1. **Desenho da Solução MVP**
      - O sistema deve estar disponível 24/7 devido à sua natureza crítica no setor de saúde.
      - Descrição de como os requisitos não funcionais serão atendidos.

  2. **Demonstração da Infraestrutura na Cloud**
      - Mostrando a aplicação funcionando na infraestrutura de nuvem, com exemplos de uso real (como chamadas de API).

  3. **Demonstração da Infraestrutura na Cloud**
      - Explicação e demonstração do pipeline de deploy da aplicação.

  4. **Demonstração do MVP**: Aplicação executando na nuvem, os itens de 1 a 6 dos requisitosfuncionais, contemplando:
      - Autenticação do Usuário (Médico).
      - Cadastro/Edição de Horários Disponíveis (Médico).
      - Aceite ou Recusa de Consultas Médicas (Médico).
      - Autenticação do Usuário (Paciente).
      - Busca por Médicos (Paciente).
      - Agendamento de Consultas (Paciente).

 <p dir="auto">Fonte: <a href="https://www.fiap.com.br/" rel="nofollow">FIAP</a></p>   
</details>

<details>
  <summary>Solução MVP</summary>

  ## Arquitetura Sistêmica
A aplicação possuí atualmente uma estrutura monolítica que está modularizada, visando como objetivo implementar uma estrutura de micro serviços no decorrer do projeto. Utilizamos o Github para gerenciar todo o código fonte, implementando automações CI/CD através do Github Actions. Além disso, fazemos uso do DockerHub como Container Registry para gerenciar as imagens de containers do projeto e Terraform para realizar o provisionamento da infrestrutura como código. Todos os nossos serviços internos são gerenciados pelo Cloud AWS, que realiza a orquestração de todos os recursos da aplicação.

- <b>API</b>: Tem como responsabilidade o recebimento e envio de requisições REST para a aplicação Tech Médicos, através do recurso EKS da Cloud AWS. A API facilita a integração e a comunicação entre usuários e a plataforma hospedada no Amazon EKS, garantindo uma experiência de uso eficiente e confiável para os clientes da aplicação.
- <b>Auth</b>: Serviço responsável pela autenticação do usuário via JWT, no qual utiliza Lambda Auth que faz a comunicação com Cognito. Este serviço garante a segurança das credenciais dos usuários, facilitando o acesso controlado aos recursos da aplicação e proporcionando uma experiência de usuário fluida e protegida.
- <b>Dynamo DB</b>: Banco de dados não relacional cuja responsabilidade é cuidar do armazenamento de dados. O DynamoDB oferece escalabilidade sob demanda, baixa latência e alta disponibilidade, sendo ideal para a aplicação Tech Medicos que necessita de um armazenamento confiável e eficiente na nuvem.

  <img src="https://github.com/g12-4soat/techmedicos-docs/blob/main/Imagens/TechMedicosArchitectureMVP-arch-system.png" style="max-width: 100%;">
  
  ## Arquitetura Monolítica Modular
Optamos por uma arquitetura monolítica modular, pois é o tipo arquitetônico mais adequado para um projeto MVP. Essa arquitetura visa demonstrar os recursos utilizados na AWS pelo projeto Tech Médicos.

- <b>AWS Cloud</b>: A AWS Cloud é uma infraestrutura global de serviços de computação em nuvem oferecida pela Amazon Web Services (AWS). Fornece uma plataforma robusta e escalável para hospedar aplicativos, armazenar dados e executar operações de computação sem a necessidade de investimentos significativos em infraestrutura física. A AWS Cloud permite às empresas escalar recursos conforme a demanda, aumentar a agilidade operacional e reduzir custos de manutenção de hardware.
    
- <b>Região da Nuvem AWS</b>: Uma Região da AWS é uma área geográfica que contém várias Zonas de Disponibilidade (AZs) da AWS, onde os serviços da AWS são hospedados. Cada Região é composta por duas ou mais AZs isoladas fisicamente, que são conectadas por redes de baixa latência. A escolha da Região da AWS é importante para garantir baixa latência e alta disponibilidade dos serviços, além de cumprir requisitos de conformidade e residência de dados. Na aplicação Tech Medicos optamos em hospedar os recursos na região us-east-1 na Virgínia do Norte, que é a região mais ecônomica da AWS.
    
- <b>VPC AWS (Amazon Virtual Private Cloud)</b>: A Amazon Virtual Private Cloud (VPC) é um serviço que permite criar uma rede virtual isolada na AWS. Ela possibilita que você configure um ambiente de rede personalizado, incluindo subnets, tabelas de rotas e gateways, e controle completamente o tráfego de entrada e saída. A VPC é essencial para separar recursos de aplicativos em diferentes redes, implementar políticas de segurança personalizadas e conectar a rede local à nuvem de forma segura e controlada. Devido a uma limitação na utilização de recursos do AWS Academy consumimos a VPC padrão do ambiente. 
  
- <b>Zona de Disponibilidade (AZ - Availability Zone)</b>: Uma Zona de Disponibilidade (AZ) é um data center ou grupo de data centers da AWS em uma Região específica. Cada AZ é isolada para proteção contra falhas em outras AZs, garantindo que aplicativos e dados permaneçam disponíveis mesmo em casos de falha de hardware ou manutenção planejada. As AZs são fundamentais para implementar arquiteturas de alta disponibilidade e tolerância a falhas em sistemas distribuídos na AWS Cloud.

- <b>Subnets</b>: Subnets são segmentos de uma VPC onde você pode lançar recursos como instâncias EC2, bancos de dados RDS, entre outros. Elas são essenciais para organizar e gerenciar a rede dentro da infraestrutura da AWS.
  - <b>Subnets Públicas</b>: As subnets públicas estão configuradas para ter acesso direto à Internet através de um Gateway de Internet. São utilizadas para hospedar recursos que precisam de conectividade direta com a Internet, como servidores web ou aplicativos que precisam ser acessíveis publicamente. Isso permite que os recursos nas subnets públicas recebam tráfego da Internet e respondam diretamente aos pedidos externos.
  - <b>Subnet Privada</b>: Subnets privadas não têm acesso direto à Internet. Elas dependem de um NAT Gateway ou NAT Instance para acessar recursos externos, como atualizações de software ou integrações com serviços na Internet. As subnets privadas são usadas para hospedar recursos sensíveis que não devem ser acessíveis publicamente, aumentando a segurança ao restringir o acesso direto a esses recursos.
  - <b>Diferença entre Subnets Públicas e Privadas</b>: A principal diferença entre subnets públicas e privadas reside na acessibilidade à Internet. Subnets públicas permitem acesso direto à Internet, enquanto subnets privadas dependem de um gateway NAT para acesso externo. Essa distinção permite aos administradores de sistema controlar o tráfego e gerenciar a exposição de aplicativos e dados, garantindo que recursos sensíveis permaneçam protegidos contra acessos não autorizados.

- <b>API Gateway</b>: O API Gateway é utilizado para criar, publicar, manter, monitorar e proteger as APIs Tech Medicos de forma segura. É essencial para fornecer pontos de acesso seguros e escaláveis para os serviços Tech Medicos, permitindo gerenciar autorizações, limitações de taxa e transformações de dados, entre outros.
  - <b>API Gateway da Lambda Auth</b>: Tem como responsabilidade gerenciar o serviço de autorização e autenticação da aplicação Tech Medicos.
  - <b>API Gateway da API Tech Medicos</b>: Lida com o mapeamento dos endpoints internos da aplicação Tech Medicos.

- <b>AWS Lambda</b>: AWS Lambda é necessária para realizar processamento de eventos de forma escalável e sem preocupações com a infraestrutura subjacente, sendo reutilizável também na execução de microserviços, processamento de dados em tempo real, entre outras aplicações. Responsável pelo engine do serviço de autorização e autenticação do usuário na aplicação Tech Medicos, tendo comunicação direta com o serviço responsável pelas ações de segurança de acesso do usuário.
  
- <b>Amazon Cognito</b>: Amazon Cognito é um serviço de autenticação, autorização e gerenciamento de usuários para aplicativos web e móveis. Oferece integração com provedores de identidade externos e permite criar pools de usuários para autenticação segura, gestão de perfis e sincronização de dados. Serviço que lida com gerenciamento de maneira geral da aplicação Tech Medicos, como por exemplo segregação por pools de usuários paciente e médico.

- <b>AWS Secrets Manager</b>: AWS Secrets Manager ajuda a proteger o acesso a informações sensíveis, como senhas, chaves de API e certificados. Permite gerenciar, rotacionar e recuperar esses segredos de forma segura, essencial para sistemas que necessitam armazenar e acessar informações confidenciais de forma centralizada. Armazena informações sensíveis que são cruciais para o funcionamento total da aplicação.

- <b>VPC Link</b>: O VPC Link é um serviço que permite integrar APIs privadas hospedadas em uma Amazon Virtual Private Cloud (VPC) com o API Gateway da AWS. Ele proporciona conectividade segura e direta entre o API Gateway e os recursos privados na VPC, permitindo que aplicativos acessem serviços internos de forma controlada e protegida, sem expor esses recursos diretamente à Internet. Isso é essencial para manter a segurança e a integridade dos dados ao permitir a comunicação segura entre sistemas externos e internos dentro de uma infraestrutura VPC. 

- <b>Load Balancer</b>: Load Balancer é um serviço que distribui o tráfego de entrada de aplicações entre múltiplas instâncias, garantindo alta disponibilidade e escalabilidade. Existem diferentes tipos de Load Balancers na AWS Cloud.
  - <b>Elastic Load Balancing (ELB)</b>: Balanceia automaticamente o tráfego de entrada entre múltiplas instâncias EC2, garantindo que a carga seja distribuída de forma equilibrada e eficiente.
  - <b>Application Load Balancer (ALB)</b>: Ideal para rotear tráfego para múltiplos destinos baseados em conteúdo em nível de aplicação (como HTTP/HTTPS), como a aplicação Tech Medicos.
  - <b>Network Load Balancer (NLB)</b>: Distribui o tráfego TCP/UDP para instâncias EC2 em nível de rede, adequado para cargas de trabalho que requerem alta taxa de transferência e baixa latência.

- <b>Amazon EKS (Elastic Kubernetes Service)</b>: Amazon EKS facilita a execução de aplicativos Kubernetes na AWS, gerenciando a infraestrutura necessária para clusters Kubernetes. É utilizado na orquestração de contêineres escalável, permitindo implementar, gerenciar e escalar a aplicação Tech Medicos de maneira contêinerizados com facilidade.
  
- <b>Amazon EC2 (Elastic Compute Cloud)<b>: Serviço da AWS Cloud que oferece capacidade computacional escalável na nuvem. Permite aos usuários provisionar e dimensionar facilmente instâncias de servidores virtuais conforme necessário. O EC2 é amplamente utilizado em sistemas para hospedar aplicativos, executar cargas de trabalho computacionais, processar dados em lotes, entre outras tarefas. Sua flexibilidade permite escolher tipos de instâncias com diferentes recursos computacionais, memória e armazenamento, adaptando-se às necessidades específicas de cada aplicação. O EC2 proporciona controle completo sobre o ambiente de execução da aplicação Tech Medicos, facilitando a implementação e a administração de infraestruturas complexas de maneira eficiente na nuvem.

- <b>Dynamo DB</b>: Serviço de banco de dados NoSQL totalmente gerenciado pela AWS Cloud. Ele oferece armazenamento de dados de baixa latência e alto desempenho, escalabilidade automática e suporte integrado para replicação multi-região. DynamoDB é recomendado para aplicações que precisam de acesso rápido e previsível a grandes volumes de dados, como a aplicação Tech Medicos. Sua flexibilidade e capacidade de dimensionamento automático tornam-no adequado para cenários onde a escalabilidade e a disponibilidade são críticas, permitindo aos desenvolvedores focar no desenvolvimento de aplicativos sem se preocupar com a infraestrutura do banco de dados.

- <b>AWS S3 (Amazon Simple Storage Service)</b>: É um serviço de armazenamento de objetos altamente escalável e durável. Ele é projetado para armazenar e recuperar qualquer quantidade de dados de forma segura através da internet. O S3 é para armazenamento de dados estáticos de websites, arquivos de mídia, dados de logs, outros tipos de dados não estruturados e backups, como por exemplo, a aplicação Tech Medicos que armazena o arquivo tf.state do Terraform que contém o estado atual da infraestrutura gerenciada e registra informações sobre os recursos provisionados na AWS Cloud. O S3 oferece alta disponibilidade, redundância de dados em várias zonas de disponibilidade, e integração fácil com outros serviços AWS Cloud, tornando-se uma solução robusta para gerenciamento e armazenamento de dados na nuvem da aplicação Tech Medicos.

- <b>IAM Role (Identity and Access Management)</b>: IAM Roles são usados para conceder permissões seguras e temporárias para entidades que precisam acessar recursos AWS. Eles são essenciais para garantir a segurança e a conformidade na aplicação Tech Medicos, permitindo gerenciar o acesso a recursos de forma granular e segura. Na aplicação Tech Medicos utiliza o LabRole padrão do AWS Academy.

- <b>Amazon CloudWatch</b>: Amazon CloudWatch é um serviço de monitoramento e observabilidade do Tech Medicos que coleta e acompanha métricas, logs e eventos em tempo real. É usado para monitorar a saúde e o desempenho da aplicação, detectar e diagnosticar problemas, e tomar ações automatizadas com base em condições definidas.
  
  <img src="https://github.com/g12-4soat/techmedicos-docs/blob/main/Imagens/TechMedicosArchitectureMVP-aws-micro-service.png" alt="TECHLANCHES" title="TECHLANCHES" style="max-width: 100%;">

- <b>Estimativa de custos AWS </b>: https://github.com/g12-4soat/techmedicos-docs/blob/main/docs/TechMedicos%20-%20MVP%20-%20Calculadora%20de%20Pre%C3%A7os%20da%20AWS.pdf
</details>
<details>
  <summary>Solução Completa</summary>

   ## Arquitetura Sistêmica
A aplicação completa terá uma estrutura em microserviços, que representa a evolução da estrutura do MVP, que é um monólito modularizado. Para a solução completa, todos os recursos implementados no MVP serão reutilizados como Github, automações CI/CD com Github Actions, DockerHub como Container Registry, recursos implementados na AWS Cloud entre outros. Como novidades, introduzimos o SonarCloud para análise de código e cobertura de testes em todos os microserviços, o padrão SAGA para garantir a consistência e integridade dos dados com atomicidade na aplicação Tech Medicos, OWASP para aumentar a segurança, identificar e mitigar as vunerabilidades de seguranças conhecidas. A conformidade com a LGPD que visa garantir que o tratamento de dados seja realizado de forma transparente, segura e em conformidade com a legislação. O relátorio de RIPD para proporcionar uma visão clara e detalhada sobre como uma organização coleta, armazena, usa e protege os dados pessoais de indivíduos. Por fim, a evolução da arquitetura dentro do AWS Cloud com a utilização de novos recursos fundamentais para garantir que a aplicação Tech Medicos tenha alta disponibilidade, escalabilidade, segurança, resiliência, observabilidade e monitoramento. 
 
- <b>AWS EKS</b>: O microserviço de consulta será responsável pelo gerenciamento completo das consultas incluindo agendamentos, busca por médicos, histórico de consultas e outras funcionalidades. O serviço de gestão de médicos cuidará da agenda, horários e disponibilidade dos profissionais de medicina com funcionalidades de cadastro e edição de agenda médica. O prontuário funcionará como o núcleo central dos dados do paciente, armazenando informações pessoais, registros médicos, exames e diagnósticos. O serviço de usuário será responsável por auxiliar no controle de acesso, gerenciando diferentes tipos de usuários na aplicação Tech Médicos e contém um Service Worker que tem como responsabilidade consumir a fila ReversaoCadastroUsuario pelo serviço de usuário para realizar a reversão do cadastro de usuário. Além disso, um microserviço dedicado ao gerenciamento de filas do RabbitMQ que irá auxiliar em todo o processo operacional dentro da aplicação Tech Medicos.

- <b>Dynamo DB</b>: Optamos por utilizar DynamoDB em todos os microserviços da aplicação Tech Médicos devido à sua capacidade de escalabilidade sob demanda, baixa latência e alta disponibilidade. Integramos o DynamoDB nos microserviços de consulta, prontuário, usuário, gestão médica e inativação de usuário, também adicionamos o DAX no microserviço de gestão médica que é um serviço de cache que melhora o desempenho de leitura de bancos de dados NoSQL em memória. No caso dos microserviços relacionados às filas do RabbitMQ, não consideramos necessária essa implementação.

- <b>AWS S3</b>:  O Amazon S3 é um serviço altamente escalável e durável de armazenamento de objetos, projetado para guardar e recuperar grandes volumes de dados de maneira segura pela internet. No microserviço de prontuário, o S3 será utilizado para armazenar os arquivos dos pacientes no prontuário clínico.

- <b>AWS Lambda</b>: Para as Lambdas, implementamos diferentes serviços na aplicação Tech Medicos:
  - <b>Cadastro</b>: Responsável pelo registro do usuário na base de dados de usuário e no AWS Cognito.
  - <b>Auth</b>: Utiliza o AWS Cognito para validar o acesso do usuário paciente ou médico. 
  - <b>Inativação</b>: Garante que o usuário possa inativar seus dados a qualquer momento, seguindo as diretrizes da LGPD.
  - <b>Notificações</b>: Serviço que gerencia o envio de notificações aos usuários, utilizando o AWS SES.
  - <b>Telemedicina</b>: Integra com o Google Workspace para gerar a teleconsulta do paciente.
    
  <p>
    Essas funções Lambdas são essenciais para o funcionamento integrado e seguro da aplicação, atendendo às necessidades específicas dos usuários e cumprindo com as normas de segurança e privacidade estabelecidas.
  </p>

  <img src="https://github.com/g12-4soat/techmedicos-docs/blob/main/Imagens/TechMedicosArchitecture-arch-system.png" style="max-width: 100%;">
  
  ## Arquitetura Microserviços

  Optamos por uma arquitetura de microserviços pois oferece diversos benefícios significativos para a aplicação Tech Medicos. Microserviços dividem a aplicação em componentes independentes e autônomos, cada um focado em realizar uma função específica. Isso proporciona maior flexibilidade no desenvolvimento, permitindo que as equipes do projeto trabalhem de forma independente em cada microserviço. Além disso, os microserviços facilitam a escalabilidade, pois cada serviço pode ser dimensionado individualmente conforme a necessidade. Isso resulta em melhor desempenho e utilização eficiente de recursos. Outro benefício é a resiliência, já que falhas em um microserviço não afetam necessariamente toda a aplicação Tech Medicos, aumentando a disponibilidade do sistema como um todo. Por fim, os microserviços promovem uma arquitetura mais modular e fácil de manter, facilitando a implementação de atualizações e melhorias contínuas na aplicação. A seguir, serão apresentados todos os recursos adicionais na solução completa, ressaltando que todos os recursos existentes no MVP serão reutilizados. Isso garante uma aplicação totalmente sustentável e preparada para expansões futuras.

- <b>AWS Shield</b>: O AWS Shield é um serviço de proteção contra ataques distribuídos de negação de serviço (DDoS) que protege aplicação Tech Medicos na AWS Cloud. Detecta e mitiga automaticamente ataques DDoS direcionados a recursos como ELB (Elastic Load Balancing), CloudFront e Amazon Route 53. O AWS Shield Standard é oferecido gratuitamente para todos os clientes da AWS, enquanto o AWS Shield Advanced oferece proteção mais avançada e suporte dedicado.

- <b>AWS WAF (Web Application Firewall)</b>: O AWS WAF é um firewall de aplicação web que ajuda a proteger a aplicação Tech Medicos contra vulnerabilidades comuns de segurança, como injeção de SQL e cross-site scripting (XSS). Ele permite configurar regras personalizadas para controlar o acesso às suas aplicações web. O AWS WAF pode ser integrado com serviços como o Amazon CloudFront e o Application Load Balancer para filtrar e monitorar o tráfego HTTP e HTTPS.

- <b>CloudFront</b>: O Amazon CloudFront é um serviço de CDN (Content Delivery Network) que distribui conteúdo estático e dinâmico, como imagens, vídeos, scripts e arquivos HTML, para usuários finais com baixa latência e alto throughput. Melhora a velocidade de entrega do conteúdo ao armazená-lo em cache em locais de edge nodes ao redor do mundo. O CloudFront é comumente usado para melhorar a performance e reduzir a carga de servidores de origem, além de proporcionar maior segurança e escalabilidade para a aplicação Tech Medicos.

- <b>Amazon Cognito</b>: Amazon Cognito é um serviço de autenticação, autorização e gerenciamento de usuários para aplicativos web e móveis. Oferece integração com provedores de identidade externos e permite criar pools de usuários para autenticação segura, gestão de perfis e sincronização de dados. Serviço que lida com gerenciamento de maneira geral da aplicação Tech Medicos, como por exemplo segregação por pools de usuários paciente e médico. No Cognito da aplicação Tech Medicos também é utilizado o 2FA com o objetivo de aumentar a segurança ao exigir duas formas distintas de verificação para acessar uma conta e também realiza a comunicação com SES para envio de notificações via e-mail.

- <b>SES (Simple Email Service)</b>: Amazon SES é um serviço de e-mail escalável e econômico para envio e recebimento de e-mails. É usado para integrar e-mails transacionais e de marketing com aplicativos na AWS, garantindo entrega confiável de e-mails para usuários finais. O SES oferece flexibilidade para personalizar conteúdo de e-mail, monitorar estatísticas de entrega e gerenciar listas de destinatários, sendo ideal para a aplicação Tech medicos que precisam de comunicação por e-mail automatizada e eficiente. O SES mantém comunicação com o Cognito para auxiliar no processo de autentição e autorização do usuário.

- <b>AWS Lambda</b>: AWS Lambda é necessária para realizar processamento de eventos de forma escalável e sem preocupações com a infraestrutura subjacente, sendo reutilizável também na execução de microserviços, processamento de dados em tempo real, entre outras aplicações. Responsável pelo engine do serviço de autorização e autenticação do usuário na aplicação Tech Medicos, tendo comunicação direta com o serviço responsável pelas ações de segurança de acesso do usuário.
  - <b>Cadastro</b>: Responsável pelo registro do usuário na base de dados de usuário e no AWS Cognito.
  - <b>Auth</b>: Utiliza o AWS Cognito para validar o acesso do usuário paciente ou médico que estaram segregados por grupos de tipo de usuário dentro user-pool.
  - <b>Inativação</b>: Garante que o usuário possa inativar seus dados a qualquer momento, seguindo as diretrizes da LGPD. Um DynamoDB será utilizado para registrar as solicitações de inativação na base de dados. 
  - <b>Notificações</b>: Serviço que gerencia o envio de notificações aos usuários, utilizando o AWS SES. Responsável por consumir a fila de notificações do RabbitMQ no EKS e enviar as mensagens para seus destinatários.
  - <b>Telemedicina</b>: Integra com o Google Workspace para gerar a teleconsulta do paciente. Será responsável por integrar com o Google Meet para gerar a teleconsulta e com o Google Agenda para adicionar o agendamento da consulta na agenda do usuário.

- <b>Load Balancer</b>: Load Balancer é um serviço que distribui o tráfego de entrada de aplicações entre múltiplas instâncias, garantindo alta disponibilidade e escalabilidade. Na aplicação Tech Médicos, foi implementado um Load Balancer para cada microserviço, com o objetivo de manter a independência e o gerenciamento separado entre eles.

- <b>AWS EKS</b>: O microserviço de consulta será responsável pelo gerenciamento completo das consultas, incluindo agendamentos, histórico e outras funcionalidades. O serviço de gestão de médicos cuidará da agenda, horários e disponibilidade dos profissionais de medicina. O prontuário funcionará como o núcleo central dos dados do paciente, armazenando informações pessoais, registros médicos, exames e diagnósticos. O serviço de usuário será responsável por auxiliar no controle de acesso, gerenciando diferentes tipos de usuários na aplicação Tech Médicos e contém um Service Worker que tem como responsabilidade consumir a fila ReversaoCadastroUsuario pelo serviço de usuário para realizar a reversão do cadastro de usuário. Além disso, um microserviço dedicado ao gerenciamento de filas do RabbitMQ que irá auxiliar em todo o processo operacional dentro da plataforma.
  
  - <b>Consulta</b>:  O microserviço de consulta será responsável pelo gerenciamento completo das consultas incluindo agendamentos, busca por médicos, histórico de consultas e outras funcionalidades. Um DynamoDB será utilizado para registrar as solicitações de agendamento de consulta e consumirá a Secret Manager para auxiliar no processo de autenticação e autorização do usuário dentro da aplicação e por fim um EC2 para provisionar a capacidade computacional.
  - <b>Gestão de Médicos</b>: O serviço de gestão de médicos cuidará da agenda, horários e disponibilidade dos profissionais de medicina com funcionalidades de cadastro e edição de agenda médica. Um DynamoDB será utilizado para registrar as solicitações de agendamento de consulta e consumirá a Secret Manager para auxiliar no processo de autenticação e autorização do usuário dentro da aplicação e por fim um EC2 para provisionar a capacidade computacional.
  - <b>Prontuário</b>:  O prontuário funcionará como o núcleo central dos dados do paciente, armazenando informações pessoais, registros médicos, exames e diagnósticos com funcionalidade como upload de arquivos e compartilhamento de arquivos. O DynamoDB será utilizado para registrar as solicitações de agendamento de consultas e integrará com o Secrets Manager para auxiliar na autenticação e autorização do usuário na aplicação. Um EC2 para provisionar a capacidade computacional necessária. O S3 será responsável pelo armazenamento dos arquivos clínicos, e o KMS será utilizado para criar e gerenciar chaves de criptografia, garantindo a proteção dos dados.
  - <b>Usuário</b>:  O serviço de usuário será responsável por auxiliar no controle de acesso, gerenciando diferentes tipos de usuários na aplicação Tech Médicos. Um DynamoDB será utilizado para registrar as solicitações de agendamento de consulta e consumirá a Secret Manager para auxiliar no processo de autenticação e autorização do usuário dentro da aplicação e por fim um EC2 para provisionar a capacidade computacional.
  - <b>RabbitMQ</b>: Serviço que faz gerenciamento de filas do RabbitMQ que irá auxiliar em todo o processo operacional dentro da aplicação Tech Medicos. Este serviço contém as seguintes filas:
    - <b>ConsultaAtualiza</b>, gerencia os status das consultas;
    - <b>Notificações</b>, consumida pela Lambda de notificações para realizar o envio de e-mails;
    - <b>TelemedicinaGerada</b>, recebe o link da telemedicina gerada e é consumida pelo serviço de consulta.
    - <b>ReversaoCadastroUsuario</b>, consumida pelo serviço de usuário para realizar a reversão do cadastro de usuário.

- <b>Dynamo DB</b>: Serviço de banco de dados NoSQL totalmente gerenciado pela AWS Cloud. Integramos o DynamoDB nos microserviços de consulta, prontuário, usuário, gestão médica e inativação de usuário, também adicionamos o DAX no microserviço de gestão médica que é um serviço de cache que melhora o desempenho de leitura de bancos de dados NoSQL em memória.

- <b>AWS DAX (Amazon DynamoDB Accelerator)</b>: AWS DAX é um serviço de cache para Amazon DynamoDB que acelera a performance de leitura de bancos de dados NoSQL em memória. Ele reduz a latência de acesso a dados e melhora a escalabilidade do DynamoDB ao fornecer cache de consultas frequentes. O DAX é usado para melhorar o desempenho de aplicativos que requerem acesso rápido e consistente aos dados armazenados no DynamoDB, sem comprometer a durabilidade e a integridade dos dados. Utilizado no conexto de gestão de médicos para atender ao requisito não funcional de escalabilidade referente a alta demanda pelos profissionais mais procurados da aplicação Tech Medicos. 

- <b>AWS S3</b>:  O Amazon S3 é um serviço altamente escalável e durável de armazenamento de objetos, projetado para guardar e recuperar grandes volumes de dados de maneira segura pela internet. No microserviço de prontuário, o S3 será utilizado para armazenar os arquivos dos pacientes no prontuário clínico. Além disso, o S3 também armazenará o arquivo tf.state do Terraform, que contém o estado atual da infraestrutura gerenciada e registra informações sobre os recursos provisionados na AWS Cloud, nos arquivos techmedicos-terraform-infra e techmedicos-terraform-gateway, e possuí um KMS para criptografar os arquivos clínicos dos pacientes.

- <b>AWS KMS (AWS Key Management Service)</b>: AWS KMS é um serviço de gerenciamento de chaves que permite criar e controlar o uso de chaves de criptografia para proteger dados e gerenciar sua integridade. Ele facilita a criação e rotação automática de chaves de criptografia, integração com outros serviços AWS para criptografar dados armazenados e transitórios, e oferece controle granular sobre quem pode acessar e usar as chaves. Utilizado no contexto de prontuário para realizar a proteção dos arquivos clinicos de seus pacientes.

  <img src="https://github.com/g12-4soat/techmedicos-docs/blob/main/Imagens/TechMedicosArchitecture-aws-micro-service.png" alt="TECHLANCHES" title="TECHLANCHES" style="max-width: 100%;">

  ## SAGA
  
SAGA é um padrão de design utilizado em sistemas distribuídos para gerenciar transações que envolvem múltiplos serviços. Em vez de executar uma transação longa e complexa em uma única etapa, o padrão divide a transação em uma sequência de operações menores e independentes. Se uma operação falhar, o padrão garante a execução de compensações para reverter as mudanças realizadas pelas operações anteriores, garantindo consistência e integridade dos dados. Esse método melhora a confiabilidade e a resiliência do sistema, facilitando a gestão de transações em ambientes distribuídos.

<b>Saga Coreografada</b>: O objetivo da saga coreografada é coordenar transações distribuídas de forma descentralizada, onde cada serviço participa e comunica o progresso ou falhas, promovendo autonomia entre serviços e evitando um ponto único de falha.

<b>Justificativa</b>: Optamos pelo padrão de Saga coreografada em nosso sistema de microserviços pelos seguintes motivos.

1. **Simplicidade e Menor Sobrecarga de Gerenciamento**: Com poucos serviços e uma equipe única de manutenção, a coreografia é mais simples de implementar e gerenciar.
   
2. **Descentralização e Independência dos Serviços**: Cada serviço reage a eventos de forma autônoma, facilitando o desenvolvimento, a implantação e a escalabilidade independentes.

3. **Redução de Acoplamento**: A comunicação por eventos promove um baixo acoplamento entre serviços, permitindo modificações e evoluções sem impactos significativos em outros componentes.

4. **Escalabilidade e Resiliência**: A ausência de um orquestrador central elimina pontos únicos de falha e melhora a capacidade de resposta sob alta carga.

5. **Ajuste ao Tamanho e Complexidade do Projeto**: Para nosso contexto, com um número limitado de serviços, a coreografia evita a sobrecarga de um orquestrador central, proporcionando uma solução proporcionalmente adequada.

  <img src="https://github.com/g12-4soat/techlanches-docs/blob/main/docs/fase5/TechLanchesArchitecture-saga-coreografada.png" alt="TECHLANCHES" title="TECHLANCHES" style="max-width: 100%;">

- <b>Estimativa de custos AWS </b>: https://github.com/g12-4soat/techmedicos-docs/blob/main/docs/TechMedicos%20-%20Solu%C3%A7%C3%A3o%20Completa%20-%20Calculadora%20de%20Pre%C3%A7os%20da%20AWS.pdf
  
</details>

# Vídeo Hackaton
<details>
  <summary>URL</summary>
<p>Link para vídeo hackaton: ADD LINK </p>
</details>

# Documentação do Miro
<details>
  <summary>URL</summary>
<p>Link para a documentação do miro: https://miro.com/app/board/uXjVKy9CWhY=/?share_link_id=473372729787 </p>
</details>