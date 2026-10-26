# Revisar vulnerabilidades e orientar correções

**ID:** `02_revisao_vulnerabilidades`  
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
Examine relatórios concretos fornecidos pelo usuário de Bandit, pip-audit, Gitleaks, Trivy e ZAP. Para cada achado, explique evidência, componente, severidade contextual, possibilidade de falso positivo, correção mínima e reteste. Monte tabela com status (aberto/corrigido/aceito sob justificativa). Nunca invente CVEs ou declare ambiente seguro sem evidências; nunca recomendar suprimir alertas sem fundamentação.

## Registro de execução (preencher após o uso)
- Data/hora: PENDENTE
- Ferramenta / modelo: PENDENTE
- Arquivos ou saídas geradas: PENDENTE
- Alterações humanas: PENDENTE
- Testes e resultados observados: PENDENTE
- Commit/PR relacionado: PENDENTE
