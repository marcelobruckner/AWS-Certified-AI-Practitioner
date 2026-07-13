# Capítulo 6 — Embeddings

---

# Objetivos de Aprendizagem

Ao concluir este capítulo, você será capaz de:

- compreender o que são embeddings;
- explicar por que embeddings representam dados como vetores;
- diferenciar embeddings de tokens, palavras, prompts e respostas geradas;
- entender como embeddings capturam similaridade semântica;
- reconhecer a relação entre embeddings, busca vetorial, busca semântica e RAG;
- identificar casos de uso comuns em aplicações corporativas;
- associar embeddings a Amazon Bedrock, Knowledge Bases e bancos vetoriais na certificação AWS Certified AI Practitioner (AIF-C01);
- reconhecer limitações, riscos e boas práticas no uso de embeddings.

---

# Pré-requisitos

Antes deste capítulo, é recomendado compreender:

- o que é IA Generativa;
- o que são LLMs;
- o que são Foundation Models;
- o que são tokens;
- o que é prompt;
- o que é RAG em visão geral;
- o que é context window em visão geral.

Os capítulos anteriores apresentam esses conceitos.

---

# Introdução

Embeddings são uma das ideias mais importantes para entender como sistemas modernos de IA trabalham com significado.

Quando uma pessoa lê duas frases, ela consegue perceber se elas têm sentido parecido, mesmo que usem palavras diferentes.

Exemplo:

```text
Como faço para redefinir minha senha?
```

```text
Esqueci minha senha, como recupero o acesso?
```

As palavras não são iguais.

Mas o significado é muito parecido.

Um sistema baseado apenas em busca por palavra-chave pode falhar se procurar exatamente "redefinir" e o documento usar "recuperar".

Embeddings ajudam a resolver esse problema.

Eles transformam textos, imagens ou outros dados em representações numéricas que preservam relações de significado.

O ponto central é:

> Embeddings são representações vetoriais que permitem comparar significado, similaridade e relação entre dados.

---

# Conceitos Fundamentais

# O que é um Embedding?

Um embedding é uma representação numérica de um dado.

Esse dado pode ser:

- palavra;
- frase;
- parágrafo;
- documento;
- imagem;
- produto;
- usuário;
- item de catálogo;
- trecho de código;
- pergunta;
- resposta;
- entidade de negócio.

Em aplicações de IA Generativa, embeddings aparecem principalmente para representar texto.

Exemplo conceitual:

```text
Texto:
Amazon Bedrock permite criar aplicações de IA Generativa.

Embedding:
[0.12, -0.44, 0.87, 0.03, ...]
```

Esse vetor não é feito para ser lido por humanos.

Ele é usado por algoritmos para comparar significado.

---

# Embedding é um Vetor

Um vetor é uma lista de números.

Exemplo simples:

```text
[0.10, 0.35, -0.22]
```

Embeddings reais geralmente possuem muitas dimensões.

Exemplo conceitual:

```text
Texto:
Política de reembolso de academia

Vetor:
[0.18, -0.09, 0.44, 0.72, -0.31, ...]
```

Cada número ajuda a posicionar aquele texto em um espaço matemático.

Textos com significados parecidos tendem a ficar próximos nesse espaço.

Textos com significados diferentes tendem a ficar distantes.

---

# Espaço Vetorial

Imagine um mapa.

Nesse mapa, cidades próximas têm alguma relação geográfica.

Em embeddings, textos próximos têm alguma relação semântica.

Exemplo conceitual:

```text
"recuperar senha"
"redefinir senha"
"esqueci minha senha"
```

Essas frases ficariam próximas no espaço vetorial.

Já frases como:

```text
"previsão do tempo"
"receita de bolo"
"configuração de rede"
```

ficariam mais distantes.

Esse conceito permite criar busca semântica.

---

# Similaridade Semântica

Similaridade semântica mede o quanto dois conteúdos são parecidos em significado.

Exemplo:

```text
Pergunta:
Como altero minha senha?

Documento A:
Procedimento para redefinir senha do usuário.

Documento B:
Política de férias e banco de horas.
```

Mesmo que a pergunta use "altero" e o documento use "redefinir", o Documento A é semanticamente mais próximo.

Embeddings permitem esse tipo de comparação.

---

# Por que Embeddings são Importantes?

Embeddings são importantes porque permitem que sistemas de IA trabalhem com significado, não apenas com palavras exatas.

Eles ajudam em:

- busca semântica;
- recomendação;
- classificação;
- agrupamento;
- detecção de duplicidade;
- RAG;
- descoberta de documentos relevantes;
- comparação de perguntas;
- análise de similaridade;
- recuperação de conhecimento corporativo.

Em IA Generativa, embeddings são especialmente importantes para RAG.

Eles ajudam a encontrar os trechos mais relevantes para enviar ao modelo como contexto.

---

# Embeddings versus Busca por Palavra-chave

Busca por palavra-chave procura termos exatos ou variações simples.

Exemplo:

```text
Busca:
redefinir senha
```

Ela tende a encontrar documentos que contenham "redefinir" e "senha".

Mas pode deixar passar um documento que diga:

```text
Como recuperar acesso quando a senha foi esquecida.
```

Busca semântica com embeddings procura significado.

Ela pode encontrar documentos relevantes mesmo sem palavras idênticas.

Comparação:

| Tipo de busca | Como funciona |
|---------------|---------------|
| Palavra-chave | Procura termos iguais ou parecidos |
| Semântica | Procura significado parecido |

---

# Como Embeddings Funcionam?

Fluxo simplificado:

```text
Texto

↓

Modelo de embedding

↓

Vetor

↓

Comparação com outros vetores
```

O modelo de embedding recebe um texto e gera um vetor.

Esse vetor é armazenado ou usado para comparação.

Quando o usuário faz uma pergunta, a pergunta também vira um vetor.

Depois, o sistema procura vetores próximos.

---

# Exemplo de Fluxo

Imagine uma base de conhecimento com três documentos.

```text
Documento 1:
Como redefinir senha.

Documento 2:
Política de reembolso.

Documento 3:
Configuração de VPN.
```

Durante a preparação da base:

```text
Documento 1 -> embedding 1
Documento 2 -> embedding 2
Documento 3 -> embedding 3
```

Quando o usuário pergunta:

```text
Esqueci minha senha. Como recupero o acesso?
```

A pergunta também vira embedding.

```text
Pergunta -> embedding da pergunta
```

O sistema compara o embedding da pergunta com os embeddings dos documentos.

Resultado:

```text
Documento mais próximo:
Documento 1
```

Mesmo sem usar exatamente as mesmas palavras, o sistema entende a relação semântica.

---

# Distância e Similaridade

Depois que textos viram vetores, o sistema precisa comparar vetores.

Métricas comuns incluem:

- cosine similarity;
- distância euclidiana;
- dot product.

Para a certificação AWS AI Practitioner, não é necessário memorizar fórmulas.

O importante é entender:

- embeddings próximos indicam conteúdos parecidos;
- embeddings distantes indicam conteúdos menos relacionados;
- busca vetorial recupera itens próximos no espaço vetorial.

Exemplo conceitual:

```text
Pergunta: "Como recupero minha senha?"

Documento A: "Redefinição de senha"
Similaridade: alta

Documento B: "Política de viagens"
Similaridade: baixa
```

---

# Embeddings e Tokens

Tokens e embeddings são conceitos relacionados, mas diferentes.

Tokens são unidades de texto processadas pelo modelo.

Embeddings são representações numéricas.

Fluxo conceitual:

```text
Texto

↓

Tokens

↓

Representações numéricas

↓

Modelo
```

Em sistemas de busca semântica, muitas vezes falamos do embedding de uma frase, parágrafo ou documento.

Esse embedding representa o significado geral daquele trecho.

Comparação:

| Conceito | Explicação |
|----------|------------|
| Token | Unidade de texto |
| Embedding | Vetor numérico que representa significado |

---

# Embeddings e LLMs

LLMs geram texto.

Modelos de embedding geram vetores.

Essa diferença é importante.

Exemplo com LLM:

```text
Entrada:
Explique Amazon Bedrock.

Saída:
Amazon Bedrock é um serviço gerenciado da AWS para criar aplicações de IA Generativa...
```

Exemplo com modelo de embedding:

```text
Entrada:
Explique Amazon Bedrock.

Saída:
[0.21, -0.07, 0.45, ...]
```

O primeiro gera uma resposta para humanos.

O segundo gera uma representação para busca, comparação ou classificação.

---

# Embeddings e RAG

RAG significa Retrieval-Augmented Generation.

Embeddings são uma peça importante em muitas arquiteturas RAG.

Fluxo típico:

```text
Documentos da empresa

↓

Divisão em trechos

↓

Geração de embeddings

↓

Armazenamento em banco vetorial

↓

Pergunta do usuário

↓

Embedding da pergunta

↓

Busca por trechos similares

↓

Envio dos trechos ao Foundation Model

↓

Resposta gerada
```

Embeddings ajudam a encontrar o contexto correto.

O Foundation Model usa esse contexto para gerar a resposta.

---

# Chunking

Chunking é o processo de dividir documentos em partes menores.

Essas partes são chamadas de chunks.

Exemplo:

```text
Documento completo

↓

Chunk 1
Chunk 2
Chunk 3
Chunk 4
```

Cada chunk pode receber seu próprio embedding.

Isso é útil porque documentos inteiros podem ser grandes demais ou misturar muitos assuntos.

Chunks menores tendem a melhorar a recuperação de trechos relevantes.

Mas chunks pequenos demais podem perder contexto.

O equilíbrio depende do caso de uso.

---

# Banco Vetorial

Um banco vetorial é usado para armazenar e consultar embeddings.

Ele permite buscar vetores parecidos de forma eficiente.

Fluxo:

```text
Embedding da pergunta

↓

Banco vetorial

↓

Embeddings mais próximos

↓

Trechos relevantes
```

Na prática, bancos vetoriais são usados para busca semântica, RAG e recomendação.

Na AWS, serviços como Amazon OpenSearch Service, Amazon OpenSearch Serverless e outros recursos integrados a Knowledge Bases podem participar desse tipo de arquitetura, dependendo do desenho escolhido.

---

# Exemplo do Mundo Real

Imagine uma empresa com milhares de documentos de RH.

Eles incluem:

- política de férias;
- benefícios;
- reembolso;
- plano de saúde;
- regras de trabalho remoto;
- código de conduta;
- guias de onboarding.

Um colaborador pergunta:

```text
Posso trabalhar de outro estado por algumas semanas?
```

Uma busca por palavra-chave talvez procure "outro estado" e não encontre a melhor política.

Mas uma busca semântica com embeddings pode encontrar trechos sobre:

- trabalho remoto temporário;
- política de mobilidade;
- autorização de gestor;
- requisitos fiscais;
- regras de residência.

O sistema entende a intenção mesmo quando as palavras não são idênticas.

---

# Exemplo Relacionado ao Desenvolvimento de Software

Uma empresa quer criar um assistente para desenvolvedores consultarem documentação interna.

Fontes:

- README de repositórios;
- ADRs;
- documentação de APIs;
- runbooks;
- incidentes anteriores;
- padrões de arquitetura;
- exemplos de código.

Processo:

```text
Documentação

↓

Chunks

↓

Embeddings

↓

Banco vetorial
```

Quando um desenvolvedor pergunta:

```text
Como faço deploy do serviço de pagamentos em ambiente de homologação?
```

O sistema busca trechos semanticamente relacionados.

Depois, envia esses trechos ao modelo generativo para criar uma resposta.

Isso evita depender apenas do conhecimento geral do modelo.

---

# Exemplos Usando AWS

# Amazon Bedrock

Amazon Bedrock fornece acesso a Foundation Models e também a modelos que podem ser usados para embeddings.

Em aplicações de IA Generativa, embeddings podem ser usados para:

- busca semântica;
- RAG;
- recuperação de documentos;
- comparação de textos;
- agrupamento;
- classificação;
- recomendação.

Fluxo conceitual:

```text
Texto

↓

Modelo de embedding no Amazon Bedrock

↓

Vetor

↓

Banco vetorial
```

Para a certificação:

```text
Embeddings + busca semântica + RAG + AWS

↓

Amazon Bedrock e arquitetura com base de conhecimento ou banco vetorial
```

---

# Amazon Titan Text Embeddings

Amazon Titan Text Embeddings é uma família de modelos de embedding disponível no Amazon Bedrock.

Esses modelos recebem texto como entrada e geram vetores.

Casos de uso comuns:

- RAG;
- busca em documentos;
- similaridade semântica;
- clustering;
- classificação;
- recuperação de trechos relevantes.

O detalhe importante para a prova não é decorar limites específicos.

O importante é entender:

- modelo generativo gera texto;
- modelo de embedding gera vetor;
- vetor é usado para comparação e recuperação;
- busca e recuperação normalmente são feitas por banco vetorial ou mecanismo de busca, não pelo modelo de embedding sozinho.

Detalhes como dimensões, limites e idiomas suportados devem ser consultados na documentação oficial.

---

# Knowledge Bases for Amazon Bedrock

Knowledge Bases for Amazon Bedrock ajuda a implementar RAG com dados corporativos.

Em alto nível, uma base de conhecimento pode:

- conectar fontes de dados;
- processar documentos;
- dividir conteúdo em chunks;
- gerar embeddings;
- armazenar embeddings em uma base vetorial;
- recuperar trechos relevantes;
- enviar contexto ao modelo para geração de resposta.

Fluxo simplificado:

```text
Documentos

↓

Knowledge Base

↓

Chunks

↓

Embeddings

↓

Recuperação

↓

Foundation Model

↓

Resposta
```

Para a certificação, associe Knowledge Bases com RAG e uso de dados próprios da empresa.

---

# Amazon OpenSearch

Amazon OpenSearch Service e Amazon OpenSearch Serverless podem ser usados em arquiteturas de busca vetorial.

Eles podem armazenar e consultar vetores para encontrar conteúdo semelhante.

Exemplo de papel na arquitetura:

```text
Embedding da pergunta

↓

OpenSearch com busca vetorial

↓

Trechos relevantes

↓

Foundation Model
```

O ponto principal é entender o papel:

- embeddings representam significado como vetores;
- mecanismo de busca vetorial encontra vetores próximos;
- modelo generativo usa os trechos recuperados para responder.

---

# Quando Utilizar Embeddings

Use embeddings quando o problema envolve comparar significado, recuperar conteúdo relacionado ou encontrar similaridade.

Exemplos:

- busca semântica;
- RAG;
- recomendação;
- detecção de perguntas parecidas;
- agrupamento de documentos;
- classificação de tickets;
- deduplicação de conteúdo;
- busca em documentação;
- comparação de currículos;
- descoberta de produtos similares;
- roteamento de chamados;
- recuperação de contexto para chatbots.

Palavras-chave comuns:

- similaridade;
- semântica;
- vetor;
- busca vetorial;
- embedding;
- RAG;
- documentos relevantes;
- base de conhecimento;
- recuperar contexto;
- encontrar conteúdo parecido.

---

# Quando NÃO Utilizar Embeddings

Embeddings não são necessários quando:

- a busca por palavra-chave resolve bem;
- a regra é simples e determinística;
- não há necessidade de comparar significado;
- o volume de dados é muito pequeno;
- a resposta deve vir de uma consulta exata;
- a aplicação exige correspondência literal;
- não existe estratégia para atualizar embeddings quando os dados mudam.

Exemplos:

| Problema | Melhor abordagem |
|----------|------------------|
| Buscar produto por código exato | Consulta tradicional |
| Validar CPF obrigatório | Regra de negócio |
| Calcular imposto | Código determinístico |
| Encontrar perguntas semanticamente parecidas | Embeddings |
| Recuperar trechos relevantes para RAG | Embeddings |
| Recomendar itens similares | Embeddings |

---

# Boas Práticas

# Escolha bons chunks

Chunks muito grandes podem misturar assuntos.

Chunks muito pequenos podem perder contexto.

Busque equilíbrio.

Exemplo:

```text
Chunk grande demais:
Manual inteiro de 80 páginas

Chunk pequeno demais:
Uma frase isolada sem contexto

Chunk adequado:
Uma seção ou parágrafo com sentido completo
```

---

# Mantenha metadados

Ao armazenar embeddings, mantenha metadados úteis.

Exemplos:

- nome do documento;
- URL;
- data de atualização;
- área responsável;
- nível de confidencialidade;
- número da página;
- seção;
- idioma;
- permissões.

Metadados ajudam a filtrar resultados e aplicar segurança.

---

# Atualize embeddings quando os dados mudarem

Se o documento original muda, o embedding antigo pode ficar desatualizado.

Exemplo:

```text
Política antiga:
Reembolso até R$ 100.

Política nova:
Reembolso até R$ 200.
```

Se a aplicação continuar usando embedding antigo, pode recuperar conteúdo incorreto.

Processos de ingestão precisam lidar com atualização, remoção e reprocessamento.

---

# Aplique controle de acesso

Busca semântica não elimina a necessidade de segurança.

Se um usuário não pode acessar determinado documento, ele também não deve receber trechos desse documento via RAG.

Cuidados:

- filtrar por permissões;
- respeitar classificação de dados;
- evitar vazamento de informações;
- auditar consultas;
- proteger dados sensíveis;
- controlar acesso à base vetorial.

---

# Avalie a qualidade da recuperação

Uma aplicação RAG depende da qualidade dos documentos recuperados.

Avalie:

- os trechos recuperados são relevantes?
- documentos importantes aparecem entre os primeiros resultados?
- há ruído?
- há documentos desatualizados?
- a resposta final está baseada nas fontes corretas?

Sem boa recuperação, o modelo pode gerar respostas ruins mesmo sendo um bom modelo.

---

# Comparações Importantes

# Embedding versus Token

| Conceito | Explicação |
|----------|------------|
| Token | Unidade de texto processada pelo modelo |
| Embedding | Vetor numérico que representa significado |

Tokens são pedaços do texto.

Embeddings representam relações semânticas.

---

# Embedding versus Prompt

Prompt é a instrução enviada ao modelo.

Embedding é uma representação vetorial.

Exemplo:

```text
Prompt:
Resuma este documento.

Embedding:
[0.12, -0.44, 0.03, ...]
```

Prompt é legível por humanos.

Embedding é usado por algoritmos.

---

# Embedding versus Resposta Gerada

| Conceito | Saída |
|----------|-------|
| Modelo generativo | Texto, imagem, código ou resposta |
| Modelo de embedding | Vetor numérico |

Se a aplicação precisa responder ao usuário, use modelo generativo.

Se a aplicação precisa comparar significado, use embeddings.

---

# Embedding versus Banco Vetorial

Embedding é o vetor.

Banco vetorial é onde os vetores podem ser armazenados e consultados.

```text
Texto

↓

Embedding

↓

Banco vetorial
```

Não confunda o dado com o sistema que armazena e consulta o dado.

---

# Embedding versus RAG

Embedding é um componente.

RAG é uma arquitetura.

```text
RAG
│
├── documentos
├── chunks
├── embeddings
├── banco vetorial
├── recuperação
└── geração
```

Embeddings ajudam a recuperar contexto.

RAG usa esse contexto para melhorar a resposta do modelo generativo.

---

# Como a AWS Cobra esse Tema

A AWS pode cobrar embeddings em cenários de busca semântica, RAG, Knowledge Bases, Amazon Bedrock e recuperação de documentos.

O enunciado pode mencionar:

- documentos corporativos;
- busca semântica;
- base de conhecimento;
- vetores;
- similaridade;
- recuperar trechos relevantes;
- reduzir hallucinations;
- responder com dados próprios;
- RAG;
- Knowledge Bases for Amazon Bedrock.

## Exemplo 1

> Uma empresa deseja que um chatbot responda perguntas com base em documentos internos, recuperando trechos semanticamente relevantes.

Palavras-chave:

- documentos internos;
- semanticamente relevantes;
- chatbot;
- recuperar trechos.

Interpretação:

**Embeddings e busca vetorial são adequados para recuperar contexto.**

Na AWS, pense em Amazon Bedrock com Knowledge Bases ou arquitetura RAG.

---

## Exemplo 2

> Uma aplicação precisa encontrar produtos parecidos mesmo quando os nomes não usam as mesmas palavras.

Palavras-chave:

- produtos parecidos;
- nomes diferentes;
- significado semelhante.

Interpretação:

**Embeddings podem representar similaridade entre produtos.**

---

## Exemplo 3

> Uma empresa quer buscar um documento pelo ID exato informado pelo usuário.

Palavras-chave:

- ID exato;
- correspondência literal;
- consulta direta.

Interpretação:

**Embeddings provavelmente não são necessários.**

Uma consulta tradicional resolve melhor.

---

# Pegadinhas da Certificação

## Pegadinha 1

**"Embedding é a resposta gerada pelo modelo."**

Falso.

Embedding é um vetor numérico.

Resposta gerada é texto ou outro conteúdo produzido por modelo generativo.

---

## Pegadinha 2

**"Busca vetorial substitui segurança."**

Falso.

Mesmo usando embeddings, a aplicação precisa respeitar permissões, privacidade e governança.

---

## Pegadinha 3

**"Embeddings sempre são melhores que busca por palavra-chave."**

Falso.

Para busca exata por código, ID ou termo literal, busca tradicional pode ser melhor.

---

## Pegadinha 4

**"RAG é a mesma coisa que embedding."**

Falso.

RAG é uma arquitetura.

Embeddings são usados em muitas arquiteturas RAG para recuperar documentos relevantes.

---

## Pegadinha 5

**"Depois de gerar embeddings, nunca é preciso atualizá-los."**

Falso.

Quando os dados mudam, embeddings podem precisar ser reprocessados.

---

# Erros Comuns

## Erro 1 — Criar chunks ruins

Chunks mal definidos prejudicam a recuperação.

Problemas comuns:

- chunks grandes demais;
- chunks pequenos demais;
- separação no meio de uma ideia;
- perda de título ou contexto;
- mistura de assuntos diferentes.

---

## Erro 2 — Não guardar metadados

Sem metadados, fica mais difícil:

- mostrar fonte;
- auditar resposta;
- aplicar filtros;
- respeitar permissões;
- atualizar documentos;
- explicar de onde veio o contexto.

---

## Erro 3 — Confundir similaridade com verdade

Um documento semanticamente parecido não é automaticamente correto.

Ele pode estar:

- desatualizado;
- incompleto;
- fora do escopo;
- sem autorização;
- contraditório com outro documento.

Similaridade ajuda a recuperar candidatos.

Validação continua necessária.

---

## Erro 4 — Ignorar atualização da base

Se documentos mudam, a base vetorial precisa acompanhar.

Caso contrário, o sistema pode recuperar conteúdo antigo.

---

# Questões Comentadas

## Questão 1 — Nível Fácil

O que é um embedding?

A) Uma regra fixa escrita em código.

B) Uma representação vetorial numérica de um dado.

C) Uma senha temporária para autenticação.

D) Um serviço de DNS.

### Resposta

**Alternativa B.**

Embedding é uma representação numérica, normalmente vetorial, usada para representar significado e relações entre dados.

---

## Questão 2 — Nível Intermediário

Uma empresa quer encontrar documentos relevantes mesmo quando a pergunta do usuário usa palavras diferentes das palavras do documento.

Qual abordagem é mais adequada?

A) Busca semântica com embeddings.

B) Cálculo de imposto.

C) Regra fixa com if/else.

D) Backup em fita.

### Resposta

**Alternativa A.**

Embeddings permitem comparar significado, não apenas palavras exatas.

---

## Questão 3 — Nível AWS

Uma empresa deseja criar uma aplicação RAG com Amazon Bedrock para responder perguntas usando documentos internos.

Qual papel os embeddings costumam desempenhar nessa arquitetura?

A) Gerar a resposta final para o usuário.

B) Representar documentos e perguntas como vetores para recuperar trechos relevantes.

C) Criar sub-redes privadas.

D) Substituir IAM.

### Resposta

**Alternativa B.**

Embeddings representam documentos e perguntas como vetores.

Isso permite recuperar trechos semanticamente próximos para fornecer contexto ao modelo generativo.

---

## Questão 4 — Nível Certificação

Uma aplicação precisa buscar um pedido pelo número exato informado pelo cliente.

Qual abordagem é mais simples e adequada?

A) Busca semântica com embeddings.

B) Consulta exata por identificador.

C) Fine-tuning de Foundation Model.

D) Geração de imagem.

### Resposta

**Alternativa B.**

Quando a busca é por identificador exato, uma consulta tradicional costuma ser mais adequada que embeddings.

---

## Questão 5 — Nível AWS

Uma empresa usa embeddings para documentos internos, mas percebe que respostas usam políticas antigas.

Qual problema é mais provável?

A) Os embeddings ou a base vetorial não foram atualizados após mudança dos documentos.

B) O roteamento DNS está sem zona pública.

C) A aplicação não usa sub-redes suficientes.

D) O token sempre é igual à palavra.

### Resposta

**Alternativa A.**

Quando documentos mudam, o processo de ingestão precisa atualizar chunks, embeddings e índice vetorial.

---

# Checklist de Revisão

Antes de avançar para o próximo capítulo, verifique se você consegue responder às perguntas abaixo sem consultar o material.

## Conceito

- [ ] Sei definir embedding.
- [ ] Sei explicar por que embedding é um vetor.
- [ ] Sei diferenciar embedding de token.
- [ ] Sei explicar similaridade semântica.

---

## Aplicação

- [ ] Sei explicar como embeddings ajudam busca semântica.
- [ ] Sei explicar como embeddings participam de RAG.
- [ ] Sei explicar o papel de chunks.
- [ ] Sei explicar o papel de banco vetorial.

---

## AWS

- [ ] Sei associar embeddings com Amazon Bedrock.
- [ ] Sei explicar o papel de Amazon Titan Text Embeddings em alto nível.
- [ ] Sei associar Knowledge Bases for Amazon Bedrock com RAG.
- [ ] Sei explicar por que detalhes de modelos devem ser consultados na documentação oficial.

---

## Boas práticas

- [ ] Sei explicar por que chunks precisam ser bem definidos.
- [ ] Sei citar metadados úteis.
- [ ] Sei explicar por que embeddings precisam ser atualizados quando dados mudam.
- [ ] Sei reconhecer quando uma busca exata é melhor que embeddings.

---

# Resumo do Capítulo

Embeddings são representações vetoriais numéricas de dados, como palavras, frases, documentos, imagens ou itens de negócio.

Eles permitem comparar significado e similaridade, o que viabiliza busca semântica, recomendação, agrupamento, classificação e recuperação de contexto.

Em aplicações de IA Generativa, embeddings são especialmente importantes em arquiteturas RAG.

Documentos são divididos em chunks, transformados em embeddings e armazenados em uma base vetorial.

Quando o usuário faz uma pergunta, a pergunta também vira embedding, e o sistema recupera trechos semanticamente próximos para enviar ao Foundation Model.

Na AWS, embeddings aparecem em cenários com Amazon Bedrock, Amazon Titan Text Embeddings, Knowledge Bases for Amazon Bedrock e mecanismos de busca vetorial.

---

# Principais Pontos para a Certificação

| Cenário | Pense em |
|---------|----------|
| Representar significado numericamente | Embedding |
| Buscar documentos por significado | Busca semântica |
| Encontrar vetores parecidos | Busca vetorial |
| Responder com documentos internos | RAG |
| Gerar embeddings na AWS | Amazon Bedrock / modelos de embedding |
| Base de conhecimento para RAG | Knowledge Bases for Amazon Bedrock |
| Armazenar e consultar vetores | Banco vetorial |
| Documento mudou | Reprocessar chunks e embeddings |
| Busca por ID exato | Consulta tradicional |

---

# Em uma Frase

> **Embeddings transformam dados em vetores que representam significado, permitindo busca semântica e recuperação de contexto para aplicações de IA Generativa e RAG.**

---

# Glossário

## Embedding

Representação vetorial numérica de um dado, usada para capturar significado e relações.

---

## Vetor

Lista de números que representa um ponto em um espaço matemático.

---

## Similaridade semântica

Medida de proximidade de significado entre dois conteúdos.

---

## Busca semântica

Busca baseada em significado, não apenas em palavras exatas.

---

## Busca vetorial

Busca que compara vetores para encontrar itens próximos em um espaço vetorial.

---

## Chunk

Trecho de documento usado como unidade de indexação, recuperação ou contexto.

---

## Banco vetorial

Sistema usado para armazenar e consultar embeddings.

---

## RAG

Retrieval-Augmented Generation. Arquitetura que recupera informações externas e as usa como contexto para geração de respostas.

---

## Modelo de embedding

Modelo que recebe um dado, como texto, e gera um vetor representando seu significado.

---

# Referências

A elaboração deste capítulo foi baseada nas seguintes referências oficiais:

- [AWS Certified AI Practitioner (AIF-C01) Exam Guide](https://docs.aws.amazon.com/pt_br/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html)
- [What are Embeddings in Machine Learning? - AWS](https://aws.amazon.com/what-is/embeddings-in-machine-learning/)
- [Amazon Titan Text Embeddings models - Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/titan-embedding-models.html)
- [Retrieve data and generate AI responses with Amazon Bedrock Knowledge Bases](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html)
- [Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)
- [Supported foundation models in Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/models-supported.html)

---

# Próximo Capítulo

No próximo capítulo será apresentado o conceito de:

## Busca Vetorial

Arquivo planejado: `chapters/07-vector-search.md`.

Você aprenderá:

- o que é busca vetorial;
- como vetores são comparados;
- por que busca vetorial é importante para RAG;
- como ela se relaciona com embeddings;
- como esse conceito aparece na certificação.

---

**Fim do Capítulo 6**
