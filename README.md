# README - Área Verde
Esse repositório foi criado com o objetivo de administrar a documentação do projeto Área Verde. Assim, arquivos e links referentes ao desenvolvimento podem ser encontrados por aqui.

---

## Nome do software
O projeto Área Verde tem seu nome baseado no local de convivência da biblioteca da UFABC, onde diariamente várias pessoas se reunem para conversar, debater, estudar em equipe e trabalhar. O sentimento ao se pensar nele foi o de trazer para o nome uma referência à união e ao maior contado entre comunidades acadêmicas, estudantes e funcionários universitários.

---

## Brainstorming - Canvas
Nosso canvas pode ser encontrado [aqui](https://drive.google.com/file/d/1jNKuMGRp6UgUyskcGRezX4Huhc6SwXmz/view?usp=sharing).

---

## Requisitos de Sistema

### Funcionais:
- RF01 - O sistema deve permitir aos usuários a realização de login em sua plataforma.
- RF02 - O sistema deve oferecer diferentes perfis de acesso baseado nas permissões oferecidas aos usuários.
- RF03 - O sistema deve coletar dados das disciplinas oferecidas pela universidade e oferecer informações destas para o usuário.
- RF04 - O sistema deve oferecer ao usuário uma interface para que ele seja capaz de montar sua grade de disciplinas.
- RF05 - O sistema deve oferecer visualização intuitiva de grupos de comunicação e divulgação para alunos.
- RF06 - O sistema deverá possuir um mural de notícias com atualizações a respeito de eventos divulgados pela direção e por entidades estudantis.

### Não Funcionais:
- RN01 - Um protótipo funcional do sistema deverá ser entregue até o dia 24 de agosto de 2023, data da entrega final da disciplina.
- RN02 - O custo total do desenvolvimento e manutenção deste protótipo não deverá ultrapassar os R$100,00.
- RN03 - As entregas parciais do projeto deverão ocorrer como determinado pela linha do tempo da disciplina.
- RN04 - O desenvolvimento será realizado conforme o método ágil SCRUM, obedecendo as entregas definidas pela linha do tempo da disciplina.
- RN05 - O projeto deverá ser desenvolvido com Reactive Native.
- RN06 - A interface deverá ser intuitiva e de fácil entendimento para utilização dos usuários.
- RN07 - A interface do sistema seguirá um sistema de cores com ênfase em tons de verde, para condizer com o título da aplicação.
- RN08 - A interface deverá se adaptar a diferentes tamanhos de tela (responsiva).
- RN09 - O sistema deverá ser acessado por dispositivos móveis com acesso a internet.
- RN10 - O software será acessado por um usuário administrador, cujo acesso abrangerá todas as funcionalidades do sistema (CRUD).
- RN11 - O sistema será acessado por um usuário docente, cujo acesso se restringirá ao login, à criação e visualização (CR) de disciplinas universitárias, mural de anúncios, informações sobre achados e perdidos e visualização (R) calendários.
- RN12 - O sistema será acessado por um usuário discente, cujo acesso se restringirá a CRU de disciplinas universitárias, murais de aviso, grupos de discentes, informações sobre achados e perdidos e de calendários.
- RN13 - O sistema será acessado por um usuário funcionário da universidade, cujo acesso se restringirá ao login, CRU de itens na seção de achados e perdidos, mural de anúncios e de calendários.
- RN14 - O sistema deverá ser resiliente, uma vez que será acessado por cerca de 185 mil usuários simultaneamente.
- RN15 - O software deverá oferecer suporte aos sistemas operacionais mobile Android e iOS.

---

## Diagramas

### Casos de Uso

- De login:

<img src="https://github.com/Software-Engineering-UFABC/README/blob/main/CasosUso_Login.png?raw=true" alt="Casos de Uso - Login">

---

- De Discentes Universitários:

<img src="https://github.com/Software-Engineering-UFABC/README/blob/main/CasosUso_DiscentesUniversitarios.png?raw=true" alt="Casos de Uso - Discentes Universitarios">

### Descrição dos Casos de Uso

- De Discentes Universitários:
(colocar arquivo)

### Diagrama Entidade-Relacionamento

<img src="https://github.com/Software-Engineering-UFABC/README/blob/main/Diagrama_ER.png?raw=true" alt="Diagrama Entidade-Relacionamento">

## Arquitetura Geral

A arquitetura do Área Verde é orientada a serviços, conforme o seguint esboço:

<img src="https://github.com/Software-Engineering-UFABC/README/blob/main/Esboco_Arquitetura_AreaVerde.jpeg" alt="Esboço da Arquitetura Geral">

## Arquitetura MVP
Descrição do Fluxo de Login: Um cliente mobile, desejando realizar cadastro ou login no sistema, fará uma solicitação síncrona para o nosso servidor, que tem como porta de entrada a API orquestradora. A API orquestradora, por sua vez, chamará o serviço de login. Esse serviço tem como responsabilidade verificar se o cliente deseja criar ou entrar em sua conta. Se a opção for criar uma conta, o serviço verificará junto à API da Universidade se há dados desse usuário e, caso não haja, o mesmo será encaminhado para uma tela de cadastro. Se a opção for a de realizar login então o usuário inserirá seus dados de e-mail e senha cadastrados e entrará no sistema.

Descrição do Fluxo de Discentes Universitários: Um cliente mobile, com perfil de discente, desejando acessar sua conta, chamará a API orquestradora, que verificará qual atividade esse usuário deseja realizar. Se o desejado for consultar sua conta, o serviço de login será chamado. Se for consultar disciplinas, o serviço de Disciplinas será chamado e assim por diante.

