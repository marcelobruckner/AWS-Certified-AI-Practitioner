# Capítulo 4 — Foundation Models

---

# Objetivos de Aprendizagem

Ao concluir este capítulo, você será capaz de:

- compreender o que são Foundation Models;
- explicar por que Foundation Models são importantes para IA Generativa;
- diferenciar Foundation Models, LLMs e modelos tradicionais de Machine Learning;
- reconhecer tarefas que podem ser executadas por Foundation Models;
- entender conceitos como pré-treinamento, adaptação, prompt, inferência, RAG e fine-tuning;
- identificar quando usar modelos prontos em vez de treinar modelos do zero;
- associar Foundation Models ao Amazon Bedrock na certificação AWS Certified AI Practitioner (AIF-C01);
- reconhecer limitações, riscos e cuidados de governança.

---

# Pré-requisitos

Antes deste capítulo, é recomendado compreender:

- o que é Inteligência Artificial;
- o que é Machine Learning;
- o que é Deep Learning;
- o que é IA Generativa;
- o que são Large Language Models (LLMs);
- a diferença entre treinamento e inferência.

Os capítulos anteriores apresentam esses conceitos.

---

# Introdução

Foundation Models são uma das bases da IA Generativa moderna.

Eles representam uma mudança importante na forma como aplicações de IA são construídas.

Durante muito tempo, era comum treinar modelos específicos para tarefas específicas.

Exemplos:

- um modelo para classificar spam;
- um modelo para prever churn;
- um modelo para reconhecer imagens de produtos;
- um modelo para detectar fraude;
- um modelo para analisar sentimento.

Cada modelo costumava ser criado para uma tarefa bem definida.

Foundation Models mudam essa lógica.

Eles são modelos grandes, treinados em grande escala, que podem servir como base para várias tarefas diferentes.

O ponto central é:

> Foundation Models são modelos grandes e gerais que podem ser adaptados ou usados como base para muitas aplicações de IA.

---

# Conceitos Fundamentais

# O que é um Foundation Model?

Um **Foundation Model (FM)** é um modelo grande de Deep Learning treinado com grande volume de dados e capaz de executar uma ampla variedade de tarefas.

Essas tarefas podem incluir:

- geração de texto;
- conversação;
- sumarização;
- tradução;
- geração de código;
- classificação de texto;
- extração de informações;
- geração de imagens;
- análise de imagens;
- respostas a perguntas;
- raciocínio sobre documentos;
- suporte a aplicações multimodais.

O nome "foundation" indica que o modelo funciona como uma fundação.

Em vez de começar do zero, empresas podem usar esse modelo como base para construir soluções específicas.

---

# Por que Foundation Models são importantes?

Treinar um modelo grande do zero pode exigir:

- grande volume de dados;
- infraestrutura especializada;
- equipes experientes;
- tempo de treinamento elevado;
- custo significativo;
- processos de avaliação;
- controles de segurança;
- manutenção contínua.

Para a maioria das empresas, isso não é viável.

Foundation Models reduzem essa barreira.

Em vez de treinar tudo do zero, a empresa pode usar um modelo já treinado e adaptá-lo ao seu caso de uso.

Fluxo simplificado:

```text
Foundation Model pronto

↓

Prompt, RAG ou personalização

↓

Aplicação de negócio
```

Essa abordagem acelera a criação de soluções de IA Generativa.

---

# Foundation Models versus Modelos Tradicionais

Modelos tradicionais de Machine Learning normalmente são treinados para uma tarefa específica.

Exemplo:

```text
Dados históricos de clientes

↓

Treinamento

↓

Modelo de previsão de churn
```

Esse modelo provavelmente não será bom para resumir contratos, escrever código ou responder perguntas em linguagem natural.

Foundation Models são diferentes.

Eles são treinados de forma ampla e podem ser usados em muitas tarefas.

```text
Grandes volumes de dados

↓

Pré-treinamento

↓

Foundation Model

↓

Várias aplicações
```

Comparação:

| Aspecto | Modelo tradicional | Foundation Model |
|---------|--------------------|------------------|
| Escopo | Tarefa específica | Uso amplo |
| Treinamento | Dados específicos | Grande volume de dados variados |
| Saída | Classe, previsão ou pontuação | Texto, imagem, código, resposta ou classificação |
| Reuso | Limitado | Alto |
| Exemplo | Modelo de churn | Modelo generativo para várias tarefas |

---

# Como Foundation Models Funcionam?

Em alto nível, Foundation Models passam por duas grandes fases:

```text
Pré-treinamento

↓

Uso ou adaptação
```

---

## 1. Pré-treinamento

Pré-treinamento é a fase em que o modelo aprende padrões gerais a partir de grandes volumes de dados.

Esses dados podem incluir:

- textos;
- páginas públicas;
- livros;
- documentação;
- código;
- imagens;
- pares de texto e imagem;
- áudio;
- vídeo;
- dados multimodais.

Durante essa fase, o modelo aprende padrões gerais.

Exemplos:

- relações entre palavras;
- estrutura de frases;
- padrões visuais;
- estilos de escrita;
- conceitos comuns;
- formatos de código;
- relações entre texto e imagem;
- instruções e respostas.

Para a certificação, não é necessário conhecer a matemática do pré-treinamento.

O importante é entender que o Foundation Model já chega com conhecimento geral aprendido em grande escala.

---

## 2. Uso ou adaptação

Depois do pré-treinamento, o modelo pode ser usado diretamente ou adaptado.

Formas comuns de uso:

- prompt;
- prompt engineering;
- RAG;
- fine-tuning;
- continued pre-training;
- guardrails;
- agentes;
- integração com ferramentas;
- avaliação e monitoramento.

Na prova AIF-C01, os termos mais importantes são:

- prompt;
- RAG;
- fine-tuning;
- guardrails;
- model evaluation;
- human in the loop;
- Amazon Bedrock.

---

# Prompt

Prompt é a instrução enviada ao modelo.

Exemplo:

```text
Resuma o documento abaixo em cinco tópicos objetivos.
```

O mesmo Foundation Model pode executar tarefas diferentes dependendo do prompt.

Exemplos:

```text
Explique este erro Java.
```

```text
Crie uma resposta educada para este cliente.
```

```text
Extraia nome, data e valor deste contrato.
```

```text
Gere uma descrição de produto com tom profissional.
```

Esse comportamento é uma das razões pelas quais Foundation Models são tão flexíveis.

---

# RAG

RAG significa **Retrieval-Augmented Generation**.

É uma arquitetura que combina recuperação de informações externas com geração de respostas.

Sem RAG:

```text
Pergunta

↓

Foundation Model

↓

Resposta baseada no conhecimento do modelo
```

Com RAG:

```text
Pergunta

↓

Busca em documentos externos

↓

Contexto recuperado

↓

Foundation Model

↓

Resposta baseada no contexto
```

RAG é útil quando a aplicação precisa responder usando dados que não estão no treinamento original do modelo.

Exemplos:

- políticas internas;
- documentos jurídicos;
- base de conhecimento;
- manuais técnicos;
- contratos;
- documentação de produto;
- tickets de suporte;
- dados corporativos.

RAG será estudado em capítulo próprio.

---

# Fine-tuning

Fine-tuning é uma técnica de personalização que ajusta um modelo com dados específicos.

Ele pode ser útil quando a empresa precisa adaptar o comportamento do modelo para:

- estilo de escrita;
- domínio específico;
- formato de resposta;
- terminologia interna;
- tarefas repetitivas;
- exemplos muito específicos.

Mas fine-tuning não é sempre a primeira escolha.

Em muitos casos, prompt engineering ou RAG resolvem melhor.

Regra prática para a prova:

| Necessidade | Técnica mais provável |
|-------------|------------------------|
| Melhorar instrução e formato | Prompt Engineering |
| Responder com dados atualizados da empresa | RAG |
| Adaptar comportamento do modelo com exemplos específicos | Fine-tuning |
| Reduzir saídas inseguras ou inadequadas | Guardrails |

---

# Foundation Models e LLMs

LLM é um tipo de Foundation Model quando o modelo grande é especializado em linguagem.

Mas Foundation Model é um conceito mais amplo.

```text
Foundation Models
│
├── Large Language Models
├── Modelos de imagem
├── Modelos de áudio
├── Modelos de vídeo
└── Modelos multimodais
```

Exemplos:

- um modelo que gera texto é um LLM;
- um modelo que gera imagem é um modelo generativo de imagem;
- um modelo que entende texto e imagem pode ser multimodal;
- todos podem ser Foundation Models se forem modelos grandes e gerais usados como base para várias tarefas.

Para a certificação:

- LLM está ligado a linguagem;
- Foundation Model é mais amplo;
- IA Generativa usa Foundation Models para gerar conteúdo;
- Amazon Bedrock fornece acesso gerenciado a Foundation Models.

---

# Tipos de Foundation Models

Foundation Models podem variar conforme a modalidade.

# Modelos de texto

Usados para:

- conversar;
- responder perguntas;
- resumir documentos;
- gerar conteúdo;
- traduzir;
- classificar texto;
- gerar código;
- extrair informações.

Exemplo:

```text
Prompt:
Resuma este contrato em linguagem simples.

Saída:
Resumo estruturado do contrato.
```

---

# Modelos de imagem

Usados para:

- gerar imagens;
- editar imagens;
- criar variações;
- transformar descrições em imagens;
- apoiar design e marketing.

Exemplo:

```text
Prompt:
Crie uma imagem de um produto em fundo branco para catálogo.

Saída:
Imagem gerada.
```

---

# Modelos multimodais

Modelos multimodais conseguem trabalhar com mais de um tipo de entrada ou saída.

Exemplos:

- texto e imagem;
- texto e vídeo;
- imagem e texto;
- áudio e texto.

Aplicações:

- responder perguntas sobre uma imagem;
- analisar um documento com texto e gráficos;
- gerar descrição de imagem;
- interpretar conteúdo visual e textual juntos.

---

# Exemplo do Mundo Real

Imagine uma empresa de seguros.

Ela precisa lidar com:

- apólices;
- sinistros;
- documentos enviados por clientes;
- e-mails;
- fotos de danos;
- contratos;
- regras internas;
- mensagens de atendimento.

Com Foundation Models, a empresa pode criar diferentes aplicações usando a mesma base conceitual.

Exemplos:

- resumir uma apólice;
- responder perguntas sobre cobertura;
- extrair informações de documentos;
- gerar resposta para cliente;
- analisar imagem de dano;
- classificar solicitações;
- apoiar o atendente humano.

O ganho principal é a flexibilidade.

Em vez de criar um modelo do zero para cada tarefa, a empresa usa modelos prontos e adapta a solução com prompt, RAG, fine-tuning ou integração com sistemas internos.

---

# Exemplo Relacionado ao Desenvolvimento de Software

Uma equipe de engenharia pode usar Foundation Models para acelerar tarefas de desenvolvimento.

Exemplos:

- explicar código legado;
- gerar documentação;
- criar testes unitários;
- resumir incidentes;
- transformar logs em hipóteses de causa;
- criar exemplos de uso de APIs;
- apoiar revisão de pull requests;
- gerar scripts de automação;
- consultar documentação técnica em linguagem natural.

Exemplo:

```text
Prompt:
Analise este trecho de código Java.
Explique o objetivo, possíveis riscos e sugestões de melhoria.
```

Um Foundation Model de linguagem pode gerar:

- explicação do comportamento;
- resumo técnico;
- riscos;
- sugestões;
- exemplos de teste.

O modelo ajuda a acelerar a análise, mas não substitui revisão técnica humana.

---

# Exemplos Usando AWS

# Amazon Bedrock

Na AWS, **Amazon Bedrock** é o serviço mais importante para Foundation Models na certificação.

Amazon Bedrock é um serviço gerenciado que fornece acesso seguro e corporativo a Foundation Models para construir e escalar aplicações de IA Generativa.

Com Bedrock, uma empresa pode:

- escolher modelos de diferentes provedores;
- chamar modelos por API;
- criar aplicações generativas;
- usar modelos para texto, imagem ou outros cenários suportados;
- aplicar guardrails;
- integrar RAG;
- construir agentes;
- avaliar modelos;
- operar sem gerenciar infraestrutura dos modelos.

Fluxo simplificado:

```text
Aplicação

↓

Amazon Bedrock

↓

Foundation Model

↓

Resposta gerada
```

Para a prova:

```text
Foundation Models gerenciados + IA Generativa + AWS

↓

Amazon Bedrock
```

---

# Modelos suportados no Bedrock

Amazon Bedrock oferece acesso a modelos de vários provedores.

Como a lista de modelos, provedores, regiões e capacidades muda com frequência, este guia evita decorar uma lista fixa.

O mais importante para a certificação é entender:

- Bedrock fornece acesso gerenciado a Foundation Models;
- diferentes modelos têm diferentes capacidades;
- a escolha do modelo depende do caso de uso;
- modelos podem variar em custo, latência, qualidade, modalidade e contexto;
- a documentação oficial deve ser consultada para detalhes atuais.

Exemplos de critérios de escolha:

| Critério | Pergunta prática |
|----------|------------------|
| Modalidade | Preciso de texto, imagem, vídeo, áudio ou multimodal? |
| Qualidade | O modelo responde bem para o domínio? |
| Latência | A aplicação precisa responder rapidamente? |
| Custo | O volume de uso será alto? |
| Contexto | O modelo aceita o tamanho necessário de entrada? |
| Idioma | O modelo lida bem com português? |
| Segurança | O caso exige controles adicionais? |

---

# Amazon SageMaker AI

Amazon SageMaker AI está mais associado ao ciclo de vida de modelos próprios de Machine Learning.

Ele aparece quando o cenário envolve:

- treinar modelo próprio;
- preparar dados;
- executar experimentos;
- implantar endpoint;
- monitorar modelo;
- gerenciar ciclo de vida de ML;
- criar soluções customizadas de ML.

Para a prova, a comparação principal é:

| Cenário | Serviço mais provável |
|---------|------------------------|
| Usar Foundation Models gerenciados | Amazon Bedrock |
| Construir aplicação generativa sem gerenciar infraestrutura de modelo | Amazon Bedrock |
| Treinar modelo próprio de Machine Learning | Amazon SageMaker AI |
| Controlar o ciclo de vida completo de ML | Amazon SageMaker AI |

---

# Amazon Q

Amazon Q é associado a assistentes generativos prontos para casos de produtividade, desenvolvimento e uso de conhecimento empresarial.

Pense em Amazon Q quando o cenário mencionar:

- assistente generativo pronto;
- apoio a desenvolvedores;
- perguntas e respostas sobre dados corporativos;
- produtividade com linguagem natural;
- ajuda para entender sistemas, código ou informações.

Comparação:

```text
Criar aplicação generativa própria

↓

Amazon Bedrock

Usar assistente generativo pronto

↓

Amazon Q
```

---

# Quando Utilizar Foundation Models

Use Foundation Models quando o problema exige flexibilidade, linguagem natural, geração de conteúdo ou interpretação de dados não estruturados.

Exemplos:

- criar chatbot generativo;
- resumir documentos;
- responder perguntas em linguagem natural;
- gerar texto;
- gerar código;
- extrair informações de documentos;
- analisar conteúdo não estruturado;
- criar imagens;
- apoiar atendimento;
- criar assistentes internos;
- transformar conteúdo técnico em explicação simples;
- criar soluções com RAG.

Palavras-chave comuns na prova:

- Foundation Model;
- modelo pré-treinado;
- IA Generativa;
- gerar conteúdo;
- resumir;
- responder perguntas;
- prompt;
- RAG;
- fine-tuning;
- Bedrock;
- modelo gerenciado.

---

# Quando NÃO Utilizar Foundation Models

Evite Foundation Models quando:

- uma regra simples resolve o problema;
- o resultado precisa ser totalmente determinístico;
- o caso não envolve linguagem, conteúdo ou dados não estruturados;
- há baixa tolerância a respostas probabilísticas;
- não existe estratégia de validação;
- custo e latência são incompatíveis;
- dados sensíveis não podem ser protegidos;
- um modelo tradicional simples resolve melhor.

Exemplos:

| Problema | Melhor abordagem |
|----------|------------------|
| Calcular imposto com fórmula fixa | Código determinístico |
| Bloquear compra acima de limite | Regra de negócio |
| Prever churn com tabela histórica | Machine Learning tradicional |
| Resumir documento jurídico | Foundation Model |
| Criar assistente de perguntas e respostas | Foundation Model |
| Responder com base em políticas internas | Foundation Model + RAG |

---

# Comparações Importantes

# Foundation Model versus LLM

| Conceito | Explicação |
|----------|------------|
| Foundation Model | Modelo grande e geral usado como base para várias tarefas |
| LLM | Foundation Model especializado em linguagem |

Muitos LLMs são Foundation Models.

Nem todo Foundation Model é um LLM.

---

# Foundation Model versus IA Generativa

| Conceito | Explicação |
|----------|------------|
| IA Generativa | Categoria de IA que cria conteúdo |
| Foundation Model | Modelo base frequentemente usado para construir aplicações generativas |

IA Generativa é o tipo de aplicação ou capacidade.

Foundation Model é o modelo usado como base.

---

# Foundation Model versus Modelo Tradicional

| Aspecto | Modelo tradicional | Foundation Model |
|---------|--------------------|------------------|
| Tarefa | Específica | Ampla |
| Dados | Normalmente específicos | Grandes e variados |
| Uso | Previsão ou classificação | Múltiplas tarefas |
| Personalização | Treinar novo modelo ou ajustar pipeline | Prompt, RAG, fine-tuning ou adaptação |
| Exemplo AWS | SageMaker AI | Bedrock |

---

# Foundation Model versus RAG

Foundation Model é o modelo.

RAG é uma arquitetura para fornecer informações externas ao modelo.

```text
Foundation Model

↓

Gera resposta
```

```text
RAG

↓

Busca documentos relevantes

↓

Envia contexto ao Foundation Model

↓

Gera resposta baseada no contexto
```

Não confunda:

- Foundation Model: componente de IA;
- RAG: padrão arquitetural;
- base de conhecimento: fonte de dados usada pelo RAG.

---

# Foundation Model versus Fine-tuning

Foundation Model é o modelo base.

Fine-tuning é uma técnica de personalização.

```text
Foundation Model

↓

Fine-tuning com dados específicos

↓

Modelo adaptado
```

Use fine-tuning quando o comportamento precisa ser adaptado com exemplos específicos.

Use RAG quando o problema principal é responder com base em dados externos ou atualizados.

---

# Limitações e Riscos

# Hallucinations

Foundation Models podem gerar respostas incorretas ou inventadas.

Isso é especialmente perigoso quando a resposta parece convincente.

Mitigações:

- validação humana;
- RAG com fontes confiáveis;
- guardrails;
- avaliação de modelo;
- testes;
- monitoramento;
- restrição de domínio.

---

# Bias

Modelos podem refletir vieses presentes nos dados de treinamento ou no contexto.

Isso pode impactar:

- justiça;
- qualidade da resposta;
- reputação;
- compliance;
- experiência do usuário.

---

# Privacidade

Prompts e documentos podem conter dados sensíveis.

Exemplos:

- dados pessoais;
- contratos;
- informações financeiras;
- código proprietário;
- documentos internos;
- dados de clientes;
- credenciais.

Aplicações com Foundation Models precisam de controles de segurança e governança.

---

# Custo e Latência

Foundation Models podem ter custo e latência maiores do que soluções tradicionais.

Fatores que influenciam:

- modelo escolhido;
- tamanho do prompt;
- tamanho da resposta;
- quantidade de chamadas;
- contexto adicional;
- RAG;
- agentes;
- volume de usuários;
- requisitos de disponibilidade.

Nem sempre o modelo mais poderoso é o melhor.

---

# Segurança

Aplicações com Foundation Models devem considerar:

- IAM;
- criptografia;
- VPC quando aplicável;
- proteção de dados sensíveis;
- auditoria;
- logs;
- monitoramento;
- guardrails;
- validação de entrada;
- validação de saída;
- controle de acesso às fontes de dados;
- proteção contra prompt injection.

---

# IA Responsável em Foundation Models

Foundation Models devem ser usados com responsabilidade.

Cuidados importantes:

- avaliar qualidade das respostas;
- testar cenários críticos;
- reduzir bias;
- proteger dados sensíveis;
- monitorar uso;
- revisar respostas de alto impacto;
- usar guardrails;
- manter rastreabilidade;
- informar limitações;
- aplicar human in the loop quando necessário.

Na prova, esse tema pode aparecer ligado a:

- fairness;
- transparency;
- explainability;
- accountability;
- privacy;
- governance;
- model evaluation;
- guardrails;
- human review.

---

# Como a AWS Cobra esse Tema

A AWS costuma cobrar Foundation Models em cenários de escolha de serviço e arquitetura.

O enunciado pode mencionar:

- modelos pré-treinados;
- Foundation Models;
- IA Generativa;
- Amazon Bedrock;
- prompts;
- RAG;
- fine-tuning;
- guardrails;
- escolha do modelo;
- aplicações generativas;
- não gerenciar infraestrutura.

## Exemplo 1

> Uma empresa deseja construir uma aplicação de IA Generativa usando modelos pré-treinados de diferentes provedores, sem gerenciar infraestrutura.

Palavras-chave:

- IA Generativa;
- modelos pré-treinados;
- diferentes provedores;
- sem gerenciar infraestrutura.

Resposta provável:

**Amazon Bedrock.**

---

## Exemplo 2

> Uma empresa deseja treinar um modelo próprio de previsão de demanda usando dados históricos estruturados.

Palavras-chave:

- treinar modelo próprio;
- previsão;
- dados históricos estruturados.

Resposta provável:

**Amazon SageMaker AI.**

Esse não é o cenário principal de Foundation Models gerenciados.

---

## Exemplo 3

> Uma empresa quer que um modelo responda perguntas com base em políticas internas atualizadas.

Palavras-chave:

- políticas internas;
- dados atualizados;
- responder perguntas;
- base de conhecimento.

Resposta provável:

**Foundation Model com RAG.**

Na AWS, pense em Amazon Bedrock com arquitetura de recuperação de informações.

---

## Exemplo 4

> Uma empresa quer reduzir respostas inadequadas de uma aplicação generativa.

Palavras-chave:

- reduzir respostas inadequadas;
- segurança;
- política de uso;
- conteúdo impróprio.

Resposta provável:

**Guardrails.**

---

# Pegadinhas da Certificação

## Pegadinha 1

**"Foundation Model é sempre um LLM."**

Falso.

Um LLM pode ser um Foundation Model, mas Foundation Models também podem ser modelos de imagem, multimodais ou de outras modalidades.

---

## Pegadinha 2

**"Amazon Bedrock serve para qualquer problema de Machine Learning."**

Falso.

Bedrock é associado a Foundation Models e IA Generativa.

Para treinar e operar modelos próprios tradicionais de ML, pense em Amazon SageMaker AI.

---

## Pegadinha 3

**"RAG treina novamente o Foundation Model."**

Falso.

RAG fornece contexto externo ao modelo durante a geração.

Ele não significa, por si só, treinar novamente o modelo.

---

## Pegadinha 4

**"Fine-tuning é sempre melhor que RAG."**

Falso.

Se a necessidade é responder usando documentos atualizados, RAG geralmente é mais adequado.

Fine-tuning é mais indicado para adaptar comportamento, estilo ou tarefa com exemplos específicos.

---

## Pegadinha 5

**"Foundation Models sempre geram respostas corretas."**

Falso.

Eles podem gerar respostas incorretas, enviesadas ou inadequadas.

Validação, avaliação e governança continuam necessárias.

---

# Erros Comuns

## Erro 1 — Decorar nomes de modelos sem entender o cenário

A prova tende a cobrar escolha de serviço e abordagem.

Mais importante do que decorar nomes é entender:

- quando usar Foundation Model;
- quando usar Bedrock;
- quando usar SageMaker AI;
- quando aplicar RAG;
- quando considerar guardrails.

---

## Erro 2 — Confundir modelo com aplicação

Foundation Model é o modelo base.

Aplicação generativa é o sistema construído usando esse modelo.

Exemplo:

```text
Foundation Model

↓

Aplicação de chatbot
```

O chatbot não é o modelo.

Ele usa o modelo.

---

## Erro 3 — Usar Foundation Model para regra simples

Se o problema pode ser resolvido com uma regra clara, use regra.

Exemplo:

```text
Se valor > limite, bloquear transação.
```

Não há necessidade de Foundation Model.

---

## Erro 4 — Ignorar segurança e privacidade

Foundation Models podem receber prompts com informações sensíveis.

Todo projeto corporativo deve considerar:

- quem pode acessar;
- quais dados podem ser enviados;
- como logs são tratados;
- quais respostas são permitidas;
- como monitorar uso;
- como auditar decisões.

---

# Questões Comentadas

## Questão 1 — Nível Fácil

O que melhor descreve um Foundation Model?

A) Uma regra fixa escrita manualmente por um desenvolvedor.

B) Um modelo grande e geral que pode servir de base para várias tarefas de IA.

C) Um banco de dados relacional usado para armazenar documentos.

D) Um serviço de rede usado para rotear tráfego.

### Resposta

**Alternativa B.**

Foundation Models são modelos grandes e gerais, treinados em grande escala, que podem ser usados como base para diferentes aplicações.

---

## Questão 2 — Nível Intermediário

Uma empresa deseja responder perguntas sobre documentos internos atualizados semanalmente.

Qual abordagem é mais adequada?

A) Usar somente o conhecimento original do modelo.

B) Usar RAG para recuperar documentos relevantes e fornecer contexto ao modelo.

C) Usar uma regra fixa para todas as perguntas.

D) Usar apenas um banco de dados sem modelo de IA.

### Resposta

**Alternativa B.**

RAG é adequado quando o modelo precisa responder com base em documentos externos ou atualizados.

---

## Questão 3 — Nível AWS

Uma empresa deseja construir uma aplicação generativa com Foundation Models gerenciados, sem provisionar servidores para hospedar os modelos.

Qual serviço AWS é mais adequado?

A) Amazon Bedrock

B) Amazon Route 53

C) AWS CloudTrail

D) Amazon EBS

### Resposta

**Alternativa A.**

Amazon Bedrock é o serviço gerenciado da AWS para construir e escalar aplicações de IA Generativa usando Foundation Models.

---

## Questão 4 — Nível AWS

Uma equipe de dados precisa construir, treinar e implantar um modelo próprio de previsão de demanda usando dados históricos estruturados.

Qual serviço AWS é mais diretamente associado a esse cenário?

A) Amazon Bedrock

B) Amazon SageMaker AI

C) Amazon Q

D) Amazon Polly

### Resposta

**Alternativa B.**

O cenário fala em construir, treinar e implantar modelo próprio de Machine Learning.

Isso aponta para Amazon SageMaker AI.

---

## Questão 5 — Nível Certificação

Uma empresa usa uma aplicação generativa e quer reduzir respostas tóxicas, inseguras ou fora da política corporativa.

Qual recurso ou prática é mais adequado?

A) Guardrails

B) NAT Gateway

C) Amazon Route 53

D) Índice secundário de banco relacional

### Resposta

**Alternativa A.**

Guardrails ajudam a aplicar políticas e reduzir saídas inadequadas em aplicações generativas.

---

# Checklist de Revisão

Antes de avançar para o próximo capítulo, verifique se você consegue responder às perguntas abaixo sem consultar o material.

## Conceito

- [ ] Sei definir Foundation Model.
- [ ] Sei explicar por que Foundation Models são importantes para IA Generativa.
- [ ] Sei diferenciar Foundation Model de LLM.
- [ ] Sei diferenciar Foundation Model de modelo tradicional de ML.

---

## Uso

- [ ] Sei explicar quando usar um Foundation Model.
- [ ] Sei explicar quando não usar um Foundation Model.
- [ ] Sei reconhecer cenários de RAG.
- [ ] Sei reconhecer cenários de fine-tuning.

---

## AWS

- [ ] Sei associar Foundation Models com Amazon Bedrock.
- [ ] Sei diferenciar Amazon Bedrock de Amazon SageMaker AI.
- [ ] Sei reconhecer cenários de Amazon Q.
- [ ] Sei explicar por que a lista de modelos suportados deve ser consultada na documentação oficial.

---

## Riscos

- [ ] Sei explicar hallucination.
- [ ] Sei citar riscos de privacidade.
- [ ] Sei explicar a função de guardrails.
- [ ] Sei reconhecer a necessidade de avaliação e governança.

---

# Resumo do Capítulo

Foundation Models são modelos grandes de Deep Learning treinados em larga escala e capazes de servir como base para várias tarefas de IA.

Eles são fundamentais para IA Generativa porque permitem criar aplicações flexíveis sem treinar modelos do zero para cada problema.

LLMs são um tipo importante de Foundation Model, mas Foundation Models também podem ser de imagem, áudio, vídeo ou multimodais.

Na AWS, o serviço mais importante para uso de Foundation Models gerenciados é o Amazon Bedrock.

Amazon SageMaker AI aparece com mais força quando o cenário envolve construir, treinar e implantar modelos próprios de Machine Learning.

Foundation Models podem ser usados com prompt engineering, RAG, fine-tuning, guardrails, avaliação e revisão humana.

Eles também exigem cuidado com hallucinations, bias, privacidade, custo, latência, segurança e governança.

---

# Principais Pontos para a Certificação

| Cenário | Pense em |
|---------|----------|
| Foundation Models gerenciados na AWS | Amazon Bedrock |
| Aplicação de IA Generativa sem gerenciar infraestrutura | Amazon Bedrock |
| Treinar modelo próprio de ML | Amazon SageMaker AI |
| Assistente generativo pronto | Amazon Q |
| Responder com documentos internos atualizados | RAG |
| Adaptar comportamento com exemplos específicos | Fine-tuning |
| Reduzir respostas inadequadas | Guardrails |
| Resposta inventada | Hallucination |
| Modelo focado em linguagem | LLM |

---

# Em uma Frase

> **Foundation Models são modelos grandes e gerais que servem como base para várias aplicações de IA, e na AWS aparecem principalmente por meio do Amazon Bedrock para construção de aplicações generativas.**

---

# Glossário

## Foundation Model

Modelo grande de Deep Learning treinado em larga escala e usado como base para várias tarefas de IA.

---

## Pré-treinamento

Fase em que o modelo aprende padrões gerais a partir de grandes volumes de dados.

---

## Prompt

Instrução enviada ao modelo para orientar a resposta.

---

## LLM

Large Language Model. Modelo grande especializado em linguagem natural.

---

## RAG

Retrieval-Augmented Generation. Arquitetura que combina busca de informações externas com geração de respostas.

---

## Fine-tuning

Técnica de personalização que ajusta um modelo com dados específicos para adaptar comportamento ou desempenho em uma tarefa.

---

## Guardrails

Controles usados para reduzir saídas inadequadas, inseguras ou fora de políticas definidas.

---

## Hallucination

Resposta incorreta, inventada ou sem base suficiente, apresentada de forma convincente por um modelo.

---

## Modelo multimodal

Modelo capaz de trabalhar com mais de uma modalidade, como texto, imagem, áudio ou vídeo.

---

# Referências

A elaboração deste capítulo foi baseada nas seguintes referências oficiais:

- [AWS Certified AI Practitioner (AIF-C01) Exam Guide](https://docs.aws.amazon.com/pt_br/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html)
- [What are Foundation Models? - AWS](https://aws.amazon.com/what-is/foundation-models/)
- [What is Generative AI? - AWS](https://aws.amazon.com/what-is/generative-ai/)
- [What is LLM? - Large Language Models Explained - AWS](https://aws.amazon.com/what-is/large-language-model/)
- [Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)
- [Supported foundation models in Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/models-supported.html)
- [Amazon Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html)
- [Amazon SageMaker AI Developer Guide](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html)

---

# Próximo Capítulo

No próximo capítulo será apresentado o conceito de:

## Tokens

Arquivo planejado: `chapters/05-tokens.md`.

Você aprenderá:

- o que são tokens;
- por que modelos processam texto como tokens;
- como tokens impactam custo, latência e contexto;
- como pensar sobre tamanho de prompt e resposta;
- como esse conceito aparece na certificação.

---

**Fim do Capítulo 4**
