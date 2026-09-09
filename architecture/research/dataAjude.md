[**Datajud-Wiki**](https://datajud-wiki.cnj.jus.br/)

URL: https://datajud-wiki.cnj.jus.br/api-publica/exemplos/exemplo2

**API Key**

A autenticação da API Pública do Datajud é realizada através de
uma **Chave Pública**, gerada e disponibilizada pelo DPJ/CNJ. A chave
vigente estará sempre acessível nesta seção da Wiki, garantindo
transparência e facilitando seu acesso. Importante ressaltar que, por
razões de segurança e gestão do sistema, a chave poderá ser alterada
pelo CNJ a qualquer momento.

Para incorporar a API Key em suas requisições, utilize o formato
\"Authorization: APIKey \[Chave Pública\]\" no cabeçalho da requisição.

-   **APIKey atual**:

    -   Authorization:
        APIKey **cDZHYzlZa0JadVREZDJCendQbXY6SkJlTzNjLV9TRENyQk1RdnFKZGRQdw==**

**POST /api_publica_tribunal/\_search**

1.  Abra o **Postman** e clique em *\"New Request\"*.

2.  Defina o método HTTP como POST.

3.  Digite a
    URL: <https://api-publica.datajud.cnj.jus.br/api_publica_trf1/_search>

4.  Selecione a aba *\"Headers\"* e inclua a chave \"Authorization\" com
    o valor \"APIKey \[Chave Pública\]\";

5.  O valor \[Chave Pública\] corresponde a chave pública disponível
    em [Chave
    Pública](https://datajud-wiki.cnj.jus.br/api-publica/exemplos/api-publica/acesso);

6.  Ainda em *\"Headers\"* inclua a chave \"Content-Type\" com o valor
    \"application/json\";

7.  Selecione a aba *\"Body\"* e escolha a opção *\"raw\"*. Insira o
    corpo da solicitação JSON conforme o exemplo abaixo:

**[Ex. 1 - Pesquisar pelo número de processo]{.mark}**

Query DSL

{

\"query\": {

\"match\": {

\"numeroProcesso\": \"00008323520184013202\"

}

}

}

8.  Clique em *Send* para enviar e aguarde a resposta da Api.

**Resposta**

A resposta esperado é um JSON com os metadados de 1 ou mais processos
conforme o critério da busca:

> {
>
> \"took\": 6679,
>
> \"timed_out\": false,
>
> \"\_shards\": {
>
> \"total\": 7,
>
> \"successful\": 7,
>
> \"skipped\": 0,
>
> \"failed\": 0
>
> },
>
> \"hits\": {
>
> \"total\": {
>
> \"value\": 1,
>
> \"relation\": \"eq\"
>
> },
>
> \"max_score\": 13.917725,
>
> \"hits\": \[
>
> {
>
> \"\_index\": \"api_publica_trf1\",
>
> \"\_type\": \"\_doc\",
>
> \"\_id\": \"TRF1_436_JE_16403_00008323520184013202\",
>
> \"\_score\": 13.917725,
>
> \"\_source\": {
>
> \"numeroProcesso\": \"00008323520184013202\",
>
> \"classe\": {
>
> \"codigo\": 436,
>
> \"nome\": \"Procedimento do Juizado Especial Cível\"
>
> },
>
> \"sistema\": {
>
> \"codigo\": 1,
>
> \"nome\": \"Pje\"
>
> },
>
> \"formato\": {
>
> \"codigo\": 1,
>
> \"nome\": \"Eletrônico\"
>
> },
>
> \"tribunal\": \"TRF1\",
>
> \"dataHoraUltimaAtualizacao\": \"2023-07-21T19:10:08.483Z\",
>
> \"grau\": \"JE\",
>
> \"@timestamp\": \"2023-08-14T11:50:51.994Z\",
>
> \"dataAjuizamento\": \"2018-10-29T00:00:00.000Z\",
>
> \"movimentos\": \[
>
> {
>
> \"complementosTabelados\": \[
>
> {
>
> \"codigo\": 2,
>
> \"valor\": 1,
>
> \"nome\": \"competência exclusiva\",
>
> \"descricao\": \"tipo_de_distribuicao_redistribuicao\"
>
> }
>
> \],
>
> \"codigo\": 26,
>
> \"nome\": \"Distribuição\",
>
> \"dataHora\": \"2018-10-30T14:06:24.000Z\"
>
> },
>
> \...
>
> {
>
> \"codigo\": 14732,
>
> \"nome\": \"Conversão de Autos Físicos em Eletrônicos\",
>
> \"dataHora\": \"2020-08-05T01:15:18.000Z\"
>
> }
>
> \],
>
> \"id\": \"TRF1_436_JE_16403_00008323520184013202\",
>
> \"nivelSigilo\": 0,
>
> \"orgaoJulgador\": {
>
> \"codigoMunicipioIBGE\": 5128,
>
> \"codigo\": 16403,
>
> \"nome\": \"JEF Adj - Tefé\"
>
> },
>
> \"assuntos\": \[
>
> {
>
> \"codigo\": 6177,
>
> \"nome\": \"Concessão\"
>
> }
>
> \]
>
> }
>
> }
>
> \]
>
> }
>
> }
>
> Esse segundo JSON é do TRF1, e traz uma estrutura muito parecida com a
> do TJDFT. Neste caso, ele encontrou exatamente 1 processo.
>
> Informações disponíveis

+------------------------+---------------------------------------------+
| > **Campo**            | > **Informação encontrada**                 |
+========================+=============================================+
| > **Tribunal**         | > **TRF1**                                  |
+------------------------+---------------------------------------------+
| > **Número do          | > **00008323520184013202**                  |
| > processo**           |                                             |
+------------------------+---------------------------------------------+
| > **Classe**           | > **Procedimento do Juizado Especial        |
|                        | > Cível**                                   |
+------------------------+---------------------------------------------+
| > **Código da classe** | > **436**                                   |
+------------------------+---------------------------------------------+
| > **Sistema**          | > **PJe**                                   |
+------------------------+---------------------------------------------+
| > **Formato**          | > **Eletrônico**                            |
+------------------------+---------------------------------------------+
| > **Grau**             | > **JE --- Juizado Especial**               |
+------------------------+---------------------------------------------+
| > **Data de            | > **29/10/2018**                            |
| > ajuizamento**        |                                             |
+------------------------+---------------------------------------------+
| > **Última             | > **21/07/2023**                            |
| > atualização**        |                                             |
+------------------------+---------------------------------------------+
| > **Nível de sigilo**  | > **0**                                     |
+------------------------+---------------------------------------------+
| > **Órgão julgador**   | > **JEF Adj - Tefé**                        |
+------------------------+---------------------------------------------+
| > **Código do órgão**  | > **16403**                                 |
+------------------------+---------------------------------------------+
| > **Município IBGE**   | > **5128**                                  |
+------------------------+---------------------------------------------+
| > **Assunto**          | > **Concessão**                             |
+------------------------+---------------------------------------------+
| > **Código do          | > **6177**                                  |
| > assunto**            |                                             |
+------------------------+---------------------------------------------+
| > **Movimentações**    | > **Histórico de eventos do processo**      |
+------------------------+---------------------------------------------+
| > **Complementos**     | > **Informações adicionais das              |
|                        | > movimentações**                           |
+------------------------+---------------------------------------------+
| > **ID interno**       | >                                           |
|                        |  **TRF1_436_JE_16403_00008323520184013202** |
+------------------------+---------------------------------------------+

> **[Ex. 2 - Pesquisar por Classe Processual e Órgão Julgador]{.mark}**
>
> No exemplo abaixo é realizada a consulta de processos que possuam a
> Classe Processual 1116 -- \"Execução Fiscal\" do Órgão
> Julgador 13597 - VARA DE EXECUÇÃO FISCAL DO DF no tribunal TJDFT.

1.  Abra o **Postman** e clique em *\"New Request\"*.

2.  Defina o método HTTP como POST.

3.  Digite a
    URL: <https://api-publica.datajud.cnj.jus.br/api_publica_tjdft/_search>

4.  Selecione a aba *\"Headers\"* e inclua a chave \"Authorization\" com
    o valor \"APIKey \[Chave Pública\]\";

5.  O valor \[Chave Pública\] corresponde a chave pública disponível
    em [Chave
    Pública](https://datajud-wiki.cnj.jus.br/api-publica/exemplos/api-publica/acesso);

6.  Ainda em *\"Headers\"* inclua a chave \"Content-Type\" com o valor
    \"application/json\";

7.  Selecione a aba *\"Body\"* e escolha a opção *\"raw\"*. Insira o
    corpo da solicitação JSON conforme o exemplo abaixo:

> Query DSL
>
> {
>
> \"query\": {
>
> \"bool\": {
>
> \"must\": \[
>
> {\"match\": {\"classe.codigo\": 1116}},
>
> {\"match\": {\"orgaoJulgador.codigo\": 13597}}
>
> \]
>
> }
>
> }
>
> }
>
> **Resposta**
>
> A resposta esperado é um JSON com os metadados de 1 ou mais processos
> conforme o critério da busca:
>
> {
>
> \"took\": 213,
>
> \"timed_out\": false,
>
> \"\_shards\": {
>
> \"total\": 3,
>
> \"successful\": 3,
>
> \"skipped\": 0,
>
> \"failed\": 0
>
> },
>
> \"hits\": {
>
> \"total\": {
>
> \"value\": 10000,
>
> \"relation\": \"gte\"
>
> },
>
> \"max_score\": 2.0,
>
> \"hits\": \[
>
> {
>
> \"\_index\": \"api_publica_tjdft\",
>
> \"\_type\": \"\_doc\",
>
> \"\_id\": \"TJDFT_1116_G1_13597_07223914020178070001\",
>
> \"\_score\": 2.0,
>
> \"\_source\": {
>
> \"classe\": {
>
> \"codigo\": 1116,
>
> \"nome\": \"Execução Fiscal\"
>
> },
>
> \"numeroProcesso\": \"07223914020178070001\",
>
> \"sistema\": {
>
> \"codigo\": 1,
>
> \"nome\": \"Pje\"
>
> },
>
> \"formato\": {
>
> \"codigo\": 1,
>
> \"nome\": \"Eletrônico\"
>
> },
>
> \"tribunal\": \"TJDFT\",
>
> \"dataHoraUltimaAtualizacao\": \"2022-09-06T12:03:20.257Z\",
>
> \"grau\": \"G1\",
>
> \"@timestamp\": \"2023-04-13T17:59:46.214Z\",
>
> \"dataAjuizamento\": \"2017-08-21T10:05:32.000Z\",
>
> \"movimentos\": \[
>
> {
>
> \"complementosTabelados\": \[
>
> {
>
> \"codigo\": 2,
>
> \"valor\": 2,
>
> \"nome\": \"sorteio\",
>
> \"descricao\": \"tipo_de_distribuicao_redistribuicao\"
>
> }
>
> \],
>
> \"codigo\": 26,
>
> \"nome\": \"Distribuição\",
>
> \"dataHora\": \"2017-08-21T10:05:32.000Z\"
>
> },
>
> \...
>
> {
>
> \"codigo\": 11382,
>
> \"nome\": \"Bloqueio/penhora on line\",
>
> \"dataHora\": \"2022-07-13T07:25:59.000Z\"
>
> },
>
> {
>
> \"codigo\": 132,
>
> \"nome\": \"Recebimento\",
>
> \"dataHora\": \"2022-07-13T07:26:00.000Z\"
>
> }
>
> \],
>
> \"id\": \"TJDFT_1116_G1_13597_07223914020178070001\",
>
> \"nivelSigilo\": 0,
>
> \"orgaoJulgador\": {
>
> \"codigoMunicipioIBGE\": 5300108,
>
> \"codigo\": 13597,
>
> \"nome\": \"VARA DE EXECU??O FISCAL DO DF\"
>
> },
>
> \"assuntos\": \[
>
> \[
>
> {
>
> \"codigo\": 6017,
>
> \"nome\": \"Dívida Ativa (Execução Fiscal)\"
>
> }
>
> \]
>
> \]
>
> }
>
> },
>
> {
>
> \"\_index\": \"api_publica_tjdft\",
>
> \"\_type\": \"\_doc\",
>
> \"\_id\": \"TJDFT_1116_G1_13597_00073039720138070015\",
>
> \"\_score\": 2.0,
>
> \"\_source\": {
>
> \"classe\": {
>
> \"codigo\": 1116,
>
> \"nome\": \"Execução Fiscal\"
>
> },
>
> \"numeroProcesso\": \"00073039720138070015\",
>
> \"sistema\": {
>
> \"codigo\": 1,
>
> \"nome\": \"Pje\"
>
> },
>
> \"formato\": {
>
> \"codigo\": 1,
>
> \"nome\": \"Eletrônico\"
>
> },
>
> \"tribunal\": \"TJDFT\",
>
> \"dataHoraUltimaAtualizacao\": \"2022-09-06T17:26:23.938Z\",
>
> \"grau\": \"G1\",
>
> \"@timestamp\": \"2023-04-13T18:02:23.754Z\",
>
> \"dataAjuizamento\": \"2019-05-30T03:17:56.000Z\",
>
> \"movimentos\": \[
>
> {
>
> \"complementosTabelados\": \[
>
> {
>
> \"codigo\": 2,
>
> \"valor\": 1,
>
> \"nome\": \"competência exclusiva\",
>
> \"descricao\": \"tipo_de_distribuicao_redistribuicao\"
>
> }
>
> \],
>
> \"codigo\": 26,
>
> \"nome\": \"Distribuição\",
>
> \"dataHora\": \"2013-02-18T13:17:23.000Z\"
>
> },
>
> \...
>
> {
>
> \"codigo\": 245,
>
> \"nome\": \"Provisório\",
>
> \"dataHora\": \"2019-05-30T11:10:02.000Z\"
>
> }
>
> \],
>
> \"id\": \"TJDFT_1116_G1_13597_00073039720138070015\",
>
> \"nivelSigilo\": 0,
>
> \"orgaoJulgador\": {
>
> \"codigoMunicipioIBGE\": 5300108,
>
> \"codigo\": 13597,
>
> \"nome\": \"VARA DE EXECU??O FISCAL DO DF\"
>
> },
>
> \"assuntos\": \[
>
> \[
>
> {
>
> \"codigo\": 6017,
>
> \"nome\": \"Dívida Ativa (Execução Fiscal)\"
>
> }
>
> \],
>
> \[
>
> {
>
> \"codigo\": 10394,
>
> \"nome\": \"Dívida Ativa não-tributária\"
>
> }
>
> \]
>
> \]
>
> }
>
> }
>
> \...
>
> \]
>
> }
>
> }

Esse retorno traz **informações de processos judiciais do TJDFT**.
Separando por categoria:

  -----------------------------------------------------------------------------------
  **Categoria**       **Informação**            **Exemplo**
  ------------------- ------------------------- -------------------------------------
  **Processo**        Número do processo        07223914020178070001

  **Processo**        ID do registro            TJDFT_1116_G1_13597\_\...

  **Classificação**   Código da classe          1116

  **Classificação**   Nome da classe            Execução Fiscal

  **Tribunal**        Tribunal                  TJDFT

  **Jurisdição**      Grau                      G1

  **Sistema**         Sistema judicial          PJe

  **Formato**         Formato do processo       Eletrônico

  **Datas**           Data de ajuizamento       21/08/2017

  **Datas**           Última atualização        06/09/2022

  **Órgão**           Código do órgão julgador  13597

  **Órgão**           Nome do órgão julgador    Vara de Execução Fiscal do DF

  **Localização**     Código IBGE do município  5300108

  **Sigilo**          Nível de sigilo           0

  **Assuntos**        Código do assunto         6017

  **Assuntos**        Nome do assunto           Dívida Ativa (Execução Fiscal)

  **Movimentações**   Código da movimentação    11382

  **Movimentações**   Nome da movimentação      Bloqueio/penhora on line

  **Movimentações**   Data/hora da movimentação 13/07/2022 07:25:59

  **Complementos**    Tipo/descrição            tipo_de_distribuicao_redistribuicao
                      complementar              

  **Complementos**    Valor do complemento      2
  -----------------------------------------------------------------------------------

**[Ex. 3 - Exemplo 3: Pesquisa com paginação (search_after):]{.mark}**

**Por padrão, as pesquisas na API do Elasticsearch retornam até 10
registros por solicitação. No entanto, é possível aumentar o número de
registros retornados utilizando o parâmetro \"size\" de paginação dos
registros. Esse parâmetro permite especificar quantos resultados devem
ser retornados por página, variando de 10 até 10.000 registros por
página.**

**Quando se tem uma necessidade de percorrer uma maior quantidade de
resultados, é possível fazer uso do recurso \"search_after\". Esse
recurso é prioritariamente recomendado para paginação de dados, pois
permite que a API do Datajud continue a partir do ponto onde a última
página parou, sem a necessidade de recarregar todos os resultados a cada
nova página. O \"search_after\" é um ponteiro que aponta para o último
registro retornado na página anterior e pode ser informado como
parâmetro para a próxima solicitação, permitindo que a API retorne os
resultados seguintes.**

**É importante ressaltar que a utilização do \"search_after\" não
prejudica a performance da API na busca de grandes volumes de dados,
pois permite que a API do Datajud execute consultas de forma mais
eficiente, sem a necessidade de recarregar todos os resultados em cada
página. Combinando o uso do parâmetro \"size\" com o \"search_after\", é
possível percorrer grandes volumes de dados de forma eficiente e com
baixo impacto no desempenho da API.**

**Para paginar os resultados utilizando o search_after, é necessário a
utilização da ordenação (sort) dos dados utilizando o
atributo "@timestamp" conforme exemplo abaixo:**

![](./media/image1.png){width="6.970833333333333in"
height="3.3333333333333335in"}

![](./media/image2.png){width="6.741666666666666in"
height="2.5833333333333335in"}Após a primeira consulta, a resposta da
API incluirá um array chamado \"sort\" que contém os valores do campo de
ordenação para cada documento retornado. Esse array pode ser utilizado
como o valor do parâmetro \"search_after\" na próxima consulta,
juntamente com o parâmetro \"size\" que define a quantidade de
documentos a serem retornados na próxima página

Para buscar os próximos 100 processos, basta adicionar o parâmetro
\"search_after\" na próxima consulta, utilizando o valor do campo "sort"
do último documento retornado na página anterior conforme exemplo
abaixo:

![](./media/image3.png){width="6.432554680664917in"
height="3.7903969816272967in"}

Observe que o valor do campo \"search_after\" é um array com os valores
do campo de ordenação para o último documento retornado na página
anterior. É importante lembrar que o \"search_after\" deve ser utilizado
em conjunto com o \"sort\" e o \"size\" para garantir uma paginação
eficiente dos resultados.