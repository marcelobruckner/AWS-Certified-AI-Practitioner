# AGENTS.md

## Objetivo do repositório

Este repositório contém um guia de estudos em português para a certificação **AWS Certified AI Practitioner (AIF-C01)**.

O material deve evoluir como um guia completo e progressivo, com capítulos conceituais, resumos dos serviços AWS de AI/ML, laboratórios, questões comentadas, simulados, glossário e referências.

## Idioma e estilo

- Escrever o conteúdo principal em português do Brasil.
- Manter termos técnicos em inglês quando forem os termos cobrados pela AWS ou usados amplamente na documentação oficial, por exemplo: `Machine Learning`, `Deep Learning`, `Foundation Models`, `Prompt Engineering`, `Fine-tuning`, `RAG`, `Tokens`, `Embeddings`.
- Explicar conceitos com linguagem didática, progressiva e prática.
- Priorizar exemplos úteis para desenvolvedores, arquitetos, profissionais cloud, DevOps e pessoas estudando para certificação.
- Evitar tradução forçada de nomes de serviços AWS.
- Não usar emojis em títulos, tabelas, exemplos, chamadas de atenção ou qualquer outro conteúdo do projeto.

## Estrutura planejada

A estrutura pública planejada está descrita no `README.md` e no `SUMMARY.md`.

Estrutura alvo:

```text
README.md
SUMMARY.md
LICENSE
chapters/
services/
labs/
practice-exams/
glossary.md
references.md
```

Nem todos os arquivos citados no `README.md` e no `SUMMARY.md` existem ainda. Trate esses documentos também como roadmap do repositório.

## Estado atual observado

No momento da criação deste arquivo, a estrutura real contém:

```text
README.md
SUMMARY.md
chapters/01-ia-machine-learning-deep-learning.md
```

Também há mudanças locais não versionadas relacionadas à migração da estrutura antiga:

- remoção de `planejamento.md`;
- remoção da pasta antiga `conceitos/`;
- criação de `SUMMARY.md`;
- criação da pasta `chapters/`;
- reestruturação de `README.md`.

Não reverta essas mudanças sem pedido explícito do usuário.

## Padrão para capítulos

Novos capítulos em `chapters/` devem seguir, sempre que fizer sentido, esta estrutura:

- Objetivos de aprendizagem
- Pré-requisitos
- Introdução
- Conceitos fundamentais
- Como funciona
- Exemplos do mundo real
- Exemplos usando AWS
- Exemplos relacionados ao desenvolvimento de software
- Quando utilizar
- Quando não utilizar
- Comparações importantes
- Pegadinhas da certificação
- Erros comuns
- Questões comentadas
- Resumo
- Glossário do capítulo
- Referências

O padrão pode ser ajustado quando um tema não justificar todas as seções, mas a experiência de leitura deve continuar consistente.

## Padrão para serviços AWS

Arquivos em `services/` devem responder objetivamente:

- O que o serviço faz?
- Quando usar?
- Quando não usar?
- Quais serviços AWS podem ser confundidos com ele?
- Quais cenários aparecem com frequência na certificação?
- Quais limitações ou cuidados são relevantes?
- Como ele se relaciona com Amazon Bedrock, Amazon SageMaker, Amazon Q ou outros serviços de AI/ML?

## Validação de informações

Informações sobre formato da prova, domínios, pesos, serviços AWS, recursos de serviços e nomes oficiais podem mudar.

Ao criar ou revisar conteúdo factual sobre AWS:

- validar informações atuais em fontes oficiais da AWS sempre que houver dúvida ou risco de desatualização;
- preferir AWS Documentation, AWS Certification Exam Guide, AWS Skill Builder e páginas oficiais dos serviços;
- indicar quando uma informação foi inferida a partir de documentação;
- evitar afirmar detalhes de preço, disponibilidade regional ou limites técnicos sem validação recente.

## Formato da prova

Quando mencionar a prova AIF-C01, manter coerência com os dados oficiais atualmente usados no projeto:

- 65 questões;
- 50 questões pontuadas e 15 não pontuadas;
- 90 minutos;
- nota mínima de aprovação: 700 de 1000;
- nível Foundational;
- tipos de questão: múltipla escolha, múltipla resposta, ordenação e associação.

Domínios:

- Fundamentos de IA e Machine Learning: 20%;
- Fundamentos de IA Generativa: 24%;
- Aplicações de Foundation Models: 28%;
- IA Responsável: 14%;
- Segurança, Compliance e Governança: 14%.

## Commits e versionamento

- Mensagens de commit devem ser sempre escritas em português.
- Antes de commitar, revisar `git status --short` e garantir que apenas mudanças intencionais estejam incluídas.
- Não incluir mudanças não relacionadas ao pedido atual.
- Se houver mudanças locais feitas pelo usuário, trabalhar com elas e não revertê-las sem autorização explícita.
- Quando o usuário pedir para versionar, criar commit local com mensagem objetiva em português.
- Para push remoto, usar `origin main` salvo se o usuário indicar outra branch.

## Cuidados operacionais

- Não apagar arquivos de estudo, capítulos, resumos ou planejamento sem pedido claro.
- Se um arquivo citado no `README.md` ou `SUMMARY.md` ainda não existir, trate-o como item planejado, não como erro automático.
- Ao expandir o guia, manter links internos coerentes com os arquivos reais.
- Ao reorganizar pastas, atualizar `README.md` e `SUMMARY.md` na mesma alteração.
- Evitar conteúdo genérico demais: o foco é preparação prática para a AWS Certified AI Practitioner.
