# Documento de Visão

Documento construído a partido do **Modelo BSI - Doc 001 - Documento de Visão** que pode ser encontrado no
link: https://docs.google.com/document/d/1DPBcyGHgflmz5RDsZQ2X8KVBPoEF5PdAz9BBNFyLa6A/edit?usp=sharing

## Descrição do Projeto

Esse projeto de software consiste no desenvolvimento de um sistema web para gerenciamento de uma empresa fictícia, TransRN, de transporte de cargas entre as cidades de Natal, Mossoró e Caicó, localizadas no estado do Rio Grande do Norte.

A aplicação tem como finalidade auxiliar na gestão das operações da transportadora, abrangendo o gerenciamento de clientes, funcionários, encomendas e veículos, além do controle de coleta, transporte entre unidades e entrega de objetos. O sistema também prevê recursos para cálculo de frete e rastreamento de encomendas.

## Equipe e Definição de Papéis

Membro     |     Papel   |   E-mail   |
---------  | ----------- | ---------- |
Karliane   | Orientadora        | karliane.vale@ufrn.br
Felipe     | Desenvolvimento    | felipe.medeiros.044@ufrn.edu.br

### Matriz de Competências

Membro     |     Competências   |
---------  | ----------- |
Karliane   | Profª. Dra. com experiência na área de Ciência da Computação, com ênfase em desenvolvimento de sistemas. |
Felipe     | Estudante, Desenvolvedor |

## Perfis dos Usuários

O sistema poderá ser utilizado por diferentes usuários, cada um com permissões e responsabilidades específicas de acordo com sua função na transportadora. São definidos os seguintes perfis/atores:

| Perfil | Descrição |
|---|---|
| **Cliente** | Este usuário poderá calcular o valor do frete e acompanhar o rastreamento de suas encomendas, consultando informações sobre a localização e a situação dos objetos transportados. |
| **Atendente** | Este usuário poderá realizar o gerenciamento de clientes e encomendas, sendo responsável pela manutenção dos cadastros e pelo registro das informações necessárias às operações da transportadora. |
| **Gerente Master** | Este usuário possui permissões administrativas, podendo gerenciar funcionários, além de supervisionar os cadastros e as informações relacionadas à administração da empresa. |
| **Gerente** | Este usuário será responsável pelo gerenciamento de clientes e das operações logísticas da unidade, podendo administrar veículos, coletas, transportes entre unidades e entregas. |
| **Motorista** | Este usuário será responsável pelas operações de entrega, podendo consultar e registrar informações relacionadas às encomendas sob sua responsabilidade e atualizar suas respectivas situações. |

# Lista de Requisitos Funcionais

## US01 – Calcular Frete

O sistema permite que qualquer pessoa realize uma simulação do valor do frete, informando os locais de origem e destino, o peso e as dimensões do objeto.

| Requisito | Descrição | Ator |
|---|---|---|
| RF01.01 – Calcular Frete | Realiza a simulação do valor do frete informando local de origem, destino, peso e dimensões do objeto. | Pessoa (Visitante) |

---

## US02 – Manter Cliente

Um cliente representa a pessoa que solicita os serviços de postagem e entrega de objetos, possuindo informações cadastrais utilizadas no gerenciamento de suas encomendas.

| Requisito | Descrição | Ator |
|---|---|---|
| RF02.01 – Inserir Cliente | Insere um novo cliente informando seus dados cadastrais e documentos. | Atendente |
| RF02.02 – Listar Clientes | Realiza a consulta de clientes utilizando informações como CPF/CNPJ ou nome. | Atendente, Gerente Master |
| RF02.03 – Atualizar Cliente | Atualiza os dados cadastrais de um cliente, exceto nome e CPF/CNPJ. | Atendente, Gerente Master |
| RF02.04 – Excluir Cliente | Exclui um cliente mediante confirmação por CPF/CNPJ, desde que não possua encomendas em aberto. | Gerente Master |

---

## US03 – Manter Coleta

Uma coleta representa o processo de retirada de objetos em determinada região, envolvendo a seleção de motorista, ajudante, veículo e encomendas que serão coletadas.

| Requisito | Descrição | Ator |
|---|---|---|
| RF03.01 – Criar Coleta | Cadastra uma nova coleta informando região, motorista, ajudante, veículo e objetos que serão coletados. | Gerente |
| RF03.02 – Concluir Coleta | Finaliza uma coleta atualizando o status dos objetos coletados e não coletados, além da disponibilidade dos recursos utilizados. | Gerente |

---

## US04 – Manter Entrega

Uma entrega representa o processo de transporte dos objetos até seus destinatários finais, permitindo o acompanhamento e a atualização dos status das encomendas.

| Requisito | Descrição | Ator |
|---|---|---|
| RF04.01 – Criar Entrega | Cadastra uma nova entrega informando região, motorista, ajudante, veículo e objetos que serão entregues. | Gerente |
| RF04.02 – Atualizar Entrega | Atualiza o status das encomendas durante o processo de entrega, identificando se foram entregues ou se o destinatário estava ausente. | Motorista |
| RF04.03 – Concluir Entrega | Finaliza uma entrega atualizando o status dos objetos e a disponibilidade do motorista, ajudante e veículo utilizados. | Gerente |

---

## US05 – Manter Funcionário

Um funcionário representa um colaborador da empresa, podendo exercer funções como gerente, atendente ou motorista. Seus dados são utilizados para identificação e controle de acesso ao sistema.

| Requisito | Descrição | Ator |
|---|---|---|
| RF05.01 – Inserir Funcionário | Insere um novo funcionário informando seus dados cadastrais e documentos. | Gerente Master |
| RF05.02 – Listar Funcionários | Realiza a consulta de funcionários utilizando filtros como CPF, função ou nome. | Gerente Master |
| RF05.03 – Atualizar Funcionário | Atualiza os dados cadastrais de um funcionário, exceto nome e CPF. | Gerente Master |
| RF05.04 – Excluir Funcionário | Exclui um funcionário mediante confirmação por CPF, desde que não esteja vinculado a uma viagem, coleta, transporte ou entrega em aberto. | Gerente Master |
| RF05.05 – Gerar Acesso ao Sistema | Gera um link para criação de senha e o envia ao e-mail cadastrado do funcionário, permitindo que ele configure suas credenciais de acesso ao sistema. | Gerente Master |

---

## US06 – Manter Objetos

Um objeto representa uma encomenda cadastrada no sistema para postagem, contendo informações do cliente, destinatário, endereço de entrega, peso, dimensões e valor do frete.

| Requisito | Descrição | Ator |
|---|---|---|
| RF06.01 – Inserir Objeto | Cadastra uma nova encomenda informando os dados do cliente e da postagem, gerando um código de identificação e registrando o status inicial do objeto. | Atendente |
| RF06.02 – Listar Objetos | Realiza a consulta de encomendas utilizando informações como CPF/CNPJ do cliente ou código de identificação do objeto. | Atendente, Gerente |
| RF06.03 – Atualizar Objeto | Atualiza os dados de uma encomenda após a conferência, verificando possíveis diferenças no valor do frete e atualizando seu status conforme necessário. | Gerente |
| RF06.04 – Excluir Objeto | Exclui uma encomenda mediante confirmação pelo código de identificação, desde que o pagamento ainda não tenha sido efetuado ou tenha sido estornado. | Gerente |

---

## US07 – Manter Transporte entre Unidades

Um transporte representa o deslocamento de objetos entre unidades da empresa, envolvendo a seleção de cidade de origem, cidade de destino, motorista, ajudante e veículo.

| Requisito | Descrição | Ator |
|---|---|---|
| RF07.01 – Criar Transporte | Cadastra um novo transporte informando as cidades de origem e destino, motorista, ajudante, veículo e objetos que serão transportados. | Gerente |
| RF07.02 – Concluir Transporte | Finaliza um transporte atualizando o status dos objetos transportados e a disponibilidade dos recursos utilizados, além da localização da unidade de destino. | Gerente |

---

## US08 – Manter Veículo

Um veículo representa um meio de transporte utilizado pela empresa para realizar coletas, transportes entre unidades e entregas de encomendas.

| Requisito | Descrição | Ator |
|---|---|---|
| RF08.01 – Inserir Veículo | Insere um novo veículo informando seus dados cadastrais e documentos. | Gerente |
| RF08.02 – Listar Veículos | Realiza a consulta de veículos utilizando filtros como placa ou tipo de veículo. | Gerente |
| RF08.03 – Atualizar Veículo | Atualiza os dados cadastrais, a disponibilidade ou a localização de um veículo. | Gerente |
| RF08.04 – Excluir Veículo | Exclui um veículo mediante confirmação pela placa, desde que não esteja vinculado a uma coleta, transporte ou entrega em aberto. | Gerente |

---

## US09 – Rastrear Objeto

O rastreamento permite que qualquer pessoa consulte o histórico de movimentações de uma encomenda por meio de seu código de identificação.

| Requisito | Descrição | Ator |
|---|---|---|
| RF09.01 – Rastrear Objeto | Consulta o histórico de movimentações de uma encomenda, apresentando as atualizações de status, datas, horários e descrições correspondentes. | Pessoa (Visitante) |

---

### Modelo Conceitual

Abaixo apresentamos o modelo conceitual usando o **Mermaid**.

```mermaid

```

#### Descrição das Entidades

## Lista de Requisitos Não-Funcionais

Requisito                                 | Descrição   |
---------                                 | ----------- |
RNF001 - Deve ser acessível via navegador | Deve abrir perfeitamento no Firefox e no Chrome. |
RNF002 - Consultas deve ser eficiente | O sistema deve executar as consultas em milessegundos |
RNF003 - Log e histórico de acesso e funções | Deve manter um log de todos os acessos e das funções executadas pelo usuário |

## Tabela de Riscos

| Data | Risco | Prioridade | Responsável | Status | Providência/Solução |
|---|---|---|---|---|---|
| 11/11/2026 | Dificuldade de aprendizado das tecnologias e ferramentas utilizadas pelos integrantes da equipe. | Alta | Toda a equipe | Aberto | Buscar materiais de estudo, documentação e realizar pequenas implementações para familiarização com as tecnologias. |
| 11/11/2026 | Sobrecarga de tarefas entre os integrantes da equipe. | Alta | Scrum Master | Aberto | Trabalhar mais horas no projeto, utilizar AI como ferramenta para acelerar o desenvolvimento ou estender o prazo de desenvolvimento decorrente do baixo número de membros na equipe. |
| 11/11/2026 | Dificuldade na implementação e integração do protótipo utilizando as tecnologias escolhidas. | Alta | Equipe de desenvolvimento | Aberto | Desenvolver inicialmente um protótipo simples para validar a integração entre front-end, back-end e banco de dados. |
| 11/11/2026 | Dificuldade na integração entre os módulos do sistema. | Alta | Equipe de desenvolvimento | Aberto | Definir previamente as estruturas de dados e os relacionamentos entre os módulos, realizando testes de integração durante o desenvolvimento. |
| 11/11/2026 | Alterações nos requisitos durante o desenvolvimento do projeto. | Média | Product Owner | Aberto | Manter o Product Backlog atualizado e avaliar o impacto das alterações antes de incorporá-las às Sprints. |
| 11/11/2026 | Atraso na implementação das funcionalidades planejadas para as Sprints. | Alta | Scrum Master | Aberto | Acompanhar o andamento das atividades, revisar as estimativas e ajustar o planejamento conforme a capacidade da equipe. |
| 11/11/2026 | Perda de código ou conflitos durante a integração das alterações realizadas pelos integrantes. | Média | Equipe de desenvolvimento | Aberto | Utilizar o Git de maneira padronizada, realizar commits frequentes e utilizar branches e pull requests para integrar as alterações. |
| 11/11/2026 | Dificuldade na implementação das regras de negócio relacionadas às operações logísticas. | Alta | Equipe de desenvolvimento | Aberto | Documentar as regras de negócio, definir critérios de aceitação e realizar testes com diferentes cenários de operação. |

### Referências

SILVA, Taciano. *Documento de Visão*. GitHub. Disponível em: [https://github.com/tacianosilva/engenharia-software/blob/main/docs/doc-visao.md](https://github.com/tacianosilva/engenharia-software/blob/main/docs/doc-visao.md). Acesso em: 11 nov. 2026.
