# Capítulo 7 — Busca Vetorial

---

# Objetivos de Aprendizagem

Ao concluir este capítulo, você será capaz de:

- compreender o que é busca vetorial;
- explicar como vetores são usados para encontrar conteúdo semelhante;
- diferenciar busca vetorial, busca semântica e busca por palavra-chave;
- entender a relação entre busca vetorial, embeddings e RAG;
- reconhecer conceitos como k-NN, similaridade, distância, índice vetorial e banco vetorial;
- identificar casos de uso comuns em aplicações corporativas;
- associar busca vetorial a Amazon Bedrock Knowledge Bases, Amazon OpenSearch e arquiteturas de IA Generativa;
- reconhecer boas práticas, limitações e pegadinhas cobradas na AWS Certified AI Practitioner (AIF-C01).

---

# Pré-requisitos

Antes deste capítulo, é recomendado compreender:

- o que são tokens;
- o que são embeddings;
- o que são Foundation Models;
- o que é IA Generativa;
- o que é RAG em visão geral;
- por que documentos podem ser divididos em chunks;
- por que embeddings representam significado como vetores.

Os capítulos anteriores apresentam esses conceitos.

---

# Introdução

Busca vetorial é uma técnica usada para encontrar itens semelhantes com base em vetores.

Em aplicações de IA Generativa, esses vetores normalmente são embeddings.

O objetivo é permitir que uma aplicação encontre conteúdos relacionados por significado, não apenas por palavras exatas.

Exemplo:

```text
Pergunta do usuário:
Como recupero o acesso se esqueci minha senha?
```

Documento armazenado:

```text
Procedimento para redefinição de senha de usuários bloqueados.
```

Mesmo sem usar exatamente as mesmas palavras, os dois textos têm significado parecido.

Busca vetorial ajuda a encontrar esse documento.

O ponto central é:

> Busca vetorial encontra itens próximos em um espaço vetorial, permitindo recuperar conteúdo semanticamente relacionado.

---

# Conceitos Fundamentais

# O que é Busca Vetorial?

Busca vetorial é o processo de procurar vetores semelhantes dentro de uma coleção de vetores.

Fluxo simplificado:

```text
Pergunta do usuário

↓

Embedding da pergunta

↓

Busca em uma base de vetores

↓

Vetores mais próximos

↓

Documentos ou trechos relacionados
```

O resultado da busca não é encontrado por igualdade textual.

Ele é encontrado por proximidade matemática.

---

# O que é um Vetor?

Um vetor é uma lista de números.

Exemplo:

```text
[0.13, -0.27, 0.88, 0.04, ...]
```

Em IA, vetores podem representar:

- textos;
- documentos;
- imagens;
- produtos;
- usuários;
- perguntas;
- trechos de código;
- tickets de suporte;
- registros de catálogo.

Quando dois vetores estão próximos, os conteúdos que eles representam tendem a ser semelhantes.

---

# Busca Vetorial versus Busca Semântica

Busca vetorial é a técnica matemática.

Busca semântica é um caso de uso.

```text
Busca vetorial

↓

Encontra vetores próximos
```

```text
Busca semântica

↓

Usa vetores para encontrar conteúdos com significado parecido
```

Exemplo:

```text
Pergunta:
Como alterar minha senha?

Resultado semântico:
Procedimento para recuperação de credenciais.
```

O sistema não encontrou apenas palavras iguais.

Ele encontrou significado parecido.

---

# Busca Vetorial versus Palavra-chave

Busca por palavra-chave procura termos exatos ou próximos.

Busca vetorial procura proximidade entre vetores.

Comparação:

| Aspecto | Palavra-chave | Busca vetorial |
|---------|---------------|----------------|
| Base | Termos textuais | Vetores |
| Encontra sinônimos | Limitado | Melhor |
| Entende significado | Limitado | Sim, quando embeddings são bons |
| Busca por ID exato | Excelente | Não é a melhor opção |
| RAG com documentos | Pode ajudar | Muito comum |
| Exemplo | "senha" encontra "senha" | "recuperar acesso" encontra "redefinir senha" |

As duas abordagens podem ser combinadas.

Isso é chamado de busca híbrida.

---

# Como Funciona

Busca vetorial normalmente possui duas fases:

- indexação;
- consulta.

```text
Indexação

↓

Preparar e armazenar vetores

Consulta

↓

Buscar vetores próximos
```

---

# 1. Indexação

Indexação é a preparação dos dados para busca.

Em um cenário com documentos, o fluxo comum é:

```text
Documentos

↓

Divisão em chunks

↓

Geração de embeddings

↓

Armazenamento em índice vetorial
```

Cada chunk recebe um embedding.

Esse embedding é armazenado junto com metadados.

Metadados úteis:

- título do documento;
- fonte;
- URL;
- data de atualização;
- permissões;
- área responsável;
- idioma;
- tipo de documento;
- número da página;
- seção.

---

# 2. Consulta

Consulta é o momento em que o usuário faz uma pergunta.

Fluxo comum:

```text
Pergunta do usuário

↓

Embedding da pergunta

↓

Busca vetorial

↓

Top resultados

↓

Trechos relevantes
```

O sistema compara o vetor da pergunta com os vetores armazenados.

Os vetores mais próximos são retornados como resultados.

---

# k-NN

k-NN significa **k-nearest neighbors**.

Em português, significa "k vizinhos mais próximos".

No contexto de busca vetorial, k indica quantos resultados próximos você deseja retornar.

Exemplo:

```text
k = 3

↓

Retornar os 3 vetores mais próximos da consulta
```

Se a pergunta é:

```text
Como redefinir minha senha?
```

O sistema pode retornar:

```text
1. Procedimento de redefinição de senha
2. Recuperação de acesso bloqueado
3. Política de autenticação multifator
```

Na certificação, o importante é entender o conceito.

Não é necessário memorizar algoritmos internos.

---

# Similaridade e Distância

Busca vetorial depende de uma forma de medir proximidade entre vetores.

Métricas comuns:

- cosine similarity;
- distância euclidiana;
- dot product.

Para a AWS Certified AI Practitioner, não é necessário memorizar fórmulas.

O que importa:

- vetores próximos representam conteúdos mais relacionados;
- vetores distantes representam conteúdos menos relacionados;
- o mecanismo de busca usa métricas matemáticas para ordenar resultados.

Exemplo conceitual:

```text
Consulta:
Como acesso minha conta?

Resultado A:
Procedimento para login e recuperação de senha.
Similaridade alta.

Resultado B:
Política de reembolso de viagens.
Similaridade baixa.
```

---

# Índice Vetorial

Um índice vetorial é uma estrutura usada para organizar vetores e acelerar buscas.

Sem índice, o sistema poderia precisar comparar a consulta com todos os vetores.

Isso pode ser caro e lento em grandes volumes.

Com índice, a busca fica mais eficiente.

Fluxo:

```text
Vetores armazenados

↓

Índice vetorial

↓

Busca rápida por vizinhos próximos
```

Índices vetoriais são comuns em bancos vetoriais e mecanismos como Amazon OpenSearch.

---

# Banco Vetorial

Banco vetorial é um sistema especializado em armazenar e consultar vetores.

Ele pode oferecer:

- armazenamento de embeddings;
- busca por similaridade;
- filtros por metadados;
- escalabilidade;
- atualização de índices;
- integração com aplicações;
- suporte a RAG.

Em arquiteturas de IA Generativa, o banco vetorial frequentemente fica entre a base de documentos e o Foundation Model.

```text
Documentos

↓

Embeddings

↓

Banco vetorial

↓

Trechos recuperados

↓

Foundation Model
```

---

# Busca Híbrida

Busca híbrida combina busca por palavra-chave com busca vetorial.

Isso é útil porque cada abordagem tem forças diferentes.

Busca por palavra-chave é boa para:

- códigos exatos;
- nomes específicos;
- IDs;
- termos obrigatórios;
- correspondência literal.

Busca vetorial é boa para:

- significado;
- sinônimos;
- perguntas em linguagem natural;
- documentos com vocabulário diferente;
- descoberta de conteúdo relacionado.

Exemplo:

```text
Consulta:
erro 403 ao acessar portal de benefícios
```

Uma busca híbrida pode considerar:

- palavra-chave: "403";
- semântica: "erro de autorização", "acesso negado", "portal de benefícios".

---

# Busca Vetorial e RAG

Busca vetorial é muito usada em RAG.

RAG combina:

- recuperação de informações;
- geração de respostas.

Fluxo:

```text
Pergunta do usuário

↓

Embedding da pergunta

↓

Busca vetorial

↓

Trechos relevantes

↓

Prompt aumentado com contexto

↓

Foundation Model

↓

Resposta gerada
```

A busca vetorial encontra o contexto.

O Foundation Model gera a resposta.

---

# Por que Busca Vetorial Ajuda em RAG?

Foundation Models possuem conhecimento geral, mas nem sempre conhecem dados internos, privados ou atualizados de uma empresa.

Busca vetorial ajuda a recuperar esse conteúdo.

Exemplos:

- políticas internas;
- contratos;
- manuais;
- documentação técnica;
- tickets;
- artigos de base de conhecimento;
- runbooks;
- catálogos;
- informações de produto.

Depois, esses trechos são enviados ao modelo como contexto.

Isso pode:

- melhorar relevância;
- reduzir hallucinations;
- permitir uso de dados privados;
- evitar treinar novamente o modelo;
- facilitar atualização de conhecimento;
- fornecer citações ou fontes.

---

# Exemplo do Mundo Real

Imagine uma empresa com uma central de atendimento.

Ela possui milhares de artigos de suporte.

Um cliente pergunta:

```text
Meu pedido aparece como entregue, mas não recebi.
```

Os artigos podem ter títulos como:

- "Contestação de entrega";
- "Produto não recebido";
- "Divergência no status de entrega";
- "Acionamento da transportadora".

Uma busca por palavra-chave pode não encontrar tudo.

Busca vetorial pode entender que essas frases estão relacionadas.

O sistema recupera os artigos mais relevantes e envia ao modelo generativo.

O modelo então responde com base nesses artigos.

---

# Exemplo Relacionado ao Desenvolvimento de Software

Uma organização possui muitos documentos técnicos:

- runbooks;
- ADRs;
- README de serviços;
- incidentes anteriores;
- documentação de deploy;
- decisões de arquitetura;
- exemplos de configuração.

Um desenvolvedor pergunta:

```text
Como faço rollback do serviço de pagamentos?
```

Busca vetorial pode recuperar trechos como:

- "procedimento de reversão";
- "rollback em produção";
- "deploy anterior";
- "restaurar versão estável";
- "pipeline do serviço de pagamentos".

Mesmo que os documentos não usem exatamente a palavra "rollback", a busca pode encontrar conteúdo semanticamente próximo.

---

# Exemplos Usando AWS

# Amazon Bedrock Knowledge Bases

Amazon Bedrock Knowledge Bases ajuda a implementar RAG com dados corporativos.

Em alto nível, ele pode:

- conectar fontes de dados;
- dividir documentos em chunks;
- gerar embeddings;
- armazenar ou integrar com uma base vetorial;
- recuperar informações relevantes;
- fornecer contexto ao modelo;
- ajudar a gerar respostas baseadas em dados da empresa.

Fluxo:

```text
Fonte de dados

↓

Knowledge Base

↓

Chunks e embeddings

↓

Busca vetorial

↓

Trechos relevantes

↓

Foundation Model

↓

Resposta
```

Para a prova:

```text
RAG + documentos internos + Amazon Bedrock

↓

Knowledge Bases for Amazon Bedrock
```

---

# Amazon OpenSearch

Amazon OpenSearch Service pode ser usado para busca vetorial por meio de k-NN.

Nesse tipo de arquitetura, OpenSearch armazena vetores e permite buscar vizinhos próximos.

Exemplo conceitual:

```text
Embedding da pergunta

↓

Consulta k-NN no OpenSearch

↓

Vetores mais próximos

↓

Documentos relevantes
```

Esse recurso pode ser usado em:

- busca semântica;
- recomendação;
- RAG;
- detecção de similaridade;
- recuperação de documentos.

Na certificação, o foco não é configurar o índice em detalhe.

O foco é entender que OpenSearch pode participar da camada de busca vetorial.

---

# Amazon OpenSearch Serverless

Amazon OpenSearch Serverless também pode aparecer em arquiteturas com busca vetorial, especialmente quando a aplicação precisa de uma opção gerenciada e escalável para consulta e indexação.

O ponto importante:

- embeddings representam documentos como vetores;
- o mecanismo de busca vetorial armazena e consulta esses vetores;
- a aplicação usa os resultados como contexto para IA Generativa.

Não memorize configurações específicas para a AIF-C01.

Entenda o papel arquitetural.

---

# Amazon S3 como Fonte de Dados

Amazon S3 frequentemente aparece como fonte de documentos em arquiteturas de RAG.

Exemplo:

```text
Documentos no Amazon S3

↓

Ingestão

↓

Chunks

↓

Embeddings

↓

Busca vetorial

↓

Resposta gerada
```

S3 armazena documentos.

Ele não é, por si só, o mecanismo de busca vetorial nesse fluxo.

---

# Quando Utilizar Busca Vetorial

Use busca vetorial quando precisar encontrar conteúdo semelhante por significado.

Exemplos:

- buscar documentos relevantes para RAG;
- encontrar perguntas parecidas;
- recomendar produtos similares;
- encontrar tickets parecidos;
- agrupar documentos;
- detectar conteúdo duplicado;
- buscar imagens similares;
- recuperar trechos de documentação;
- alimentar chatbots com contexto;
- localizar políticas internas relacionadas;
- comparar descrições de incidentes.

Palavras-chave comuns:

- vetor;
- embeddings;
- similaridade;
- semântica;
- k-NN;
- busca vetorial;
- banco vetorial;
- RAG;
- contexto relevante;
- documentos internos;
- Knowledge Base.

---

# Quando NÃO Utilizar Busca Vetorial

Busca vetorial não é ideal para todo problema.

Evite quando:

- a busca é por ID exato;
- a busca é por código literal;
- uma consulta SQL simples resolve;
- o problema exige correspondência exata;
- não há necessidade de similaridade;
- a base é muito pequena e simples;
- dados não foram preparados corretamente;
- permissões não podem ser aplicadas no resultado.

Exemplos:

| Problema | Melhor abordagem |
|----------|------------------|
| Buscar pedido pelo ID exato | Consulta tradicional |
| Validar se CPF foi informado | Regra de negócio |
| Encontrar documentos com significado parecido | Busca vetorial |
| Recuperar contexto para RAG | Busca vetorial |
| Buscar código de produto exato | Busca por chave ou filtro |

---

# Boas Práticas

# Use chunks bem definidos

Busca vetorial depende da qualidade do conteúdo indexado.

Chunks ruins prejudicam resultados.

Problemas comuns:

- chunks grandes demais;
- chunks pequenos demais;
- texto sem título;
- perda de contexto;
- divisão no meio de uma ideia;
- documentos desatualizados.

---

# Mantenha metadados

Metadados ajudam a filtrar, auditar e proteger resultados.

Exemplos:

- fonte;
- URL;
- data de atualização;
- dono do documento;
- tipo do conteúdo;
- confidencialidade;
- permissões;
- idioma;
- produto;
- região;
- versão.

Metadados são especialmente importantes para segurança.

---

# Combine filtros com busca vetorial

Em aplicações corporativas, similaridade não basta.

Exemplo:

```text
Usuário pergunta sobre política salarial.
```

Mesmo que exista um documento semanticamente relevante, ele só deve ser retornado se o usuário tiver permissão.

Filtros por metadados podem restringir resultados por:

- área;
- permissões;
- país;
- idioma;
- data;
- produto;
- tipo de documento.

---

# Atualize o índice

Se documentos mudam, o índice precisa acompanhar.

Processos comuns:

- detectar documentos novos;
- reprocessar documentos alterados;
- remover documentos excluídos;
- atualizar embeddings;
- preservar metadados;
- registrar data da ingestão.

Índice desatualizado gera respostas desatualizadas.

---

# Avalie a recuperação

Uma boa aplicação RAG depende de boa recuperação.

Avalie:

- os resultados são relevantes?
- os documentos corretos aparecem no topo?
- há documentos irrelevantes?
- os resultados respeitam permissões?
- o contexto recuperado responde à pergunta?
- há citações ou rastreabilidade?

Sem avaliação, a aplicação pode parecer boa em demonstrações e falhar em uso real.

---

# Controle quantidade de resultados

Retornar resultados demais pode aumentar tokens e ruído.

Retornar resultados de menos pode deixar faltar contexto.

O valor de `k` deve equilibrar:

- relevância;
- custo;
- latência;
- tamanho do prompt;
- cobertura de informação;
- risco de ruído.

---

# Comparações Importantes

# Busca Vetorial versus Embeddings

| Conceito | Explicação |
|----------|------------|
| Embedding | Vetor que representa um dado |
| Busca vetorial | Processo de encontrar vetores semelhantes |

Embedding é o dado.

Busca vetorial é a operação.

---

# Busca Vetorial versus RAG

| Conceito | Explicação |
|----------|------------|
| Busca vetorial | Recupera itens semelhantes |
| RAG | Usa recuperação para melhorar geração |

Busca vetorial pode ser uma etapa dentro de RAG.

RAG inclui também o Foundation Model gerando a resposta.

---

# Busca Vetorial versus Busca Semântica

Busca vetorial é técnica.

Busca semântica é aplicação dessa técnica para significado.

```text
Embeddings

↓

Busca vetorial

↓

Busca semântica
```

---

# Busca Vetorial versus Banco Vetorial

| Conceito | Explicação |
|----------|------------|
| Busca vetorial | Operação de consulta por similaridade |
| Banco vetorial | Sistema que armazena e consulta vetores |

O banco vetorial viabiliza a busca.

A busca é o processo executado sobre os vetores.

---

# Busca Vetorial versus Busca por Palavra-chave

| Critério | Palavra-chave | Vetorial |
|----------|---------------|----------|
| Usa termos exatos | Sim | Não necessariamente |
| Usa significado | Limitado | Sim |
| Boa para IDs | Sim | Não é ideal |
| Boa para perguntas naturais | Limitado | Sim |
| Boa para RAG | Pode ajudar | Muito comum |

---

# Como a AWS Cobra esse Tema

A AWS pode cobrar busca vetorial em cenários de RAG, Amazon Bedrock Knowledge Bases, embeddings, busca semântica e recuperação de documentos.

O enunciado pode mencionar:

- documentos internos;
- base de conhecimento;
- busca por significado;
- encontrar documentos relevantes;
- embeddings;
- vetores;
- k-NN;
- RAG;
- contexto para Foundation Model;
- Amazon OpenSearch;
- Amazon Bedrock Knowledge Bases.

## Exemplo 1

> Uma empresa deseja que uma aplicação generativa responda perguntas com base em documentos internos, recuperando trechos relevantes antes de gerar a resposta.

Palavras-chave:

- documentos internos;
- recuperar trechos relevantes;
- aplicação generativa;
- resposta baseada em contexto.

Interpretação:

**RAG com busca vetorial e embeddings.**

Na AWS, pense em Amazon Bedrock Knowledge Bases ou arquitetura com banco vetorial.

---

## Exemplo 2

> Uma aplicação precisa encontrar artigos relacionados mesmo quando o usuário usa sinônimos e termos diferentes dos documentos.

Palavras-chave:

- termos diferentes;
- sinônimos;
- artigos relacionados.

Interpretação:

**Busca semântica com embeddings e busca vetorial.**

---

## Exemplo 3

> Uma empresa precisa buscar uma nota fiscal pelo número exato informado.

Palavras-chave:

- número exato;
- busca literal;
- identificador.

Interpretação:

**Busca tradicional ou consulta por chave.**

Busca vetorial não é necessária.

---

## Exemplo 4

> Uma aplicação RAG recupera muitos documentos irrelevantes e envia tudo ao modelo, aumentando custo e piorando respostas.

Palavras-chave:

- documentos irrelevantes;
- envia tudo;
- custo;
- piora de resposta.

Interpretação:

É necessário melhorar recuperação, chunking, filtros, ranking ou quantidade de resultados.

---

# Pegadinhas da Certificação

## Pegadinha 1

**"Busca vetorial é a mesma coisa que embedding."**

Falso.

Embedding é o vetor.

Busca vetorial é o processo de consultar vetores semelhantes.

---

## Pegadinha 2

**"Busca vetorial substitui RAG."**

Falso.

Busca vetorial pode ser uma etapa de RAG.

RAG também envolve geração de resposta com um modelo.

---

## Pegadinha 3

**"Busca vetorial é sempre melhor que busca por palavra-chave."**

Falso.

Para IDs, códigos e correspondência literal, busca tradicional pode ser melhor.

---

## Pegadinha 4

**"Enviar mais resultados ao modelo sempre melhora a resposta."**

Falso.

Resultados irrelevantes aumentam tokens, latência, custo e ruído.

---

## Pegadinha 5

**"Similaridade significa verdade."**

Falso.

Um documento parecido pode estar errado, desatualizado ou fora de escopo.

Validação e governança continuam necessárias.

---

# Erros Comuns

## Erro 1 — Indexar documentos sem preparar chunks

Documentos muito grandes podem misturar vários assuntos.

Isso dificulta recuperação precisa.

---

## Erro 2 — Ignorar metadados e permissões

Sem filtros e permissões, a aplicação pode retornar documentos que o usuário não deveria acessar.

Busca vetorial não substitui segurança.

---

## Erro 3 — Retornar contexto demais

Muitos resultados podem causar:

- prompts maiores;
- mais custo;
- mais latência;
- respostas menos focadas;
- aumento de ruído.

---

## Erro 4 — Não atualizar o índice

Se documentos mudam e o índice não é atualizado, a aplicação pode recuperar informações antigas.

---

## Erro 5 — Não avaliar recuperação

Avaliar apenas a resposta final pode esconder problemas.

É importante avaliar também os documentos recuperados.

---

# Questões Comentadas

## Questão 1 — Nível Fácil

O que é busca vetorial?

A) Uma busca por vetores semelhantes em um espaço matemático.

B) Uma regra fixa para validar idade.

C) Um serviço de DNS.

D) Uma técnica para criar sub-redes.

### Resposta

**Alternativa A.**

Busca vetorial encontra vetores próximos, normalmente para recuperar conteúdos semelhantes ou semanticamente relacionados.

---

## Questão 2 — Nível Intermediário

Uma empresa quer encontrar documentos sobre "recuperar acesso" mesmo quando os documentos usam a expressão "redefinir senha".

Qual abordagem é mais adequada?

A) Busca vetorial com embeddings.

B) Consulta por ID exato.

C) Regra de bloqueio por limite.

D) Backup em arquivo.

### Resposta

**Alternativa A.**

Embeddings representam significado e a busca vetorial recupera conteúdos semanticamente próximos.

---

## Questão 3 — Nível AWS

Uma empresa quer construir uma aplicação RAG com Amazon Bedrock para responder perguntas sobre documentos internos.

Qual componente ajuda a recuperar trechos semanticamente relevantes?

A) Busca vetorial.

B) NAT Gateway.

C) Amazon Route 53.

D) Snapshot de volume.

### Resposta

**Alternativa A.**

Busca vetorial é usada para encontrar trechos relacionados com base em embeddings.

Esses trechos podem ser enviados ao Foundation Model como contexto.

---

## Questão 4 — Nível Certificação

Uma aplicação precisa buscar um pedido pelo número exato do pedido.

Qual abordagem é mais adequada?

A) Busca vetorial.

B) Consulta exata por identificador.

C) RAG com documentos longos.

D) Fine-tuning de imagem.

### Resposta

**Alternativa B.**

Busca por identificador exato não exige similaridade semântica.

Uma consulta tradicional é mais simples e adequada.

---

## Questão 5 — Nível AWS

Uma aplicação RAG recupera muitos trechos irrelevantes e envia todos ao modelo, aumentando custo e piorando respostas.

Qual ação pode ajudar?

A) Melhorar chunking, filtros, ranking e quantidade de resultados recuperados.

B) Remover IAM.

C) Enviar sempre todos os documentos completos.

D) Ignorar metadados.

### Resposta

**Alternativa A.**

A qualidade da recuperação impacta diretamente custo, latência e qualidade da resposta em RAG.

---

# Checklist de Revisão

Antes de avançar para o próximo capítulo, verifique se você consegue responder às perguntas abaixo sem consultar o material.

## Conceito

- [ ] Sei definir busca vetorial.
- [ ] Sei explicar o que é k-NN em alto nível.
- [ ] Sei diferenciar busca vetorial de embedding.
- [ ] Sei diferenciar busca vetorial de busca por palavra-chave.

---

## Aplicação

- [ ] Sei explicar como busca vetorial participa de RAG.
- [ ] Sei explicar por que chunks são importantes.
- [ ] Sei explicar por que metadados ajudam.
- [ ] Sei reconhecer quando busca exata é melhor.

---

## AWS

- [ ] Sei associar busca vetorial com Amazon Bedrock Knowledge Bases.
- [ ] Sei reconhecer Amazon OpenSearch como opção para busca vetorial.
- [ ] Sei explicar o papel de Amazon S3 como fonte de documentos, não como mecanismo vetorial.
- [ ] Sei evitar decorar configurações avançadas desnecessárias para AIF-C01.

---

## Boas práticas

- [ ] Sei explicar por que retornar resultados demais pode prejudicar.
- [ ] Sei explicar por que o índice precisa ser atualizado.
- [ ] Sei explicar por que busca vetorial não substitui segurança.
- [ ] Sei explicar por que similaridade não garante verdade.

---

# Resumo do Capítulo

Busca vetorial é uma técnica para encontrar vetores semelhantes em um espaço matemático.

Em aplicações de IA Generativa, esses vetores normalmente são embeddings de textos, documentos, imagens ou outros dados.

Busca vetorial permite busca semântica, recomendação, recuperação de documentos e arquiteturas RAG.

Em RAG, a pergunta do usuário é convertida em embedding, a busca vetorial encontra trechos semanticamente próximos, e esses trechos são enviados ao Foundation Model como contexto.

Na AWS, esse tema aparece em cenários com Amazon Bedrock Knowledge Bases, Amazon OpenSearch, embeddings, bancos vetoriais e recuperação de documentos.

Busca vetorial é poderosa, mas não substitui segurança, metadados, avaliação, atualização de índice nem consultas exatas quando o problema exige correspondência literal.

---

# Principais Pontos para a Certificação

| Cenário | Pense em |
|---------|----------|
| Encontrar vetores próximos | Busca vetorial |
| Buscar por significado | Busca semântica |
| Recuperar contexto para RAG | Busca vetorial + embeddings |
| Documentos internos com Amazon Bedrock | Knowledge Bases |
| Busca k-NN na AWS | Amazon OpenSearch |
| Buscar por ID exato | Consulta tradicional |
| Muitos resultados irrelevantes | Melhorar chunking, filtros e ranking |
| Documento alterado | Atualizar índice e embeddings |
| Controle de acesso | Metadados e permissões |

---

# Em uma Frase

> **Busca vetorial encontra conteúdos semelhantes comparando embeddings em um espaço vetorial, sendo uma peça central para busca semântica e RAG em aplicações de IA Generativa.**

---

# Glossário

## Busca Vetorial

Processo de encontrar vetores semelhantes em uma coleção de vetores.

---

## Busca Semântica

Busca baseada em significado, normalmente usando embeddings e busca vetorial.

---

## k-NN

k-nearest neighbors. Técnica para recuperar os k vetores mais próximos de uma consulta.

---

## Embedding

Representação vetorial numérica de um dado, como texto, imagem ou documento.

---

## Índice Vetorial

Estrutura usada para organizar vetores e acelerar consultas por similaridade.

---

## Banco Vetorial

Sistema usado para armazenar e consultar embeddings.

---

## RAG

Retrieval-Augmented Generation. Arquitetura que recupera informações externas e as usa como contexto para geração de respostas.

---

## Chunk

Trecho de documento usado como unidade de indexação, recuperação e contexto.

---

## Busca Híbrida

Combinação de busca por palavra-chave com busca vetorial.

---

# Referências

A elaboração deste capítulo foi baseada nas seguintes referências oficiais:

- [AWS Certified AI Practitioner (AIF-C01) Exam Guide](https://docs.aws.amazon.com/pt_br/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html)
- [k-Nearest Neighbor (k-NN) search in Amazon OpenSearch Service](https://docs.aws.amazon.com/opensearch-service/latest/developerguide/knn.html)
- [Retrieve data and generate AI responses with Amazon Bedrock Knowledge Bases](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html)
- [How Amazon Bedrock Knowledge Bases work](https://docs.aws.amazon.com/bedrock/latest/userguide/kb-how-it-works.html)
- [What are Embeddings in Machine Learning? - AWS](https://aws.amazon.com/what-is/embeddings-in-machine-learning/)
- [Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)

---

# Próximo Capítulo

No próximo capítulo será apresentado o conceito de:

## Context Window

Arquivo planejado: `chapters/08-context-window.md`.

Você aprenderá:

- o que é context window;
- como ela se relaciona com tokens;
- por que ela limita o que o modelo consegue considerar;
- como RAG e resumo ajudam a lidar com contextos longos;
- como esse conceito aparece na certificação.

---

**Fim do Capítulo 7**
