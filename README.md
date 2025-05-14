
# 🧠 Criação de um Copiloto com Fluxo de Conversa Personalizado no Microsoft Copilot Studio

Este documento apresenta o passo a passo completo para a criação de um Copiloto com **fluxo de conversa personalizado** no **Microsoft Copilot Studio**. Abordamos desde a estruturação de tópicos, uso de entidades, criação e manipulação de variáveis, aplicação de condicionais, integração com IA generativa (incluindo alimentação com dados), até os testes de funcionamento.

---

## 🛠️ Etapas do Desenvolvimento

---

### 1. 📋 Planejamento Inicial

Antes de criar o copiloto, defina:

- **Objetivo do Copiloto:** O que ele irá resolver? Qual o contexto de uso?
- **Usuário-alvo:** Quais são as dúvidas ou tarefas que ele espera resolver?
- **Cenários de Conversa:** Quais tópicos devem estar disponíveis?

---

### 2. 🧵 Criação de Tópicos

Tópicos representam blocos de conversa com propósito definido.

**Passos:**

1. Acesse o Copilot Studio.
2. Vá para **"Tópicos"** e clique em **"Novo tópico"**.
3. Defina:
   - Nome do tópico
   - Frases de gatilho (ex: “quero agendar reunião”, “me ajuda com boleto”)
4. Use o **editor visual** para construir o fluxo de diálogo com perguntas, mensagens, ações, chamadas de IA ou fluxos externos.

> Um tópico pode ter ramificações com base nas respostas e condições do usuário.

---

### 3. 🧠 Uso de Entidades

As **entidades** extraem dados da entrada do usuário.

#### Tipos:

- **De sistema:** já prontas (ex: `datetime`, `number`, `age`, `email`).
- **De ambiente (personalizadas):** criadas por você, com valores definidos (ex: `Produto` com valores como “notebook”, “fone”).

**Utilização:**

- Vincule entidades a perguntas para capturar dados automaticamente.
- Ajudam a validar a entrada do usuário e melhorar a precisão do fluxo.

**Exemplo:**
```txt
Pergunta: Qual produto você está interessado?
→ Entidade usada: Produto
```

---

### 4. 🧩 Variáveis e sua Manipulação

As variáveis armazenam informações durante o fluxo.

#### Tipos de Variáveis:

- **Locais:** Existentes apenas dentro de um tópico.
- **Globais:** Acessíveis por todos os tópicos e persistentes entre sessões.

#### Criação e Manipulação:

- Capturadas por perguntas ou ações (ex: resposta do usuário).
- Modificadas por ações lógicas, retorno de API ou IA generativa.
- Usadas em mensagens, condicionais ou prompts.

**Exemplo de uso:**
```txt
Variável Local: nome_cliente
Ação: "Olá, {nome_cliente}! Como posso ajudar você hoje?"
```

#### Atribuições Manuais:

- Atribua valores fixos com "Definir variável"
- Utilize operadores lógicos para comparações e atribuições condicionais

---

### 5. 🔀 Uso de Condicionais

As **condições** controlam o fluxo baseado em decisões.

**Tipos de Condições:**

- Comparações (`=`, `≠`, `>`, `<`)
- Combinações (`E`, `OU`)
- Verificação de entidades

**Exemplo:**
```txt
SE categoria = "Notebook"
→ Mostrar recomendações de notebooks
SENÃO
→ Mostrar categorias disponíveis
```

Essas condições são construídas no editor visual com **ramificações**.

---

### 6. 🤖 Uso de IA Generativa (GPT)

O Microsoft Copilot Studio permite utilizar **IA generativa** para criar respostas contextuais e dinâmicas.

#### Inserção de Ações de IA:

1. Dentro de um tópico, clique em **“Adicionar”** > **“Ação”** > **“Resposta com IA generativa”**.
2. Crie um **prompt claro e objetivo**, utilizando variáveis se necessário.

**Exemplo de Prompt:**
```
Explique, em linguagem simples, as diferenças entre os produtos {produto1} e {produto2}.
```

#### Alimentação de Dados (Grounding):

A IA pode ser alimentada com conhecimento externo:

- **Arquivos:** Word, PDF, Excel
- **Sites/URLs:** Permite consultas ao conteúdo de uma página
- **SharePoint e Dataverse:** Para dados empresariais

> Isso melhora a precisão e controle das respostas da IA.

---

### 7. 🔁 Integração com Fluxos Externos (Power Automate)

É possível acionar fluxos do Power Automate para:

- Consultas a banco de dados
- Envio de emails
- Operações externas com lógica mais complexa

Esses fluxos retornam dados que podem ser atribuídos a variáveis no Copiloto.

---

### 8. 🧪 Testes do Copiloto

O Copilot Studio fornece ferramentas para testar a experiência.

#### Etapas:

1. Clique em **"Testar Copiloto"** no canto superior.
2. Simule conversas com frases diferentes (variações dos gatilhos).
3. Verifique:
   - Acionamento correto dos tópicos
   - Preenchimento das variáveis
   - Respostas da IA generativa
   - Execução correta de condicionais
4. Use o painel lateral para rastrear:
   - Variáveis
   - Entidades extraídas
   - Decisões de fluxo

#### Dicas:

- Teste entradas válidas e inválidas
- Simule interrupções e trocas de assunto
- Ajuste gatilhos e condições conforme necessário

---

## 📌 Boas Práticas

- Use nomes descritivos para variáveis e tópicos
- Separe fluxos grandes em subtópicos ou fluxos reutilizáveis
- Documente os prompts de IA e vincule aos dados de origem
- Mantenha os tópicos objetivos e com foco claro
- Use IA generativa com moderação, sempre controlando o escopo

---

## ✅ Conclusão

Criar um Copiloto com fluxo de conversa personalizado no Microsoft Copilot Studio é um processo poderoso que combina:

- Estruturação lógica via tópicos e condições
- Captura inteligente de dados com entidades
- Armazenamento e uso de variáveis
- Geração de linguagem natural com IA generativa
- Integração com fontes de dados externas

Com testes e planejamento cuidadoso, você pode entregar uma **experiência conversacional robusta e inteligente** para os usuários.
