[**Datajud-Wiki**](https://datajud-wiki.cnj.jus.br/)

URL: https://datajud-wiki.cnj.jus.br/api-publica/exemplos/exemplo2

**API Key**

Authentication for the Datajud Public API is done through a
**Public Key**, generated and made available by the DPJ/CNJ. The
current key will always be accessible in this section of the Wiki,
ensuring transparency and making it easier to access. It's important
to note that, for security and system management reasons, the key
may be changed by the CNJ at any time.

To include the API Key in your requests, use the format
"Authorization: APIKey [Public Key]" in the request header.

-   **Current APIKey**:

    -   Authorization:
        APIKey **cDZHYzlZa0JadVREZDJCendQbXY6SkJlTzNjLV9TRENyQk1RdnFKZGRQdw==**

**POST /api_publica_tribunal/_search**

1.  Open **Postman** and click *"New Request"*.

2.  Set the HTTP method to POST.

3.  Enter the
    URL: <https://api-publica.datajud.cnj.jus.br/api_publica_trf1/_search>

4.  Select the *"Headers"* tab and add the key "Authorization" with
    the value "APIKey [Public Key]";

5.  The [Public Key] value corresponds to the public key available
    at [Public
    Key](https://datajud-wiki.cnj.jus.br/api-publica/exemplos/api-publica/acesso);

6.  Still in *"Headers"*, add the key "Content-Type" with the value
    "application/json";

7.  Select the *"Body"* tab and choose the *"raw"* option. Enter the
    JSON request body as shown in the example below:

**[Ex. 1 - Search by process number]{.mark}**

## Query DSL

```json
{
  "query": {
    "match": {
      "numeroProcesso": "00008323520184013202"
    }
  }
}


8.  Click *Send* to submit and wait for the API's response.

**Response**

The expected response is a JSON with the metadata of 1 or more
processes according to the search criteria:

## Expected Response

```json
{
  "took": 6679,
  "timed_out": false,
  "_shards": {
    "total": 7,
    "successful": 7,
    "skipped": 0,
    "failed": 0
  },
  "hits": {
    "total": {
      "value": 1,
      "relation": "eq"
    },
    "max_score": 13.917725,
    "hits": [
      {
        "_index": "api_publica_trf1",
        "_type": "_doc",
        "_id": "TRF1_436_JE_16403_00008323520184013202",
        "_score": 13.917725,
        "_source": {
          "numeroProcesso": "00008323520184013202",
          "classe": {
            "codigo": 436,
            "nome": "Procedimento do Juizado Especial Cível"
          },
          "sistema": { "codigo": 1, "nome": "Pje" },
          "formato": { "codigo": 1, "nome": "Eletrônico" },
          "tribunal": "TRF1",
          "dataHoraUltimaAtualizacao": "2023-07-21T19:10:08.483Z",
          "grau": "JE",
          "@timestamp": "2023-08-14T11:50:51.994Z",
          "dataAjuizamento": "2018-10-29T00:00:00.000Z",
          "movimentos": [
            {
              "complementosTabelados": [
                {
                  "codigo": 2,
                  "valor": 1,
                  "nome": "competência exclusiva",
                  "descricao": "tipo_de_distribuicao_redistribuicao"
                }
              ],
              "codigo": 26,
              "nome": "Distribuição",
              "dataHora": "2018-10-30T14:06:24.000Z"
            },
            {
              "codigo": 14732,
              "nome": "Conversão de Autos Físicos em Eletrônicos",
              "dataHora": "2020-08-05T01:15:18.000Z"
            }
          ],
          "id": "TRF1_436_JE_16403_00008323520184013202",
          "nivelSigilo": 0,
          "orgaoJulgador": {
            "codigoMunicipioIBGE": 5128,
            "codigo": 16403,
            "nome": "JEF Adj - Tefé"
          },
          "assuntos": [
            { "codigo": 6177, "nome": "Concessão" }
          ]
        }
      }
    ]
  }
}

>
> This second JSON is from TRF1, and it has a structure very similar
> to that of TJDFT. In this case, it found exactly 1 process.
>
> Available information

| **Field**             | **Information found**                          |
|------------------------|-----------------------------------------------|
| **Court**              | TRF1                                          |
| **Process number**     | 00008323520184013202                          |
| **Class**              | Procedimento do Juizado Especial Cível        |
| **Class code**         | 436                                           |
| **System**             | PJe                                           |
| **Format**             | Electronic                                    |
| **Level (instance)**   | JE — Small Claims Court                       |
| **Filing date**        | 10/29/2018                                    |
| **Last update**        | 07/21/2023                                    |
| **Confidentiality**    | 0                                             |
| **Judging body**       | JEF Adj - Tefé                                |
| **Body code**          | 16403                                         |
| **IBGE municipality**  | 5128                                          |
| **Subject**            | Concessão (Grant)                             |
| **Subject code**       | 6177                                          |
| **Movements**          | Process event history                         |
| **Complements**        | Additional movement information               |
| **Internal ID**        | TRF1_436_JE_16403_00008323520184013202        |


> **[Ex. 2 - Search by Process Class and Judging Body]{.mark}**
>
> In the example below, a query is performed for processes with
> Process Class 1116 -- "Execução Fiscal" (Tax Enforcement) from the
> Judging Body 13597 - VARA DE EXECUÇÃO FISCAL DO DF, in the TJDFT
> court.

1.  Open **Postman** and click *"New Request"*.

2.  Set the HTTP method to POST.

3.  Enter the
    URL: <https://api-publica.datajud.cnj.jus.br/api_publica_tjdft/_search>

4.  Select the *"Headers"* tab and add the key "Authorization" with
    the value "APIKey [Public Key]";

5.  The [Public Key] value corresponds to the public key available
    at [Public
    Key](https://datajud-wiki.cnj.jus.br/api-publica/exemplos/api-publica/acesso);

6.  Still in *"Headers"*, add the key "Content-Type" with the value
    "application/json";

7.  Select the *"Body"* tab and choose the *"raw"* option. Enter the
    JSON request body as shown in the example below:

## Query DSL

```json
{
  "query": {
    "bool": {
      "must": [
        { "match": { "classe.codigo": 1116 } },
        { "match": { "orgaoJulgador.codigo": 13597 } }
      ]
    }
  }
}


> **Response**
>
> The expected response is a JSON with the metadata of 1 or more
> processes according to the search criteria:

{
  "took": 213,
  "timed_out": false,
  "_shards": {
    "total": 3,
    "successful": 3,
    "skipped": 0,
    "failed": 0
  },
  "hits": {
    "total": {
      "value": 10000,
      "relation": "gte"
    },
    "max_score": 2.0,
    "hits": [
      {
        "_index": "api_publica_tjdft",
        "_type": "_doc",
        "_id": "TJDFT_1116_G1_13597_07223914020178070001",
        "_score": 2.0,
        "_source": {
          "classe": { "codigo": 1116, "nome": "Execução Fiscal" },
          "numeroProcesso": "07223914020178070001",
          "sistema": { "codigo": 1, "nome": "Pje" },
          "formato": { "codigo": 1, "nome": "Eletrônico" },
          "tribunal": "TJDFT",
          "dataHoraUltimaAtualizacao": "2022-09-06T12:03:20.257Z",
          "grau": "G1",
          "@timestamp": "2023-04-13T17:59:46.214Z",
          "dataAjuizamento": "2017-08-21T10:05:32.000Z",
          "movimentos": [
            {
              "complementosTabelados": [
                {
                  "codigo": 2,
                  "valor": 2,
                  "nome": "sorteio",
                  "descricao": "tipo_de_distribuicao_redistribuicao"
                }
              ],
              "codigo": 26,
              "nome": "Distribuição",
              "dataHora": "2017-08-21T10:05:32.000Z"
            },
            { "codigo": 11382, "nome": "Bloqueio/penhora on line", "dataHora": "2022-07-13T07:25:59.000Z" },
            { "codigo": 132, "nome": "Recebimento", "dataHora": "2022-07-13T07:26:00.000Z" }
          ],
          "id": "TJDFT_1116_G1_13597_07223914020178070001",
          "nivelSigilo": 0,
          "orgaoJulgador": {
            "codigoMunicipioIBGE": 5300108,
            "codigo": 13597,
            "nome": "VARA DE EXECUÇÃO FISCAL DO DF"
          },
          "assuntos": [
            [ { "codigo": 6017, "nome": "Dívida Ativa (Execução Fiscal)" } ]
          ]
        }
      },
      {
        "_index": "api_publica_tjdft",
        "_type": "_doc",
        "_id": "TJDFT_1116_G1_13597_00073039720138070015",
        "_score": 2.0,
        "_source": {
          "classe": { "codigo": 1116, "nome": "Execução Fiscal" },
          "numeroProcesso": "00073039720138070015",
          "sistema": { "codigo": 1, "nome": "Pje" },
          "formato": { "codigo": 1, "nome": "Eletrônico" },
          "tribunal": "TJDFT",
          "dataHoraUltimaAtualizacao": "2022-09-06T17:26:23.938Z",
          "grau": "G1",
          "@timestamp": "2023-04-13T18:02:23.754Z",
          "dataAjuizamento": "2019-05-30T03:17:56.000Z",
          "movimentos": [
            {
              "complementosTabelados": [
                {
                  "codigo": 2,
                  "valor": 1,
                  "nome": "competência exclusiva",
                  "descricao": "tipo_de_distribuicao_redistribuicao"
                }
              ],
              "codigo": 26,
              "nome": "Distribuição",
              "dataHora": "2013-02-18T13:17:23.000Z"
            },
            { "codigo": 245, "nome": "Provisório", "dataHora": "2019-05-30T11:10:02.000Z" }
          ],
          "id": "TJDFT_1116_G1_13597_00073039720138070015",
          "nivelSigilo": 0,
          "orgaoJulgador": {
            "codigoMunicipioIBGE": 5300108,
            "codigo": 13597,
            "nome": "VARA DE EXECUÇÃO FISCAL DO DF"
          },
          "assuntos": [
            [ { "codigo": 6017, "nome": "Dívida Ativa (Execução Fiscal)" } ],
            [ { "codigo": 10394, "nome": "Dívida Ativa não-tributária" } ]
          ]
        }
      }
    ]
  }
}


This response brings **information on TJDFT court cases**.
Broken down by category:

 | **Category**        | **Information**           | **Example**                                |
|---------------------|---------------------------|--------------------------------------------|
| **Process**         | Process number            | 07223914020178070001                       |
| **Process**         | Record ID                 | TJDFT_1116_G1_13597_...                    |
| **Classification**  | Class code                | 1116                                       |
| **Classification**  | Class name                | Execução Fiscal (Tax Enforcement)          |
| **Court**           | Court                     | TJDFT                                      |
| **Jurisdiction**    | Level (instance)          | G1                                         |
| **System**          | Judicial system           | PJe                                        |
| **Format**          | Process format            | Electronic                                 |
| **Dates**           | Filing date               | 08/21/2017                                 |
| **Dates**           | Last update               | 09/06/2022                                 |
| **Body**            | Judging body code         | 13597                                      |
| **Body**            | Judging body name         | Vara de Execução Fiscal do DF              |
| **Location**        | IBGE municipality code    | 5300108                                    |
| **Confidentiality** | Confidentiality level     | 0                                          |
| **Subjects**        | Subject code              | 6017                                       |
| **Subjects**        | Subject name              | Dívida Ativa (Execução Fiscal)             |
| **Movements**       | Movement code             | 11382                                      |
| **Movements**       | Movement name             | Bloqueio/penhora on line                   |
| **Movements**       | Movement date/time        | 07/13/2022 07:25:59                        |
| **Complements**     | Type/description          | tipo_de_distribuicao_redistribuicao        |
| **Complements**     | Complement value          | 2                                          |


**[Ex. 3 - Example 3: Search with pagination (search_after):]{.mark}**

**By default, searches in the Elasticsearch API return up to 10
records per request. However, it's possible to increase the number of
records returned using the "size" pagination parameter. This
parameter allows you to specify how many results should be returned
per page, ranging from 10 up to 10,000 records per page.**

**When there is a need to go through a larger amount of results, it
is possible to use the "search_after" feature. This feature is the
recommended approach for data pagination, as it allows the Datajud
API to continue from where the last page left off, without needing
to reload all the results on each new page. The "search_after" is a
pointer that references the last record returned on the previous
page and can be passed as a parameter for the next request, allowing
the API to return the following results.**

**It's important to note that using "search_after" does not hurt the
API's performance when searching large volumes of data, since it
allows the Datajud API to run queries more efficiently, without
needing to reload all the results on each page. Combining the "size"
parameter with "search_after" makes it possible to go through large
volumes of data efficiently and with low impact on the API's
performance.**

**To paginate results using search_after, it is necessary to sort
the data using the "@timestamp" attribute, as shown in the example
below:**

![](./media/image1.png){width="6.970833333333333in"
height="3.3333333333333335in"}

![](./media/image2.png){width="6.741666666666666in"
height="2.5833333333333335in"}After the first query, the API's
response will include an array called "sort" that contains the
values of the sort field for each document returned. This array can
be used as the value of the "search_after" parameter in the next
query, together with the "size" parameter that defines the number of
documents to be returned on the next page.

To fetch the next 100 processes, simply add the "search_after"
parameter to the next query, using the value of the "sort" field
from the last document returned on the previous page, as shown in
the example below:

![](./media/image3.png){width="6.432554680664917in"
height="3.7903969816272967in"}

Note that the value of the "search_after" field is an array with the
sort field values for the last document returned on the previous
page. It's important to remember that "search_after" must be used
together with "sort" and "size" to ensure efficient pagination of
results.