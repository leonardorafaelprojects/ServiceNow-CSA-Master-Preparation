# ⚙️ Domain 02: Instance Configuration

![CSA Weight](https://img.shields.io/badge/Exam_Weight-10%25-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)
![Methodology](https://img.shields.io/badge/Methodology-Advanced_Framework-8A2BE2?style=for-the-badge)

## 📌 Visão Arquitetural
O Domínio de **Instance Configuration** (10% do exame CSA) é a camada onde a experiência de utilizador (UX) encontra a base de dados. Este documento não se limita a listar funcionalidades; ele aplica um Framework de Estudo Avançado para desconstruir o comportamento da interface do ServiceNow.

---

## 🏢 O Caso de Negócio (Nebula Cloud Dynamics)
Na **Nebula Cloud Dynamics**, os nossos gestores de operações (PMO) e analistas de Service Desk queixavam-se de sobrecarga cognitiva: formulários repletos de campos não utilizados e dificuldade em filtrar incidentes críticos em massa.

**A Nossa Missão:**
Aplicar governança visual. Precisamos otimizar a "Ficha Cadastral" (Formulários) e as visões de "Planilha" (Listas) da equipa, poupando tempo em cada interação diária, sempre garantindo a separação estrita entre o que afeta a empresa inteira e o que afeta apenas o utilizador individual.

---

## 🧠 Framework de Estudo Avançado: A Teoria Desconstruída

Para dominar este domínio, aplicamos a **Técnica de Feynman** aliada à **Engenharia Reversa** das armadilhas da plataforma.

### 1. Analogia do Mundo Real (Lists vs. Forms)
* **As Listas (Lists):** Pensa na base de dados como uma gigantesca *Planilha de Excel*. Cada linha (Row) é um `Record` (Registo). Cada coluna (Column) é um `Field` (Campo).
* **Os Formulários (Forms):** É como clicar numa linha específica dessa planilha e abrir uma "Ficha Cadastral" detalhada apenas desse registo.
* **A Regra do Escritório (Instance vs. Personalization):** Se como Admin eu pintar as paredes do escritório de azul, todos veem azul (**Instance Configuration** - List/Form Layout). Mas se um funcionário ajusta a altura da sua própria cadeira, só o afeta a ele (**User Personalization** - Personalized List).

### 2. Anatomia Técnica e Filtros
* **A Regra FOV:** O *Condition Builder* (Construtor de Filtros) exige uma ordem exata: **F**ield -> **O**perator -> **V**alue (Ex: `State` -> `is` -> `In Progress`).
* **Formatters:** A maior "pegadinha" arquitetural! Um Formatter (ex: *Activity Stream*) **NÃO** é um campo da base de dados. É um elemento visual que injeta dados de outras tabelas (`sys_journal_field`) diretamente no ecrã do utilizador.
* **Form Layout vs. Form Designer:** O *Form Layout* (slushbucket) é para adições rápidas. O **Form Designer** (drag-and-drop) é a única ferramenta capaz de criar **Sections** (Secções) com 1 ou 2 colunas.

### 3. Engenharia Reversa (Mapeamento de Armadilhas)
* **Como partilhar um filtro?** Não existe botão "Make Active". A arquitetura exige 3 passos: `Assign a Name` (Dar um nome), `Set Visibility` (Definir visibilidade para Everyone/Grupo) e `Save`.
* **Automação de Preenchimento:** Para preencher múltiplos campos (Categoria, Grupo, Urgência) num só clique ao criar um novo incidente, não se usa código. Usa-se um **Template**.

---

## 🛠️ Execução na PDI & Mapeamento de Evidências

Abaixo, a prova prática da aplicação destes conceitos no ambiente da Nebula Cloud Dynamics.

### Passo 1: Otimização Rápida de Listas (List Editor e Gráficos)
Usando o *Column Context Menu* (clique direito no cabeçalho da coluna), geramos relatórios dinâmicos instantâneos e utilizamos o *List Editor* para modificar registos em massa sem abrir os formulários.

> 📸 **PRINT 1: Criação de Bar Chart e uso do List Editor**
> ![List Operations](../../images/lab2_1_step1.png)

### Passo 2: User Personalization (Ocultando Colunas)
Um Gestor da Nebula precisava de ocultar a coluna "Subcategory", mas sem afetar os seus analistas. Clicámos no ícone da **Engrenagem** (Personalized List) e removemos a coluna apenas para ele (registo guardado em `sys_user_preference`).

> 📸 **PRINT 2: Personalized List (Engrenagem)**
> ![Personalized List](../../images/lab2_1_step2.png)

### Passo 3: Reestruturação de Formulários (Form Designer)
Acedemos ao *Form Designer* para criar uma nova secção estruturada em duas colunas, otimizando a leitura dos campos de resolução do ticket.

> 📸 **PRINT 3: Interface do Form Designer com nova Section**
> ![Form Designer](../../images/lab2_1_step3.png)

---

## 📝 CSA Practice Simulator (Domain 2)

Teste a sua prontidão para o exame oficial com estas 10 questões, calibradas com a taxonomia de Elite da ServiceNow.

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

#### 8. Which tool is used to quickly apply a predefined set of field values to a new form to speed up data entry?
A) Assignment Rule  
B) Formatter  
C) Template  
D) Reference Qualifier  

#### 9. While on an Incident list, you apply a complex filter and want to save it so your entire team can use it. After assigning a name, what is the correct next step?
A) Make the filter active and save.  
B) Assign the group 'Network' and save.  
C) Set the visibility dropdown to "Everyone" (or a specific group) and save.  
D) Export the filter as an XML file.  

#### 10. Which term best describes something that is created, has work performed upon it, and is eventually moved to a state of closed?
A) event  
B) flow  
C) report  
D) task  

---

### 🔑 Gabarito Comentado (Análise do Arquiteto)

**1. Resposta Correta: C** *Comentário:* FOV (Field, Operator, Value) é a sintaxe padrão e inquebrável de todas as queries (buscas) no ServiceNow.
**2. Resposta Correta: B** *Comentário:* A criação de relatórios rápidos a partir de listas é sempre feita clicando com o botão direito no **cabeçalho da coluna** (Column Context Menu).
**3. Resposta Correta: C** *Comentário:* Embora o *Form Layout* adicione campos, **apenas o Form Designer** possui a capacidade visual de criar novas Secções (Sections) com colunas.
**4. Resposta Correta: B** *Comentário:* A armadilha clássica! Um Formatter (como o Activity Stream) traz dados agregados para o ecrã, mas não representa uma coluna real na tabela do registo atual.
**5. Resposta Correta: D** *Comentário:* O *List Editor* (duplo clique numa célula) é a ferramenta primária para edições em linha (*inline*) de forma rápida.
**6. Resposta Correta: A** *Comentário:* List Layout = Pintar as paredes do escritório (Muda para todos). Personalized List = Ajustar a própria cadeira (Muda só para o utilizador e guarda na tabela `sys_user_preference`).
**7. Respostas Corretas: A, D** *Comentário:* O agrupamento de dados é uma função de visualização de lista e pode ser ativado no cabeçalho da coluna ou no menu hambúrguer da lista.
**8. Resposta Correta: C** *Comentário:* *Templates* são carimbos de preenchimento automático. *Assignment Rules* apenas automatizam quem vai trabalhar no ticket, não preenchem a ficha inteira.
**9. Resposta Correta: C** *Comentário:* Não existe a opção "Make Active". A partilha de filtros obedece ao tripé: Name -> Visibility -> Save.
**10. Resposta Correta: D** *Comentário:* Uma Tarefa (*Task*) é a unidade de trabalho fundamental da plataforma, possuindo um ciclo de vida inerente (Aberta > Em andamento > Fechada).
