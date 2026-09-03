# 📚 Miniguia de Estudos: Engenharia de Prompt (O Método do Google)

> **Projeto / Desafio de Projeto da DIO**  
> **Tema:** Engenharia de Prompt com suporte do NotebookLM e Inteligência Artificial  
> **Autor:** Paulo Roberto da Silva Nunes  
> **Repositório:** [miniguia-estudos-notebooklm](https://github.com/paulorsnunes/miniguia-estudos-notebooklm)

---

## 🎯 Contexto e Objetivos

Este repositório foi criado como parte de um **Desafio de Projeto na DIO (Digital Innovation One)** com o intuito de aplicar na prática técnicas avançadas de **Engenharia de Prompt** organizadas e destiladas através do **NotebookLM**.

### Objetivos de Estudo:
1. **Compreender o Framework do Google para Prompts:** Entender como estruturar instruções eficientes com base nos pilares: *Tarefa, Contexto, Referências, Avaliação, Iteração, Personas e Formatos*.
2. **Construção de Agentes de IA:** Aprender a montar *Agentes de Simulação* e *Agentes de Feedback Especialista*.
3. **Aplicação do Metaprompting:** Utilizar a própria IA para otimizar, refinar e evoluir prompts complexos.
4. **Organização do Conhecimento:** Consolidar os aprendizados em um Miniguia de Estudo reutilizável para consultas e revisões futuras.

---

## 📂 Curadoria de Fontes

Para alimentar o caderno no **NotebookLM** e gerar as análises e sínteses deste guia, foram selecionadas as seguintes fontes de referência:

1. 🎬 **Vídeo-base Principal:** [RESUMI o Curso de 7h do GOOGLE de ENGENHARIA de PROMPTS em 20 MINUTOS](https://www.youtube.com/watch?v=ixKOCQHrxgg) (Canal: *Negócios em Mente*)
2. 📄 **Google Prompt Engineering Whitepaper / Documentation:** Documentação oficial e diretrizes do Google Cloud / Gemini para Engenharia de Prompt.
3. 📖 **Artigo Técnico de Referência:** *Prompt Engineering Guide (DAIR.AI)* — Cobertura sobre Few-Shot Prompting, Chain-of-Thought e Metaprompting.
4. 📝 **Notas de Campo e Testes Práticos:** Registros de experimentos de prompting e troubleshooting realizados no Gemini/NotebookLM.

---

## 🧪 Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Nesta seção estão registradas as perguntas estratégicas, variações de prompts testadas e as lições aprendidas ("cicatrizes") no processo de extração do melhor resultado da IA.

### 1. Teste de Definição de Tarefa sem e com Contexto
* **Prompt Fraco (Sem Contexto):**
  > *"Me ajude a reescrever este texto de atualização de prazos."*
  * **Resultado:** Resposta genérica, vaga e sem adequação de tom.
* **Prompt Otimizado (Com Contexto, Persona e Formato):**
  > *"Atue como um gestor de projetos de tecnologia. Reescreva a mensagem a seguir em um tom profissional para o WhatsApp, informando ao cliente que o prazo do entregável mudou de 3 para 5 dias devido a ajustes de qualidade. Devolva a resposta em 2 opções no formato de tópicos (bullet points)."*
  * **Resultado:** Excelente tom, direto ao ponto e pronto para uso.

---

### 2. Dificuldades Encontradas e Resolução (Troubleshooting)

| Problema / Dificuldade | Causa Raiz | Solução Aplicada |
| :--- | :--- | :--- |
| **Respostas Genéricas e Clichês** | Falta de contexto específico e ausência de exemplos. | Inclusão de **3 pilares**: Persona + Cenário/Contexto + Exemplos de referência (Few-shot). |
| **A IA encerrava a conversa muito cedo** | Ausência de uma instrução explícita de "condição de parada". | Definição de **Ciclos de Iteração**: *"Trabalhe em ciclos de feedback e pare apenas quando eu disser 'Sessão Encerrada'"*. |
| **Bloqueio ao criar prompts do zero** | Falta de clareza na estrutura do prompt. | Aplicação de **Metaprompting**: Perguntar à IA *"Quais informações ou contextos faltam neste prompt para torná-lo mais preciso?"*. |

---

## 📖 Miniguia de Estudo (Entrega Final)

### 🔹 1. Resumo Estruturado: Os 5 Princípios do Google

1. **Tarefa (Task):** O resultado exato que você precisa (não um tópico geral). Reforçado por **Persona** (quem fala) e **Formato** (como entrega).
2. **Contexto (Context):** O "GPS" da IA. Detalhes do público-alvo, restrições, dor atacada e canal de publicação.
3. **Referências (Few-Shot / Examples):** Exemplos práticos de textos ou posts com bom desempenho para a IA replicar a estrutura/estilo.
4. **Avaliação & Iteração (Loop):** Analisar criticamente a resposta e pedir ajustes em ciclos contínuos de refinamento.
5. **Agentes & Metaprompting:** Criação de personas especialistas (simulação/feedback) e uso da IA para aprimorar os próprios comandos.

---

### 🔹 2. Glossário de Conceitos

* **Prompt:** Instrução ou texto de entrada enviado a um modelo de linguagem para obter uma resposta específica.
* **Persona:** Filtro de papel ou identidade atribuído à IA (ex: *"Atue como um especialista em segurança..."*) para guiar vocabulário e profundidade.
* **Few-Shot Prompting:** Tática de fornecer 1 ou mais exemplos de entrada/saída dentro do prompt para guiar o padrão do modelo.
* **Metaprompting:** Técnica de utilizar o próprio LLM para gerar, avaliar ou otimizar prompts.
* **Agente de Simulação:** Configuração de um prompt interativo onde a IA atua como um parceiro de treino em um cenário realista.
* **Condition of Stop (Condição de Parada):** Regra explícita que instrui a IA sobre quando continuar fazendo perguntas e quando finalizar a tarefa.

---

### 🔹 3. Biblioteca de Prompts Reutilizáveis

#### 🤖 Agente 1: Consultor de Feedback Especialista
```text
Atue como um Especialista em Comunicação Técnica e Redação com mais de 10 anos de experiência.
Análise o texto que vou enviar a seguir. 
Critique:
1. Clareza e objetividade;
2. Tom de voz e adequação ao público;
3. Possíveis pontos de ambiguidade.

Seja brutalmente honesto. Apresente os pontos fracos e reescreva uma versão otimizada em tabela comparativa.
Aguarde eu enviar o texto.

🔄 Agente 2: Gerador de Metaprompt (Otimizador)

Eu quero criar um prompt para [INSERIR OBJETIVO AQUI]. 
Antes de gerar a resposta final, analise meu objetivo e me faça 3 perguntas sobre contexto, restrições ou exemplos que faltam para tornar este prompt perfeito.

📊 Template Padrão de Prompt em Camadas (Google Method)
[PERSONA]: Atue como [Papel do Especialista].
[TAREFA]: [Ação clara e resultado final desejado].
[CONTEXTO]: [Detalhes do cenário, público-alvo, canal e objetivo].
[REFERÊNCIAS]: [Cole aqui exemplos de estilo ou formato desejados].
[FORMATO DE SAÍDA]: Apresente o resultado no formato [Bullet points / Tabela / Markdown].

🛠️ Como Executar / Utilizar este Material

Clone o repositório: git clone https://github.com/paulorsnunes/miniguia-estudos-notebooklm.git

Utilize os templates da biblioteca de prompts nos seus LLMs de preferência (Gemini, ChatGPT, Claude).

Importe os arquivos/fontes no NotebookLM para realizar buscas semânticas personalizadas sobre o material.

✒️ Licença e Créditos
Projeto desenvolvido para fins educacionais no âmbito dos desafios da DIO (Digital Innovation One).

Fontes e conteúdos inspirados nas diretrizes públicas do Google e no canal Negócios em Mente.

