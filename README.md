[README.md](https://github.com/user-attachments/files/33991261/README.md)
# Acervo-de-prompts-API---CyberDesk-AI

# CyberDesk AI — Acervo de Prompts

**Planejamento de uma aplicação local de triagem assistida de chamados de cybersecurity com IA e práticas DevSecOps.**

> **Status:** projeto acadêmico em fase de planejamento. Este repositório reúne os prompts preparados para orientar a implementação; ele **não** comprova que a aplicação, os controles ou o pipeline já estejam funcionando.

## Sobre o projeto

O **CyberDesk AI** foi proposto para apoiar a triagem inicial de chamados de segurança da informação. A aplicação receberá uma descrição textual, sugerirá uma categoria e uma prioridade, e apresentará uma justificativa para a análise humana.

O analista será responsável por confirmar ou ajustar a classificação e decidir os próximos passos. **Não estão previstas ações automáticas de bloqueio ou contenção.**

### Categorias de chamados

- Phishing
- Acesso suspeito
- Malware
- Possível vazamento de dados
- Vulnerabilidade
- Outros / revisão manual

## Objetivo deste repositório

Documentar e versionar **os prompts utilizados ou planejados** para orientar o desenvolvimento do CyberDesk AI com auxílio de IA generativa, desde o levantamento de requisitos até a revisão de segurança e a documentação.

A ideia é tornar o processo **rastreável, revisável e reproduzível**: guardar o prompt, a finalidade, o modelo utilizado quando houver execução, a saída produzida, as alterações humanas e a evidência dos testes.

**A IA generativa auxiliará a construir a aplicação.** A classificação dos chamados, por sua vez, está planejada com um modelo local de aprendizado de máquina, sem dependência de API externa de IA.

## Tecnologias planejadas

| Camada | Tecnologia ou abordagem |
| --- | --- |
| Aplicação e API | Python + FastAPI |
| Classificação de texto | scikit-learn: TF-IDF + regressão logística |
| Priorização | Regras explícitas de impacto e urgência |
| Interface | Formulário web local |
| Implantação | Docker + Docker Compose, vinculados a `127.0.0.1` |
| CI/CD | GitHub Actions; publicação de imagem aprovada no GHCR |
| Análise de segurança | Bandit, pip-audit, Gitleaks, Trivy e OWASP ZAP Baseline |
| Avaliação de IA | Separação treino/teste, F1 macro e matriz de confusão |

## Estrutura do acervo

O acervo está dividido em **22 prompts** em seis etapas:

```text
prompts/
├── 01_planejamento/
│   ├── 01_requisitos_escopo.md
│   ├── 02_arquitetura_ameacas.md
│   └── 03_estrutura_repositorio.md
├── 02_dados_ia/
│   ├── 01_gerar_chamados_sinteticos.md
│   ├── 02_validar_base.md
│   ├── 03_treinar_classificador.md
│   ├── 04_avaliar_modelo.md
│   └── 05_regras_prioridade.md
├── 03_aplicacao/
│   ├── 01_api_fastapi.md
│   ├── 02_interface_web.md
│   ├── 03_autenticacao_auditoria.md
│   └── 04_testes_api_integracao.md
├── 04_implantacao/
│   ├── 01_dockerfile_compose.md
│   └── 02_configuracao_ambiente.md
├── 05_devsecops/
│   ├── 01_pipeline_github_actions.md
│   ├── 02_revisao_vulnerabilidades.md
│   ├── 03_testes_seguranca.md
│   ├── 04_sca_imagem_segredos.md
│   └── 05_zap_baseline_local.md
└── 06_documentacao/
    ├── 01_readme_demo.md
    ├── 02_matriz_conformidade.md
    └── 03_relatorio_final.md
```

### Navegação rápida

| Etapa | Finalidade | Prompts |
| --- | --- | ---: |
| [01 — Planejamento](prompts/01_planejamento/) | Requisitos, arquitetura, ameaças e organização do projeto | 3 |
| [02 — Dados e IA](prompts/02_dados_ia/) | Dados sintéticos, validação, treinamento, avaliação e prioridade | 5 |
| [03 — Aplicação](prompts/03_aplicacao/) | API, interface, autenticação, auditoria e testes | 4 |
| [04 — Implantação](prompts/04_implantacao/) | Docker e configuração do ambiente local | 2 |
| [05 — DevSecOps](prompts/05_devsecops/) | CI/CD, varreduras e avaliação de vulnerabilidades | 5 |
| [06 — Documentação](prompts/06_documentacao/) | Demonstração, conformidade e relatório final | 3 |

## Como utilizar os prompts

1. **Comece pelo planejamento:** leia os arquivos em `prompts/01_planejamento/` e avance na ordem numerada.
2. **Envie um prompt por tarefa** à ferramenta de IA de sua escolha, incluindo o contexto e os critérios presentes no arquivo.
3. **Revise a resposta antes de aplicá-la:** verifique bibliotecas, dependências, permissões, validação de entradas e decisões de arquitetura.
4. **Implemente e teste em ambiente local e autorizado.** Não considere código gerado por IA seguro apenas por ter sido gerado.
5. **Preencha o “Registro de execução”** no próprio arquivo do prompt após seu uso, distinguindo o que foi sugerido do que foi realmente implementado.
6. **Versione as alterações no Git**, associando prompts, código produzido, correções e evidências de testes, quando houver.

### Informações a registrar por execução

- Data e ferramenta/modelo de IA utilizado;
- arquivos ou respostas produzidas;
- ajustes feitos manualmente;
- testes realizados e resultados observados;
- commit ou pull request relacionado.

## Fluxo de funcionamento proposto

```text
Relato sintético / chamado
           |
           v
  Formulário web local
           |
           v
       API FastAPI
           |
           v
 TF-IDF + Regressão Logística
           |
           v
 Sugestão de categoria
           |
           v
Regras de impacto e urgência
           |
           v
     Revisão do analista
           |
           v
      Decisão humana
```

Casos ambíguos ou com classificação incerta deverão ser encaminhados para revisão manual.

## Segurança, privacidade e conformidade

O planejamento inclui o uso de **chamados inteiramente sintéticos**, autenticação no protótipo, execução local em loopback, ausência de segredos no código, minimização de dados em logs e rastreabilidade das decisões do analista.

A abordagem DevSecOps proposta compreende revisão de pull requests, testes, varredura de segredos e dependências, análise da imagem Docker e avaliação passiva da aplicação em ambiente controlado. Achados precisarão ser revisados, corrigidos e reavaliados antes da liberação.

Essas medidas são **controles planejados para apoiar boas práticas e a adequação à LGPD**; não equivalem, por si só, a uma certificação ou comprovação de conformidade integral.

## Critérios previstos para a entrega da aplicação

- Aplicação em execução local por Docker Compose, com autenticação;
- API e interface funcional para abertura e triagem de chamados sintéticos;
- avaliação do classificador com métricas documentadas;
- testes automatizados e evidências das verificações de segurança;
- revisão humana dos resultados;
- acervo de prompts atualizado com histórico de utilização.

**Situação atual:** esses critérios são metas do projeto, ainda não resultados comprovados.

## Referências técnicas

- [FastAPI](https://fastapi.tiangolo.com/)
- [scikit-learn — Extração de atributos de texto](https://scikit-learn.org/stable/modules/feature_extraction.html)
- [Docker Compose](https://docs.docker.com/compose/)
- [GitHub Actions](https://docs.github.com/en/actions)
- [Bandit](https://bandit.readthedocs.io/)
- [pip-audit](https://github.com/pypa/pip-audit)
- [Gitleaks](https://github.com/gitleaks/gitleaks)
- [Trivy](https://trivy.dev/)
- [OWASP ZAP Baseline](https://www.zaproxy.org/docs/docker/baseline-scan/)
- [ANPD](https://www.gov.br/anpd/)

---

**Projeto acadêmico — FIAP**  
**João Pedro de Toledo Pescara**  
**Outubro de 2026**
