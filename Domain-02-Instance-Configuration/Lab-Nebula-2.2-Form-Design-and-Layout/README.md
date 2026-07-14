# 🔵 Lab Nebula 2.2: Form Design and Layout

## 🏢 O Cenário (Business Case na Nebula)
A equipa de Service Desk da Nebula Cloud Dynamics reportou que o formulário de Incidentes estava desorganizado, misturando campos de resolução com dados do cliente e aumentando o MTTR (Mean Time to Resolve). Além disso, incidentes recorrentes de queda de rede (*Network Outages*) estavam a ser preenchidos manualmente com muita lentidão. A tua missão é aplicar o Form Designer para reestruturar o layout e criar Templates para automação de dados.

---

## 📚 Teoria de Ouro para o Exame CSA (Anota isto!)
* **Form Layout vs. Form Designer:** O *Form Layout* usa a interface clássica *Slushbucket* para adicionar campos rapidamente. O **Form Designer** é a única interface que permite criar visualmente **Sections** (secções estruturadas com 1 ou 2 colunas).
* **Formatters:** Cuidado! Um *Formatter* (como o Activity Stream) não é uma coluna da base de dados. É um elemento visual injetado no formulário para mostrar dados complexos originários de outras tabelas.
* **Templates:** São "carimbos" que permitem pré-preencher instantaneamente múltiplos campos (como Categoria, Prioridade e Grupo) num novo registo, poupando tempo na introdução de dados.

---

## 🛠️ Execução na PDI (Hands-on)
Abre o teu ambiente da Nebula Cloud Dynamics e segue estes passos:

### Parte 1: Reestruturação com o Form Designer
1. Abre qualquer registo de Incidente (`Incident > All` e clica num número).
2. Clica com o botão direito no cabeçalho superior (cinza) e seleciona **Configure > Form Design**.
3. Desce até ao final da nova janela e arraste o bloco **Section** do menu esquerdo para o fundo do formulário.
4. Dá o nome `Nebula Resolution Info` a esta nova Section e garante que tem um layout de **2 Colunas**.
5. Arraste os campos `Close code` e `Close notes` para dentro desta Section. Clica em **Save** no topo direito.
6. Volta ao formulário do incidente e recarrega a página.

> 📸 **PRINT 1: Manipulação visual no Form Designer**
> 
> ![Form Designer UI](../../images/lab2_2_step1.png)

> 📸 **PRINT 2: Formulário em Produção (Resultado)**
> 
> ![Live Form](../../images/lab2_2_step2.png)

### Parte 2: Automação de Entrada de Dados (Templates)
1. No formulário do Incidente, clica no ícone **More options (...)** no cabeçalho e seleciona **Toggle Template Bar**.
2. No rodapé da página que acabou de aparecer, clica no botão `+` (*Create a new template*).
3. Cria o Template com as seguintes configurações: 
   * **Name:** `Nebula Network Outage`
   * **Template (Conditions):** `Category = Network`, `Priority = 1 - Critical`, `Impact = 1 - High`. 
4. Clica em Submit.
5. Cria um novo Incidente vazio (`Incident > Create New`). Clica no teu template no rodapé e verifica o preenchimento automático.

> 📸 **PRINT 3: Aplicação instantânea do Template**
> *(A barra azul no topo comprova a injeção automática dos dados)*
> 
> ![Template Applied](../../images/lab2_2_step3.png)
