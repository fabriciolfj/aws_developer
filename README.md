# Aws developer

## Regiões
 - aonde encontra-se um grupo de data centers
 
### Zone de disponibilidade
- aonde encontra-se os data centers de uma região

### Critérios para escolha de uma região
- compliance
- latência -> escolher regiões aonde meus usuários estão
- serviços -> nem todas as regiões possuem todos os serviços
- preço -> muda conforme a região

### Aws points of presence (pontos de presença)
- uma forma de entregar sua aplicação mais próximo do usuário (conjunto de usuários) em uma região específica

## IAM
- identificação e gerenciamento de acesso -> é um serviço global
- serve para darmos permissões aos nosso usuários a determinados serviços e o que podem fazer neles
- podemos criar grupos de permissões e vincular usuários neles
- cada usuário pode pertencer a mais de uma grupo
- as permissões vinculadas ao grupo, função ou usuário são chamdas de policys (políticas)
- as policys tem um formato json, descreve as permissões do usuário em relação aos serviços
- como boa prática, devemos seguir o permissionamento minimo, ou seja, dê permissão apenas o que o usuário realmente precisa.
- um ponto importante que grupos não podem ter outros grupos

## Route53
- podemos registrar um dominio e usar ele como um alias (apelido) vinculado dominio criado para o load balance
- dessa forma ao bater no dominio nosso, ele redirecionará ao load balance
- no arquivo criar-route-53.txt explica como efetuar tal processo.

## Organizações da aws
- serviço oferecido pela aws, com intuito de administrar/gerenciar centralmente várias contas diferentes
- existe a conta raiz, conta de gerenciamento e contas membros

### Conta raiz
- conta principal
- abaixo segue as principais desvantagens no uso da conta root:
  - todos os novos usuários precisaram passar pela conta root
  - segregar ambientes por região é uma má pratica
  - dificuldade para gerar relatórios de faturamento por região
  - conta principal exposta 

### Contas membros e unidades organizacionais (OUs)
- essas contas são criadas para havar uma segregação de funções e responsabilidades
- ous são usadas para agrupar contas membro
- elas podem herdar a estrutura organizacional, mas não se limita a ela
- com o uso dessas contas, a conta root passará ser acessível somente pelo usuario root
- cada conta membro serve a um propósito específico
- por exemplo:
  -  conta membro para identidade, onde todos os usuários, funções e grupos do iam serão criados
  -  conta de desenvolvimento
  -  conta de homologação
  -  conta de produção 
