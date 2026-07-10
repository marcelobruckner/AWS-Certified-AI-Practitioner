# IA (Artificial Intelligence)

**Inteligência Artificial** é o conceito mais amplo.

É qualquer sistema capaz de realizar tarefas que normalmente exigiriam inteligência humana.

Por exemplo:

* reconhecer uma imagem;
* conversar com uma pessoa;
* traduzir um texto;
* recomendar um filme;
* dirigir um carro;
* detectar fraude.

O importante é entender que **não importa como isso foi implementado**.

Se o sistema consegue simular alguma capacidade humana, ele é considerado IA.

Imagine a seguinte hierarquia:

```
Inteligência Artificial
        │
        ├── Machine Learning
        │        │
        │        └── Deep Learning
        │
        └── Sistemas baseados em regras
```

Ou seja:

Todo Machine Learning é IA.

Todo Deep Learning é Machine Learning.

Mas nem toda IA utiliza Machine Learning.

---

## IA baseada em regras

Antes do Machine Learning era muito comum construir IA assim:

```java
if (idade > 18)
    aprovar();

else
    negar();
```

ou

```java
if (temperatura > 38)
    suspeitaCovid();
```

Quem criou a inteligência?

O desenvolvedor.

O computador apenas executa.

Isso também é IA.

---

# Machine Learning

Agora muda completamente.

Em vez de escrever regras...

Você fornece exemplos.

O algoritmo aprende sozinho.

Imagine um sistema para detectar spam.

Ao invés de escrever:

```java
if (assunto.contains("PIX"))
```

você entrega milhares de emails classificados como

* Spam
* Não Spam

O algoritmo encontra padrões.

Depois disso consegue classificar novos emails.

Ou seja...

Você não programa a lógica.

Você programa o treinamento.

---

## Exemplo

Entradas:

```
Email 1 -> Spam

Email 2 -> Spam

Email 3 -> Não Spam

Email 4 -> Spam
```

Depois do treinamento...

Novo email

↓

O modelo responde

```
97% chance de ser Spam
```

Você nunca escreveu uma regra dizendo isso.

---

## Pense assim

Java tradicional

```
Dados

↓

Código

↓

Resposta
```

Machine Learning

```
Dados

+

Resposta correta

↓

Treinamento

↓

Modelo

↓

Novos dados

↓

Resposta
```

A lógica foi descoberta automaticamente.

---

# Deep Learning

Deep Learning é um tipo especial de Machine Learning.

Ele usa Redes Neurais Artificiais.

Essas redes são inspiradas no cérebro humano.

Não são iguais ao cérebro.

Apenas inspiradas.

---

Imagine reconhecer um cachorro.

Machine Learning tradicional:

Você fornece características.

```
Tem pelo?

Tem quatro patas?

Tem focinho?

Tem rabo?
```

O algoritmo aprende.

---

Deep Learning

Você fornece apenas a imagem.

Nada mais.

A rede neural descobre tudo.

Ela aprende sozinha.

```
Olho

↓

Focinho

↓

Cabeça

↓

Animal

↓

Cachorro
```

Ela cria milhares de representações internas.

---

## Exemplo

Reconhecimento facial.

Você jamais conseguiria escrever:

```java
if (distanciaOlhos == 2.34 &&
    nariz == ...)
```

É impossível.

Mas uma rede neural consegue.

---

# Comparação

## IA tradicional

```
Programador

↓

Escreve regras

↓

Sistema
```

---

## Machine Learning

```
Dados

↓

Algoritmo aprende

↓

Modelo

↓

Sistema
```

---

## Deep Learning

```
Milhões de dados

↓

Rede Neural

↓

Aprende representações complexas

↓

Modelo
```

---

# Exemplo da AWS

Imagine um banco.

Quer detectar fraude.

### IA baseada em regras

```
Valor > 20.000

↓

Bloquear
```

Muito simples.

---

### Machine Learning

Treina usando

* horário
* localização
* valor
* dispositivo
* histórico
* frequência

O algoritmo aprende.

---

### Deep Learning

Além disso analisa

* comportamento do cliente
* sequência de compras
* padrões extremamente complexos

Obtém uma precisão muito maior.

---

# Um exemplo do seu dia a dia

Você trabalhou com checklist do **PowerCenter**.

Imagine que hoje você queira detectar automaticamente se uma execução vai falhar.

IA baseada em regras:

```
Se log contém "ERROR"

↓

Falhou
```

Machine Learning:

Analisa milhares de execuções passadas.

Aprende padrões.

Prevê:

> "Existe 94% de chance deste workflow falhar."

Deep Learning:

Além dos logs, analisa:

* histórico completo
* métricas
* consumo de CPU
* memória
* sequência de eventos
* dependências entre jobs

Encontra padrões que um humano dificilmente perceberia.

---

# O que a AWS gosta de cobrar

Eles adoram perguntas conceituais como estas:

* Quando usar IA baseada em regras?
* Quando Machine Learning é mais adequado?
* Quando Deep Learning é necessário?
* Deep Learning é um subconjunto de Machine Learning?
* Machine Learning depende de dados rotulados?
* É preciso escrever regras em Machine Learning?

---

# Resumo para decorar

| IA                        | Machine Learning                 | Deep Learning                                             |
| ------------------------- | -------------------------------- | --------------------------------------------------------- |
| Conceito mais amplo       | Subconjunto da IA                | Subconjunto do ML                                         |
| Pode usar regras          | Aprende com dados                | Aprende com grandes volumes de dados usando redes neurais |
| Pode não aprender         | Aprende padrões                  | Aprende padrões complexos automaticamente                 |
| Poucos dados              | Dados de treinamento             | Grandes volumes de dados                                  |
| Desenvolvedor cria regras | Desenvolvedor cria o treinamento | Desenvolvedor cria a arquitetura e fornece os dados       |

## O que você precisa guardar para a prova

1. **IA é o guarda-chuva** que engloba diferentes técnicas para criar sistemas inteligentes.
2. **Machine Learning** permite que o sistema aprenda padrões a partir de dados, em vez de depender de regras escritas manualmente.
3. **Deep Learning** é um tipo de Machine Learning baseado em redes neurais profundas, especialmente eficaz para tarefas como visão computacional, reconhecimento de fala e IA generativa.

---

### Pergunta para fixação (estilo AWS)

Uma empresa possui milhões de imagens de produtos e deseja criar um sistema que identifique automaticamente a categoria de cada imagem, sem que os desenvolvedores precisem definir manualmente características como cor, formato ou textura.

Qual abordagem é a mais adequada?

A) IA baseada em regras

B) Machine Learning tradicional com regras definidas pelo desenvolvedor

C) Deep Learning utilizando redes neurais

D) Banco de dados relacional com consultas SQL

**Pense na resposta e me diga qual alternativa você escolheria e por quê.** Depois analisamos juntos o raciocínio, como aconteceria na prova da AWS.

**Como a questão fala de milhões de imagens, me leva a crer que a resposta é a letra C, deep learning.**

🎯 **Exatamente! A resposta correta é a letra C.**

Mais importante do que acertar é entender **por que** ela é a correta. A AWS gosta de criar alternativas que parecem plausíveis.

---

## Vamos analisar a questão

> Uma empresa possui **milhões de imagens** e deseja identificar automaticamente a categoria de cada imagem, **sem que os desenvolvedores precisem definir manualmente características**.

Existem duas pistas muito fortes:

### Pista 1: Milhões de imagens

Isso indica um problema com um enorme volume de dados.

Deep Learning se beneficia justamente de grandes quantidades de dados. Em geral:

* Machine Learning tradicional → funciona bem com milhares ou dezenas de milhares de exemplos.
* Deep Learning → costuma atingir seu potencial com centenas de milhares ou milhões de exemplos.

### Pista 2: Sem definir características manualmente

Essa é a dica mais importante.

No Machine Learning tradicional, muitas vezes o engenheiro precisa fazer **feature engineering**, ou seja, escolher quais características serão usadas pelo modelo.

Por exemplo, para identificar um cachorro, alguém poderia extrair atributos como:

* altura;
* largura;
* quantidade de pixels escuros;
* formato das orelhas.

No Deep Learning, especialmente com redes neurais convolucionais (CNNs), o próprio modelo aprende automaticamente essas características.

É por isso que Deep Learning revolucionou visão computacional.

---

## Vamos eliminar as alternativas

### A) IA baseada em regras ❌

Imagine escrever:

```text
Se tiver quatro patas...
Se tiver pelo...
Se tiver focinho...
```

Isso não funciona para milhões de imagens com milhares de variações.

---

### B) Machine Learning tradicional ❌

Seria possível?

Sim.

Seria a melhor opção?

Não.

A própria questão diz que **não quer definir características manualmente**, exatamente um dos pontos fortes do Deep Learning.

---

### C) Deep Learning ✅

Perfeito.

Ele aprende sozinho quais padrões diferenciam:

* cachorro
* gato
* carro
* bicicleta
* árvore

Sem alguém programar essas características.

---

### D) Banco de dados relacional ❌

Um banco de dados armazena informações.

Ele não aprende padrões.

---

# Um detalhe importante para a prova

A AWS adora usar palavras que servem como "gatilhos". Quando você vê uma delas, já deve pensar em determinadas tecnologias.

| A questão menciona...                     | Pense em...                  |
| ----------------------------------------- | ---------------------------- |
| Milhões de imagens                        | Deep Learning                |
| Reconhecimento facial                     | Deep Learning                |
| Reconhecimento de voz                     | Deep Learning                |
| Tradução automática                       | Deep Learning                |
| IA Generativa                             | Deep Learning                |
| Grandes volumes de dados não estruturados | Deep Learning                |
| Poucos dados e problema simples           | Machine Learning tradicional |
| Regras fixas de negócio                   | IA baseada em regras         |

Esses gatilhos não são absolutos, mas aparecem com muita frequência em questões da AWS.

---

# Fazendo uma ligação com sua experiência

Imagine o sistema que você desenvolveu para monitorar os jobs do PowerCenter.

Se você escrevesse:

```java
if (log.contains("ORA-"))
    falha();
```

➡️ IA baseada em regras.

Se você treinasse um modelo com **10.000 execuções anteriores** para prever falhas a partir de métricas e logs:

➡️ Machine Learning.

Se você utilizasse **milhões de linhas de logs**, métricas de CPU, memória, sequência temporal dos eventos e um modelo de rede neural para descobrir padrões complexos sem definir manualmente quais características são importantes:

➡️ Deep Learning.

Percebe como é uma evolução natural? Você sai de regras explícitas para modelos que aprendem padrões cada vez mais complexos.

---

## Para consolidar

Quero deixar uma pergunta no estilo da AWS, um pouco mais difícil:

> Uma empresa possui apenas **5.000 registros históricos** de aprovação de empréstimos. Cada registro contém idade, renda, profissão, score de crédito e se o empréstimo foi aprovado. O objetivo é prever se novos clientes terão o empréstimo aprovado.

Qual abordagem tende a ser a mais adequada?

A) IA baseada em regras

B) Machine Learning tradicional

C) Deep Learning

D) IA Generativa

Qual alternativa você escolheria? E, mais importante, **qual é o seu raciocínio?** Esse raciocínio é o que realmente vai fazer você passar na AIF-C01.

**letra B - Machine Learning Tradicional.**

👏 Excelente. Você está raciocinando exatamente da forma que a AWS espera.

A resposta correta é **B) Machine Learning tradicional**.

Vamos entender o porquê.

---

# Analisando a questão

A empresa possui:

* apenas **5.000 registros**
* dados estruturados
* um problema de classificação (aprovar ou não um empréstimo)

Os dados são como uma tabela:

| Idade | Salário | Score | Profissão  | Aprovado |
| ----- | ------- | ----- | ---------- | -------- |
| 32    | 8000    | 780   | Engenheiro | Sim      |
| 24    | 2500    | 610   | Professor  | Não      |
| 41    | 15000   | 900   | Médico     | Sim      |

Isso é um conjunto de dados estruturado e relativamente pequeno.

---

## Por que Machine Learning?

Machine Learning tradicional funciona muito bem quando:

* os dados são estruturados;
* o número de atributos é pequeno;
* existe um histórico rotulado (neste caso, "Aprovado" ou "Não aprovado");
* o volume de dados não é gigantesco.

Algoritmos como:

* Regressão Logística
* Árvores de Decisão
* Random Forest
* Gradient Boosting

costumam resolver esse tipo de problema com excelente desempenho.

---

## Por que não Deep Learning?

É aqui que muitos candidatos erram.

Pensam:

> IA = Deep Learning.

Não.

Deep Learning não é automaticamente a melhor escolha.

Na verdade, ele costuma ser uma escolha pior quando:

* há poucos dados;
* o problema é simples;
* os dados são tabulares.

Treinar uma rede neural profunda com apenas 5.000 registros pode levar ao **overfitting**, quando o modelo "decora" os dados de treinamento e generaliza mal para novos casos.

---

## Por que não IA baseada em regras?

Você poderia escrever algo como:

```java
if (score > 700 && salario > 5000)
    aprovar();
```

Mas essa abordagem tem limitações:

* difícil de manter;
* rígida;
* não aprende novos padrões;
* pode ignorar relações mais sutis entre as variáveis.

O Machine Learning consegue descobrir essas relações automaticamente.

---

## Por que não IA Generativa?

IA Generativa serve para criar conteúdo, como:

* texto;
* imagens;
* áudio;
* código;
* vídeos.

Ela não é a ferramenta adequada para prever aprovação de empréstimos.

---

# Um quadro mental útil para a prova

Sempre pergunte:

### O dado é estruturado?

✔️ Sim → pense primeiro em Machine Learning.

---

### O dado é imagem, áudio ou texto?

✔️ Sim → considere Deep Learning.

---

### Existem milhões de exemplos?

✔️ Sim → Deep Learning ganha força.

---

### Existem poucos milhares de registros?

✔️ Sim → Machine Learning tradicional costuma ser suficiente.

---

### O problema é criar conteúdo?

✔️ Sim → IA Generativa.

---

## Como a AWS costuma formular essas questões

Em vez de perguntar "qual algoritmo usar?", ela apresenta um cenário.

Por exemplo:

> "Uma empresa deseja prever quais clientes cancelarão a assinatura utilizando dados históricos de compras."

Você deve identificar:

* problema de previsão ✔️
* dados estruturados ✔️
* histórico rotulado ✔️

➡️ **Machine Learning**.

Já se disser:

> "Uma empresa deseja analisar milhões de radiografias para identificar tumores."

Você identifica:

* imagens ✔️
* milhões de exemplos ✔️

➡️ **Deep Learning**.

---

## Até agora, seu desempenho

Você acertou **2 de 2 questões**, e o mais importante: justificou as respostas com o raciocínio correto. Isso é um ótimo sinal para a AIF-C01.

A partir de agora, vamos entrar em um conceito que aparece em praticamente todas as provas atuais de IA da AWS: **IA Generativa**.

Vamos responder às perguntas:

* O que torna a IA Generativa diferente do Machine Learning tradicional?
* O que é um **LLM (Large Language Model)**?
* O que são **Foundation Models**?
* Qual é a diferença entre um modelo treinado tradicionalmente e um Foundation Model?

Esses conceitos são a base do serviço **Amazon Bedrock**, que é um dos temas mais cobrados na certificação.
