# Segundo Cérebro com Inteligência Artificial — Fundamentos dos LLMs

> Projeto prático para o desafio da DIO: estudo orientado por fontes com o Gemini Notebook, com perguntas, citações verificáveis e materiais de revisão.

## Tema e objetivo

**Tema:** fundamentos dos grandes modelos de linguagem (LLMs), com foco em tokenização, embeddings, arquitetura Transformer e mecanismos de atenção.

**Objetivo:** construir um segundo cérebro que explique, usando referências técnicas e educacionais selecionadas, como os modelos de linguagem processam textos e geram respostas, apresentando exemplos didáticos, fontes rastreáveis e limitações do material consultado.

## Notebook compartilhado

**[Abrir o notebook no Gemini Notebook](https://notebook.google.com/notebook/42ca70d9-0641-453b-b9ce-8b489e9a5237)**

> O acesso pelo link deve estar configurado como **"Qualquer pessoa com o link"**, na opção **Compartilhar**. O endereço foi informado pelo autor; a visibilidade pública ainda precisa ser verificada em uma sessão Google diferente.

## Fontes selecionadas e justificativa

Foram adicionadas ao notebook três fontes técnicas externas, em três formatos complementares:

| ID | Fonte efetivamente adicionada | Formato | Por que foi escolhida |
|:--:|---|---|---|
| **F1** | [Vaswani et al. (2017), *Attention Is All You Need*](https://arxiv.org/pdf/1706.03762) | Artigo científico em PDF | Trabalho que apresenta a arquitetura Transformer e fundamenta a descrição de self-attention, multi-head attention e codificação posicional. |
| **F2** | [Hugging Face — Documentação da biblioteca Transformers](https://huggingface.co/docs/transformers/index) | Documentação técnica web | Explica o ecossistema de implementação e uso de modelos Transformer, com documentação mantida pelo projeto. |
| **F3** | [3Blue1Brown — *Transformers, the tech behind LLMs*](https://www.youtube.com/watch?v=wjZofJX0v4M) | Aula em vídeo | Explicações visuais e exemplos sobre tokens, embeddings e mecanismos de processamento dos LLMs. |

**Critérios:** autoria identificável, pertinência temática, possibilidade de abrir a fonte original, complementaridade entre artigo, documentação e vídeo, e ausência de informações pessoais inseridas como fontes. Notas criadas durante o trabalho também podem ser contabilizadas na interface como fontes do notebook; a lista acima identifica as três referências externas originais.

## Diretriz de comportamento usada na conversa

A seguinte instrução foi enviada no **chat** do Gemini Notebook antes das perguntas. Ela orientou aquela conversa; não há confirmação de que tenha sido salva como uma configuração permanente do caderno.

> Atue como um especialista e tutor em Inteligência Artificial, com foco em LLMs, Transformers, tokens, embeddings e mecanismos de atenção. Responda em português brasileiro, de forma didática, utilizando exclusivamente as fontes deste notebook. Sempre apresente citações das fontes utilizadas e explique os conceitos com exemplos práticos. Se uma informação não estiver nas fontes, informe essa limitação em vez de inventar respostas.

## Perguntas, respostas e rastreabilidade

As respostas abaixo são **sínteses fiéis** das respostas recebidas no notebook, não transcrições integrais. As citações numeradas aparecem dentro do Gemini Notebook e nos prints, pois esses identificadores são locais à interface da ferramenta. Os links F1–F3 permitem localizar as fontes originais.

### Pergunta 1 — Transformers e self-attention

**Pergunta enviada:** "O que são Transformers e como o mecanismo de self-attention funciona? Explique de forma simples, com um exemplo prático, utilizando exclusivamente as fontes deste notebook. Inclua citações para comprovar as informações."

**O que o notebook respondeu:** a arquitetura Transformer proposta em 2017 utiliza mecanismos de atenção e favorece processamento paralelo. A autoatenção relaciona tokens da sequência por vetores *Query*, *Key* e *Value*: calcula afinidades, normaliza os pesos com softmax e combina informações para contextualizar cada token. O notebook exemplificou a diferença de sentido da palavra "modelo" em contextos distintos e explicou a atenção com múltiplas cabeças.

**Fontes às quais a resposta fez referência:** F1, F2 e F3; o print abaixo mostra citações numeradas e um trecho aberto do vídeo F3 que explica como os vetores se comunicam e incorporam contexto.

![Resposta 1 e consulta à fonte citada](evidencias/pergunta-01-transformers.png)

### Pergunta 2 — Tokens e embeddings

**Pergunta enviada:** "O que são tokens e embeddings em modelos de linguagem? Explique a diferença entre eles, apresente exemplos práticos e cite as fontes utilizadas neste notebook."

**O que o notebook respondeu:** tokens são unidades discretas de uma entrada textual, como palavras, subpalavras ou sinais; embeddings são vetores numéricos contínuos associados a essas unidades. O notebook explicou o papel da matriz de embeddings, da codificação posicional e apresentou analogias de proximidade semântica e relações geométricas.

**Fontes às quais a resposta fez referência:** F1, F2 e F3; o print mostra a seção de exemplos com citações e um trecho da explicação do produto escalar no vídeo F3.

![Resposta 2 e consulta à fonte citada](evidencias/pergunta-02-tokens-embeddings.png)

### Pergunta 3 — Limitações e riscos

**Pergunta enviada:** "Quais são as principais limitações e riscos dos modelos de linguagem (LLMs)? Explique as alucinações, os vieses e as dificuldades de interpretação, utilizando exclusivamente as fontes disponíveis neste notebook. Inclua citações e informe quando alguma informação não estiver presente nas fontes."

**O que o notebook respondeu:** as fontes permitem discutir tamanho da janela de contexto, riscos de geração incoerente, dificuldade de interpretação de algumas camadas, custo computacional e medidas contra superajuste. **O próprio notebook advertiu que as fontes selecionadas não oferecem uma discussão formal sobre alucinações nem sobre vieses éticos e sociais.** Essa limitação foi mantida em vez de preenchida por informações externas.

**Fontes às quais a resposta fez referência:** F1 e F3, com documentação F2 na coleção; o print apresenta as citações numeradas, um trecho aberto de F3 e a nota salva no Estúdio.

![Resposta 3 e consulta à fonte citada](evidencias/pergunta-03-limitacoes-llms.png)

### Pergunta 4 — Como um LLM gera texto

**Pergunta enviada:** "Como um modelo de linguagem (LLM) gera uma resposta a partir de uma pergunta? Explique passo a passo o processo, desde a tokenização e os embeddings até o mecanismo de atenção e a previsão do próximo token. Utilize exemplos simples e inclua citações das fontes deste notebook."

**O que o notebook respondeu:** descreveu um fluxo didático de tokenização, conversão em embeddings e representação posicional, blocos de atenção e feed-forward, projeção para logits, distribuição de probabilidades por softmax e geração autorregressiva de novos tokens. São etapas descritas para o tipo de LLM autorregressivo abordado pelas fontes, não uma especificação universal de todos os modelos.

**Fontes às quais a resposta fez referência:** F1 e F3, com a documentação F2 como suporte geral; o print mostra os passos de previsão e o trecho do vídeo F3 aberto para conferência.

![Resposta 4 e consulta à fonte citada](evidencias/pergunta-04-funcionamento-llms.png)

## Materiais gerados no Estúdio

Os materiais foram gerados no Gemini Notebook a partir do conteúdo estudado:

- **[Mapa mental — Anatomia e arquitetura dos Transformers e LLMs](materiais/mapa-mental-llms.png)** (PNG). A imagem registra parte das ramificações abertas e outras recolhidas na visualização.
- **[Apresentação — A Geometria dos LLMs](materiais/A_Geometria_dos_LLMs.pdf)** (PDF, 15 páginas). Resume tokenização, embeddings, atenção, geração de texto e limites da arquitetura.

![Mapa mental gerado no notebook](materiais/mapa-mental-llms.png)

## Aprendizados e boas práticas

Este exercício demonstrou como um caderno apoiado em fontes pode organizar a aprendizagem técnica: cruzando explicações visuais com documentação e texto acadêmico, fazendo perguntas com citações e abrindo o trecho original para conferir a resposta. A pergunta sobre limites dos LLMs também demonstrou uma prática importante: reconhecer explicitamente quando a bibliografia escolhida não dá suporte a uma afirmação.

As analogias e os números de exemplos apresentados no material devem ser interpretados no contexto das fontes que os descrevem, e não como propriedades universais de todos os LLMs.

## Checklist de entrega

- [x] Tema e objetivo definidos
- [x] Referências técnicas selecionadas em PDF, página web e vídeo
- [x] Diretriz enviada no chat do notebook
- [x] Quatro perguntas, sínteses das respostas e evidências de citações documentadas
- [x] Mapa mental e slides incluídos neste repositório
- [x] Link do notebook adicionado
- [ ] **Confirmar** que o notebook está acessível como "Qualquer pessoa com o link" e testar com outra conta Google
- [ ] **Criar/publicar** o repositório GitHub com visibilidade pública
- [ ] **Submeter** o link do repositório GitHub (não apenas o link do notebook) na DIO

---

**Ferramenta de estudo:** [Gemini Notebook](https://notebook.google.com/). Este projeto documenta as fontes selecionadas e as saídas produzidas em uma sessão real de estudo assistido por IA.
