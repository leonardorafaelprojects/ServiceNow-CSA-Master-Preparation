# ⚙️ Domain 02: Instance Configuration

![CSA Weight](https://img.shields.io/badge/Exam_Weight-10%25-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

## 📌 Bem-vindo ao Domínio 2
O Domínio de **Instance Configuration** (10% do exame CSA) é onde a experiência de utilizador (UX) encontra a administração de base de dados. Aqui, aprendemos a manipular as duas estruturas mais fundamentais através das quais os utilizadores interagem com o ServiceNow: **Lists (Listas)** e **Forms (Formulários)**.

---

## 🏢 O Caso de Negócio (Nebula Cloud Dynamics)
Na **Nebula Cloud Dynamics**, os nossos gestores de projeto e equipes de operações queixavam-se frequentemente de duas coisas:
1. "Não consigo encontrar rapidamente os Incidentes Críticos da minha equipa" (Problema de Filtragem).
2. "O formulário de Incidente tem muitos campos que não usamos, e os importantes estão escondidos" (Problema de Layout de Formulário).

A nossa missão arquitetural neste domínio é aplicar configurações globais para otimizar os ecrãs para a equipa, poupando tempo em cada interação. Isto envolve dominar o *Form Designer*, compreender a diferença entre vistas (Views) e usar operadores de filtros avançados.

---

## 📚 Deep Dive: Teoria de Ouro para o Exame CSA

### 1. A Estrutura de Listas e Filtros
Uma *List* exibe um conjunto de registos de uma tabela.
* **O Condition Builder (Construtor de Filtros):** A prova adora perguntar a ordem exata de construção de um filtro. A resposta é sempre **FOV**: `Field -> Operator -> Value` (Ex: `Priority` [Field] -> `is` [Operator] -> `Critical` [Value]).
* **List Editor:** Permite edição *inline* (duplo clique numa célula) sem abrir o formulário.
* **Column Context Menu vs. List Context Menu:** * O menu da coluna (botão direito no cabeçalho) permite agrupar (`Group By`), criar gráficos rápidos (`Bar Chart`) e configurar a vista da lista. 
  * O menu da lista (botão direito numa linha) oferece ações para aquele registo específico (ex: `Copy URL`, `Assign to me`).

### 2. Form Layout vs. Form Designer
Formulários exibem um único registo (uma linha da base de dados). O ServiceNow oferece duas ferramentas para os modificar:
* **Form Layout:** Uma interface clássica (baseada em listas `Slushbucket` – Available/Selected). É rápida para adicionar um ou dois campos.
* **Form Designer:** Uma interface visual *drag-and-drop*. Apenas no Form Designer podes criar **Secções** (Sections) com 1 ou 2 colunas.

### 3. Views (Vistas) e Formatters
* **Views:** Podes ter múltiplas visões do mesmo formulário (ex: a Vista "Default" para todos, e a Vista "Metrics" para os Gestores). Mudares um campo numa vista não o altera na outra.
* **Formatters:** A pegadinha sagrada! Um Formatter **não é um campo na base de dados**. É um elemento visual inserido no formulário para exibir informações contextuais (ex: O *Activity Stream* que mostra os comentários, ou o *Process Flow*).

---

## 📝 CSA Practice Simulator (Domain 2)

Testa o teu conhecimento com 10 questões desenhadas com a taxonomia exata e as "pegadinhas" do exame oficial da ServiceNow.

### Questions

#### 1. In what specific order should filter elements be specified using the Condition Builder?
A) Operator, Condition, then Value  
B) Value, Operator, then Field  
C) Field, Operator, then Value  
D) Field, Condition, then Operator  

#### 2. What is the quickest method to generate a Bar Chart from data currently displayed in a list view?
A) Click the Context Menu on a record and select Create Report  
B) Right-click on a column header and select Bar Chart  
C) Drag and drop the filter breadcrumb onto the Report > Create New module  
D) Open the Data Dictionary and select Generate Visualization  

#### 3. A customer requires a new field to be added to the Incident form and placed inside a newly created two-column section. Which tool must be used to accomplish this?
A) Form Layout (accessed via right-click on the header)  
B) Field Class Manager  
C) Form Designer (accessed via context menu)  
D) System Dictionary  

#### 4. Which of the following describes a "Formatter" in a ServiceNow form?
A) A script that auto-populates commonly used fields when a form loads.  
B) A form element used to display information that is not a field in the record, such as the Activity Stream.  
C) A UI Policy that formats text to bold or italic.  
D) A database table that stores field format properties.  

#### 5. What feature allows you to update multiple records at one time directly from a list view?
A) Bulk Record Update  
B) Data Remediation Dashboard  
C) Update Selected Action  
D) List Editor  

#### 6. When configuring a list, what is the difference between "List Layout" and "Personalized List"?
A) List Layout affects all users (Instance Configuration); Personalized List affects only the user who made the change (User Personalization).  
B) They are two names for the same feature.  
C) Personalized List requires the `admin` role, while List Layout can be done by any user.  
D) List Layout is used for custom tables only.  

#### 7. If you want to show records grouped by the "Category" column in a list, which method is valid? (Choose two.)
A) On the Category column header, right-click and select Group By Category.  
B) On the Filter Menu, select Group By > Category.  
C) Click the Group On icon, select Category.  
D) On the List Context Menu (hamburger icon), select Group By > Category.  

#### 8. Which term best describes something that is created, has work performed upon it, and is eventually moved to a state of closed?
A) event  
B) flow  
C) report  
D) task  

#### 9. Which tool is used to quickly apply a predefined set of field values to a new form to speed up data entry?
A) Assignment Rule  
B) Formatter  
C) Template  
D) Reference Qualifier  

#### 10. While on an Incident list, you apply a complex filter and want to save it so your entire team can use it. After assigning a name, what is the correct next step?
A) Make the filter active and save.  
B) Assign the group 'Network' and save.  
C) Set the visibility dropdown to "Everyone" (or a specific group) and save.  
D) Export the filter as an XML file.  

---

### 🔑 Gabarito Comentado (Análise do Arquiteto)

**1. Resposta Correta: C** *Comentário:* FOV (Field, Operator, Value) é a sintaxe padrão de todas as *queries* no ServiceNow, seja no UI ou via script.

**2. Resposta Correta: B** *Comentário:* A criação de relatórios rápidos a partir de listas é sempre feita clicando com o botão direito no **cabeçalho da coluna** (Column Context Menu), selecionando diretamente o tipo de gráfico pretendido.

**3. Resposta Correta: C** *Comentário:* Embora o *Form Layout* permita adicionar campos, **apenas o Form Designer** permite a criação gráfica de novas Secções (Sections) com layouts de 1 ou 2 colunas.

**4. Resposta Correta: B** *Comentário:* Rasteira clássica! O *Activity Stream* mostra e-mails, notas e comentários. Essa informação vem da tabela `sys_journal_field`, não de uma coluna da tabela de Incidentes. O *Formatter* é o widget que traz essa informação externa para o ecrã.

**5. Resposta Correta: D** *Comentário:* O *List Editor* (duplo clique numa célula) é a ferramenta primária para edições em linha e em massa sem abrir os formulários. ("Update Selected Action" também existe, mas "List Editor" é o termo core esperado no CSA para esta definição).

**6. Resposta Correta: A** *Comentário:* Regra base de governação: List Layout (Configure > List Layout) é uma mudança global. Personalized List (Ícone de engrenagem) é uma preferência de utilizador armazenada em `sys_user_preference`.

**7. Respostas Corretas: A, D** *Comentário:* Podes agrupar dados clicando com o botão direito no cabeçalho da coluna pretendida (A) ou clicando no menu hambúrguer da lista e selecionando Group By (D).

**8. Resposta Correta: D** *Comentário:* Esta questão testa a taxonomia core. Um *Task* (Tarefa) é a unidade de trabalho base na plataforma, contendo um ciclo de vida desde a sua criação até ser fechada.

**9. Resposta Correta: C** *Comentário:* Um *Template* é como um "carimbo" que preenche múltiplos campos (ex: Categoria, Urgência, Grupo) simultaneamente num formulário novo.

**10. Resposta Correta: C** *Comentário:* Para partilhar filtros no ServiceNow, basta definir um Nome, escolher a *Visibility* (Everyone, Group, ou Me) e clicar em Guardar. Não existe uma checkbox de "Make Active".
