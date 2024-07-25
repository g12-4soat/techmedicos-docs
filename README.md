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

  1. **Autenticação do Usuário (Médico)**: O sistema deve permitir que o médico faça login usando o número de CRM e uma senha.
  2. **Cadastro/Edição de Horários Disponíveis (Médico)**: O sistema deve permitir que o médico faça login usando o número de CRM e uma senha.
  3. **Aceite ou Recusa de Consultas Médicas (Médico)**: O médico deve poder aceitar ou recusar consultas médicas agendadas.
  4. **Autenticação do Usuário (Paciente)**: O sistema deve permitir que o paciente faça login usando um e-mail, CPF e uma senha.
  5. **Busca por Médicos (Paciente)**: O sistema deve permitir que o paciente visualize a lista de médicos disponíveis, utilizando filtros como especialidade, distância (em kms) e avaliação.
  6. **Agendamento de Consultas (Paciente)**: Após selecionar o médico, o paciente deve poder visualizar a agenda do médico e o valor da consulta, e efetuar o agendamento.
  7. **Agendamento de Consultas (Paciente)**: O usuário paciente poderá cancelar a consulta mediante justificativa.
  8. **Teleconsulta**: A consulta agendada deve criar um link de reunião online de duração padrão de 50 minutos que será utilizado pelo usuário e pelo médico no dia da consulta.
  9. **Prontuário Eletrônico (Acesso e Upload)**: O paciente deve poder acessar seu prontuário eletrônico e fazer o upload de arquivos, como exames e laudos médicos.
  10. **Prontuário Eletrônico (Gestão de Compartilhamento)**: O paciente deve poder compartilhar seu prontuário com médicos, definindo quais arquivos ou grupos de arquivos serão acessíveis e por quanto tempo.

Para o MVP foi implementado os requisitos ...

<p dir="auto">Fonte: <a href="https://www.fiap.com.br/" rel="nofollow">FIAP</a></p>
</details>

<details>
  <summary>Requisitos Não Funcionais</summary>

   ## Entregáveis
   1. **Alta Disponibilidade**: O sistema deve estar disponível 24/7 devido à sua natureza crítica no setor de saúde.
   2. **Escalabilidade**: O sistema deve ser capaz de lidar com alta demanda, especialmente para profissionais muito procurados.
   3. **Escalabilidade**: O sistema deve suportar até 20.000 usuários simultâneos em horários de pico.
   4. **Segurança**: O prontuário eletrônico deve possuir alta camada de segurança para prevenir falhas no compartilhamento de documentos.
   5. **Segurança**: A proteção dos dados sensíveis dos pacientes deve seguir as melhores práticas de segurança da informação.

<p dir="auto">Fonte: <a href="https://www.fiap.com.br/" rel="nofollow">FIAP</a></p>
</details>

<details>
  <summary>MVP</summary>

  ## Arquitetura Sistêmica
A aplicação possuí atualmente uma estrutura monolítica que está modularizada, visando como objetivo implementar uma estrutura de micro serviços no decorrer do projeto. Utilizamos o Github para gerenciar todo o código fonte, implementando automações CI/CD através do Github Actions. Além disso, fazemos uso do DockerHub como Container Registry para gerenciar as imagens de containers do projeto e Terraform para realizar o provisionamento da infrestrutura como código. Todos os nossos serviços internos são gerenciados pelo Cloud AWS, que realiza a orquestração de todos os recursos da aplicação.

- <b>API</b>: Tem como responsabilidade o recebimento e envio de requisições REST para a aplicação Tech Medicos, atraves do recurso EKS da Cloud AWS.
- <b>Auth</b>: Serviço responsável pela autenticação do usuário via JWT, no qual utiliza Lambda Auth que faz a comunicação com Cognito.
- <b>Dynamo DB</b>: Banco de dados não relacional cujo a responsabilidade é cuidar do armazenamento de dados.

  <img src="https://github.com/g12-4soat/tech-lanches/blob/main/docs/arquitetura-sistemica.png" style="max-width: 100%;">
  
  ## Arquitetura Monolítica Modular
Optamos por uma arquitetura monolítica modular, pois é o tipo arquitetônico mais adequado para um projeto MVP. Essa arquitetura visa demonstrar os recursos utilizados na AWS pelo projeto Tech Médicos.

  - <b>API</b>: Tem como responsabilidade o recebimento e envio de requisições REST para a aplicação Tech Medicos, atraves do recurso EKS da Cloud AWS.
  - <b>Auth</b>: Serviço responsável pela autenticação do usuário via JWT, no qual utiliza Lambda Auth que faz a comunicação com Cognito.
  - <b>Dynamo DB</b>: Banco de dados não relacional cujo a responsabilidade é cuidar do armazenamento de dados.

  - <b>API Gateway</b>: O API Gateway é utilizado para criar, publicar, manter, monitorar e proteger APIs de forma segura. É essencial em sistemas para fornecer pontos de acesso seguros e escaláveis para serviços e aplicativos, permitindo gerenciar autorizações, limitações de taxa e transformações de dados.

  - <b>AWS Lambda</b>: AWS Lambda permite executar código sem provisionar ou gerenciar servidores. É ideal para sistemas onde é necessário processamento de eventos de forma escalável e sem preocupações com a infraestrutura subjacente, sendo usado para execução de microserviços, processamento de dados em tempo real, entre outras aplicações.

  - <b>Amazon Cognito</b>: Amazon Cognito é um serviço de autenticação, autorização e gerenciamento de usuários para aplicativos web e móveis. Ele oferece integração com provedores de identidade externos e permite criar pools de usuários para autenticação segura, gestão de perfis e sincronização de dados.

  - <b>AWS Secrets Manager</b>: AWS Secrets Manager ajuda a proteger o acesso a informações sensíveis, como senhas, chaves de API e certificados. Ele permite gerenciar, rotacionar e recuperar esses segredos de forma segura, essencial para sistemas que necessitam armazenar e acessar informações confidenciais de forma centralizada.

  - <b>Amazon EKS (Elastic Kubernetes Service)</b>: Amazon EKS facilita a execução de aplicativos Kubernetes na AWS, gerenciando a infraestrutura necessária para clusters Kubernetes. É usado em sistemas que requerem orquestração de contêineres escalável, permitindo implementar, gerenciar e escalar aplicativos contêinerizados com facilidade.

  - <b>IAM Role (Identity and Access Management)</b>: IAM Roles são usados para conceder permissões seguras e temporárias para entidades que precisam acessar recursos AWS. Eles são essenciais para garantir a segurança e a conformidade em sistemas, permitindo gerenciar o acesso a recursos de forma granular e segura.

  - <b>Amazon CloudWatch</b>: Amazon CloudWatch é um serviço de monitoramento e observabilidade que coleta e acompanha métricas, logs e eventos em tempo real. É usado para monitorar a saúde e o desempenho de sistemas, detectar e diagnosticar problemas, e tomar ações automatizadas com base em condições definidas.

  
  <img src="https://github.com/g12-4soat/techlanches-docs/blob/main/docs/fase5/TechLanchesArchitecture-aws-micro-service.png" alt="TECHLANCHES" title="TECHLANCHES" style="max-width: 100%;">
</details>
<details>
  <summary>Completo</summary>

   ## Arquitetura Sistêmica
A aplicação possuí atualmente uma estrutura monolítica que está modularizada, visando como objetivo implementar uma estrutura de micro serviços no decorrer do projeto. Utilizamos o Github para gerenciar todo o código fonte, implementando automações CI/CD através do Github Actions. Além disso, fazemos uso do DockerHub como Container Registry para gerenciar as imagens de containers do projeto. Todos os nossos serviços internos são gerenciados pelo Cluster Kubernetes, que realiza a orquestração de todos os recursos da aplicação.

- <b>API</b>: Tem como responsabilidade o recebimento e envio de requisições REST para a aplicação Tech Lanches.
- <b>Fila de Pedidos</b>: Serviço do tipo "background service" que executa e gerencia a fila de pedidos.
- <b>Application Core</b>: Responsável por implementar os principais requisitos da aplicação.
- <b>SQL Server</b>: Banco de dados relacional cujo a responsabilidade é cuidar do armazenamento de dados.
- <b>ACL Pagamento</b>: Intermediário entre a comunicação da API com o serviço externo do Mercado Pago, visando a proteção da API para que não seja impactado diretamente na aplicação caso algo no serviço seja modificado.
- <b>[Mercado Pago](https://www.mercadopago.com.br/developers/pt)</b>: Serviço externo utilizado para efetuação de pagamento dos pedidos. Para mais informações sobre a implementação clique no nome do serviço.
- <b>[NGROK](https://ngrok.com/)</b>: Utilizamos como intermediário para realizar a comunicação do Mercado Pago com a API Tech Lanches, atráves de uma URL estática que é enviada ao webhook do Mercado Pago, que após a efetivação do pagamento é enviado uma requisição para o NGrok com o status do pagamento que faz o redirecionamento para o endpoint responsável da API Tech Lanches. Para mais informações clique no nome da ferramenta.
- <b>[RABBITMQ](https://www.rabbitmq.com/)</b>: Utilizado para auxiliar a fila de pedido no controle e gerenciamento. Para mais informações clique no nome da ferramenta.

  <img src="https://github.com/g12-4soat/tech-lanches/blob/main/docs/arquitetura-sistemica.png" style="max-width: 100%;">
  
  ## Arquitetura Monolítica Modular
  <img src="https://github.com/g12-4soat/techlanches-docs/blob/main/docs/fase5/TechLanchesArchitecture-aws-micro-service.png" alt="TECHLANCHES" title="TECHLANCHES" style="max-width: 100%;">

  ## Diagrama Saga Coreografada
  <img src="https://github.com/g12-4soat/techlanches-docs/blob/main/docs/fase5/TechLanchesArchitecture-saga-coreografada.png" alt="TECHLANCHES" title="TECHLANCHES" style="max-width: 100%;">
</details>

# Vídeo Hackaton
<details>
  <summary>URL</summary>
<p>Link para vídeo hackaton: ADD LINK </p>
</details>
