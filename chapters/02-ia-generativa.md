# Capítulo 2 — IA Generativa

---

# Objetivos de Aprendizagem

Ao concluir este capítulo, você será capaz de:

- compreender o conceito de IA Generativa;
- diferenciar IA tradicional, Machine Learning tradicional e IA Generativa;
- identificar os principais tipos de conteúdo que podem ser gerados;
- entender a relação entre IA Generativa, Deep Learning, Foundation Models e LLMs;
- reconhecer casos de uso comuns em empresas;
- identificar limitações, riscos e cuidados importantes;
- compreender como a AWS costuma cobrar IA Generativa na certificação AWS Certified AI Practitioner (AIF-C01).

---

# Pré-requisitos

Antes deste capítulo, é recomendado compreender:

- o que é Inteligência Artificial;
- o que é Machine Learning;
- o que é Deep Learning;
- a diferença entre treinamento e inferência.

Esses conceitos foram apresentados no capítulo anterior.

---

# Introdução

IA Generativa é uma das áreas mais importantes da Inteligência Artificial moderna.

Ela ficou popular por causa de ferramentas capazes de conversar, escrever textos, gerar imagens, resumir documentos, criar código, responder perguntas e auxiliar profissionais em tarefas do dia a dia.

Apesar da popularidade, é comum confundir IA Generativa com qualquer sistema de IA.

Nem toda IA é generativa.

Um sistema que classifica uma transação como fraude ou não fraude utiliza IA, mas não está criando conteúdo novo.

Um sistema que recomenda filmes utiliza IA, mas normalmente não está gerando um novo filme.

Já um sistema que escreve uma resposta, cria uma imagem, resume um contrato ou gera um trecho de código está usando IA Generativa.

O ponto central é:

> IA Generativa é usada para criar conteúdo novo a partir de padrões aprendidos durante o treinamento.

---

# Conceitos Fundamentais

# O que é IA Generativa?

IA Generativa, ou Generative AI, é um tipo de Inteligência Artificial capaz de criar novos conteúdos e ideias.

Esses conteúdos podem incluir:

- texto;
- conversas;
- imagens;
- vídeos;
- músicas;
- código;
- resumos;
- respostas a perguntas;
- dados sintéticos;
- estruturas ou propostas de design.

A IA Generativa aprende padrões a partir de grandes volumes de dados e usa esses padrões para produzir novas saídas.

Ela não apenas classifica uma entrada.

Ela gera uma nova resposta.

---

# Diferença entre IA e IA Generativa

Inteligência Artificial é o conceito mais amplo.

IA Generativa é um subconjunto da IA.

```text
Inteligência Artificial
│
├── Sistemas baseados em regras
│
├── Machine Learning
│   │
│   ├── Modelos preditivos
│   │
│   └── Deep Learning
│       │
│       └── IA Generativa
```

Essa hierarquia é importante para a prova.

Toda IA Generativa é IA.

Grande parte das aplicações modernas de IA Generativa usa Deep Learning.

Mas nem toda IA é IA Generativa.

---

# IA Tradicional versus IA Generativa

Em muitos cenários, a diferença principal está no tipo de saída.

## IA Tradicional

A IA tradicional costuma produzir uma decisão, classificação, previsão ou pontuação.

Exemplos:

- este e-mail é spam;
- esta imagem contém um cachorro;
- este cliente tem alta chance de cancelar;
- esta transação parece fraudulenta;
- este documento pertence à categoria jurídica.

Fluxo típico:

```text
Entrada

↓

Modelo

↓

Classificação ou predição
```

## IA Generativa

A IA Generativa produz novo conteúdo.

Exemplos:

- escrever uma resposta para um cliente;
- gerar um resumo de um documento;
- criar uma imagem a partir de uma descrição;
- transformar uma pergunta em uma consulta SQL;
- gerar um exemplo de código;
- criar uma explicação personalizada.

Fluxo típico:

```text
Prompt

↓

Modelo generativo

↓

Novo conteúdo
```

---

# Como Funciona

De forma simplificada, uma aplicação de IA Generativa possui quatro elementos principais.

```text
Entrada do usuário

↓

Prompt

↓

Foundation Model

↓

Resposta gerada
```

Vamos analisar cada parte.

---

## 1. Entrada do usuário

A entrada é o que o usuário deseja fazer.

Exemplos:

- "Resuma este contrato."
- "Explique este erro Java."
- "Crie uma mensagem para o cliente."
- "Gere uma imagem de um produto em fundo branco."
- "Liste riscos de segurança neste desenho de arquitetura."

---

## 2. Prompt

O prompt é a instrução enviada ao modelo.

Ele pode conter:

- a pergunta;
- o objetivo;
- o contexto;
- o formato esperado da resposta;
- restrições;
- exemplos;
- dados de apoio.

Exemplo simples:

```text
Explique IA Generativa em linguagem simples para uma pessoa que conhece AWS, mas não conhece Machine Learning.
```

Exemplo mais específico:

```text
Você é um instrutor de certificação AWS.
Explique a diferença entre Machine Learning tradicional e IA Generativa.
Use uma tabela com três linhas e linguagem objetiva.
```

Prompt Engineering será estudado em um capítulo próprio.

Neste momento, entenda apenas que a qualidade da instrução influencia diretamente a qualidade da resposta.

---

## 3. Foundation Model

Foundation Models são modelos grandes, treinados com amplo volume de dados e capazes de executar diferentes tipos de tarefa.

Eles podem ser usados como base para:

- geração de texto;
- chatbots;
- sumarização;
- classificação;
- extração de informações;
- geração de código;
- geração de imagens;
- respostas baseadas em contexto.

O capítulo 4 será dedicado a Foundation Models.

Neste capítulo, basta entender que muitas aplicações de IA Generativa usam Foundation Models como motor principal.

---

## 4. Resposta gerada

A saída é o conteúdo produzido pelo modelo.

Exemplo:

```text
Prompt:
Explique o que é IA Generativa em uma frase.

Resposta:
IA Generativa é um tipo de inteligência artificial capaz de criar novos conteúdos, como textos, imagens, código e respostas, a partir de padrões aprendidos em dados.
```

Essa resposta não foi recuperada de uma tabela fixa.

Ela foi gerada pelo modelo com base nos padrões aprendidos durante o treinamento e no contexto recebido no prompt.

---

# Exemplo do Mundo Real

Imagine uma central de atendimento.

Todos os dias, clientes enviam mensagens perguntando sobre:

- status de pedidos;
- troca de produtos;
- segunda via de boleto;
- problemas de entrega;
- políticas de garantia.

Uma abordagem tradicional poderia usar respostas prontas.

```text
Se pergunta contém "boleto"

↓

Enviar resposta padrão sobre segunda via
```

Essa abordagem funciona para perguntas simples, mas falha quando o cliente escreve de forma diferente ou mistura vários assuntos.

Com IA Generativa, a aplicação pode:

- interpretar a intenção do cliente;
- consultar dados relevantes;
- gerar uma resposta personalizada;
- manter tom adequado;
- resumir o atendimento para o operador humano.

Exemplo:

```text
Cliente:
Comprei ontem, mas o endereço saiu errado. Ainda consigo alterar?

IA Generativa:
Entendi. Como o pedido ainda está em processamento, é possível solicitar a alteração do endereço. Vou encaminhar sua solicitação para validação e confirmar se a transportadora ainda não recebeu o pacote.
```

A resposta foi criada para aquele contexto específico.

---

# Exemplo Relacionado ao Desenvolvimento de Software

Uma equipe de desenvolvimento mantém uma aplicação Java com microsserviços.

Durante um incidente, os logs mostram:

```text
Timeout waiting for connection from pool
```

Um sistema tradicional poderia apenas classificar o erro como "banco de dados".

Uma aplicação com IA Generativa poderia ajudar de forma mais ampla:

- resumir o erro;
- explicar possíveis causas;
- sugerir hipóteses;
- montar uma checklist de investigação;
- gerar uma mensagem para o canal de incidentes;
- propor uma consulta para verificar conexões abertas.

Exemplo de prompt:

```text
Analise o erro abaixo em uma aplicação Java com PostgreSQL.
Explique causas prováveis e sugira uma checklist de investigação.

Erro:
Timeout waiting for connection from pool
```

Esse tipo de uso é comum em assistentes de desenvolvimento, operações e suporte técnico.

---

# Exemplos Usando AWS

# Amazon Bedrock

Na AWS, o serviço mais importante para IA Generativa na certificação é o **Amazon Bedrock**.

Amazon Bedrock é um serviço gerenciado que fornece acesso a Foundation Models para criação e escala de aplicações de IA Generativa.

Com Bedrock, uma empresa pode construir aplicações como:

- chatbot corporativo;
- assistente de atendimento;
- sumarizador de documentos;
- gerador de respostas;
- extração de informações;
- assistente de código;
- aplicações com RAG;
- agentes para execução de tarefas.

Fluxo simplificado:

```text
Aplicação

↓

Prompt

↓

Amazon Bedrock

↓

Foundation Model

↓

Resposta
```

Para a prova, associe:

```text
IA Generativa + Foundation Models gerenciados + AWS

↓

Amazon Bedrock
```

---

# Amazon SageMaker AI

Amazon SageMaker AI aparece quando o cenário envolve construir, treinar, ajustar, implantar ou operar modelos próprios de Machine Learning.

Ele também pode ser usado em cenários avançados de IA, mas a prova costuma diferenciar:

| Cenário | Serviço mais provável |
|---------|------------------------|
| Usar Foundation Models gerenciados para GenAI | Amazon Bedrock |
| Treinar e implantar modelo próprio de ML | Amazon SageMaker AI |
| Criar solução generativa sem gerenciar infraestrutura de modelo | Amazon Bedrock |
| Controlar treinamento, algoritmo, dados e implantação de modelo próprio | Amazon SageMaker AI |

Essa distinção é uma das mais importantes para a certificação.

---

# Amazon Q

Amazon Q é uma família de assistentes generativos da AWS.

Na certificação, pense em Amazon Q quando o cenário mencionar assistente generativo para aumentar produtividade, responder perguntas, apoiar desenvolvimento ou ajudar usuários a interagir com informações e serviços.

Exemplos de associação:

- assistente para desenvolvedores;
- apoio para entender documentação e código;
- respostas baseadas em dados corporativos;
- produtividade em tarefas de trabalho.

Bedrock é a plataforma para construir aplicações generativas.

Amazon Q é um produto/assistente generativo pronto para casos de uso específicos.

---

# Quando Utilizar IA Generativa

Use IA Generativa quando o objetivo for criar, transformar, resumir ou adaptar conteúdo.

Exemplos:

- gerar texto;
- responder perguntas em linguagem natural;
- resumir documentos;
- criar imagens;
- gerar código;
- explicar erros;
- transformar conteúdo técnico em linguagem simples;
- criar rascunhos de e-mails;
- gerar ideias;
- extrair informações de documentos longos;
- criar assistentes conversacionais.

Palavras-chave comuns:

- gerar;
- criar;
- resumir;
- reescrever;
- conversar;
- responder em linguagem natural;
- produzir conteúdo;
- criar assistente;
- Foundation Model;
- prompt.

---

# Quando NÃO Utilizar IA Generativa

Evite IA Generativa quando:

- uma regra simples resolve o problema;
- o resultado precisa ser sempre exatamente igual;
- não há tolerância para respostas probabilísticas;
- o caso exige cálculo determinístico simples;
- o cenário é apenas classificação ou previsão tradicional;
- a resposta precisa vir exclusivamente de uma fonte autorizada sem risco de variação;
- não há estratégia para validação, segurança e governança.

Exemplos:

| Problema | Melhor abordagem |
|----------|------------------|
| Bloquear compra acima de limite fixo | Regra de negócio |
| Calcular imposto com fórmula conhecida | Sistema determinístico |
| Prever churn com dados históricos estruturados | Machine Learning |
| Classificar imagem de produto | Computer Vision / Deep Learning |
| Resumir contrato em linguagem simples | IA Generativa |
| Criar resposta personalizada ao cliente | IA Generativa |

---

# Comparações Importantes

# IA Generativa versus Machine Learning Tradicional

| Aspecto | Machine Learning tradicional | IA Generativa |
|---------|------------------------------|---------------|
| Saída comum | Classe, pontuação ou previsão | Novo conteúdo |
| Exemplo | Prever churn | Escrever resposta para cliente |
| Entrada comum | Dados estruturados ou eventos | Prompt, texto, imagem ou contexto |
| Resultado esperado | Decisão ou probabilidade | Texto, imagem, código, resumo |
| Serviço AWS típico | Amazon SageMaker AI | Amazon Bedrock |

---

# IA Generativa versus RAG

IA Generativa cria conteúdo.

RAG, ou Retrieval-Augmented Generation, é uma arquitetura que combina geração com recuperação de informações externas.

Exemplo sem RAG:

```text
Pergunta

↓

Modelo

↓

Resposta baseada no conhecimento do modelo
```

Exemplo com RAG:

```text
Pergunta

↓

Busca em documentos da empresa

↓

Contexto recuperado

↓

Modelo

↓

Resposta baseada nos documentos
```

RAG será estudado em capítulo próprio.

Por enquanto, lembre:

- IA Generativa é a capacidade de gerar conteúdo.
- RAG é uma forma de melhorar respostas usando dados externos.

---

# IA Generativa versus Fine-tuning

Fine-tuning é uma técnica de personalização de modelo.

Ele ajusta um modelo com dados específicos para melhorar comportamento em um domínio ou tarefa.

Não confunda:

- IA Generativa: categoria de aplicação/modelo que gera conteúdo.
- Fine-tuning: técnica para adaptar um modelo.
- RAG: técnica para fornecer contexto externo ao modelo.

---

# Limitações e Riscos

IA Generativa é poderosa, mas possui limitações importantes.

## Hallucinations

Hallucination ocorre quando o modelo gera uma resposta incorreta, inventada ou sem base suficiente, mas com aparência convincente.

Exemplo:

```text
Usuário:
Qual política interna permite aprovar despesas sem nota fiscal?

Modelo:
A política FIN-202 permite aprovação automática até R$ 500.
```

Se essa política não existir, a resposta é uma hallucination.

Esse tema será aprofundado no capítulo 10.

---

## Bias

Modelos podem refletir vieses presentes nos dados de treinamento ou no contexto recebido.

Isso pode gerar respostas injustas, incompletas ou inadequadas.

---

## Privacidade

Prompts podem conter dados sensíveis.

Exemplos:

- dados pessoais;
- informações financeiras;
- documentos internos;
- código proprietário;
- credenciais;
- informações de clientes.

Aplicações de IA Generativa precisam de controles de segurança, governança e proteção de dados.

---

## Custo e latência

Modelos generativos podem ter custo e latência maiores do que soluções determinísticas simples.

Antes de usar IA Generativa, avalie:

- volume de requisições;
- tamanho dos prompts;
- tamanho das respostas;
- modelo escolhido;
- necessidade de baixa latência;
- criticidade do caso de uso.

---

# IA Responsável em IA Generativa

IA Generativa deve ser usada com responsabilidade.

Cuidados importantes:

- validar respostas críticas;
- evitar exposição de dados sensíveis;
- usar controles de acesso;
- registrar e monitorar uso;
- aplicar filtros e guardrails;
- revisar respostas em cenários de alto impacto;
- informar limitações ao usuário;
- manter rastreabilidade quando necessário.

Na AWS, o tema aparece ligado a:

- segurança;
- privacidade;
- governança;
- transparência;
- explainability;
- fairness;
- human in the loop;
- guardrails.

Esses assuntos serão aprofundados em capítulos posteriores, mas já são relevantes desde o primeiro contato com IA Generativa.

---

# Como a AWS Cobra esse Tema

A AWS costuma apresentar cenários empresariais.

O candidato precisa identificar quando IA Generativa é adequada e qual serviço AWS faz mais sentido.

## Exemplo 1

> Uma empresa deseja criar um assistente que responda perguntas de clientes em linguagem natural.

Palavras-chave:

- assistente;
- linguagem natural;
- respostas geradas;
- cliente.

Resposta provável:

**IA Generativa com Amazon Bedrock.**

---

## Exemplo 2

> Uma empresa deseja treinar um modelo próprio para prever cancelamento de clientes usando dados históricos.

Palavras-chave:

- treinar modelo próprio;
- prever;
- dados históricos.

Resposta provável:

**Machine Learning com Amazon SageMaker AI.**

Não é o cenário principal de IA Generativa.

---

## Exemplo 3

> Uma empresa deseja resumir milhares de documentos jurídicos e responder perguntas sobre eles.

Palavras-chave:

- resumir;
- responder perguntas;
- documentos;
- linguagem natural.

Resposta provável:

**IA Generativa.**

Se as respostas precisarem se basear nos documentos da empresa, pense também em **RAG**.

---

# Pegadinhas da Certificação

## Pegadinha 1

**"Toda IA moderna é IA Generativa."**

Falso.

IA Generativa é uma parte da IA.

Sistemas de recomendação, classificação, previsão e detecção de fraude podem usar IA sem gerar novo conteúdo.

---

## Pegadinha 2

**"Amazon Bedrock é usado para qualquer Machine Learning na AWS."**

Falso.

Bedrock é o serviço central para construir aplicações de IA Generativa com Foundation Models gerenciados.

Para treinar, construir e implantar modelos próprios de ML, o serviço mais associado é Amazon SageMaker AI.

---

## Pegadinha 3

**"IA Generativa sempre responde corretamente."**

Falso.

Modelos generativos podem gerar respostas incorretas ou inventadas.

Por isso, validação, RAG, guardrails, revisão humana e governança são importantes.

---

## Pegadinha 4

**"Prompt Engineering substitui segurança."**

Falso.

Prompts ajudam a orientar o modelo, mas não substituem IAM, criptografia, controles de acesso, guardrails, monitoramento e boas práticas de governança.

---

# Erros Comuns

## Erro 1 — Usar IA Generativa para problemas determinísticos simples

Se uma regra resolve o problema de forma clara, previsível e auditável, não há motivo para usar IA Generativa.

Exemplo:

```text
Se idade >= 18, permitir cadastro.
```

Esse é um caso de regra de negócio.

---

## Erro 2 — Confundir resposta fluente com resposta correta

Modelos generativos podem escrever muito bem.

Isso não garante que a resposta esteja correta.

Sempre valide respostas em cenários críticos.

---

## Erro 3 — Enviar dados sensíveis sem controle

Aplicações generativas precisam tratar dados com cuidado.

Nunca presuma que qualquer conteúdo pode ser enviado ao modelo sem avaliação de segurança, privacidade e compliance.

---

## Erro 4 — Confundir Bedrock com SageMaker AI

Na prova:

- Bedrock aparece fortemente ligado a Foundation Models e aplicações generativas.
- SageMaker AI aparece fortemente ligado ao ciclo de vida de modelos próprios de ML.

---

# Questões Comentadas

## Questão 1 — Nível Fácil

Uma empresa deseja criar automaticamente respostas personalizadas para perguntas frequentes enviadas por clientes.

Qual abordagem é a mais adequada?

A) Sistema baseado em regras

B) IA Generativa

C) Banco de dados relacional

D) Balanceador de carga

### Resposta

**Alternativa B.**

O cenário envolve criação de respostas em linguagem natural.

Esse é um caso típico de IA Generativa.

---

## Questão 2 — Nível Intermediário

Uma empresa deseja prever quais clientes têm maior chance de cancelar o serviço nos próximos 30 dias, usando histórico de pagamentos, chamados e tempo de contrato.

Qual abordagem é mais adequada?

A) IA Generativa

B) Machine Learning tradicional

C) Prompt Engineering

D) Geração de imagem

### Resposta

**Alternativa B.**

O cenário envolve previsão baseada em dados históricos.

Esse é um caso típico de Machine Learning tradicional, não de IA Generativa.

---

## Questão 3 — Nível AWS

Uma empresa deseja criar uma aplicação que usa Foundation Models gerenciados para resumir documentos e responder perguntas em linguagem natural, sem gerenciar a infraestrutura dos modelos.

Qual serviço AWS é mais adequado?

A) Amazon EC2

B) Amazon Bedrock

C) Amazon S3 Glacier

D) AWS CloudTrail

### Resposta

**Alternativa B.**

Amazon Bedrock é o serviço gerenciado da AWS para construir e escalar aplicações de IA Generativa usando Foundation Models.

---

## Questão 4 — Nível AWS

Uma equipe de ciência de dados precisa construir, treinar e implantar um modelo próprio de Machine Learning para previsão de demanda.

Qual serviço AWS é mais diretamente associado a esse cenário?

A) Amazon Bedrock

B) Amazon SageMaker AI

C) Amazon Route 53

D) Amazon Polly

### Resposta

**Alternativa B.**

O cenário fala em construir, treinar e implantar modelo próprio.

Na AWS, isso aponta para Amazon SageMaker AI.

Bedrock seria mais adequado para uso de Foundation Models gerenciados em aplicações generativas.

---

# Checklist de Revisão

Antes de avançar para o próximo capítulo, verifique se você consegue responder às perguntas abaixo sem consultar o material.

## Conceito

- [ ] Sei definir IA Generativa.
- [ ] Sei explicar por que IA Generativa é um subconjunto de IA.
- [ ] Sei diferenciar IA Generativa de Machine Learning tradicional.
- [ ] Sei citar exemplos de conteúdo gerado por IA Generativa.

---

## AWS

- [ ] Sei associar IA Generativa com Amazon Bedrock.
- [ ] Sei diferenciar Amazon Bedrock de Amazon SageMaker AI.
- [ ] Sei explicar quando Amazon Q pode aparecer em cenários de assistente generativo.

---

## Riscos

- [ ] Sei explicar o que é hallucination.
- [ ] Sei citar riscos de privacidade em prompts.
- [ ] Sei explicar por que guardrails e validação são importantes.

---

# Resumo do Capítulo

IA Generativa é um tipo de Inteligência Artificial capaz de criar novos conteúdos, como textos, imagens, código, resumos e respostas em linguagem natural.

Diferente de muitos modelos tradicionais de Machine Learning, que produzem classificações ou previsões, modelos generativos produzem conteúdo novo a partir de padrões aprendidos durante o treinamento e do contexto recebido no prompt.

Na AWS, o serviço mais importante para construir aplicações generativas com Foundation Models gerenciados é o Amazon Bedrock.

Amazon SageMaker AI aparece com mais força em cenários de construção, treinamento e implantação de modelos próprios de Machine Learning.

IA Generativa também exige cuidados importantes, como validação de respostas, proteção de dados sensíveis, governança, guardrails e revisão humana em cenários críticos.

---

# Principais Pontos para a Certificação

| Cenário | Pense em |
|---------|----------|
| Gerar texto, resumo, imagem ou código | IA Generativa |
| Usar Foundation Models gerenciados na AWS | Amazon Bedrock |
| Criar chatbot generativo | Amazon Bedrock |
| Treinar modelo próprio com dados históricos | Amazon SageMaker AI |
| Assistente generativo pronto para produtividade | Amazon Q |
| Responder com base em documentos da empresa | IA Generativa + RAG |
| Reduzir respostas inadequadas | Guardrails |
| Resposta inventada ou incorreta | Hallucination |

---

# Em uma Frase

> **IA Generativa é a área da Inteligência Artificial que usa modelos capazes de criar novos conteúdos, e na AWS o serviço central para construir aplicações generativas com Foundation Models gerenciados é o Amazon Bedrock.**

---

# Glossário

## IA Generativa

Tipo de Inteligência Artificial capaz de criar novos conteúdos, como texto, imagem, código, áudio, vídeo ou respostas em linguagem natural.

---

## Prompt

Instrução enviada ao modelo para orientar a resposta gerada.

---

## Foundation Model

Modelo grande treinado em amplo volume de dados e capaz de executar diferentes tipos de tarefa.

---

## Large Language Model (LLM)

Modelo especializado em linguagem natural, capaz de processar e gerar texto.

---

## Hallucination

Resposta incorreta, inventada ou sem base suficiente, gerada de forma convincente por um modelo.

---

## RAG

Retrieval-Augmented Generation. Arquitetura que combina recuperação de informações externas com geração de respostas.

---

## Fine-tuning

Técnica de personalização que ajusta um modelo com dados específicos.

---

## Guardrails

Controles usados para reduzir saídas inadequadas, inseguras ou fora das políticas definidas.

---

# Referências

A elaboração deste capítulo foi baseada nas seguintes referências oficiais:

- [AWS Certified AI Practitioner (AIF-C01) Exam Guide](https://docs.aws.amazon.com/pt_br/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html)
- [What is Generative AI? - AWS](https://aws.amazon.com/what-is/generative-ai/)
- [Amazon Bedrock User Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)
- [Amazon Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html)
- [Amazon SageMaker AI Developer Guide](https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html)
- [Amazon Q Business User Guide](https://docs.aws.amazon.com/amazonq/latest/qbusiness-ug/what-is.html)
- [Amazon Q Developer User Guide](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html)

---

# Próximo Capítulo

No próximo capítulo será apresentado um dos principais componentes da IA Generativa:

## Large Language Models (LLMs)

Arquivo planejado: `chapters/03-llms.md`.

Você aprenderá:

- o que são Large Language Models;
- como LLMs processam linguagem;
- por que tokens são importantes;
- como LLMs se relacionam com Foundation Models;
- como a AWS cobra esse conceito na certificação.

---

**Fim do Capítulo 2**
