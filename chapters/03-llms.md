# Capítulo 3 — Large Language Models (LLMs)

---

# Objetivos de Aprendizagem

Ao concluir este capítulo, você será capaz de:

- compreender o que são Large Language Models (LLMs);
- explicar por que LLMs são importantes para IA Generativa;
- entender, em alto nível, como LLMs processam e geram linguagem;
- diferenciar LLMs, Foundation Models e modelos tradicionais de Machine Learning;
- reconhecer conceitos como tokens, parâmetros, prompt, contexto e inferência;
- identificar aplicações práticas de LLMs em empresas;
- compreender limitações, riscos e cuidados importantes;
- associar LLMs aos serviços AWS cobrados na certificação AWS Certified AI Practitioner (AIF-C01).

---

# Pré-requisitos

Antes deste capítulo, é recomendado compreender:

- o que é Inteligência Artificial;
- o que é Machine Learning;
- o que é Deep Learning;
- o que é IA Generativa;
- a diferença entre treinamento e inferência.

Os capítulos anteriores apresentam esses conceitos.

---

# Introdução

Large Language Models, ou LLMs, são modelos de Inteligência Artificial especializados em processar e gerar linguagem.

Eles ficaram conhecidos por permitir conversas em linguagem natural, geração de textos, sumarização, tradução, criação de código, respostas a perguntas e análise de documentos.

Quando uma aplicação recebe uma pergunta escrita por uma pessoa e responde com texto coerente, provavelmente existe um LLM envolvido.

Exemplos de uso:

- responder perguntas de clientes;
- resumir contratos;
- explicar erros de software;
- gerar e-mails;
- criar descrições de produtos;
- transformar texto em consulta SQL;
- auxiliar no desenvolvimento de código;
- interpretar documentos longos;
- criar chatbots corporativos.

O ponto central é:

> LLMs são modelos grandes de Deep Learning treinados para entender e gerar linguagem natural.

---

# Conceitos Fundamentais

# O que é um LLM?

Um **Large Language Model (LLM)** é um modelo de Deep Learning treinado com grandes volumes de texto para aprender padrões de linguagem.

Esses padrões incluem:

- gramática;
- vocabulário;
- relações entre palavras;
- contexto;
- estilos de escrita;
- estruturas de perguntas e respostas;
- padrões de raciocínio textual;
- formatos de documentos;
- exemplos de código;
- instruções em linguagem natural.

Depois do treinamento, o modelo consegue receber uma entrada textual e gerar uma continuação provável.

Essa continuação pode parecer uma resposta, um resumo, um código, uma explicação ou uma análise.

---

# O que significa "Large"?

O termo **Large** indica que esses modelos são grandes em diferentes sentidos.

Eles normalmente possuem:

- muitos parâmetros;
- grande volume de dados de treinamento;
- alto custo computacional de treinamento;
- capacidade de executar várias tarefas;
- suporte a entradas e saídas complexas;
- dependência de infraestrutura especializada.

Na prática, um LLM aprende relações estatísticas em grande escala.

Ele não funciona como uma tabela de respostas prontas.

Ele calcula a próxima parte mais provável de uma resposta com base no que recebeu como entrada e no que aprendeu durante o treinamento.

---

# O que significa "Language"?

O termo **Language** indica que o foco principal é linguagem.

Isso inclui:

- texto em linguagem natural;
- perguntas;
- instruções;
- diálogos;
- documentos;
- código-fonte;
- estruturas de dados textuais;
- mensagens de erro;
- logs;
- consultas;
- documentação técnica.

Embora muitos LLMs sejam usados para texto, modelos modernos podem aparecer em soluções multimodais, combinando texto com imagem, áudio ou vídeo.

Para a certificação AWS Certified AI Practitioner, o foco principal é entender LLMs como modelos capazes de processar e gerar linguagem.

---

# O que significa "Model"?

Um **Model** é o resultado de um processo de treinamento.

No caso de um LLM, o treinamento ajusta bilhões de relações matemáticas internas para que o modelo consiga prever e gerar linguagem.

De forma simplificada:

```text
Grandes volumes de texto

↓

Treinamento

↓

Large Language Model

↓

Geração de texto durante a inferência
```

O modelo não é o código da aplicação.

O modelo é o artefato treinado que a aplicação utiliza para gerar respostas.

---

# LLMs e Deep Learning

LLMs são baseados em Deep Learning.

Mais especificamente, muitos LLMs modernos usam uma arquitetura chamada **Transformer**.

Para este guia, não é necessário conhecer a matemática interna do Transformer.

O que importa para a prova é compreender que essa arquitetura permitiu que modelos processassem linguagem em grande escala, capturando relações entre palavras, frases e contexto.

Fluxo simplificado:

```text
Texto de entrada

↓

Representação numérica

↓

Rede neural profunda

↓

Predição do próximo token

↓

Texto gerado
```

---

# Como um LLM Gera Texto?

Um LLM gera texto de forma incremental.

Ele recebe uma entrada e prevê a próxima unidade de texto mais provável.

Essa unidade é chamada de **token**.

Depois, o token gerado passa a fazer parte do contexto, e o modelo prevê o próximo token.

O processo se repete até formar a resposta.

```text
Prompt

↓

Próximo token

↓

Próximo token

↓

Próximo token

↓

Resposta completa
```

Exemplo simplificado:

```text
Entrada:
A capital do Brasil é

Predição:
Brasília
```

Em uma resposta maior, o processo acontece várias vezes.

---

# Tokens em Visão Geral

Tokens são unidades de texto processadas pelo modelo.

Um token pode ser:

- uma palavra;
- parte de uma palavra;
- um sinal de pontuação;
- um espaço;
- um fragmento de código;
- um símbolo.

Exemplo simplificado:

```text
Texto:
Amazon Bedrock usa modelos.

Tokens aproximados:
Amazon | Bedrock | usa | modelos | .
```

Este capítulo apresenta apenas a ideia geral.

Tokens serão estudados em detalhe no capítulo 5.

Para a prova, lembre:

- LLMs não processam texto exatamente como humanos.
- LLMs processam texto como tokens.
- O tamanho do prompt e da resposta impacta custo, latência e limite de contexto.

---

# Parâmetros

Parâmetros são valores internos aprendidos durante o treinamento.

Eles representam padrões estatísticos aprendidos pelo modelo.

Em modelos grandes, o número de parâmetros pode ser muito alto.

Em geral, mais parâmetros podem aumentar a capacidade do modelo, mas isso não significa automaticamente que ele será melhor para qualquer caso de uso.

Ao escolher um modelo, considere:

- qualidade da resposta;
- custo;
- latência;
- tamanho da janela de contexto;
- suporte ao idioma;
- capacidade de seguir instruções;
- requisitos de segurança;
- necessidade de raciocínio;
- tipo de tarefa.

Na certificação, evite a ideia simplista de que "o maior modelo sempre é o melhor".

---

# Context Window

A **Context Window** é a quantidade de informação que o modelo consegue considerar em uma interação.

Ela inclui:

- prompt do usuário;
- instruções do sistema;
- histórico da conversa;
- documentos fornecidos como contexto;
- exemplos;
- resposta gerada.

Exemplo:

```text
Instruções

+

Pergunta do usuário

+

Trechos de documentos

+

Histórico da conversa

↓

Contexto enviado ao LLM
```

Se o contexto for grande demais, parte da informação pode precisar ser removida, resumida ou recuperada por outra arquitetura, como RAG.

Context Window será estudada com mais detalhe em capítulo próprio.

---

# Prompt

Prompt é a instrução enviada ao LLM.

Um prompt pode ser simples:

```text
Explique o que é um LLM.
```

Ou pode ser mais estruturado:

```text
Você é um instrutor de certificação AWS.
Explique LLMs para alguém que conhece Java e AWS.
Use linguagem simples, exemplos práticos e uma tabela comparativa.
```

O prompt orienta:

- objetivo;
- estilo;
- formato;
- restrições;
- contexto;
- nível de detalhe.

Prompt Engineering será estudado em capítulo próprio.

---

# Inferência com LLMs

Inferência é o processo de usar um modelo já treinado para gerar uma resposta.

No contexto de LLMs:

```text
Aplicação

↓

Prompt

↓

LLM

↓

Resposta gerada
```

A aplicação não treina o modelo a cada pergunta.

Ela chama um modelo já treinado e recebe uma saída.

Esse ponto é importante para a prova:

- treinamento cria ou ajusta o modelo;
- inferência usa o modelo para responder;
- prompt orienta a resposta durante a inferência.

---

# Como Funciona uma Aplicação com LLM

Uma aplicação corporativa com LLM normalmente envolve mais do que apenas enviar uma pergunta ao modelo.

Fluxo comum:

```text
Usuário

↓

Aplicação

↓

Validação e autorização

↓

Montagem do prompt

↓

Chamada ao modelo

↓

Pós-processamento

↓

Resposta ao usuário
```

Em cenários empresariais, também podem existir:

- autenticação;
- autorização;
- filtros de conteúdo;
- logs;
- auditoria;
- guardrails;
- busca em documentos;
- revisão humana;
- monitoramento de custo;
- monitoramento de qualidade.

---

# LLMs e IA Generativa

LLMs são uma das bases mais importantes da IA Generativa.

Quando a saída é texto, conversa, resumo, explicação ou código, normalmente o motor principal é um LLM.

```text
IA Generativa
│
├── Geração de texto
│   └── LLMs
│
├── Geração de imagem
│   └── Modelos de imagem
│
├── Geração de áudio
│   └── Modelos de áudio
│
└── Geração de vídeo
    └── Modelos de vídeo
```

Um LLM é especializado em linguagem.

IA Generativa é a categoria mais ampla de sistemas capazes de gerar conteúdo.

---

# LLMs e Foundation Models

Foundation Model é um conceito mais amplo.

Um Foundation Model é um modelo grande, treinado em grande escala, que pode servir de base para várias tarefas.

Um LLM pode ser um tipo de Foundation Model quando é um modelo grande de linguagem usado como base para diferentes aplicações.

```text
Foundation Models
│
├── Large Language Models
├── Modelos de imagem
├── Modelos multimodais
└── Outros modelos generativos
```

O capítulo 4 será dedicado a Foundation Models.

Para este capítulo, memorize:

- LLM é focado em linguagem.
- Foundation Model é uma categoria mais ampla.
- Muitos LLMs são Foundation Models.
- Nem todo Foundation Model é um LLM.

---

# Exemplo do Mundo Real

Imagine uma empresa que recebe milhares de e-mails de suporte por dia.

Os e-mails podem conter:

- dúvidas sobre pagamento;
- problemas técnicos;
- solicitações de cancelamento;
- reclamações;
- pedidos de segunda via;
- anexos e descrições longas.

Um LLM pode ajudar a:

- resumir a mensagem;
- identificar intenção;
- sugerir uma resposta;
- classificar prioridade;
- extrair dados importantes;
- gerar uma resposta em tom profissional.

Exemplo:

```text
Cliente:
Estou tentando acessar minha conta desde ontem, mas aparece uma mensagem de erro depois que informo o código de verificação. Preciso resolver isso hoje porque tenho uma reunião.

LLM:
Resumo: cliente não consegue acessar a conta após informar o código de verificação.
Prioridade sugerida: alta.
Resposta sugerida: Entendo a urgência. Vamos verificar o processo de autenticação da sua conta e validar se há bloqueio temporário ou falha no envio do código.
```

O modelo não apenas escolhe uma resposta fixa.

Ele interpreta o texto e gera uma saída adequada ao contexto.

---

# Exemplo Relacionado ao Desenvolvimento de Software

Uma equipe de desenvolvimento pode usar LLMs para apoiar tarefas comuns.

Exemplos:

- explicar stack traces;
- gerar testes unitários;
- revisar documentação;
- criar exemplos de uso de APIs;
- converter pseudocódigo em código;
- gerar consultas SQL;
- resumir pull requests;
- criar mensagens de release;
- explicar comportamento de logs.

Exemplo de prompt:

```text
Explique o erro abaixo em uma aplicação Spring Boot.
Liste possíveis causas e uma checklist de investigação.

Erro:
java.sql.SQLTransientConnectionException: HikariPool - Connection is not available
```

Resposta esperada:

- explicação do erro;
- possíveis causas;
- verificações no pool;
- verificações no banco;
- sugestões de métricas;
- próximos passos.

O LLM ajuda a acelerar o raciocínio, mas a equipe ainda precisa validar as hipóteses.

---

# Exemplos Usando AWS

# Amazon Bedrock

Na AWS, **Amazon Bedrock** é o serviço central para construir e escalar aplicações de IA Generativa usando Foundation Models.

Para cenários com LLMs, Bedrock permite que aplicações chamem modelos por API para tarefas como:

- chat;
- geração de texto;
- sumarização;
- extração de informações;
- geração de código;
- respostas baseadas em documentos;
- classificação textual;
- agentes generativos.

Fluxo simplificado:

```text
Aplicação

↓

Prompt

↓

Amazon Bedrock

↓

LLM ou Foundation Model

↓

Resposta
```

Para a prova:

```text
Aplicação generativa + LLM gerenciado + AWS

↓

Amazon Bedrock
```

---

# Amazon Q

Amazon Q aparece em cenários de assistentes generativos prontos para produtividade, desenvolvimento ou acesso a conhecimento empresarial.

Pense em Amazon Q quando o enunciado mencionar:

- assistente generativo;
- apoio a desenvolvedores;
- perguntas e respostas sobre dados corporativos;
- ajuda para usuários trabalharem com informações;
- produtividade com linguagem natural.

Comparação simples:

| Cenário | Serviço mais provável |
|---------|------------------------|
| Criar uma aplicação generativa própria com modelos | Amazon Bedrock |
| Usar assistente generativo pronto da AWS | Amazon Q |
| Treinar modelo próprio de ML | Amazon SageMaker AI |

---

# Amazon SageMaker AI

Amazon SageMaker AI está mais associado ao ciclo de vida de modelos próprios de Machine Learning.

Na prova, ele costuma aparecer quando o cenário pede:

- criar modelo próprio;
- treinar modelo;
- ajustar algoritmo;
- implantar endpoint;
- monitorar modelo;
- controlar o ciclo de vida de ML.

Ele pode participar de projetos avançados com modelos grandes, mas, para o nível da certificação, a distinção principal é:

```text
Usar LLMs e Foundation Models gerenciados

↓

Amazon Bedrock

Construir, treinar e implantar modelo próprio

↓

Amazon SageMaker AI
```

---

# Quando Utilizar LLMs

Use LLMs quando o problema envolve linguagem natural ou geração textual.

Exemplos:

- chatbots;
- assistentes virtuais;
- sumarização de documentos;
- respostas a perguntas;
- análise de sentimento;
- classificação textual;
- extração de informações;
- geração de código;
- transformação de texto;
- tradução;
- explicação de conteúdo técnico;
- geração de e-mails;
- consulta a bases de conhecimento.

Palavras-chave comuns:

- texto;
- linguagem natural;
- conversa;
- chat;
- resumo;
- pergunta e resposta;
- gerar resposta;
- interpretar documento;
- transformar texto;
- código;
- prompt.

---

# Quando NÃO Utilizar LLMs

Evite LLMs quando:

- uma regra simples resolve o problema;
- o resultado precisa ser determinístico e idêntico sempre;
- o caso de uso não envolve linguagem;
- o problema é apenas cálculo matemático simples;
- há baixa tolerância a respostas aproximadas;
- não existe estratégia de validação;
- os dados sensíveis não podem ser protegidos adequadamente;
- custo e latência são incompatíveis com o requisito.

Exemplos:

| Problema | Melhor abordagem |
|----------|------------------|
| Calcular imposto com fórmula fixa | Código determinístico |
| Bloquear transação acima de limite | Regra de negócio |
| Prever churn com tabela histórica | Machine Learning tradicional |
| Classificar imagem de produto | Visão computacional |
| Resumir documento longo | LLM |
| Criar assistente de perguntas e respostas | LLM |

---

# Comparações Importantes

# LLM versus Machine Learning Tradicional

| Aspecto | Machine Learning tradicional | LLM |
|---------|------------------------------|-----|
| Entrada comum | Dados estruturados, eventos, atributos | Texto, prompt, contexto |
| Saída comum | Classe, número, probabilidade | Texto, código, resumo, resposta |
| Uso típico | Previsão e classificação | Linguagem natural e geração textual |
| Exemplo | Prever churn | Responder pergunta de cliente |
| Serviço AWS típico | Amazon SageMaker AI | Amazon Bedrock |

---

# LLM versus IA Generativa

| Conceito | Explicação |
|----------|------------|
| IA Generativa | Categoria ampla de IA que cria conteúdo |
| LLM | Modelo especializado em linguagem |

Todo LLM usado para gerar texto participa de uma solução de IA Generativa.

Mas IA Generativa também pode incluir modelos de imagem, áudio, vídeo ou modelos multimodais.

---

# LLM versus Foundation Model

| Conceito | Explicação |
|----------|------------|
| Foundation Model | Modelo grande e geral que pode servir de base para várias tarefas |
| LLM | Modelo grande focado em linguagem |

Muitos LLMs são Foundation Models.

Nem todo Foundation Model é um LLM.

---

# LLM versus Chatbot

LLM não é a mesma coisa que chatbot.

Um chatbot é uma aplicação ou interface conversacional.

Um LLM pode ser o modelo usado por trás do chatbot.

```text
Usuário

↓

Chatbot

↓

LLM

↓

Resposta
```

Na prova, se o cenário fala em construir chatbot generativo com Foundation Models na AWS, pense em Amazon Bedrock.

---

# Limitações e Riscos

# Hallucinations

LLMs podem gerar respostas incorretas ou inventadas com aparência convincente.

Exemplo:

```text
Pergunta:
Qual política interna permite publicar dados de clientes?

Resposta incorreta:
A política DATA-102 permite publicação sem anonimização.
```

Se essa política não existir ou se a resposta não tiver base, trata-se de uma hallucination.

Mitigações comuns:

- validação humana;
- RAG com fontes confiáveis;
- guardrails;
- testes;
- monitoramento;
- instruções claras;
- restrição de domínio.

---

# Bias

LLMs podem refletir vieses presentes nos dados de treinamento ou no contexto fornecido.

Isso pode levar a respostas injustas, incompletas ou inadequadas.

---

# Privacidade

Prompts podem conter dados sensíveis.

Exemplos:

- dados pessoais;
- contratos;
- chaves de acesso;
- código proprietário;
- informações financeiras;
- dados de clientes;
- documentos internos.

Aplicações com LLM precisam de controles de segurança, governança e compliance.

---

# Custo e Latência

LLMs podem ter custo e latência maiores do que soluções simples.

Fatores que influenciam:

- modelo escolhido;
- tamanho do prompt;
- tamanho da resposta;
- quantidade de chamadas;
- necessidade de baixa latência;
- contexto adicional;
- uso de RAG;
- volume de usuários.

Na prova, se uma regra simples resolve o problema, LLM provavelmente não é a melhor escolha.

---

# Segurança

Aplicações com LLM devem considerar:

- controle de acesso;
- criptografia;
- proteção de dados sensíveis;
- logging adequado;
- auditoria;
- isolamento de dados;
- validação de entrada;
- validação de saída;
- proteção contra prompt injection;
- uso de guardrails.

Prompt injection ocorre quando uma entrada tenta manipular o modelo para ignorar instruções, revelar informações ou executar comportamento inadequado.

---

# Como a AWS Cobra esse Tema

A AWS costuma cobrar LLMs em cenários práticos.

O enunciado pode mencionar:

- linguagem natural;
- geração de texto;
- sumarização;
- chatbot;
- perguntas e respostas;
- Foundation Models;
- prompts;
- contexto;
- Amazon Bedrock;
- Amazon Q.

## Exemplo 1

> Uma empresa deseja criar uma aplicação que responda perguntas de clientes em linguagem natural usando modelos gerenciados.

Palavras-chave:

- perguntas;
- linguagem natural;
- modelos gerenciados;
- aplicação generativa.

Resposta provável:

**LLM com Amazon Bedrock.**

---

## Exemplo 2

> Uma empresa deseja prever a probabilidade de cancelamento de clientes usando uma tabela histórica.

Palavras-chave:

- prever;
- probabilidade;
- dados históricos estruturados.

Resposta provável:

**Machine Learning tradicional**, provavelmente com Amazon SageMaker AI.

Não é o cenário principal de LLM.

---

## Exemplo 3

> Uma equipe deseja um assistente generativo para ajudar desenvolvedores a entender código e aumentar produtividade.

Palavras-chave:

- assistente;
- desenvolvedores;
- produtividade;
- linguagem natural.

Resposta provável:

**Amazon Q Developer** ou Amazon Q, dependendo do enunciado.

---

# Pegadinhas da Certificação

## Pegadinha 1

**"LLM é a mesma coisa que IA Generativa."**

Falso.

LLM é um tipo de modelo focado em linguagem.

IA Generativa é uma categoria mais ampla.

---

## Pegadinha 2

**"Todo Foundation Model é um LLM."**

Falso.

Foundation Models podem ser de texto, imagem, áudio, vídeo ou multimodais.

LLM é um Foundation Model quando o modelo grande é especializado em linguagem.

---

## Pegadinha 3

**"LLMs sempre sabem a resposta correta."**

Falso.

LLMs geram respostas prováveis com base em padrões e contexto.

Eles podem errar, inventar ou omitir informações.

---

## Pegadinha 4

**"Quanto maior o modelo, melhor a escolha."**

Falso.

Modelos maiores podem custar mais, responder mais lentamente ou ser desnecessários para tarefas simples.

Escolha o modelo conforme caso de uso, custo, latência, qualidade e requisitos.

---

## Pegadinha 5

**"Prompt substitui governança."**

Falso.

Prompts ajudam a orientar o modelo, mas não substituem IAM, criptografia, guardrails, auditoria, validação e políticas de segurança.

---

# Erros Comuns

## Erro 1 — Usar LLM para tudo

LLMs são úteis para linguagem, mas não são solução universal.

Problemas determinísticos, regras simples e cálculos exatos podem ser resolvidos com código tradicional.

---

## Erro 2 — Confundir treinamento com inferência

Quando uma aplicação chama um LLM para responder a um prompt, ela está fazendo inferência.

Ela não está treinando o modelo do zero.

---

## Erro 3 — Enviar contexto demais sem estratégia

Adicionar muito texto ao prompt pode aumentar custo, latência e ruído.

Para documentos grandes, pode ser melhor usar RAG, resumo prévio ou seleção de trechos relevantes.

---

## Erro 4 — Ignorar validação

Respostas de LLMs precisam ser avaliadas, principalmente em cenários de alto impacto.

Exemplos:

- jurídico;
- saúde;
- financeiro;
- segurança;
- decisões automatizadas;
- dados sensíveis.

---

# Questões Comentadas

## Questão 1 — Nível Fácil

Uma empresa deseja criar um assistente que responda perguntas em linguagem natural e gere explicações em texto para seus usuários.

Qual tipo de modelo é mais adequado?

A) Banco relacional

B) Large Language Model

C) Sistema de arquivos

D) Load balancer

### Resposta

**Alternativa B.**

O cenário envolve linguagem natural e geração de texto.

Esse é o uso típico de um LLM.

---

## Questão 2 — Nível Intermediário

Uma empresa deseja prever se clientes irão cancelar uma assinatura usando dados históricos estruturados, como valor mensal, tempo de contrato e número de chamados.

Qual abordagem é mais adequada?

A) LLM

B) Machine Learning tradicional

C) Prompt Engineering

D) Chatbot generativo

### Resposta

**Alternativa B.**

O cenário envolve previsão com dados históricos estruturados.

Isso aponta para Machine Learning tradicional, não para LLM.

---

## Questão 3 — Nível AWS

Uma organização deseja construir uma aplicação generativa que use modelos de linguagem gerenciados para resumir documentos e responder perguntas.

Qual serviço AWS é mais adequado?

A) Amazon Bedrock

B) AWS CloudTrail

C) Amazon Route 53

D) Amazon EBS

### Resposta

**Alternativa A.**

Amazon Bedrock é o serviço gerenciado da AWS para construir e escalar aplicações de IA Generativa usando Foundation Models, incluindo modelos de linguagem.

---

## Questão 4 — Nível AWS

Uma equipe precisa de um assistente generativo para apoiar desenvolvedores em tarefas de código e produtividade.

Qual serviço AWS é mais associado a esse cenário?

A) Amazon Q Developer

B) Amazon S3 Glacier

C) AWS WAF

D) Amazon VPC

### Resposta

**Alternativa A.**

Amazon Q Developer é associado a assistência generativa para desenvolvimento e produtividade técnica.

---

## Questão 5 — Nível Certificação

Uma empresa quer usar um LLM para responder perguntas sobre políticas internas. As respostas devem ser baseadas nos documentos oficiais da empresa.

Qual arquitetura ajuda mais diretamente a conectar o modelo a esses documentos?

A) RAG

B) RAID

C) NAT Gateway

D) Auto Scaling Group

### Resposta

**Alternativa A.**

RAG combina recuperação de informações externas com geração de respostas.

Ele ajuda o modelo a responder com base em documentos fornecidos como contexto.

---

# Checklist de Revisão

Antes de avançar para o próximo capítulo, verifique se você consegue responder às perguntas abaixo sem consultar o material.

## Conceito

- [ ] Sei definir Large Language Model.
- [ ] Sei explicar por que LLMs são baseados em Deep Learning.
- [ ] Sei explicar a relação entre LLMs e IA Generativa.
- [ ] Sei diferenciar LLM de chatbot.

---

## Funcionamento

- [ ] Sei explicar, em alto nível, como um LLM gera texto.
- [ ] Sei explicar o que são tokens em visão geral.
- [ ] Sei diferenciar prompt, contexto e resposta.
- [ ] Sei diferenciar treinamento e inferência.

---

## AWS

- [ ] Sei associar LLMs gerenciados com Amazon Bedrock.
- [ ] Sei diferenciar Amazon Bedrock de Amazon SageMaker AI.
- [ ] Sei reconhecer cenários de Amazon Q.

---

## Riscos

- [ ] Sei explicar hallucination.
- [ ] Sei citar riscos de privacidade.
- [ ] Sei explicar por que guardrails e validação são importantes.
- [ ] Sei reconhecer quando LLM não é a melhor solução.

---

# Resumo do Capítulo

Large Language Models são modelos grandes de Deep Learning especializados em linguagem natural.

Eles processam entradas textuais como tokens e geram respostas prevendo continuações prováveis com base no contexto recebido e nos padrões aprendidos durante o treinamento.

LLMs são uma das principais bases da IA Generativa, especialmente para casos como chatbots, sumarização, geração de texto, respostas a perguntas, geração de código e análise de documentos.

Na AWS, Amazon Bedrock é o serviço central para construir aplicações generativas com Foundation Models, incluindo LLMs.

Amazon Q aparece em cenários de assistentes generativos prontos, enquanto Amazon SageMaker AI aparece com mais força em cenários de construção, treinamento e implantação de modelos próprios.

LLMs também possuem riscos: hallucinations, bias, privacidade, custo, latência, prompt injection e necessidade de governança.

---

# Principais Pontos para a Certificação

| Cenário | Pense em |
|---------|----------|
| Linguagem natural | LLM |
| Geração de texto | LLM |
| Chatbot generativo | LLM + Amazon Bedrock |
| Foundation Models gerenciados na AWS | Amazon Bedrock |
| Assistente generativo pronto | Amazon Q |
| Treinar modelo próprio | Amazon SageMaker AI |
| Resposta baseada em documentos internos | RAG |
| Resposta inventada | Hallucination |
| Entrada tentando manipular instruções | Prompt injection |

---

# Em uma Frase

> **LLMs são modelos grandes de Deep Learning especializados em linguagem, usados para gerar, interpretar, resumir e transformar texto, e na AWS normalmente aparecem em aplicações construídas com Amazon Bedrock ou em assistentes como Amazon Q.**

---

# Glossário

## Large Language Model (LLM)

Modelo grande de Deep Learning especializado em processar e gerar linguagem natural.

---

## Token

Unidade de texto processada por um modelo, podendo representar uma palavra, parte de palavra, símbolo ou pontuação.

---

## Prompt

Instrução ou entrada enviada ao modelo para orientar a resposta.

---

## Context Window

Quantidade de informação que o modelo consegue considerar em uma interação.

---

## Parâmetro

Valor interno aprendido durante o treinamento e usado pelo modelo para gerar respostas.

---

## Inferência

Uso de um modelo já treinado para gerar uma resposta ou previsão.

---

## Transformer

Arquitetura de rede neural amplamente usada em LLMs modernos para processar relações entre tokens e contexto.

---

## Hallucination

Resposta incorreta, inventada ou sem base suficiente, apresentada de forma convincente pelo modelo.

---

## Prompt Injection

Tentativa de manipular o modelo por meio da entrada para fazê-lo ignorar instruções, revelar dados ou produzir comportamento inadequado.

---

## RAG

Retrieval-Augmented Generation. Arquitetura que combina busca de informações externas com geração de respostas.

---

# Referências

A elaboração deste capítulo foi baseada nas seguintes referências oficiais:

- [AWS Certified AI Practitioner (AIF-C01) Exam Guide](https://docs.aws.amazon.com/pt_br/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html)
- [What is LLM? - Large Language Models Explained - AWS](https://aws.amazon.com/what-is/large-language-model/)
- [What is Generative AI? - AWS](https://aws.amazon.com/what-is/generative-ai/)
- [Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)
- [Amazon Q Business User Guide](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/what-is.html)
- [Amazon Q Developer User Guide](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html)
- [Amazon SageMaker AI Developer Guide](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html)

---

# Próximo Capítulo

No próximo capítulo será apresentado o conceito de:

## Foundation Models

Arquivo planejado: `chapters/04-foundation-models.md`.

Você aprenderá:

- o que são Foundation Models;
- como eles se relacionam com LLMs;
- por que eles são centrais em IA Generativa;
- quando usar modelos prontos;
- como Amazon Bedrock trabalha com Foundation Models.

---

**Fim do Capítulo 3**
