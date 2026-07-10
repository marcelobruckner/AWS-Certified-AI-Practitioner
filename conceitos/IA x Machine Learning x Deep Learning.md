Excelente escolha. Considerando sua experiência com Java, arquitetura, Kubernetes e OpenShift, vou explicar relacionando esses conceitos com o mundo de desenvolvimento, porque isso facilita muito a assimilação.

---

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
