# Capítulo 1
# Inteligência Artificial, Machine Learning e Deep Learning

---

# Objetivos de Aprendizagem

Ao concluir este capítulo, você será capaz de:

- compreender o conceito de Inteligência Artificial (IA);
- diferenciar IA, Machine Learning e Deep Learning;
- identificar quando cada abordagem é mais adequada;
- reconhecer as principais aplicações de cada tecnologia;
- compreender como a AWS costuma abordar esse tema na certificação AWS Certified AI Practitioner (AIF-C01).

---

# Pré-requisitos

Não há pré-requisitos para este capítulo.

Os conceitos apresentados servirão como base para todos os demais capítulos deste guia.

---

# Introdução

Nos últimos anos, a Inteligência Artificial passou de um tema restrito à pesquisa acadêmica para uma das tecnologias mais importantes da indústria de software.

Assistentes virtuais, sistemas de recomendação, tradutores automáticos, reconhecimento facial, carros autônomos e ferramentas como o ChatGPT demonstram que a IA deixou de ser apenas uma promessa para se tornar parte do cotidiano de milhões de pessoas.

Apesar da popularidade do termo, ainda existe muita confusão entre Inteligência Artificial, Machine Learning e Deep Learning.

É comum ouvir frases como:

> "Minha aplicação utiliza Inteligência Artificial."

Ou ainda:

> "Estamos desenvolvendo um modelo de Machine Learning."

Em muitos casos, esses termos são utilizados como sinônimos, embora representem conceitos diferentes.

Compreender essa diferença é fundamental para qualquer profissional que pretenda trabalhar com soluções baseadas em IA ou obter a certificação AWS Certified AI Practitioner.

Este capítulo apresenta a relação entre essas tecnologias e estabelece a base conceitual necessária para os próximos módulos.

---

# Visão Geral

A relação entre IA, Machine Learning e Deep Learning pode ser representada pela seguinte hierarquia:

```text
Inteligência Artificial
│
├── Sistemas Baseados em Regras
│
└── Machine Learning
      │
      └── Deep Learning
```

Essa representação mostra que:

- Todo sistema de Deep Learning é um sistema de Machine Learning.
- Todo sistema de Machine Learning faz parte da Inteligência Artificial.
- Nem toda Inteligência Artificial utiliza Machine Learning.

Essa é uma das distinções conceituais mais cobradas na certificação AWS Certified AI Practitioner.

---

# O que é Inteligência Artificial?

A Inteligência Artificial (Artificial Intelligence – AI) é um ramo da Ciência da Computação dedicado ao desenvolvimento de sistemas capazes de executar tarefas que normalmente exigiriam inteligência humana.

Entre essas tarefas estão:

- interpretar informações;
- aprender padrões;
- tomar decisões;
- compreender linguagem natural;
- reconhecer imagens;
- identificar voz;
- resolver problemas;
- realizar previsões.

A definição de IA é bastante ampla.

Não existe uma única técnica para construir um sistema inteligente.

Diversas abordagens podem ser utilizadas, dependendo do problema que se deseja resolver.

Entre elas:

- sistemas baseados em regras;
- Machine Learning;
- Deep Learning;
- algoritmos de busca;
- sistemas especialistas;
- lógica fuzzy;
- algoritmos genéticos.

Machine Learning é apenas uma dessas abordagens.

---

# Exemplo do Mundo Real

Imagine um sistema responsável por controlar o acesso de funcionários a um prédio corporativo.

Uma primeira implementação poderia utilizar regras simples.

```text
Se funcionário possui crachá válido

↓

Permitir entrada

Caso contrário

↓

Negar acesso
```

Nesse caso, toda a inteligência do sistema foi programada por um desenvolvedor.

As regras são conhecidas antecipadamente.

Sempre que surgir uma nova situação, será necessário modificar o código.

Esse sistema ainda pode ser considerado uma forma de Inteligência Artificial baseada em regras.

---

# Inteligência Artificial Baseada em Regras

Antes da popularização do Machine Learning, grande parte das soluções de IA era construída utilizando regras definidas manualmente.

Considere o exemplo abaixo.

```java
if (idade >= 18) {
    aprovarCadastro();
} else {
    negarCadastro();
}
```

Outro exemplo:

```java
if (temperatura > 38) {
    emitirAlerta();
}
```

Ou ainda:

```java
if (valorCompra > 20000) {
    bloquearTransacao();
}
```

Em todos esses casos:

- alguém definiu previamente as regras;
- o computador apenas executa essas instruções;
- o sistema não aprende com novos dados;
- qualquer alteração exige intervenção humana.

Essa abordagem continua sendo amplamente utilizada em diversas aplicações de negócio.

---

# Características da IA Baseada em Regras

## Vantagens

- Fácil de compreender.
- Fácil de implementar.
- Resultado previsível.
- Excelente para regras de negócio bem definidas.
- Baixo custo computacional.

## Desvantagens

- Não aprende.
- Difícil de escalar.
- Requer manutenção constante.
- Não identifica padrões ocultos.
- Torna-se complexa quando o número de regras cresce.

---

# Estudo de Caso

Imagine um sistema responsável por identificar fraudes em cartões de crédito.

Uma abordagem baseada em regras poderia utilizar critérios como:

```text
Valor superior a R$ 20.000

↓

Bloquear operação
```

Ou

```text
Compra realizada em país diferente

↓

Solicitar confirmação
```

Esse sistema funciona enquanto todas as situações forem conhecidas.

Entretanto, fraudadores mudam constantemente seu comportamento.

Criar manualmente milhares de regras torna-se inviável.

Nesse momento surge uma nova abordagem: permitir que o próprio sistema descubra padrões nos dados.

Essa abordagem é conhecida como Machine Learning.

---

# O que é Machine Learning?

Machine Learning (ML), ou Aprendizado de Máquina, é um subconjunto da Inteligência Artificial cujo objetivo é permitir que computadores aprendam padrões a partir de dados, sem que todas as regras precisem ser programadas explicitamente.

Em vez de informar ao computador **como** resolver um problema, fornecemos exemplos para que ele descubra sozinho quais padrões levam ao resultado esperado.

Essa é a principal diferença em relação aos sistemas baseados em regras.

Na abordagem tradicional:

```text
Desenvolvedor

↓

Escreve regras

↓

Sistema executa
```

No Machine Learning:

```text
Dados históricos

+

Respostas corretas

↓

Algoritmo de treinamento

↓

Modelo

↓

Novos dados

↓

Predição
```

Observe que o desenvolvedor continua sendo essencial, mas seu papel muda.

Em vez de programar todas as regras, ele passa a:

- selecionar os dados;
- escolher o algoritmo;
- treinar o modelo;
- avaliar os resultados;
- colocar o modelo em produção.

---

# Como o Machine Learning Funciona?

O ciclo de vida de um modelo de Machine Learning pode ser resumido em quatro etapas.

```text
Coleta dos Dados

↓

Treinamento

↓

Modelo

↓

Inferência (Predição)
```

Vamos analisar cada uma delas.

---

## 1. Coleta dos Dados

Todo modelo começa com dados.

Esses dados representam exemplos do problema que desejamos resolver.

Exemplo:

Uma empresa deseja identificar e-mails de spam.

Ela reúne milhares de mensagens já classificadas.

| Assunto | Spam? |
|----------|--------|
| Ganhe dinheiro rápido | Sim |
| Convite para reunião | Não |
| Atualização do sistema | Não |
| Oferta imperdível | Sim |

Esse conjunto recebe o nome de **dataset**.

Quanto melhor a qualidade dos dados, melhor tende a ser o modelo treinado.

> 💡 **Importante**
>
> Em Machine Learning costuma-se dizer:
>
> **"Garbage In, Garbage Out."**
>
> Se os dados forem ruins, o modelo também será.

---

## 2. Treinamento

Durante o treinamento, o algoritmo procura identificar padrões presentes nos dados.

Considere novamente o exemplo dos e-mails.

O algoritmo pode perceber que mensagens contendo determinadas palavras ou estruturas possuem maior probabilidade de serem spam.

Nenhuma dessas regras foi programada manualmente.

Elas foram aprendidas automaticamente.

Esse processo pode durar desde alguns segundos até vários dias, dependendo da complexidade do problema.

---

## 3. Modelo

Ao final do treinamento, temos um **modelo**.

O modelo representa todo o conhecimento aprendido durante o treinamento.

Ele não guarda apenas exemplos.

Ele aprende relações matemáticas capazes de generalizar para novos casos.

É esse modelo que será utilizado pelas aplicações.

---

## 4. Inferência

Inferência é o processo de utilizar um modelo já treinado para responder novas perguntas.

Exemplo:

```text
Novo e-mail

↓

Modelo treinado

↓

98% de probabilidade de ser Spam
```

A inferência costuma ser muito mais rápida do que o treinamento.

Enquanto o treinamento pode levar horas, a inferência normalmente ocorre em milissegundos.

Esse conceito aparecerá diversas vezes ao longo deste guia, especialmente quando estudarmos Foundation Models e Amazon Bedrock.

---

# Exemplo Completo

Imagine que uma instituição financeira deseja prever a aprovação de empréstimos.

Ela possui o seguinte histórico.

| Idade | Renda | Score | Empréstimo Aprovado |
|--------|--------|--------|----------------------|
| 25 | 3000 | 720 | Sim |
| 40 | 12000 | 890 | Sim |
| 19 | 1800 | 580 | Não |
| 31 | 5500 | 760 | Sim |

Esses registros são utilizados durante o treinamento.

Após aprender os padrões existentes, o modelo poderá responder algo como:

```text
Novo cliente

↓

Probabilidade de aprovação

↓

94%
```

Observe que o modelo não utiliza regras escritas manualmente.

Ele utiliza padrões aprendidos durante o treinamento.

---

# Aprendizado Supervisionado

O Aprendizado Supervisionado (Supervised Learning) é o tipo de Machine Learning mais utilizado.

Nesse modelo, cada exemplo do conjunto de treinamento já possui a resposta correta.

Exemplo:

| Imagem | Categoria |
|---------|-----------|
| 🐶 | Cachorro |
| 🐱 | Gato |
| 🚗 | Carro |

O algoritmo aprende observando exemplos já classificados.

Depois do treinamento:

```text
Nova imagem

↓

Modelo

↓

"Cachorro"
```

Problemas comuns resolvidos por Aprendizado Supervisionado:

- classificação de spam;
- detecção de fraude;
- previsão de cancelamento de clientes;
- análise de crédito;
- diagnóstico médico;
- previsão de demanda.

---

# Aprendizado Não Supervisionado

No Aprendizado Não Supervisionado (Unsupervised Learning), os dados não possuem respostas conhecidas.

O algoritmo tenta descobrir padrões por conta própria.

Exemplo:

Uma loja possui milhões de clientes.

Ela deseja descobrir grupos de consumidores com comportamentos semelhantes.

Não existe uma classificação pronta.

O algoritmo identifica agrupamentos automaticamente.

```text
Clientes

↓

Algoritmo

↓

Grupo A

Grupo B

Grupo C
```

Esse tipo de algoritmo é bastante utilizado para:

- segmentação de clientes;
- identificação de padrões de consumo;
- detecção de comportamentos incomuns;
- análise exploratória de dados.

---

# Aprendizado por Reforço (Visão Geral)

Existe ainda uma terceira categoria conhecida como **Reinforcement Learning**.

Nesse modelo, um agente aprende através de tentativa e erro.

Cada ação produz uma recompensa ou uma penalidade.

```text
Agente

↓

Executa ação

↓

Recebe recompensa

↓

Aprende

↓

Executa nova ação
```

Esse tipo de aprendizado é comum em:

- robótica;
- veículos autônomos;
- jogos;
- otimização de processos.

Embora seja um tema importante na área de IA, ele aparece apenas superficialmente na certificação AWS Certified AI Practitioner.

---

# Estudo de Caso

Imagine uma empresa de telecomunicações.

Ela deseja identificar quais clientes possuem maior probabilidade de cancelar o serviço.

Durante anos, a empresa armazenou informações como:

- idade;
- tempo de contrato;
- quantidade de chamados;
- valor da mensalidade;
- histórico de pagamentos.

Além disso, sabe quais clientes efetivamente cancelaram o serviço.

Esse conjunto de dados é utilizado para treinar um modelo supervisionado.

Após o treinamento, o modelo poderá responder:

> "Este cliente possui 92% de probabilidade de cancelar o contrato nos próximos 30 dias."

Essa informação permite que a empresa entre em contato com o cliente antes que o cancelamento aconteça.

Esse é um exemplo clássico de uso de Machine Learning para previsão de eventos futuros.

---

# Exemplo Relacionado ao Desenvolvimento de Software

Suponha que uma equipe de operações queira prever falhas em workflows do PowerCenter.

Em vez de criar regras como:

```java
if (log.contains("ORA-")) {
    falhou();
}
```

Ela pode utilizar Machine Learning.

Durante o treinamento, o modelo recebe:

- logs anteriores;
- consumo de CPU;
- utilização de memória;
- tempo de execução;
- quantidade de registros processados;
- resultado final da execução.

Após aprender os padrões, o modelo pode prever:

> "Existe 96% de probabilidade deste workflow falhar."

Nenhuma regra específica precisou ser programada.

O modelo aprendeu esse comportamento a partir dos dados históricos.

---

# O que é Deep Learning?

Deep Learning (Aprendizado Profundo) é um subconjunto do Machine Learning baseado em **Redes Neurais Artificiais Profundas (Deep Neural Networks)**.

Enquanto o Machine Learning tradicional normalmente depende da seleção manual de características dos dados (feature engineering), o Deep Learning é capaz de aprender essas características automaticamente.

Essa capacidade tornou possível resolver problemas que anteriormente eram considerados extremamente complexos para os computadores.

Entre eles:

- reconhecimento facial;
- reconhecimento de voz;
- tradução automática;
- direção autônoma;
- diagnóstico por imagem;
- Inteligência Artificial Generativa.

---

# Redes Neurais Artificiais

As Redes Neurais Artificiais foram inspiradas no funcionamento do cérebro humano.

É importante destacar que elas **não reproduzem o cérebro**, apenas utilizam um modelo matemático inspirado na forma como neurônios se conectam.

Uma rede neural é composta por diversas camadas.

```text
Entrada

↓

Camada Oculta

↓

Camada Oculta

↓

Camada Oculta

↓

Saída
```

Cada camada aprende diferentes níveis de abstração.

Por exemplo, ao reconhecer um rosto:

```text
Imagem

↓

Linhas

↓

Bordas

↓

Olhos

↓

Nariz

↓

Boca

↓

Rosto
```

Nenhuma dessas características precisa ser programada manualmente.

O próprio modelo aprende essas representações durante o treinamento.

---

# Machine Learning Tradicional versus Deep Learning

Considere o problema de identificar cachorros em imagens.

## Machine Learning Tradicional

O engenheiro precisa extrair características manualmente.

Por exemplo:

- quantidade de pixels claros;
- quantidade de pixels escuros;
- largura da imagem;
- altura;
- formato das orelhas;
- comprimento do focinho.

Depois disso, o algoritmo aprende utilizando essas informações.

O fluxo fica assim:

```text
Imagem

↓

Extração manual de características

↓

Modelo

↓

Resultado
```

---

## Deep Learning

No Deep Learning a imagem é enviada diretamente para a rede neural.

```text
Imagem

↓

Rede Neural

↓

Resultado
```

O próprio modelo aprende quais características são importantes.

Esse é um dos principais motivos pelos quais Deep Learning revolucionou áreas como visão computacional e processamento de linguagem natural.

---

# Por que "Deep"?

O termo "Deep" significa "profundo".

Ele faz referência ao número de camadas existentes na rede neural.

Uma rede simples possui poucas camadas.

Uma rede profunda pode possuir dezenas ou até centenas de camadas.

Quanto maior a profundidade, maior a capacidade de aprender padrões complexos.

Em compensação:

- exige maior poder computacional;
- necessita de maior quantidade de dados;
- costuma demandar mais tempo de treinamento.

---

# Características do Deep Learning

## Vantagens

- Aprende características automaticamente.
- Excelente desempenho em imagens.
- Excelente desempenho em áudio.
- Excelente desempenho em texto.
- Resolve problemas extremamente complexos.
- Base para IA Generativa.

---

## Desvantagens

- Necessita grande quantidade de dados.
- Alto custo computacional.
- Treinamento mais demorado.
- Difícil interpretação do processo interno de decisão.
- Pode sofrer overfitting quando treinado com poucos dados.

---

# Estudo de Caso

Imagine um hospital que deseja detectar tumores em exames de ressonância magnética.

Seria praticamente impossível programar manualmente regras como:

```text
Se existir uma mancha nesta posição

↓

Tumor
```

Cada exame possui pequenas diferenças.

Cada paciente possui anatomia diferente.

Cada equipamento gera imagens diferentes.

Nesse cenário, Deep Learning é a abordagem mais adequada.

Após analisar milhões de exames anteriores, o modelo aprende automaticamente quais padrões costumam indicar a presença de um tumor.

---

# Exemplo Relacionado ao Desenvolvimento de Software

Imagine que uma equipe de operações deseje prever incidentes em um ambiente Kubernetes.

Ela possui milhões de registros contendo:

- logs;
- métricas;
- consumo de CPU;
- utilização de memória;
- eventos do cluster;
- histórico de deploys.

Um modelo de Deep Learning pode analisar simultaneamente milhares de variáveis e identificar padrões que dificilmente seriam percebidos por regras tradicionais.

O resultado pode ser algo como:

> Existe 98,3% de probabilidade deste deployment apresentar falha nas próximas duas horas.

---

# Comparação entre IA, Machine Learning e Deep Learning

| Característica | Inteligência Artificial | Machine Learning | Deep Learning |
|----------------|-------------------------|------------------|----------------|
| Escopo | Conceito mais amplo | Subconjunto da IA | Subconjunto do ML |
| Aprende com dados | Nem sempre | Sim | Sim |
| Utiliza regras | Pode utilizar | Normalmente não | Não |
| Necessita treinamento | Nem sempre | Sim | Sim |
| Redes neurais | Não necessariamente | Opcional | Essencial |
| Grandes volumes de dados | Não obrigatório | Desejável | Normalmente necessário |
| Exemplos | Sistemas especialistas | Classificação de spam | Reconhecimento facial |

---

# Quando utilizar cada abordagem?

## Inteligência Artificial Baseada em Regras

Utilize quando:

- as regras são conhecidas;
- o comportamento é previsível;
- poucas regras resolvem o problema;
- auditoria é importante.

Exemplos:

- cálculo de impostos;
- validação de formulários;
- regras de negócio;
- motores de decisão.

---

## Machine Learning

Utilize quando:

- existe histórico de dados;
- deseja prever eventos futuros;
- deseja classificar informações;
- deseja detectar padrões.

Exemplos:

- fraude;
- previsão de vendas;
- churn;
- classificação de documentos.

---

## Deep Learning

Utilize quando:

- há grande quantidade de dados;
- o problema envolve imagens;
- o problema envolve voz;
- o problema envolve linguagem natural;
- deseja utilizar IA Generativa.

Exemplos:

- ChatGPT;
- Claude;
- Amazon Nova;
- reconhecimento facial;
- OCR avançado;
- tradução automática.

---

# Quando NÃO utilizar

## IA Baseada em Regras

Evite quando:

- o comportamento muda constantemente;
- existem milhares de exceções;
- os padrões não são conhecidos.

---

## Machine Learning

Evite quando:

- não existem dados suficientes;
- o problema pode ser resolvido facilmente com regras simples;
- não há dados históricos confiáveis.

---

## Deep Learning

Evite quando:

- existem poucos dados;
- o problema é simples;
- o custo computacional é uma preocupação;
- é necessária total explicabilidade do modelo.

---

# Como a AWS cobra esse tema

A AWS raramente pergunta definições diretamente.

Em vez disso, apresenta cenários.

Por exemplo:

> Uma empresa deseja classificar milhões de imagens de produtos automaticamente.

Palavras-chave:

- milhões;
- imagens;
- classificação automática.

Resposta esperada:

**Deep Learning.**

---

Outro exemplo.

> Uma empresa deseja prever quais clientes cancelarão seus contratos utilizando dados históricos.

Palavras-chave:

- prever;
- dados históricos;
- classificação.

Resposta esperada:

**Machine Learning.**

---

Outro exemplo.

> Uma empresa possui regras tributárias bem definidas.

Palavras-chave:

- regras conhecidas;
- comportamento previsível.

Resposta esperada:

**Sistema baseado em regras.**

---

# Pegadinhas da Certificação

## Pegadinha 1

**"Deep Learning sempre é melhor."**

Falso.

Deep Learning costuma exigir mais dados, mais processamento e maior custo.

---

## Pegadinha 2

**"Toda IA utiliza Machine Learning."**

Falso.

Sistemas baseados em regras também são formas de Inteligência Artificial.

---

## Pegadinha 3

**"Machine Learning elimina o papel do desenvolvedor."**

Falso.

O desenvolvedor continua responsável por:

- preparar dados;
- selecionar algoritmos;
- avaliar resultados;
- implantar modelos;
- monitorar desempenho.

---

## Pegadinha 4

**"Poucos dados indicam Deep Learning."**

Falso.

Com poucos dados, Machine Learning tradicional costuma ser mais adequado.

---

---

# Erros Comuns

Ao iniciar os estudos sobre Inteligência Artificial é bastante comum confundir conceitos que, embora relacionados, possuem objetivos diferentes.

Conhecer esses erros ajuda tanto na compreensão do assunto quanto na resolução das questões da certificação.

---

## Erro 1 — Considerar IA, Machine Learning e Deep Learning como sinônimos

Este é, provavelmente, o erro mais comum.

Embora estejam relacionados, representam níveis diferentes da mesma área.

```text
Inteligência Artificial
│
├── Sistemas Baseados em Regras
│
└── Machine Learning
      │
      └── Deep Learning
```

Sempre lembre:

- IA é o conceito mais amplo.
- Machine Learning é uma técnica utilizada para construir sistemas de IA.
- Deep Learning é uma técnica especializada de Machine Learning.

---

## Erro 2 — Acreditar que Machine Learning substitui todas as regras

Machine Learning não elimina completamente a necessidade de regras de negócio.

Na prática, aplicações corporativas normalmente utilizam ambos.

Exemplo:

```text
Cliente solicita empréstimo

↓

Regras obrigatórias

• CPF válido?
• Cliente maior de idade?
• Documentação completa?

↓

Machine Learning

↓

Probabilidade de inadimplência

↓

Decisão final
```

É extremamente comum encontrar soluções híbridas.

---

## Erro 3 — Escolher Deep Learning para qualquer problema

Deep Learning não é uma solução universal.

Na verdade, em muitos projetos ele representa uma escolha inadequada.

Exemplo:

Uma empresa possui apenas 3.000 registros históricos para prever inadimplência.

Nesse cenário, normalmente um algoritmo tradicional de Machine Learning produzirá melhores resultados do que uma rede neural profunda.

Sempre considere:

- quantidade de dados;
- custo computacional;
- complexidade do problema;
- necessidade de explicabilidade.

---

## Erro 4 — Acreditar que mais dados sempre significam melhor desempenho

Embora dados sejam fundamentais para o treinamento, quantidade não é sinônimo de qualidade.

Um conjunto pequeno, porém bem preparado, costuma produzir resultados superiores a um conjunto enorme com informações inconsistentes.

Por isso, a preparação dos dados é uma das etapas mais importantes de qualquer projeto de Machine Learning.

---

## Erro 5 — Confundir treinamento com inferência

Esses dois conceitos aparecerão diversas vezes durante este guia.

Treinamento:

```text
Dados históricos

↓

Algoritmo aprende

↓

Modelo
```

Inferência:

```text
Novo dado

↓

Modelo treinado

↓

Predição
```

Treinar um modelo significa ensiná-lo.

Inferência significa utilizar esse modelo para responder novas perguntas.

---

# Fluxograma de Decisão

O fluxograma abaixo ajuda a escolher a abordagem mais adequada para um problema.

```text
Existe uma regra conhecida?

        │
   ┌────┴────┐
   │         │
 Sim        Não
   │         │
   ▼         ▼
Sistema      Existe histórico
Baseado      de dados?
em Regras
             │
        ┌────┴────┐
        │         │
       Não       Sim
        │         │
        ▼         ▼
 Reavaliar     Os dados são
 o problema    complexos?
                    │
             ┌──────┴──────┐
             │             │
            Não           Sim
             │             │
             ▼             ▼
      Machine Learning   Deep Learning
```

Naturalmente, existem exceções, mas esse fluxo resolve a maioria dos cenários apresentados na certificação.

---

# Resumo para Decorar

| Conceito | Definição |
|----------|-----------|
| Inteligência Artificial | Área da computação dedicada ao desenvolvimento de sistemas capazes de executar tarefas que normalmente exigem inteligência humana. |
| Machine Learning | Técnica que permite aos computadores aprender padrões a partir de dados. |
| Deep Learning | Subárea do Machine Learning baseada em redes neurais profundas. |

---

## Quando utilizar cada abordagem

| Situação | Melhor abordagem |
|----------|------------------|
| Regras conhecidas | IA baseada em regras |
| Classificação de spam | Machine Learning |
| Previsão de churn | Machine Learning |
| Detecção de fraude | Machine Learning |
| Reconhecimento facial | Deep Learning |
| Tradução automática | Deep Learning |
| Reconhecimento de voz | Deep Learning |
| IA Generativa | Deep Learning |

---

# Palavras-chave da Certificação

A AWS costuma utilizar determinadas palavras para indicar implicitamente a tecnologia mais adequada.

| Se a questão mencionar... | Pense em... |
|---------------------------|-------------|
| Regras conhecidas | IA baseada em regras |
| Dados históricos | Machine Learning |
| Previsão | Machine Learning |
| Classificação | Machine Learning |
| Segmentação de clientes | Machine Learning |
| Milhões de imagens | Deep Learning |
| Reconhecimento facial | Deep Learning |
| Reconhecimento de voz | Deep Learning |
| Linguagem natural | Deep Learning |
| Grandes volumes de dados não estruturados | Deep Learning |

Essas associações não são regras absolutas, mas aparecem com frequência nas questões da AWS.

---

# Questões Comentadas

## Questão 1 — Nível Fácil

Uma empresa deseja bloquear automaticamente compras acima de R$ 20.000,00.

Qual abordagem é a mais adequada?

A) IA Generativa

B) Deep Learning

C) Machine Learning

D) Sistema baseado em regras

### Resposta

**Alternativa D.**

O comportamento é completamente conhecido.

Não há necessidade de treinamento.

Uma regra simples resolve o problema.

---

## Questão 2 — Nível Intermediário

Uma empresa possui milhares de registros históricos contendo idade, renda, score de crédito e informação sobre aprovação de empréstimos.

Ela deseja prever se novos clientes terão seus empréstimos aprovados.

Qual abordagem é a mais adequada?

A) Sistema baseado em regras

B) Machine Learning

C) Deep Learning

D) IA Generativa

### Resposta

**Alternativa B.**

O problema utiliza:

- dados estruturados;
- histórico conhecido;
- objetivo de previsão.

Essas características são típicas de Machine Learning.

---

## Questão 3 — Nível AWS

Uma empresa possui milhões de radiografias digitais e deseja identificar automaticamente pacientes com suspeita de pneumonia.

Os desenvolvedores não desejam definir manualmente quais características das imagens devem ser analisadas.

Qual abordagem é a mais adequada?

A) Sistema baseado em regras

B) Machine Learning tradicional

C) Deep Learning

D) Banco de Dados Relacional

### Resposta

**Alternativa C.**

As palavras-chave da questão são:

- milhões de imagens;
- aprendizado automático de características;
- visão computacional.

Esse cenário caracteriza um problema clássico de Deep Learning.

---

# Estudo de Caso AWS

Imagine uma empresa de comércio eletrônico.

Ela deseja desenvolver três soluções distintas.

## Solução 1

Bloquear pedidos acima de determinado valor quando o cartão for internacional.

Como as regras são conhecidas e mudam pouco, um sistema baseado em regras é suficiente.

---

## Solução 2

Prever quais clientes possuem maior probabilidade de cancelar uma assinatura.

Existe um histórico de milhares de clientes.

Machine Learning é a melhor escolha.

---

## Solução 3

Permitir que usuários pesquisem produtos utilizando fotografias.

Nesse caso, a aplicação precisa compreender imagens.

Deep Learning é a tecnologia mais indicada.

Esse exemplo demonstra que uma mesma empresa pode utilizar diferentes abordagens de IA, dependendo do problema que deseja resolver.

---

---

# Checklist de Revisão

Antes de avançar para o próximo capítulo, verifique se você consegue responder às perguntas abaixo sem consultar o material.

## Inteligência Artificial

- [ ] Sei definir Inteligência Artificial.
- [ ] Sei explicar por que IA é um conceito mais amplo.
- [ ] Sei citar exemplos de IA baseada em regras.
- [ ] Sei explicar quando uma solução baseada em regras é suficiente.

---

## Machine Learning

- [ ] Sei explicar o que é Machine Learning.
- [ ] Sei diferenciar treinamento e inferência.
- [ ] Sei explicar a diferença entre aprendizado supervisionado e não supervisionado.
- [ ] Sei identificar situações em que Machine Learning é mais adequado.

---

## Deep Learning

- [ ] Sei explicar o que é Deep Learning.
- [ ] Sei justificar por que Deep Learning utiliza redes neurais.
- [ ] Sei identificar situações em que Deep Learning é mais indicado que Machine Learning.
- [ ] Sei explicar por que Deep Learning normalmente necessita de grandes volumes de dados.

---

## Comparação

- [ ] Sei diferenciar IA, Machine Learning e Deep Learning.
- [ ] Sei identificar a abordagem correta para diferentes cenários.
- [ ] Consigo explicar a hierarquia entre os três conceitos.

---

# Resumo do Capítulo

Este capítulo apresentou os conceitos fundamentais que sustentam todo o restante deste guia.

A Inteligência Artificial representa o campo mais amplo, responsável pelo desenvolvimento de sistemas capazes de executar tarefas que normalmente exigiriam inteligência humana.

Dentro desse universo encontra-se o Machine Learning, abordagem que permite aos computadores aprender padrões a partir de dados históricos, substituindo parte das regras escritas manualmente por modelos treinados.

O Deep Learning, por sua vez, é uma especialização do Machine Learning baseada em redes neurais profundas, especialmente eficiente para problemas envolvendo imagens, voz, linguagem natural e grandes volumes de dados.

Também foi apresentada a principal diferença entre sistemas baseados em regras, Machine Learning e Deep Learning, bem como seus respectivos casos de uso, vantagens e limitações.

Esses conceitos servirão de base para compreender todos os assuntos abordados nos próximos capítulos.

---

# Principais Pontos para a Certificação

Ao resolver questões da AWS Certified AI Practitioner, lembre-se das seguintes associações:

| Cenário | Tecnologia mais indicada |
|---------|---------------------------|
| Regras de negócio conhecidas | IA baseada em regras |
| Dados históricos estruturados | Machine Learning |
| Previsão de eventos | Machine Learning |
| Classificação | Machine Learning |
| Segmentação de clientes | Machine Learning |
| Reconhecimento facial | Deep Learning |
| Reconhecimento de voz | Deep Learning |
| Tradução automática | Deep Learning |
| IA Generativa | Deep Learning |

---

# Em uma Frase

> **Inteligência Artificial é o conceito mais amplo; Machine Learning permite que sistemas aprendam padrões a partir de dados; Deep Learning utiliza redes neurais profundas para resolver problemas complexos e constitui a base das aplicações modernas de IA Generativa.**

---

# Glossário

## Artificial Intelligence (AI)

Área da Ciência da Computação dedicada ao desenvolvimento de sistemas capazes de executar tarefas normalmente associadas à inteligência humana.

---

## Machine Learning (ML)

Subárea da Inteligência Artificial que utiliza algoritmos capazes de aprender padrões a partir de dados.

---

## Deep Learning (DL)

Subárea do Machine Learning baseada em redes neurais profundas.

---

## Modelo (Model)

Representação matemática produzida durante o treinamento e utilizada para realizar inferências.

---

## Dataset

Conjunto de dados utilizado durante o treinamento de um modelo.

---

## Treinamento (Training)

Processo de aprendizado do modelo a partir de exemplos.

---

## Inferência (Inference)

Processo de utilização de um modelo treinado para realizar previsões ou classificações sobre novos dados.

---

## Aprendizado Supervisionado

Tipo de Machine Learning em que os dados de treinamento já possuem as respostas corretas.

---

## Aprendizado Não Supervisionado

Tipo de Machine Learning em que o algoritmo identifica padrões sem possuir respostas previamente conhecidas.

---

## Rede Neural Artificial

Modelo computacional inspirado no funcionamento dos neurônios biológicos, utilizado em algoritmos de Deep Learning.

---

# Referências

A elaboração deste capítulo foi baseada nas seguintes referências oficiais:

- AWS Certified AI Practitioner (AIF-C01) Exam Guide
- AWS Skill Builder – AI Practitioner Learning Plan
- AWS Documentation – Artificial Intelligence
- AWS Documentation – Machine Learning
- Amazon SageMaker Developer Guide
- Amazon Bedrock User Guide

Complementarmente, foram consultadas obras clássicas da área para fundamentação conceitual:

- Russell, Stuart; Norvig, Peter. *Artificial Intelligence: A Modern Approach.*
- Goodfellow, Ian; Bengio, Yoshua; Courville, Aaron. *Deep Learning.*
- Géron, Aurélien. *Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow.*

---

# Próximo Capítulo

No próximo capítulo será apresentado um dos temas centrais da certificação AWS Certified AI Practitioner:

# IA Generativa

Você aprenderá:

- o que diferencia IA Generativa do Machine Learning tradicional;
- como modelos generativos produzem novos conteúdos;
- quais problemas essa tecnologia resolve;
- por que ela revolucionou o mercado de software;
- como a AWS utiliza IA Generativa em serviços como o Amazon Bedrock.

Os conceitos apresentados nesse próximo capítulo servirão como base para compreender Large Language Models (LLMs), Foundation Models e os demais assuntos relacionados à IA Generativa.

---

**Fim do Capítulo 1**