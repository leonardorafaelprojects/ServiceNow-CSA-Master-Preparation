# 🔵 Lab Nebula 2.1: Lists and Filters Optimization

## 🏢 O Cenário Corporativo (Business Case)
Os gestores da **Nebula Cloud Dynamics** perdiam tempo diariamente recriando filtros manuais para visualizar incidentes críticos. Além disso, a visão de lista padrão continha colunas irrelevantes para os coordenadores de plantão. Como Arquiteto, fui encarregado de aplicar a governança de filtros e treinar a equipe no uso de personalização e relatórios instantâneos.

## 🛠️ Execução e Evidências Práticas

### 1. Construção e Partilha de Filtros (Condition Builder)
Utilizando a metodologia **FOV (Field, Operator, Value)**, criamos uma query rigorosa para incidentes ativos de alta prioridade. A principal aplicação arquitetural aqui foi salvar o filtro definindo a visibilidade para **Everyone**, garantindo que toda a equipa de operações tenha acesso imediato a esta visão sem precisarem de ser administradores.

> 📸 **Evidência 01: Filtro "Nebula Critical Incidents"**
> 
> ![Condition Builder](../../images/lab2_1_step1.png)

### 2. User Personalization (Ajustando a Visão do Utilizador)
Diferente do *List Layout* (que afeta a instância inteira), instruímos o gestor a usar o ícone de **Engrenagem** (*Personalized List*). Removemos colunas ruidosas e adicionamos as essenciais. O sistema armazena esta preferência de forma isolada na tabela `sys_user_preference`.

> 📸 **Evidência 02: Lista Personalizada Ativa**
> 
> ![Personalized List](../../images/lab2_1_step2.png)

### 3. Edição em Massa e Relatórios Instantâneos
Para operações ágeis, validamos o uso do **List Editor** (edição inline via duplo clique) e do **Column Context Menu** para gerar gráficos de barras em tempo real, eliminando a necessidade de navegar até o módulo de relatórios para análises rápidas.

> 📸 **Evidência 03: List Editor em Ação**
> 
> ![List Editor](../../images/lab2_1_step3.png)

> 📸 **Evidência 04: Gráfico gerado via Context Menu**
> 
> ![Quick Report](../../images/lab2_1_step4.png)
