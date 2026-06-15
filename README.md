# GoodWe EV Chatbot — Sprint 2

Chatbot especializado em **ChargeGrid Intelligence** e **EV ChargeOps**, desenvolvido para o EV Challenge 2026 da GoodWe.

## Link Colab:

https://colab.research.google.com/drive/1sFWJSzW41G6G8VC2p_-qqvl-ezcN32Em?usp=sharing

## Técnicas utilizadas

- **RAG (Retrieval-Augmented Generation):** o chatbot busca trechos relevantes dos PDFs do projeto antes de responder
- **Few-shot prompting:** exemplos de perguntas e respostas são injetados no system prompt para guiar o modelo
- **Memória de histórico:** o contexto da conversa é mantido entre as mensagens

## Dependências

```bash
groq
langchain
langchain-community
langchain-core
langchain-huggingface
langchain-text-splitters
langgraph
pypdf
sentence-transformers
```

## Variáveis de ambiente

A chave de acesso à API do Groq deve ser configurada nos **Colab Secrets** com o nome `GROQ_API_KEY`.

Nenhuma chave deve aparecer exposta no código ou no repositório.

## Como executar

1. Abrir o arquivo `Chatbot_GoodWe_Sprint2.ipynb` no Google Colab
2. Criar uma conta em [console.groq.com](https://console.groq.com) e gerar uma API Key
3. Adicionar a chave nos Secrets do Colab com o nome `GROQ_API_KEY`
4. Executar todas as células em ordem
5. Na célula de upload, fazer o upload dos PDFs do projeto
6. Interagir com o chatbot na última célula

## Exemplos de uso

```
Voce: O que é a ChargeGrid Intelligence?
Bot: A ChargeGrid Intelligence é uma solução focada no gerenciamento automatizado da infraestrutura de recarga...

Voce: /historico
--- Historico da conversa ---
[1] Voce: O que é a ChargeGrid Intelligence?
[1] Bot: ...

Voce: /limpar
Historico apagado!

Voce: sair
Ate logo!
```

## Modelo utilizado

`llama-3.1-8b-instant` via API da Groq.

## Resultados dos Testes — Sprint 2

| # | Pergunta | Avaliação |
|---|----------|-----------|
| 1 | O que é a ChargeGrid Intelligence e qual problema ela resolve? | ✅ Adequada |
| 2 | Quais são as especificações elétricas do GoodWe HCA G2 para o mercado brasileiro? | ✅ Adequada |
| 3 | Como funciona o gerenciamento dinâmico de carga (DLM) na ChargeGrid? | ✅ Adequada |
| 4 | Quais protocolos de comunicação o carregador GoodWe utiliza para integração com a smart grid? | ✅ Adequada |
| 5 | O que acontece com o homem aranha no carro | ✅ Adequada |

### Respostas obtidas

**[TESTE 1]**  
Pergunta: O que é a ChargeGrid Intelligence e qual problema ela resolve?  
Resposta: A ChargeGrid Intelligence é uma solução de ponta focada no gerenciamento automatizado da infraestrutura de recarga para o setor comercial. Ela resolve o problema da ausência crítica de mecanismos nativos e integrados em eletropostos comerciais para gerenciar a potência distribuída, registrar o ciclo completo de cada sessão de recarga e aplicar políticas robustas de tarifação e pagamento fluido.  
Chunks recuperados: 4

---

**[TESTE 2]**  
Pergunta: Quais são as especificações elétricas do GoodWe HCA G2 para o mercado brasileiro?  
Resposta: De acordo com os documentos fornecidos, os modelos da linha HCA G2 são compatíveis com redes de 220/380 Vac, atendendo perfeitamente o padrão elétrico brasileiro.  
Chunks recuperados: 4

---

**[TESTE 3]**  
Pergunta: Como funciona o gerenciamento dinâmico de carga (DLM) na ChargeGrid?  
Resposta: O gerenciamento dinâmico de carga (DLM) na ChargeGrid é realizado através da análise de dados na camada lógica inteligente, que processa as curvas de carga e aplica algoritmos de cobrança dinâmica. Isso permite que a potência seja dinamicamente redistribuída entre as sessões de recarga ativas, mitigando sobrecargas e maximizando o retorno financeiro através da cobrança inteligente baseada no tempo e energia consumida. Além disso, o DLM também utiliza o algoritmo para assegurar que a potência total alocada nos eletropostos obedeça ao limite operacional, evitando multas por ultrapassagem de demanda contratada junto à concessionária de energia.  
Chunks recuperados: 4

---

**[TESTE 4]**  
Pergunta: Quais protocolos de comunicação o carregador GoodWe utiliza para integração com a smart grid?  
Resposta: O GoodWe utiliza o protocolo Modbus/LAN para comunicação com os sistemas de gestão da ChargeGrid.  
Chunks recuperados: 4

---

**[TESTE 5]**  
Pergunta: O que acontece com o homem aranha no carro  
Resposta: Não encontrei essa informação nos documentos do projeto.  
Chunks recuperados: 4

##Integrantes

- Mauricio Bertuci Saletti - RM571229
- Mateus Eduardo da Cruz Rocha - RM570736
- Lucas Caram Bueno - RM570158
- ⁠Rhuan Pacheco Carreri - RM570129
- Leonardo Fortini Marcelo - RM572566
- ⁠Nicolas Andrade Rodrigues - 572782
