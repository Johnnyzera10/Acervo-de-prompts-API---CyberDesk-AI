# Criar regras transparentes de priorização

**ID:** `05_regras_prioridade`  
**Finalidade:** orientar uma etapa de construção/revisão do CyberDesk AI.

## Contexto obrigatório
Projeto acadêmico **CyberDesk AI**: aplicação local de triagem assistida de chamados de cybersecurity. Stack: Python, FastAPI, scikit-learn (TF-IDF + regressão logística), interface web simples, Docker Compose e GitHub Actions. Categorias: phishing, acesso suspeito, malware, possível vazamento de dados, vulnerabilidade e outros/revisão manual. Prioridade sugerida por regras de impacto e urgência; classificação e decisão final cabem ao analista. Ambiente inicial: localhost/127.0.0.1:8000, sem serviços externos de IA e sem dados reais. Não executar contenção automática.

## Critérios gerais de resposta da IA
- Fornecer arquivos completos com seus caminhos, comandos de execução e dependências explícitas.
- Priorizar bibliotecas estáveis e versões fixadas; não inventar resultados de testes ou métricas.
- Validar entradas; evitar segredos hardcoded, logs com texto de incidentes e exposição externa por padrão.
- Explicar decisões técnicas e incluir critérios de aceite e testes reproduzíveis.
- Registrar hipóteses e pendências separadamente de funcionalidades implementadas.

## Prompt para enviar à IA
Projete função determinística que combine impacto e urgência (baixo/médio/alto) e sinais objetivos do relato, gerando prioridade sugerida e justificativa. Separe prioridade da categoria prevista. Trate credenciais expostas e acesso privilegiado como exemplos de maior urgência conforme regra documentada, mas não dê decisão final automática. Crie casos de teste de fronteira e falso positivo.

## Registro de execução (preencher após o uso)
- Data/hora: PENDENTE
- Ferramenta / modelo: PENDENTE
- Arquivos ou saídas geradas: PENDENTE
- Alterações humanas: PENDENTE
- Testes e resultados observados: PENDENTE
- Commit/PR relacionado: PENDENTE
