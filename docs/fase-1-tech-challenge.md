# Tech Challenge — Fase 1

O Tech Challenge é o projeto da fase que engloba os conhecimentos obtidos em todas as disciplinas. Esta atividade deve, a princípio, ser desenvolvida em grupo e vale 90% da nota desta fase.

## Desafio

Uma oficina mecânica de médio porte, especializada em manutenção de veículos, enfrenta dificuldades para expandir seus serviços com qualidade e eficiência. Hoje, o atendimento, diagnóstico, execução de serviços e entrega dos veículos são feitos com anotações manuais e planilhas, o que causa:

- Erros na priorização dos atendimentos
- Falhas no controle de peças e insumos
- Dificuldade em acompanhar o status dos serviços
- Perda de histórico de clientes e veículos
- Ineficiência no fluxo de orçamentos e autorizações

## Proposta

Desenvolver a primeira versão (**MVP**) do back-end de um **Sistema Integrado de Atendimento e Execução de Serviços** para a oficina. O sistema deve permitir que clientes acompanhem, em tempo real, o andamento do serviço e autorizem reparos adicionais, além de garantir gestão interna eficiente e segura.

O foco é a gestão de ordens de serviço, clientes e peças, aplicando Domain-Driven Design (DDD) e boas práticas de qualidade de software e segurança.

## Funcionalidades obrigatórias

### Criação da Ordem de Serviço (OS)

- Identificação do cliente por CPF/CNPJ
- Cadastro de veículo com placa, marca, modelo e ano
- Inclusão dos serviços solicitados, como troca de óleo e alinhamento
- Inclusão de peças e insumos necessários
- Geração automática do orçamento com base nos serviços e peças
- Envio do orçamento ao cliente para aprovação

### Acompanhamento da OS

A OS deve possuir os seguintes status:

- Recebida
- Em diagnóstico
- Aguardando aprovação
- Em execução
- Finalizada
- Entregue

O sistema deve alterar os status conforme as ações realizadas e permitir que o cliente consulte o progresso da OS por API.

### Gestão administrativa

- CRUD de clientes
- CRUD de veículos
- CRUD de serviços
- CRUD de peças e insumos, com controle de estoque
- Listagem e detalhamento de ordens de serviço
- Monitoramento do tempo médio de execução dos serviços

### Segurança e qualidade

- Autenticação JWT para APIs administrativas
- Validação de CPF/CNPJ e placa de veículo
- Testes unitários e de integração para os principais fluxos

## Requisitos técnicos

- Back-end monolítico, organizado em camadas
- Banco de dados de livre escolha, com justificativa da preferência adotada
- APIs RESTful documentadas via Swagger, OpenAPI ou equivalente
- `Dockerfile` para build da aplicação
- `docker-compose.yml` para orquestrar o ambiente completo
- Testes automatizados com cobertura mínima de 80% nos domínios críticos
- Configuração simples para execução local, documentada em `README.md`

## Entregáveis da Fase 1

A entrega será realizada por meio de **um único arquivo PDF**, contendo todas as informações e links necessários para avaliação. O grupo é responsável por garantir que todos os links estejam corretos, acessíveis e vinculados à versão efetivamente entregue.

### 1. Identificação da entrega

A primeira página do PDF deverá apresentar:

- Curso: SOAT — Software Architecture
- Fase: 1
- Número do grupo
- Nome completo e RM de todos os integrantes
- Username utilizado no Discord
- Linguagem e principais tecnologias utilizadas

### 2. Repositório do projeto

O PDF deve conter o link completo e clicável de todos os repositórios utilizados.

Os repositórios devem:

- Estar públicos no GitHub durante o período de correção e revisão de notas
- Possuir uma versão identificada por branch, tag ou hash de commit
- Corresponder ao código apresentado no vídeo e na documentação
- Conter apenas arquivos necessários, sem credenciais, senhas, tokens ou informações sensíveis
- Possuir `README.md` completo e instruções suficientes para execução local
- Possuir testes automatizados com cobertura mínima de 80%
- Possuir documentação da API por Swagger, OpenAPI ou equivalente
- Possuir relatório ou resultado da análise de vulnerabilidades

O `README.md` deverá apresentar, no mínimo:

- Objetivo do projeto e descrição resumida da solução
- Arquitetura e tecnologias utilizadas
- Pré-requisitos e instruções para execução e testes
- Instruções de acesso ao Swagger ou à documentação da API
- Decisão e justificativa do banco de dados
- Usuários, credenciais de demonstração ou procedimento de autenticação
- Estrutura dos principais diretórios
- Links para a documentação DDD e para o vídeo da entrega

O PDF deve informar a branch e o hash do commit que representam a entrega final. A avaliação considerará exclusivamente essa versão.

> **Observação:** a branch `main` deve permanecer protegida, e tudo que chegar nela deve passar por Pull Request (PR).

### 3. Vídeo da entrega

O PDF deverá conter o link completo e clicável de um vídeo **público** no YouTube. O vídeo deve ter até 15 minutos, permanecer disponível durante a correção, apresentar o projeto correspondente ao commit informado, ter áudio compreensível e identificar os integrantes.

O vídeo deverá demonstrar, no mínimo:

- A proposta da solução, a arquitetura e a organização do monólito em camadas
- A escolha e a justificativa do banco de dados
- O processo de Event Storming e os elementos de DDD utilizados
- O fluxo de criação e acompanhamento de uma OS
- A inclusão de serviços, peças e insumos, além da geração e aprovação do orçamento
- A alteração dos status da OS e a autenticação das APIs administrativas
- A execução da aplicação, a documentação Swagger/OpenAPI, os testes automatizados e a análise de vulnerabilidades

### 4. Documentação DDD

O PDF deverá conter um link direto e acessível sem solicitação manual de permissão para a documentação DDD criada no Miro ou em ferramenta equivalente.

Além do link externo, a documentação deve ser exportada para PDF ou imagens e armazenada no repositório, preferencialmente nesta estrutura:

```text
docs/
└── ddd/
    ├── event-storming.pdf
    ├── diagramas.pdf
    └── linguagem-ubiqua.md
```

A documentação deverá apresentar:

- Event Storming dos fluxos de criação e acompanhamento da OS e da gestão de peças e insumos
- Eventos de domínio, comandos, políticas ou regras de negócio e atores
- Agregados, entidades, objetos de valor e bounded contexts, quando identificados
- Diagramas solicitados na disciplina de DDD
- Linguagem ubíqua, glossário dos termos do domínio e relação entre documentação e implementação

A documentação deve representar a solução entregue. Diagramas genéricos, exemplos de aula ou documentos que não correspondam ao código não serão considerados evidência completa.

### 5. Funcionalidades obrigatórias no repositório

O repositório deverá implementar e permitir identificar as seguintes funcionalidades:

#### Criação da Ordem de Serviço

- Identificação do cliente por CPF ou CNPJ
- Cadastro do veículo com placa, marca, modelo e ano
- Inclusão de serviços solicitados, peças e insumos
- Geração automática e envio ou disponibilização do orçamento
- Registro da aprovação ou rejeição do orçamento

#### Acompanhamento da Ordem de Serviço

A OS deverá possuir os status **Recebida**, **Em diagnóstico**, **Aguardando aprovação**, **Em execução**, **Finalizada** e **Entregue**.

O sistema deverá controlar as alterações de status, aplicar as regras de transição e permitir a consulta do andamento da OS pelo cliente via API.

#### Gestão administrativa

- CRUD de clientes, veículos, serviços, peças e insumos
- Controle de estoque
- Listagem e detalhamento de ordens de serviço
- Monitoramento ou cálculo do tempo médio de execução dos serviços

### 6. Requisitos técnicos obrigatórios

A solução deverá apresentar:

- Back-end monolítico e organização em camadas
- Banco de dados de livre escolha, com decisão justificada
- APIs RESTful e Swagger, OpenAPI ou documentação equivalente
- Autenticação JWT para APIs administrativas
- Validação de CPF/CNPJ e placa de veículo
- Testes unitários e testes de integração dos fluxos principais
- Evidência de cobertura mínima de 80% nos domínios críticos
- Instruções para execução local
- Tratamento adequado das transações dos principais fluxos

> Estamos disponíveis no Discord para auxiliar durante todo o processo do Tech Challenge. Vamos lá?
