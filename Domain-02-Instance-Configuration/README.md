# ⚙️ Domain 02: Instance Configuration

![CSA Weight](https://img.shields.io/badge/Exam_Weight-10%25-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)
![Methodology](https://img.shields.io/badge/Methodology-Advanced_Framework-8A2BE2?style=for-the-badge)

## 📌 Visão Arquitetural e Metodologia de Estudo
O Domínio de **Instance Configuration** (10% do exame CSA) é a camada onde a experiência do usuário (UX) interage diretamente com as engrenagens do banco de dados. 

Neste documento, não nos limitamos a listar "como clicar em botões". Aplicamos o nosso **Framework de Estudo Avançado** (utilizando a Técnica de Feynman e Engenharia Reversa) para desconstruir o comportamento da interface do ServiceNow e documentar as armadilhas exatas cobradas na prova oficial.

---

## 🏢 O Caso de Negócio (Nebula Cloud Dynamics)
Na **Nebula Cloud Dynamics**, os nossos gestores de operações (PMO) e analistas de Service Desk queixavam-se frequentemente de sobrecarga cognitiva: formulários repletos de campos não utilizados e dificuldade em filtrar incidentes críticos rapidamente.

**A Nossa Missão Técnica:**
Aplicar uma governança visual impecável. Precisamos otimizar as "Fichas Cadastrais" (Formulários) e as visões de "Planilha" (Listas) da equipe. O objetivo é poupar tempo em cada interação diária, garantindo a separação estrita entre o que afeta a empresa inteira e o que afeta apenas o usuário individual.

---

## 🧠 Framework de Estudo Avançado: A Teoria Desconstruída

Para dominar este domínio e atingir os 90%+ na prova, desconstruímos a arquitetura visual da plataforma:

### 1. A Analogia do Mundo Real (Feynman Technique)
* **As Listas (Lists):** Pense no banco de dados como uma gigantesca *Planilha de Excel*. Cada linha (Row) é um `Record` (Registro). Cada coluna (Column) é um `Field` (Campo).
* **Os Formulários (Forms):** É o equivalente a clicar numa linha específica dessa planilha e abrir uma "Ficha Cadastral" detalhada com os dados exclusivos daquele registro.
* **A Regra do Escritório (Instance vs. Personalization):** Se, como Admin, eu pintar as paredes do escritório de azul, todos os funcionários verão azul (**Instance Configuration** - ex: *List Layout* e *Form Layout*). Mas se um funcionário ajusta a altura da sua própria cadeira, só afeta a ele (**User Personalization** - ex: *Personalized List*, armazenado na tabela secreta `sys_user_preference`).

### 2. A Engenharia Reversa da Prova (Pegadinhas Arquiteturais)
* **A Regra FOV (Condition Builder):** A prova cobra a ordem exata da construção de filtros lógicos. O acrônimo inquebrável é **FOV**: **F**ield -> **O**perator -> **V**alue (Ex: `State` -> `is` -> `In Progress`).
* **Formatters (A Maior Pegadinha):** Se a prova perguntar "O que é um Formatter?", a resposta é contra-intuitiva: **É um elemento visual no formulário que NÃO é um campo do banco de dados.** Por exemplo, o *Activity Stream* apenas cria uma "janela" para exibir dados injetados de outra tabela (`sys_journal_field`).
* **Como compartilhar um filtro?** Muitos candidatos caem na armadilha de procurar um botão "Make Active". Para compartilhar um filtro com a equipe, a arquitetura exige apenas 3 passos: `Assign a Name` (Dar um nome), `Set Visibility` (Definir para Everyone/Grupo) e `Save` (Salvar).

### 3. As Ferramentas de Design (Layout vs. Designer)
* **Form Layout:** Usa a interface clássica *Slushbucket* (Disponível vs. Selecionado). Ideal para injeções rápidas de campos simples.
* **Form Designer:** A ferramenta moderna de drag-and-drop. **Regra de Ouro:** É a *única* ferramenta capaz de criar **Sections (Sessões)** estruturadas em 1 ou 2 colunas no formulário.

---

## 📝 CSA Practice Simulator (Domain 2)

Abaixo, aplicamos a técnica de **Active Recall** com 10 questões desenhadas com a taxonomia e as armadilhas exatas do exame oficial da ServiceNow, baseadas na nossa inteligência de estudos atualizada.

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

**1. Resposta Correta: C** *Comentário:* A regra inquebrável do Condition Builder é o **FOV** (Field, Operator, Value).

**2. Resposta Correta: B** *Comentário:* Relatórios instantâneos a partir de uma lista são gerados através do *Column Context Menu* (clique com botão direito no título da coluna).

**3. Resposta Correta: C** *Comentário:* Somente o *Form Designer* (interface visual) possui os controles para adicionar novas *Sections* de 1 ou 2 colunas.

**4. Resposta Correta: B** *Comentário:* Pegadinha mapeada! O *Activity Stream* não é uma coluna da tabela atual; o Formatter é apenas a "janela" que exibe os dados externos no formulário.

**5. Resposta Correta: D** *Comentário:* O *List Editor* (duplo clique numa célula) é a ferramenta primária e mais rápida para edições de registros em linha (*inline*).

**6. Resposta Correta: A** *Comentário:* A "Regra do Escritório": Pintar a parede (List Layout) é global. Ajustar a própria cadeira (Personalized List) é individual e não requer privilégios de admin.

**7. Respostas Corretas: A, D** *Comentário:* O agrupamento visual na lista pode ser feito tanto no *Column Context Menu* quanto no *List Context Menu* principal (hambúrguer icon).

**8. Resposta Correta: C** *Comentário:* *Templates* atuam como "carimbos" que preenchem automaticamente múltiplos campos em formulários novos.

**9. Resposta Correta: C** *Comentário:* Não existe opção "Make Active" para filtros. A tríade de compartilhamento é: Name -> Visibility -> Save.

**10. Resposta Correta: D** *Comentário:* Uma Tarefa (*Task*) é a unidade de trabalho fundamental da plataforma, possuindo um ciclo de vida inerente (Aberta > Em andamento > Fechada).

