# 🔵 Lab Nebula 1.2: Corporate Branding and Next Experience

## 🏢 O Cenário Corporativo (Business Case na Nebula)
Para garantir a adoção correta da plataforma e evitar que os colaboradores da **Nebula Cloud Dynamics** confundam os ambientes de Desenvolvimento (DEV), Qualidade (QA) e Produção (PROD), a diretoria exigiu uma identidade visual corporativa rigorosa na interface do ServiceNow. 

Como System Administrator, a nossa missão é aplicar o *Branding* global da empresa (Logótipo e Títulos) de forma segura, garantindo que estas definições globais não sejam quebradas quando os utilizadores aplicarem as suas próprias preferências pessoais de UI (como o *Dark Mode* da Next Experience).

---

## 📚 Teoria de Ouro & Deep Dive (Foco Total no Exame CSA)
Para garantires uma pontuação de elite neste domínio do exame, precisas de dominar a diferença crucial entre configurações do sistema e preferências do utilizador:

### 1. Instance Configuration vs. User Personalization
* **Instance Configuration:** São configurações que afetam a plataforma inteira e todos os utilizadores (ex: mudar o logótipo da empresa, o título do browser ou o fuso horário padrão do sistema). Exigem a *role* de `admin` e são geralmente feitas no módulo **Basic Configuration UI16** ou na tabela de Propriedades do Sistema (`sys_properties`).
* **User Personalization:** São configurações que o utilizador final pode alterar para si mesmo sem afetar os outros (ex: mudar de tema claro para escuro, alterar a própria *timezone* ou recolher o menu lateral). Estas escolhas ficam guardadas na tabela de **User Preferences** (`sys_user_preference`).

### 2. O Módulo "Basic Configuration UI16"
Este é o "hub" central para o Branding no ServiceNow. As três configurações que **mais caem no exame CSA** que são feitas aqui são:
1. **Banner Image:** O logótipo da empresa que aparece no cabeçalho.
2. **Browser Tab Title:** O nome que aparece no separador do navegador web.
3. **System Date Format:** O formato de data e hora global da plataforma (ex: `yyyy-MM-dd`).

### 3. A Resiliência da Next Experience
Na nova interface (Next Experience), a ServiceNow introduziu os *Themes* (Temas) e as *Variants* (Variantes, como o Dark Mode). Uma boa arquitetura de *Branding* garante que o logótipo enviado em formato PNG (com fundo transparente) se adapte perfeitamente quando o utilizador ativa o tema escuro nas suas preferências.

---

## 🛠️ Execução na PDI & Mapeamento de Evidências

Vamos executar as configurações de marca na instância da Nebula Cloud Dynamics.

### Passo 1: Aceder ao Hub de Branding
Navegamos até ao módulo de configurações básicas, que centraliza as propriedades de interface de utilizador mais comuns.

> 📸 **PRINT 1: Navegação para o Basic Configuration UI16**
> *(Tira um print do ecrã mostrando o módulo "Basic Configuration UI16" aberto com os campos de edição)*
> ![Basic Configuration Panel](../../images/lab1_2_step1.png)

### Passo 2: Aplicação da Identidade Corporativa
Editamos os campos vitais de identificação do ambiente:
1. Em **Browser tab title**, escrevemos: `Nebula Cloud Dynamics - DEV`
2. Fazemos o *upload* da imagem oficial da Nebula no campo **Banner image for UI16**.
3. Em **Page header caption**, inserimos o texto secundário do cabeçalho.

> 📸 **PRINT 2: Upload do Logótipo e Alteração de Títulos**
> *(Tira um print focado na secção de upload do logo e do título do browser preenchidos)*
> ![Branding Upload](../../images/lab1_2_step2.png)

### Passo 3: Padronização Regional (Date Format)
A Nebula é uma empresa internacional, mas o ambiente de DEV segue a norma europeia/sul-americana. Ajustamos o **Date/Time format** global para o padrão `dd-MM-yyyy`. Em seguida, clicamos em **Save**.

> 📸 **PRINT 3: Configuração do System Date Format**
> *(Tira um print mostrando a configuração da data e a mensagem verde de sucesso no topo)*
> ![Date Format Saved](../../images/lab1_2_step3.png)

### Passo 4: Validação de User Personalization (Dark Mode Test)
Para provar que a nossa configuração global (Instance Configuration) é robusta, clicamos no ícone de engrenagem no cabeçalho superior direito (**Preferences**), ativamos o **Dark Theme** e validamos que a nossa logo transparente se manteve visível e profissional.

> 📸 **PRINT 4: Instância em Dark Mode com a Logo da Nebula**
> *(Tira um print do ecrã inteiro mostrando o tema escuro aplicado e a logo da empresa no cabeçalho)*
> ![Dark Theme Validation](../../images/lab1_2_step4.png)

---

## 📝 CSA Practice Simulator (Domain 1: Branding & UI)

Teste os teus conhecimentos com estas 10 questões de nível de exame real.

### Questions

#### 1. Which module is used to customize the banner image, browser tab title, and system date format globally across the ServiceNow instance?
A) Basic Configuration UI16  
B) System Dictionary  
C) User Preferences  
D) Next Experience Themes  

#### 2. An administrator uploaded a new company logo and changed the browser tab title. This is an example of what type of configuration?
A) User Personalization  
B) Instance Configuration  
C) Client-side Scripting  
D) Form Design Configuration  

#### 3. A user changes their preferred time zone and activates the Dark Theme from the gear icon in the banner frame. Where are these settings stored?
A) sys_properties table  
B) User Preferences (sys_user_preference) table  
C) The User's browser cache only  
D) Basic Configuration UI16  

#### 4. Which of the following can be customized through the Basic Configuration UI16 module? (Choose three.)
A) Banner Image  
B) Record Number Format (e.g., INC prefix)  
C) System Date Format  
D) Browser Tab Title  
E) Form Header Size  

#### 5. If an end-user changes their personal Date/Time format in their preferences, how does this affect other users in the platform?
A) It changes the date format globally for all users.  
B) It requires an administrator to approve the change.  
C) It has no effect on other users; it is a User Personalization.  
D) It triggers a Business Rule to update the Basic Configuration.  

#### 6. What role is strictly required to make changes to the instance's global banner image and browser title?
A) itil  
B) impersonator  
C) admin  
D) ui_designer  

#### 7. Why is it considered a best practice to configure a unique Browser Tab Title and Banner Image for Development, Test, and Production instances?
A) To increase the platform's processing speed.  
B) To prevent administrators and developers from accidentally making changes in the wrong environment.  
C) Because ServiceNow licensing requires different logos.  
D) It is a strict requirement to use Update Sets.  

#### 8. Which icon in the Next Experience banner frame allows a user to access their individual User Personalization settings?
A) The Star icon (Favorites)  
B) The Clock icon (History)  
C) The Gear icon (Settings/Preferences)  
D) The Magnifying Glass icon (Global Search)  

#### 9. A developer wants to change the prefix of incident records from "INC" to "INCD". Can this be done in the Basic Configuration UI16 module?
A) Yes, under the "Record Prefix" setting.  
B) No, record prefixes are configured per-table in the Number Maintenance module.  
C) Yes, but it requires the security_admin role.  
D) No, record prefixes cannot be changed once the instance is provisioned.  

#### 10. When an administrator saves a change in the Basic Configuration UI16 module, what underlying platform component is actually being updated?
A) UI Policies  
B) Client Scripts  
C) System Properties (sys_properties)  
D) System Dictionary (sys_dictionary)  

---

### 🔑 Gabarito Comentado (Análise de Especialista)

**1. Resposta Correta: A** *Comentário:* O *Basic Configuration UI16* é o local centralizado criado pela ServiceNow para que os administradores alterem as definições globais de branding de forma rápida, sem precisarem de mexer diretamente no código.

**2. Resposta Correta: B** *Comentário:* Como afeta a instância inteira (todos os utilizadores verão o mesmo logótipo), trata-se de uma *Instance Configuration*. Personalizações afetam apenas o utilizador atual.

**3. Resposta Correta: B** *Comentário:* Sempre que um utilizador clica na engrenagem e altera o tema ou as suas configurações regionais, o ServiceNow grava um registo na tabela `sys_user_preference` vinculado a esse utilizador específico.

**4. Respostas Corretas: A, C, D** *Comentário:* Questão clássica do CSA! O Formato do Número do Registo (opção B) é feito no *Number Maintenance* e o Tamanho do Cabeçalho do Formulário (opção E) não é uma configuração nativa do *Basic Configuration*.

**5. Resposta Correta: C** *Comentário:* A *User Personalization* é isolada. Se o Abel Tuter mudar o formato da data dele, só ele verá a alteração. O sistema continuará a usar a formatação base para os restantes utilizadores.

**6. Resposta Correta: C** *Comentário:* Alterações globais de interface e marca (*Branding*) afetam toda a organização, portanto, o princípio de menor privilégio exige a *role* de Administrador do Sistema (`admin`).

**7. Resposta Correta: B** *Comentário:* No mundo corporativo, um erro comum é um administrador pensar que está em "DEV" e alterar algo em "PROD" por acidente. Colocar a palavra "DEV" no logótipo e no título do browser previne falhas humanas críticas.

**8. Resposta Correta: C** *Comentário:* O ícone da engrenagem (Settings/Preferences) é a porta de entrada para todas as configurações de visualização, acessibilidade, notificações e temas do próprio utilizador.

**9. Resposta Correta: B** *Comentário:* Prefixos de numeração (INC, CHG, PRB) pertencem à arquitetura da base de dados e não ao branding visual. Devem ser alterados no módulo *Number Maintenance* (`sys_number`).

**10. Resposta Correta: C** *Comentário:* O ecrã do *Basic Configuration UI16* é apenas uma interface gráfica amigável. Quando clicas em "Save", o ServiceNow está a atualizar a tabela de propriedades globais do sistema (`sys_properties`).
