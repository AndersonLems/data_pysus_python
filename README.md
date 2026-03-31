# Análise de Leishmaniose Visceral com PySUS

Este projeto usa o `PySUS` para baixar dados públicos do SINAN e explorar notificações de leishmaniose visceral no Brasil em 2025. A análise foi construída em notebook, com enriquecimento de informações geográficas de UF e município, tratamento de datas e geração de gráficos para apoiar leitura epidemiológica inicial dos registros.

## Objetivo

O objetivo do projeto é transformar os dados brutos do SINAN em uma análise exploratória mais legível, respondendo perguntas como:

- Como os casos estão distribuídos por classificação final e evolução?
- Quais municípios concentram mais casos confirmados e mais óbitos?
- Como sexo, mês de notificação e droga inicial se relacionam com a evolução dos casos?
- Em quais UFs há maior concentração de registros inconclusivos sem diagnóstico parasitológico realizado?

## O que o notebook faz

O fluxo do notebook é:

1. Baixa os metadados e os registros de leishmaniose visceral (`LEIV`) com `PySUS`.
2. Inspeciona estrutura, colunas, tipos e frequência de valores.
3. Busca listas públicas de estados e municípios para converter códigos em nomes legíveis.
4. Normaliza datas de notificação e óbito.
5. Cria recortes analíticos, principalmente:
   - casos confirmados;
   - óbitos por leishmaniose;
   - registros inconclusivos sem teste parasitológico.
6. Gera visualizações comparativas e exporta imagens em `.png`.

## Arquivos do projeto

- [pimadataset.ipynb](/home/anderson/projetos/data_pysus_python/pimadataset.ipynb): notebook principal da análise.
- [data/metadata_LEIV.xlsx](/home/anderson/projetos/data_pysus_python/data/metadata_LEIV.xlsx): metadados do agravo `LEIV`.
- [analise_leishmaniose_completa.png](/home/anderson/projetos/data_pysus_python/analise_leishmaniose_completa.png): painel com sexo, evolução, droga e distribuição temporal.
- [analise_leishmaniose_completa2.png](/home/anderson/projetos/data_pysus_python/analise_leishmaniose_completa2.png): painel com municípios, óbitos e inconclusivos sem teste.
- [comparativo_rn_completo.png](/home/anderson/projetos/data_pysus_python/comparativo_rn_completo.png): comparação adicional focada no Rio Grande do Norte.
- [argumentos_leishmaniose.png](/home/anderson/projetos/data_pysus_python/argumentos_leishmaniose.png): imagem de apoio gerada no projeto.

## Tecnologias usadas

- Python
- Jupyter Notebook
- pandas
- numpy
- seaborn
- matplotlib
- requests
- pysus

## Como executar

Se quiser rodar a análise localmente:

```bash
source .venv/bin/activate
jupyter notebook
```

Depois, abra o arquivo `pimadataset.ipynb` e execute as células em ordem.

## Como visualizar o notebook no GitHub

O GitHub já renderiza arquivos `.ipynb` automaticamente. Depois de subir o projeto, basta abrir o arquivo `pimadataset.ipynb` no repositório.

Exemplo de URL:

```text
https://github.com/SEU-USUARIO/SEU-REPOSITORIO/blob/main/pimadataset.ipynb
```

Se a renderização do GitHub ficar lenta ou incompleta, use o `nbviewer`, que costuma funcionar melhor para notebooks maiores:

```text
https://nbviewer.org/github/SEU-USUARIO/SEU-REPOSITORIO/blob/main/pimadataset.ipynb
```

## Observações

- Os dados analisados são públicos e dependem da disponibilidade das fontes online no momento da execução.
