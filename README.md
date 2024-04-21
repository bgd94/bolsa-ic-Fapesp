# Bolsa IC Fapesp em Análise de Dados - Cátedra Sérgio Henrique Ferreira/IEA-RP

Este repositório foi criado com o objetivo de concorrer à Bolsa de Iniciação Científica (IC) da Fapesp na área de Análise de Dados. 

Para ganhar familiaridade e demonstrar meu conhecimento nos aspectos solicitados, desenvolvi rotinas automatizadas para coleta, análise e visualização de dados do portal [SEADE (Fundação Sistema Estadual de Análise de Dados Estatísticos)](https://www.seade.gov.br/) utilizando as seguintes tecnologias:
 - Python e R.
 - Shiny e Plotly
 - Conhecimentos em Análise de Dados

*Como tenho anos de experiência profissional atuando com Modelagem de dados, Banco de Dados e SQL, investi um tempo menor para demonstrar meus conhecimentos nessas áreas, **e disponibilizei neste neste outro repositório***

## Descrição técnica
### Solução composta por um *back-end* e um *front-end* (aplicativo web)
*Notebook Google Colab*: Esse repositório contém um arquivo *notebook* desenvolvido no ambiente do *Google Colab* ([disponível aqui](https://colab.research.google.com/drive/1m99nELor8bsXleH8mQ8lWQUIG2KPy-rl?usp=share_link)) cuja extensão é ".ipynb"
 - Back-end: Escrito em *Python*, realiza raspagem de dados (*web-scrap*) do portal SEADE e indexa informações-chave num arquivo *JSON* para a posterior navegação.
 - Front-end em R: Viabiliza navegação amigável pelos conjuntos de dados do portal. Além disso, oferece seis  visualizações rápidas para cada fonte *".CSV"* indexada.
 - Arquitetura *CQRS*: **todo diagrama arquitetura**




# exercicio-dados-saede.ipynb
É o nome do arquivo *Notebook Google Colab* contendo toda a solução


## Para utilizar
Acesse o [notebook colab "exercicio-dados-saede.ipynb"](https://colab.research.google.com/drive/1m99nELor8bsXleH8mQ8lWQUIG2KPy-rl?usp=share_link)

### 1) Indexar conjuntos de dados SEADE 

Use o Backend em Python para raspar os dados e gerar arquivo JSON esperado:
 - Executar as 6 células sob o título "1. Backend em Python". A execução desse passo leva cerca de 20 minutos (instalação de dependências e raspagem em si)
 - Ao final, o arquivo "seade-repositorio.json" será criado no diretório da VM no seguinte formato
```
{
    "categories": [
        {
            "category": "COVID-19",
            "title": "2 conjuntos de dados encontrados",
            "detail": "2 compatível(is) com web-scrap (formato .csv)",
            "datasets": [
                {
                    "name": "Covid-19 Semanal",
                    "entity": "",
                    "description": "Dados semanais sobre casos e óbitos decorrentes de COVID-19 nos municípios do Estado de São Paulo e sobre leitos e internações por Departamento Regional de Saúde do estado....",
                    "resources": [
                        {
                            "resource_title": "Casos e óbitos por municípios e data - Dicionário de variáveis",
                            "format": "CSV",
                            "download_url": "https://repositorio.seade.gov.br/dataset/ba7bdfa7-88b4-49b7-bec2-797b4c5f5576/resource/26419cf0-2387-4ef8-9eba-d3bd8217f06c/download/dicvariaveis_dados_covid_sp.csv",
                            "description": "Dicionário de variáveis do arquivo de \"Casos e óbitos por municípios e data\"..."
                        }
                    ], ...
                    "last_update": ""
                }
            ], ...
        }
    ], ...
}

```

### 2) Iniciar aplicação web para navegação

Use o Frontend em R para visualizar os dados raspados:
 - Executar as 8 células sob o título "2. Frontend em R".
 - A anti-penúltima célula revela uma "senha" necessária para prosseguir. Copie o valor que aparece para você. A seguir um exemplo ilustrativo:
```
Password/Enpoint IP for localtunnel is: 34.32.225.251
```


 - A última célula revela o endereço para acesso da aplicação web - que varia a cada execução -, antecedido por "*your url is:*". A seguir um exemplo ilustrativo
```
..................] / rollbackFailedOptional: verb npm-session 168de0b35e9e44a
Attaching package: ‘shiny’

The following object is masked from ‘package:jsonlite’:

    validate

npx: installed 22 in 2.832s
your url is: https://green-taxis-begin.loca.lt

Listening on http://127.0.0.1:8501
```

No exemplo acima, a senha informada foi "34.32.225.251" e a aplicação web Shiny ficou disponível no endereço "https://green-taxis-begin.loca.lt", porém isso varia de acordo com sua sessão no Google Colab. Usar os valores citados acima não vai funcionar, para funcionar deve-se usar os valores que aparecem na hora da execução

A seguir um vídeo demonstrando o passo a passo
**todo video YouTube**

[GPL-3.0](https://choosealicense.com/licenses/gpl-3.0/)
