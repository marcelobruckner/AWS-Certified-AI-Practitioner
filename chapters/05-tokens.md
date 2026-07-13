# Capítulo 5 — Tokens

---

# Objetivos de Aprendizagem

Ao concluir este capítulo, você será capaz de:

- compreender o que são tokens;
- explicar por que LLMs e Foundation Models processam texto como tokens;
- diferenciar tokens de palavras, caracteres e frases;
- entender como tokens impactam custo, latência e tamanho de contexto;
- reconhecer a diferença entre tokens de entrada e tokens de saída;
- entender por que prompts longos exigem mais atenção em aplicações generativas;
- associar tokens a Amazon Bedrock, LLMs e IA Generativa na certificação AWS Certified AI Practitioner (AIF-C01);
- evitar erros comuns em cenários de prova envolvendo contexto, custo e limites.

---

# Pré-requisitos

Antes deste capítulo, é recomendado compreender:

- o que é IA Generativa;
- o que são Large Language Models (LLMs);
- o que são Foundation Models;
- o que é prompt;
- o que é inferência;
- o que é context window em visão geral.

Os capítulos anteriores apresentam esses conceitos.

---

# Introdução

Quando uma pessoa lê um texto, ela pensa em palavras, frases e parágrafos.

Modelos de linguagem não trabalham exatamente assim.

LLMs e muitos Foundation Models processam texto em unidades chamadas **tokens**.

Tokens são pedaços de texto usados pelo modelo para representar, interpretar e gerar linguagem.

Um token pode ser:

- uma palavra inteira;
- parte de uma palavra;
- um número;
- um sinal de pontuação;
- um espaço;
- um símbolo;
- parte de um comando;
- parte de um trecho de código.

O ponto central é:

> Tokens são as unidades que modelos de linguagem usam para processar entrada e gerar saída.

Entender tokens é essencial porque eles afetam:

- tamanho máximo do prompt;
- tamanho máximo da resposta;
- custo;
- latência;
- capacidade de lidar com documentos longos;
- arquitetura de RAG;
- escolha do modelo;
- qualidade da experiência do usuário.

---

# Conceitos Fundamentais

# O que é um Token?

Um token é uma unidade de texto usada por um modelo.

Ele não é necessariamente igual a uma palavra.

Exemplo simples:

```text
Texto:
Amazon Bedrock usa Foundation Models.

Tokens aproximados:
Amazon | Bedrock | usa | Foundation | Models | .
```

Em outros casos, uma palavra pode ser quebrada em mais de um token.

Exemplo conceitual:

```text
Texto:
tokenização

Tokens possíveis:
token | ização
```

Isso varia conforme o tokenizer usado pelo modelo.

Tokenizer é o componente responsável por dividir o texto em tokens.

---

# Token não é Palavra

Uma palavra pode corresponder a um token, vários tokens ou parte de um token.

Exemplo:

| Texto | Possível tokenização |
|-------|----------------------|
| AWS | AWS |
| Bedrock | Bedrock |
| certificação | `certific` + `ação` |
| AIF-C01 | `AIF` + `-` + `C` + `01` |
| user_id | `user` + `_` + `id` |

Essa tabela é conceitual.

Cada modelo pode dividir o texto de maneira diferente.

O importante para a prova é entender que:

- tokens não são exatamente palavras;
- tokens dependem do tokenizer do modelo;
- diferentes modelos podem contar tokens de maneiras diferentes;
- texto maior geralmente significa mais tokens.

---

# Token não é Caractere

Um token também não é igual a um caractere.

Exemplo:

```text
Texto:
IA

Caracteres:
I | A

Tokens possíveis:
IA
```

Outro exemplo:

```text
Texto:
Amazon Bedrock

Caracteres:
A | m | a | z | o | n | espaço | B | e | d | r | o | c | k

Tokens possíveis:
Amazon | Bedrock
```

Para estimativas simples, é comum pensar que textos maiores usam mais tokens, mas não há conversão perfeita entre caracteres, palavras e tokens.

---

# Por que Modelos Usam Tokens?

Modelos de Machine Learning trabalham com números.

Texto puro precisa ser transformado em uma representação numérica antes de ser processado.

Fluxo simplificado:

```text
Texto

↓

Tokenização

↓

Tokens

↓

Representação numérica

↓

Modelo

↓

Resposta
```

O modelo não "lê" texto como uma pessoa.

Ele processa representações numéricas associadas aos tokens.

---

# Tokenizer

Tokenizer é o componente que transforma texto em tokens.

Ele define como o texto será dividido.

Exemplo:

```text
Entrada:
Explique Amazon Bedrock.

Tokenizer:
Explique | Amazon | Bedrock | .
```

Depois disso, esses tokens são convertidos em IDs numéricos.

Exemplo conceitual:

```text
Explique -> 8452
Amazon   -> 3921
Bedrock  -> 18044
.        -> 13
```

Os números acima são apenas ilustrativos.

Cada modelo possui seu próprio vocabulário e tokenizer.

---

# Vocabulário do Modelo

O vocabulário é o conjunto de tokens que o modelo conhece.

Ele pode incluir:

- palavras comuns;
- partes de palavras;
- pontuação;
- números;
- espaços;
- símbolos;
- trechos comuns de código;
- tokens especiais.

Quando uma palavra não está diretamente no vocabulário, o tokenizer pode dividi-la em partes menores.

Exemplo:

```text
Palavra incomum:
hiperpersonalização

Tokens possíveis:
hiper | personal | ização
```

Isso permite que o modelo lide com palavras novas ou raras usando combinações de tokens conhecidos.

---

# Tokens de Entrada e Tokens de Saída

Em aplicações generativas, é comum separar:

- tokens de entrada;
- tokens de saída.

# Tokens de Entrada

Tokens de entrada são os tokens enviados ao modelo.

Eles podem incluir:

- pergunta do usuário;
- instruções do sistema;
- histórico da conversa;
- exemplos;
- documentos recuperados por RAG;
- contexto adicional;
- metadados;
- formato esperado da resposta.

Exemplo:

```text
Você é um assistente de certificação AWS.
Explique tokens em linguagem simples.
Use uma tabela curta.
```

Todo esse texto entra no modelo como tokens de entrada.

---

# Tokens de Saída

Tokens de saída são os tokens gerados pelo modelo na resposta.

Exemplo:

```text
Tokens são unidades de texto processadas por modelos de linguagem.
```

Essa resposta também é composta por tokens.

Em muitos serviços de IA Generativa, tanto entrada quanto saída podem influenciar custo, latência e limites.

Não memorize preços.

Consulte sempre a documentação oficial do serviço e do modelo usado.

---

# Como Tokens Afetam Custo

Muitos serviços de Foundation Models consideram uso em tokens.

Em geral:

- prompts maiores usam mais tokens de entrada;
- respostas maiores usam mais tokens de saída;
- mais tokens tendem a aumentar custo;
- diferentes modelos podem ter preços diferentes;
- tokens de entrada e saída podem ter valores diferentes dependendo do serviço e do modelo.

Exemplo conceitual:

```text
Prompt curto

↓

Menos tokens de entrada

↓

Menor custo relativo
```

```text
Prompt longo + documentos grandes + resposta longa

↓

Mais tokens de entrada e saída

↓

Maior custo relativo
```

Para a prova, a associação importante é:

```text
Mais tokens

↓

Mais processamento

↓

Maior impacto em custo e latência
```

---

# Como Tokens Afetam Latência

Latência é o tempo que a aplicação leva para receber resposta.

Tokens impactam latência porque:

- prompts maiores levam mais tempo para serem processados;
- respostas maiores levam mais tempo para serem geradas;
- modelos maiores podem responder mais lentamente;
- RAG pode adicionar mais contexto ao prompt;
- agentes podem executar várias chamadas ao modelo.

Exemplo:

```text
Pergunta curta:
Explique tokens.

↓

Menos contexto

↓

Resposta tende a ser mais rápida
```

```text
Pergunta com 40 páginas de documentação:
Resuma tudo e compare com a política interna.

↓

Muito contexto

↓

Resposta tende a ser mais lenta
```

Na prática, arquitetura e escolha do modelo também influenciam.

---

# Como Tokens Afetam Context Window

Context window é a quantidade máxima de tokens que o modelo consegue considerar em uma interação.

Ela inclui:

- instruções;
- prompt;
- histórico;
- documentos;
- exemplos;
- resposta gerada.

Exemplo conceitual:

```text
Context window disponível

↓

Instruções do sistema
+
Pergunta do usuário
+
Histórico da conversa
+
Documentos recuperados
+
Resposta gerada
```

Se o conteúdo excede a context window, a aplicação precisa lidar com isso.

Estratégias comuns:

- resumir conteúdo;
- dividir documentos em partes;
- usar RAG;
- recuperar apenas trechos relevantes;
- limitar histórico da conversa;
- escolher modelo com maior context window;
- reduzir tamanho da resposta esperada.

O capítulo 8 será dedicado a Context Window.

---

# Exemplo Simples de Contagem

Considere o prompt:

```text
Explique IA Generativa em uma frase.
```

Uma tokenização conceitual poderia ser:

```text
Explique | IA | Generativa | em | uma | frase | .
```

Isso resultaria em 7 tokens nesse exemplo simplificado.

Mas essa contagem não é garantida.

Outro modelo poderia quebrar "Generativa" de outra forma.

Por isso, em projetos reais, a contagem deve ser feita com o tokenizer ou ferramenta compatível com o modelo usado.

---

# Exemplo com Código

Tokens também aparecem em código.

Exemplo:

```java
public String hello() {
    return "Hello";
}
```

O tokenizer pode dividir esse trecho em tokens como:

```text
public | String | hello | ( | ) | { | return | " | Hello | " | ; | }
```

Em código, símbolos e pontuação podem consumir tokens.

Isso é relevante para assistentes de desenvolvimento, revisão de código e análise de logs.

---

# Exemplo com JSON

Dados estruturados em JSON também viram tokens.

Exemplo:

```json
{
  "servico": "Amazon Bedrock",
  "uso": "IA Generativa"
}
```

Possíveis tokens incluem:

```text
{ | " | servico | " | : | " | Amazon | Bedrock | " | , | " | uso | " | : | " | IA | Generativa | " | }
```

JSON muito verboso pode aumentar bastante a quantidade de tokens.

Em aplicações reais, vale enviar apenas os campos necessários ao modelo.

---

# Tokens e Idiomas

A quantidade de tokens pode variar conforme o idioma.

Alguns idiomas, palavras compostas, acentos e estruturas linguísticas podem ser divididos de maneira diferente.

Exemplo:

```text
certificação
certification
certificacion
```

Cada uma dessas palavras pode ter tokenização diferente.

Para aplicações em português, sempre teste o modelo com exemplos reais no idioma esperado.

Na certificação, o ponto importante é:

- tokenização depende do modelo;
- não existe equivalência perfeita entre palavra e token;
- idioma pode influenciar a quantidade de tokens.

---

# Tokens Especiais

Além de texto comum, modelos podem usar tokens especiais.

Exemplos conceituais:

- início de texto;
- fim de texto;
- separador;
- mensagem do sistema;
- mensagem do usuário;
- mensagem do assistente;
- marcador de função;
- máscara;
- padding.

Esses tokens ajudam o modelo ou a aplicação a entender estrutura e controle.

Em APIs gerenciadas, muitos detalhes ficam abstraídos.

Mesmo assim, é útil saber que nem todos os tokens correspondem diretamente a palavras visíveis.

---

# Como Funciona em uma Aplicação

Uma aplicação que usa LLM ou Foundation Model normalmente passa por este fluxo:

```text
Usuário envia mensagem

↓

Aplicação monta prompt

↓

Texto é convertido em tokens

↓

Modelo processa tokens

↓

Modelo gera tokens de saída

↓

Tokens são convertidos em texto

↓

Usuário recebe resposta
```

O usuário vê texto.

O modelo trabalha com tokens.

---

# Exemplo do Mundo Real

Imagine uma empresa que cria um assistente para responder dúvidas sobre benefícios corporativos.

O usuário pergunta:

```text
Tenho direito a reembolso de academia?
```

A aplicação pode montar um prompt maior:

```text
Você é um assistente de RH.
Responda apenas com base na política abaixo.

Política:
Colaboradores em regime CLT têm direito a reembolso mensal de academia até o limite definido pelo plano de benefícios.

Pergunta:
Tenho direito a reembolso de academia?
```

Mesmo que a pergunta do usuário seja curta, o prompt final enviado ao modelo é maior.

Ele inclui:

- instrução;
- política;
- pergunta;
- formato implícito de resposta.

Tudo isso vira tokens.

Se a aplicação recuperar muitas políticas, o número de tokens cresce rapidamente.

---

# Exemplo Relacionado ao Desenvolvimento de Software

Uma equipe usa um assistente para analisar erros em logs.

Prompt curto:

```text
Explique este erro:
Timeout waiting for connection from pool
```

Prompt longo:

```text
Você é um especialista em Java, Spring Boot e PostgreSQL.
Analise os logs abaixo, considere o contexto da aplicação, explique hipóteses prováveis e gere uma checklist.

Logs:
... milhares de linhas ...
```

O segundo prompt pode ser muito mais útil, mas também usa muito mais tokens.

Isso impacta:

- custo;
- latência;
- tamanho máximo aceito pelo modelo;
- quantidade de informação realmente relevante;
- risco de inserir ruído.

Uma boa aplicação não envia tudo automaticamente.

Ela seleciona o contexto mais relevante.

---

# Exemplos Usando AWS

# Amazon Bedrock

Amazon Bedrock permite construir aplicações de IA Generativa usando Foundation Models gerenciados.

Ao chamar modelos, a aplicação envia entrada para o modelo e recebe saída gerada.

Em cenários com texto, essa entrada e saída são processadas em tokens.

Fluxo conceitual:

```text
Aplicação

↓

Prompt

↓

Tokens de entrada

↓

Amazon Bedrock

↓

Foundation Model

↓

Tokens de saída

↓

Resposta
```

Na prática, cada modelo pode ter:

- limites próprios;
- formas próprias de contagem;
- custo próprio;
- latência própria;
- tamanho máximo de entrada e saída.

Por isso, detalhes específicos devem ser consultados na documentação oficial do Amazon Bedrock e do modelo escolhido.

---

# RAG no Amazon Bedrock

Em uma arquitetura RAG, a aplicação recupera documentos relevantes e adiciona trechos ao contexto enviado ao modelo.

Isso aumenta a quantidade de tokens de entrada.

Fluxo:

```text
Pergunta do usuário

↓

Busca em base de conhecimento

↓

Trechos relevantes

↓

Prompt final

↓

Foundation Model
```

O desafio é equilibrar:

- quantidade de contexto;
- relevância dos trechos;
- custo;
- latência;
- qualidade da resposta;
- limite de contexto.

Enviar documentos demais pode piorar a resposta e aumentar custo.

Enviar documentos de menos pode deixar faltar informação importante.

---

# Escolha de Modelo

Na AWS, diferentes modelos podem ter capacidades e limites diferentes.

Ao escolher um modelo, avalie:

- tamanho da context window;
- custo por uso;
- latência;
- qualidade;
- suporte ao idioma;
- modalidade;
- capacidade de seguir instruções;
- limite de saída;
- adequação ao caso de uso.

Para a certificação, não memorize números específicos.

Entenda a lógica:

```text
Mais tokens e modelo mais pesado

↓

Maior impacto potencial em custo e latência
```

---

# Quando se Preocupar com Tokens

Você deve se preocupar com tokens quando:

- o prompt é grande;
- a resposta esperada é longa;
- há histórico de conversa;
- há documentos recuperados por RAG;
- há muitos usuários;
- há chamadas frequentes;
- há necessidade de baixa latência;
- há orçamento limitado;
- a aplicação processa código, logs ou documentos longos;
- o modelo retorna respostas cortadas.

Exemplo:

```text
Chatbot simples de FAQ

↓

Poucos tokens por chamada
```

```text
Assistente jurídico lendo contratos completos

↓

Muitos tokens por chamada
```

---

# Quando Tokens não são o Principal Problema

Tokens são importantes, mas nem todo problema de IA Generativa é problema de token.

Às vezes o problema real é:

- prompt mal escrito;
- contexto irrelevante;
- modelo inadequado;
- falta de guardrails;
- falta de dados confiáveis;
- ausência de avaliação;
- permissões incorretas;
- arquitetura RAG ruim;
- expectativa errada sobre o modelo.

Não otimize apenas quantidade de tokens.

Otimize qualidade do contexto.

---

# Boas Práticas

# Seja objetivo no prompt

Prompts objetivos tendem a usar menos tokens e reduzir ambiguidade.

Exemplo ruim:

```text
Fale tudo que você sabe sobre este assunto.
```

Exemplo melhor:

```text
Explique tokens em até cinco tópicos, com foco em custo, latência e contexto.
```

---

# Envie apenas contexto relevante

Em vez de enviar um documento inteiro, envie os trechos mais importantes.

Isso é especialmente relevante em RAG.

```text
Documento completo

↓

Muitos tokens, mais ruído
```

```text
Trechos relevantes

↓

Menos tokens, mais foco
```

---

# Controle o tamanho da resposta

Se a resposta não precisa ser longa, diga isso no prompt.

Exemplo:

```text
Responda em no máximo 5 bullets.
```

Ou:

```text
Gere um resumo com até 120 palavras.
```

Isso ajuda a controlar tokens de saída.

---

# Gerencie histórico de conversa

Em chatbots, cada nova mensagem pode incluir parte do histórico.

Histórico longo aumenta tokens.

Estratégias:

- manter apenas mensagens recentes;
- resumir histórico antigo;
- armazenar fatos importantes;
- recuperar contexto sob demanda;
- evitar repetir instruções desnecessárias.

---

# Monitore uso

Aplicações em produção devem monitorar:

- tokens de entrada;
- tokens de saída;
- custo estimado;
- latência;
- erros por limite excedido;
- respostas truncadas;
- qualidade da resposta.

Sem monitoramento, é difícil controlar custo e experiência do usuário.

---

# Comparações Importantes

# Token versus Palavra

| Conceito | Explicação |
|----------|------------|
| Palavra | Unidade linguística percebida por humanos |
| Token | Unidade usada pelo modelo para processar texto |

Uma palavra pode virar um ou mais tokens.

---

# Token versus Caractere

| Conceito | Explicação |
|----------|------------|
| Caractere | Letra, número, símbolo ou espaço |
| Token | Parte de texto definida pelo tokenizer |

Um token pode conter vários caracteres.

---

# Tokens de Entrada versus Tokens de Saída

| Tipo | O que é |
|------|---------|
| Tokens de entrada | O que a aplicação envia ao modelo |
| Tokens de saída | O que o modelo gera como resposta |

Ambos podem impactar custo, latência e limites.

---

# Token versus Context Window

| Conceito | Explicação |
|----------|------------|
| Token | Unidade de processamento |
| Context Window | Quantidade máxima de tokens considerada pelo modelo |

Context window é medida em tokens.

---

# Token versus Embedding

Token é uma unidade de texto.

Embedding é uma representação vetorial numérica.

Fluxo simplificado:

```text
Texto

↓

Tokens

↓

Representações numéricas

↓

Modelo
```

Embeddings serão estudados no próximo capítulo.

---

# Como a AWS Cobra esse Tema

A AWS pode cobrar tokens de forma indireta, dentro de cenários sobre IA Generativa, LLMs, Foundation Models e Amazon Bedrock.

O enunciado pode mencionar:

- prompt grande;
- documentos longos;
- custo alto;
- resposta lenta;
- limite de contexto;
- respostas truncadas;
- RAG com muitos documentos;
- necessidade de otimizar uso do modelo;
- tokens de entrada e saída.

## Exemplo 1

> Uma empresa percebe aumento de custo em uma aplicação generativa depois de passar a enviar documentos completos em cada prompt.

Palavras-chave:

- documentos completos;
- cada prompt;
- aumento de custo.

Interpretação:

**Mais tokens de entrada estão sendo enviados ao modelo.**

Solução provável:

- recuperar apenas trechos relevantes;
- resumir documentos;
- otimizar RAG;
- reduzir contexto desnecessário.

---

## Exemplo 2

> Um chatbot está ficando lento porque envia todo o histórico da conversa a cada interação.

Palavras-chave:

- todo o histórico;
- cada interação;
- lento.

Interpretação:

**O número de tokens de entrada cresce com o histórico.**

Solução provável:

- resumir histórico;
- limitar mensagens anteriores;
- manter apenas contexto relevante.

---

## Exemplo 3

> Uma aplicação retorna respostas incompletas ao tentar resumir documentos muito longos.

Palavras-chave:

- documentos muito longos;
- respostas incompletas;
- resumir.

Interpretação:

Pode haver limite de contexto ou limite de saída.

Solução provável:

- dividir documento em partes;
- resumir por etapas;
- usar RAG;
- escolher modelo com context window adequada;
- controlar tamanho da resposta.

---

# Pegadinhas da Certificação

## Pegadinha 1

**"Token é sempre uma palavra."**

Falso.

Um token pode ser palavra, parte de palavra, pontuação, espaço, número ou símbolo.

---

## Pegadinha 2

**"Enviar mais contexto sempre melhora a resposta."**

Falso.

Contexto irrelevante pode aumentar custo, latência e ruído.

O ideal é enviar contexto relevante.

---

## Pegadinha 3

**"Tokens só afetam custo."**

Falso.

Tokens afetam custo, latência, context window, limites e desenho da aplicação.

---

## Pegadinha 4

**"Tokens de saída não importam."**

Falso.

Respostas longas também consomem tokens, podem aumentar latência e podem impactar custo.

---

## Pegadinha 5

**"Todos os modelos contam tokens do mesmo jeito."**

Falso.

Tokenização pode variar entre modelos.

---

# Erros Comuns

## Erro 1 — Enviar documentos inteiros sem necessidade

Enviar todo o documento pode parecer mais seguro, mas pode:

- aumentar custo;
- aumentar latência;
- exceder limite de contexto;
- incluir informações irrelevantes;
- piorar a qualidade da resposta.

---

## Erro 2 — Não limitar tamanho da resposta

Se o modelo pode responder livremente, ele pode gerar mais tokens do que o necessário.

Quando fizer sentido, defina formato e tamanho.

Exemplo:

```text
Responda em até 5 tópicos.
```

---

## Erro 3 — Ignorar histórico em chatbots

Chatbots podem acumular histórico.

Se todo o histórico for enviado sempre, o consumo de tokens cresce ao longo da conversa.

---

## Erro 4 — Confundir limite de tokens com qualidade

Um modelo com context window maior não é automaticamente melhor para todo problema.

Ele apenas consegue considerar mais tokens.

Qualidade depende também de:

- modelo;
- prompt;
- contexto;
- avaliação;
- dados;
- tarefa;
- guardrails.

---

# Questões Comentadas

## Questão 1 — Nível Fácil

O que é um token em modelos de linguagem?

A) Sempre uma palavra completa.

B) Uma unidade de texto processada pelo modelo.

C) Um usuário autenticado no sistema.

D) Uma chave de criptografia.

### Resposta

**Alternativa B.**

Token é uma unidade de texto processada pelo modelo.

Ele pode ser palavra, parte de palavra, pontuação, número ou símbolo.

---

## Questão 2 — Nível Intermediário

Uma aplicação de IA Generativa ficou mais cara após passar a enviar documentos completos no prompt.

Qual é a explicação mais provável?

A) O número de tokens de entrada aumentou.

B) O banco de dados relacional ficou indisponível.

C) A VPC passou a usar mais sub-redes.

D) O modelo deixou de usar inferência.

### Resposta

**Alternativa A.**

Documentos completos aumentam o tamanho do prompt.

Isso aumenta a quantidade de tokens de entrada enviados ao modelo.

---

## Questão 3 — Nível AWS

Uma equipe usa Amazon Bedrock para criar um chatbot. Com o tempo, as respostas ficam mais lentas porque a aplicação envia todo o histórico da conversa em cada chamada.

Qual ação pode ajudar?

A) Remover IAM da aplicação.

B) Resumir ou limitar o histórico enviado ao modelo.

C) Usar Amazon Route 53 para reduzir tokens.

D) Trocar o banco relacional por armazenamento em bloco.

### Resposta

**Alternativa B.**

Histórico completo aumenta tokens de entrada.

Resumir ou limitar histórico reduz contexto desnecessário e pode melhorar custo e latência.

---

## Questão 4 — Nível Certificação

Uma aplicação precisa responder perguntas com base em documentos longos, mas não deve enviar todos os documentos completos ao modelo.

Qual abordagem é mais adequada?

A) RAG para recuperar trechos relevantes.

B) Regra fixa com if/else.

C) NAT Gateway.

D) Excluir o prompt.

### Resposta

**Alternativa A.**

RAG permite recuperar trechos relevantes e enviá-los como contexto ao modelo.

Isso ajuda a controlar tokens e melhora a relevância da resposta.

---

## Questão 5 — Nível AWS

Uma empresa quer reduzir a quantidade de tokens de saída de uma aplicação generativa.

Qual instrução no prompt ajuda mais diretamente?

A) "Responda em até 5 tópicos objetivos."

B) "Use qualquer tamanho de resposta."

C) "Ignore todas as restrições."

D) "Adicione todo o histórico da conversa."

### Resposta

**Alternativa A.**

Definir limite e formato de resposta ajuda a controlar tokens de saída.

---

# Checklist de Revisão

Antes de avançar para o próximo capítulo, verifique se você consegue responder às perguntas abaixo sem consultar o material.

## Conceito

- [ ] Sei definir token.
- [ ] Sei explicar por que token não é sempre uma palavra.
- [ ] Sei explicar a diferença entre token, palavra e caractere.
- [ ] Sei explicar o papel do tokenizer.

---

## Aplicação

- [ ] Sei diferenciar tokens de entrada e tokens de saída.
- [ ] Sei explicar como tokens impactam custo.
- [ ] Sei explicar como tokens impactam latência.
- [ ] Sei explicar como tokens se relacionam com context window.

---

## AWS

- [ ] Sei associar tokens a aplicações com Amazon Bedrock.
- [ ] Sei explicar por que detalhes de preço e limite devem ser consultados na documentação oficial.
- [ ] Sei reconhecer cenários em que RAG ajuda a reduzir contexto desnecessário.

---

## Boas práticas

- [ ] Sei explicar por que não enviar contexto irrelevante.
- [ ] Sei limitar tamanho de resposta no prompt.
- [ ] Sei reconhecer riscos de histórico muito longo em chatbots.
- [ ] Sei explicar por que mais tokens nem sempre significam melhor resposta.

---

# Resumo do Capítulo

Tokens são unidades de texto usadas por modelos de linguagem para processar entrada e gerar saída.

Eles não são necessariamente palavras ou caracteres.

Um token pode ser uma palavra inteira, parte de uma palavra, pontuação, número, espaço, símbolo ou parte de código.

Tokens importam porque afetam custo, latência, context window, limites e desenho da aplicação.

Em aplicações com Amazon Bedrock e Foundation Models, prompts longos, documentos grandes, histórico de conversa e respostas extensas podem aumentar o uso de tokens.

Boas práticas incluem enviar apenas contexto relevante, controlar tamanho da resposta, resumir histórico, usar RAG de forma eficiente e monitorar tokens de entrada e saída.

---

# Principais Pontos para a Certificação

| Cenário | Pense em |
|---------|----------|
| Unidade processada por LLM | Token |
| Texto enviado ao modelo | Tokens de entrada |
| Texto gerado pelo modelo | Tokens de saída |
| Prompt longo | Mais tokens de entrada |
| Resposta longa | Mais tokens de saída |
| Custo e latência altos | Verificar uso de tokens |
| Documento muito longo | Dividir, resumir ou usar RAG |
| Histórico de conversa grande | Resumir ou limitar histórico |
| Limite do que o modelo considera | Context window |

---

# Em uma Frase

> **Tokens são as unidades de texto que LLMs e Foundation Models processam, e entender seu uso é essencial para controlar contexto, custo, latência e qualidade em aplicações de IA Generativa.**

---

# Glossário

## Token

Unidade de texto processada por um modelo de linguagem.

---

## Tokenizer

Componente que divide texto em tokens.

---

## Tokens de entrada

Tokens enviados ao modelo no prompt, incluindo instruções, pergunta, contexto e documentos.

---

## Tokens de saída

Tokens gerados pelo modelo como resposta.

---

## Context Window

Quantidade máxima de tokens que o modelo consegue considerar em uma interação.

---

## Prompt

Instrução enviada ao modelo para orientar a resposta.

---

## RAG

Retrieval-Augmented Generation. Arquitetura que recupera informações relevantes e as envia como contexto ao modelo.

---

## Embedding

Representação vetorial numérica de texto, imagem ou outro dado. Será estudado no próximo capítulo.

---

# Referências

A elaboração deste capítulo foi baseada nas seguintes referências oficiais:

- [AWS Certified AI Practitioner (AIF-C01) Exam Guide](https://docs.aws.amazon.com/pt_br/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html)
- [What is LLM? - Large Language Models Explained - AWS](https://aws.amazon.com/what-is/large-language-model/)
- [What is Generative AI? - AWS](https://aws.amazon.com/what-is/generative-ai/)
- [Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)
- [Supported foundation models in Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/models-supported.html)
- [Amazon Bedrock pricing](https://aws.amazon.com/bedrock/pricing/)
- [Amazon Bedrock quotas](https://docs.aws.amazon.com/bedrock/latest/userguide/quotas.html)

---

# Próximo Capítulo

No próximo capítulo será apresentado o conceito de:

## Embeddings

Arquivo planejado: `chapters/06-embeddings.md`.

Você aprenderá:

- o que são embeddings;
- como textos podem ser representados como vetores;
- por que embeddings são importantes para busca semântica;
- como embeddings se relacionam com RAG;
- como esse conceito aparece na certificação.

---

**Fim do Capítulo 5**
