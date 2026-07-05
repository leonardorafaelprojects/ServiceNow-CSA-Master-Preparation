# 🌐 Domain 01: Platform Overview and Navigation

![CSA Weight](https://img.shields.io/badge/Exam_Weight-7%25-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

## 📌 Bem-vindo ao Domínio 1
Este é o ponto de partida da nossa jornada na plataforma ServiceNow. O Domínio de **Platform Overview and Navigation** representa **7% do exame CSA**. Pode parecer pouco, mas os conceitos aqui abordados (navegação, listas, formulários e personalização) são a base para entenderes todo o resto do sistema. Se não souberes como a plataforma se comporta na sua interface (UI), não conseguirás automatizá-la.

---

## 🏢 O Caso de Negócio (Nebula Cloud Dynamics)
Na **Nebula Cloud Dynamics**, temos centenas de colaboradores com diferentes perfis: Analistas de Service Desk, Gestores de TI, Auditores de Segurança e Utilizadores Finais. 

Se entregarmos a plataforma a estas pessoas sem governança de navegação, teremos caos operacional. A nossa missão arquitetural neste domínio é:
1. Garantir que cada utilizador só vê o que precisa de ver (Princípio do Menor Privilégio via *Roles* e *Impersonation*).
2. Reduzir o tempo de cliques através de atalhos e personalização de listas.
3. Garantir que a plataforma tem a identidade visual da empresa (Branding) para transmitir confiança e oficialidade ao ambiente.

---

## 📚 Deep Dive: Teoria de Ouro para o Exame CSA

Para garantires os teus 90%+ no exame, memoriza estes pilares fundamentais sobre a interface e navegação do ServiceNow:

### 1. A Interface Unificada (Next Experience)
A *Next Experience* é a interface padrão moderna do ServiceNow. Os utilizadores navegam principalmente através do cabeçalho superior que contém os seguintes menus:
* **All:** Mostra todas as aplicações e módulos aos quais o utilizador tem acesso.
* **Favorites:** Atalhos personalizados pelo utilizador (com cores e ícones).
* **History:** Registo cronológico de listas e formulários visitados. **Pegadinha de Prova:** Elementos do sistema como *UI Pages* e páginas de portal não aparecem no histórico!
* **Workspaces:** Áreas de trabalho desenhadas para tarefas específicas de certas personas (ex: *Service Operations Workspace*).

### 2. O Escopo do "Filter Navigator"
A barra de pesquisa dentro do menu *All* chama-se *Filter Navigator*. 
* **O que ele pesquisa:** Nomes de Aplicações (ex: Incident), Nomes de Módulos (ex: Create New) e Favoritos.
* **O que ele NÃO pesquisa:** Dados (ex: o número do incidente `INC0001` ou o nome de um utilizador). Para pesquisar dados em toda a plataforma, utiliza a **Global Search** (o ícone da lupa no cabeçalho superior).

### 3. Listas, Formulários e Menus de Contexto
A plataforma é essencialmente construída sobre Listas (tabelas de dados) e Formulários (detalhes de um registo).
* **List Editor:** Permite dar um duplo clique numa célula de uma lista para editar o valor sem precisar de abrir o formulário.
* **Column Context Menu:** Clicar com o botão direito no cabeçalho de uma coluna permite *Sort* (ordenar), *Group By* (agrupar), *Create Quick Report* (criar relatório rápido) e *Configure*.
* **Record Context Menu:** Clicar com o botão direito ao lado de um registo na lista ou no cabeçalho do formulário revela ações relacionadas ao registo (ex: Assign to me, Insert, Update).

### 4. Instance Configuration vs. User Personalization
* **Instance Configuration:** Afeta *todos* os utilizadores (ex: mudar o logótipo da empresa no `Basic Configuration UI16` ou alterar o layout de uma lista global). Requer *roles* de administrador.
* **User Personalization:** Afeta *apenas* o próprio utilizador (ex: ativar o Dark Mode no ícone da engrenagem, ou criar Favoritos).

### 5. Auditoria e Testes (User Impersonation)
O *User Impersonation* permite que os administradores assumam a sessão de outro utilizador sem precisarem da sua password. É vital para testar o que um utilizador vê e o que ele pode fazer (Security/Roles).
* Requer a *role* de `admin` ou `impersonator`.
* É registado no log do sistema (fica guardado quem personificou quem, por motivos de auditoria).

---

## 📝 CSA Practice Simulator (Domain 1)

Prepara-te para a prova! Responde a estas 10 questões em inglês (formato oficial do exame). As respostas e os comentários do Arquiteto estão no final.

**1. Which of the following allows a user to edit field values in a list without opening the form?**
A) Form Designer
B) Data Editor
C) List Editor
D) Edit Menu

**2. What is the primary function of user impersonation?**
A) View custom perspectives
B) Testing and visibility
C) Unlock Application master list
D) Activate verbose logging

**3. Which one of the following statements is true about Column Context Menus in a list view?**
A) It displays actions related to viewing and filtering the entire list.
B) It displays actions such as creating quick reports, configuring the list, and exporting data.
C) It displays actions such as view form, view related task, and add relationship.
D) It displays actions related to filtering options, assigning tags, and search.

**4. When searching using the App Navigator (Filter Navigator) search field, what can be returned? (Choose three)**
A) Names of Applications
B) History Records
C) Names of Modules
D) Favorites
E) Specific Incident numbers

**5. Which module would a System Administrator use to change the banner image, browser tab title, and system date format globally?**
A) User Preferences
B) Basic Configuration UI16
C) System Properties > UI Design
D) Application Configuration

**6. Which feature in the Next Experience UI displays a chronological list of recently accessed records and lists?**
A) Workspaces
B) Favorites
C) Bookmarks
D) History

**7. Which type of ServiceNow page does NOT typically appear in the History tab of the Application Navigator?**
A) Incident Lists
B) Problem Forms
C) UI Pages
D) Change Request Records

**8. If an administrator wants to globally change which columns are displayed for everyone on the Incident list, they should modify the:**
A) List Layout
B) Personalized List
C) Form Layout
D) User Preferences

**9. What is the name of the search feature used to find specific data (like a user's name or a specific task number) across multiple tables in the entire instance?**
A) Filter Navigator
B) Global Search
C) Connect Chat
D) Schema Map

**10. To perform user impersonation, a user must have either the 'admin' role or which other role?**
A) security_admin
B) itil_admin
C) user_admin
D) impersonator

---

### 🔑 Gabarito Comentado (Análise do Arquiteto)

**1. Resposta: C (List Editor)**
*Comentário:* O List Editor (duplo clique na célula) é a funcionalidade padrão para edições em linha (*inline editing*), poupando tempo ao utilizador por não exigir a abertura do formulário completo.

**2. Resposta: B (Testing and visibility)**
*Comentário:* Impersonation não tem a ver com logs ou desbloqueios mágicos. É puramente uma ferramenta de testes e validação de segurança (o que o utilizador vê e o que ele tem permissão para fazer).

**3. Resposta: B (Creating quick reports, configuring...)**
*Comentário:* O Context Menu da Coluna (botão direito no cabeçalho da coluna) tem ações focadas na *coluna*, como agrupar, ordenar, criar gráficos (quick reports) e configurar.

**4. Respostas: A, C, D (Applications, Modules, Favorites)**
*Comentário:* A barra de pesquisa do menu lateral (Filter Navigator) pesquisa a *estrutura de navegação*, não os dados. Histórico e números específicos de incidentes não são retornados ali.

**5. Resposta: B (Basic Configuration UI16)**
*Comentário:* Este é o módulo central para o *Corporate Branding* global da instância (Instance Configuration).

**6. Resposta: D (History)**
*Comentário:* O próprio nome indica a funcionalidade. O menu History (ícone de relógio) gere as tuas interações cronológicas recentes.

**7. Resposta: C (UI Pages)**
*Comentário:* Clássica pegadinha do CSA. O ServiceNow rastreia formulários e listas no histórico, mas páginas de interface isoladas (*UI Pages*) não são capturadas pelo motor do History.

**8. Resposta: A (List Layout)**
*Comentário:* O *List Layout* afeta a visão global de todos os utilizadores (configuração de instância). O *Personalized List* (ícone de engrenagem na lista) afeta apenas o utilizador que fez a alteração (preferência pessoal).

**9. Resposta: B (Global Search)**
*Comentário:* Ao contrário do Filter Navigator, o Global Search (lupa no topo) pesquisa dados em várias tabelas indexadas usando o motor Zing da ServiceNow.

**10. Resposta: D (impersonator)**
*Comentário:* A *role* `impersonator` foi criada justamente para permitir que analistas de suporte testem acessos de utilizadores sem precisarem de receber privilégios de `admin` total do sistema.

---
*Este documento suporta os laboratórios práticos disponíveis nesta diretoria. Explora as pastas dos laboratórios para ver a aplicação prática (hands-on) na PDI da Nebula Cloud Dynamics!*
