# 📊 Análise da Desistência no ENEM 2019 — Minas Gerais

Investigação exploratória sobre os fatores associados à ausência de candidatos no ENEM 2019, usando os microdados oficiais do INEP filtrados para Minas Gerais.

##  Motivação

Em análises iniciais dos dados, percebi que o maior percentual de candidatos ausentes no dia da prova era de escola pública. Minha hipótese inicial era: alunos de escola pública são isentos da taxa de inscrição do ENEM, então parte deles se inscreve sem compromisso real de comparecer, inclusive desde os primeiros anos do Ensino Médio, "só para treinar",  o que explicaria a maior desistência.

Este projeto documenta o processo real de testar essa hipótese com os dados: o que se confirmou, o que foi refutado, e a explicação mais consistente que emergiu da análise.

## Pergunta de pesquisa

A desistência no ENEM entre estudantes de escola pública está associada à isenção da taxa de inscrição (inscrição "sem custo, sem compromisso"), ou existe uma explicação mais consistente nos dados?

## Sobre os dados

- **Fonte:** [Microdados do ENEM 2019 — INEP](https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem)
- **Filtro aplicado:** candidatos residentes em Minas Gerais
- **Principais colunas utilizadas:** `TP_ESCOLA`, `TP_ST_CONCLUSAO`, `IN_TREINEIRO`, `TP_PRESENCA_CH`, `TP_PRESENCA_CN`, `NU_IDADE`, `Q006` (renda familiar)

> O arquivo de dados não está incluído neste repositório por ser um recorte de uma base pública extensa. Baixe os microdados completos no link acima e filtre por `SG_UF_RESIDENCIA == 'MG'`.

## Tecnologias

- Python 3
- pandas
- matplotlib
- Jupyter Notebook

## Principais descobertas

| Achado | Resultado |
|---|---|
| Hipótese do treineiro | **Refutada** — treineiros desistem menos (13%), não mais, que não-treineiros (31%) dentro do mesmo grupo |
| Maior bloco de desistência | Pessoas que já concluíram o Ensino Médio há anos e repetem a prova (29%) |
| Efeito idade | Real, mas concentrado em estudantes adultos (provável EJA), não em jovens "testando de graça" |
| Comparação mais sólida (17-18 anos, amostras grandes) | Escola pública desiste **5 a 6x mais** que escola privada (8-11% vs 1,6-2%) |
| Fator mais explicativo | Renda familiar — queda quase linear na desistência conforme a renda aumenta |

**Conclusão:** a diferença de desistência entre escola pública e privada parece estar mais associada à vulnerabilidade socioeconômica (transporte, trabalho concorrendo com o horário da prova, suporte estrutural) do que à ausência de custo na inscrição.

## Como executar

```bash
git clone <url-do-repositorio>
cd analise-enem-mg-2019
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install pandas matplotlib jupyter
jupyter notebook analise_enem_mg_2019.ipynb
```

## Estrutura do repositório

```
analise-enem-mg-2019/
├── analise_enem_mg_2019.ipynb   # Notebook com toda a análise
├── README.md
└── graficos/
    ├── grafico_idade.png
    └── grafico_renda.png
```

## Aprendizados

- Antes de comparar percentuais entre grupos, sempre checar o tamanho da amostra — idades e categorias extremas podem distorcer a leitura.
- A explicação mais intuitiva nem sempre é a mais sustentada pelos dados e o processo de refutar a própria hipótese inicial é tão valioso quanto confirmá-la.

## 📬 Contato

- Instagram: [@nellyintech](https://instagram.com/nellyintech)
- LinkedIn: [_Rinelly Vasconcelos_](https://www.linkedin.com/in/rinelly-vasconcelos/)
