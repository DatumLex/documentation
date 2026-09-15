# TJDFT Public Jurisprudence Query API Documentation

## Purpose

The TJDFT Jurisprudence API provides a structured and standardized access point to publicly available appellate decisions and rulings, promoting transparency, accessibility, and efficiency. Through the API, users can perform programmatic queries using search terms and specific filters. The API is particularly useful for other courts, researchers, lawyers, and developers who want to integrate TJDFT jurisprudence data into their applications or data analysis workflows.

## Endpoint

```text
POST https://jurisdf.tjdft.jus.br/api/v1/pesquisa
```

## Request Format

The request must be sent using the `POST` method with a JSON body.

### Required Parameters

| Parameter | Description                | Type                      |
| --------- | -------------------------- | ------------------------- |
| `query`   | Main search term           | string                    |
| `pagina`  | Page number                | integer (starting from 0) |
| `tamanho` | Number of results per page | integer                   |

### Optional Parameter

* **`termosAcessorios`**: list of additional filters, each containing:

  * `campo`: field name (string)
  * `valor`: filter value (string or date)

## Available Filter Fields (`termosAcessorios`)

Filters must be provided inside the `termosAcessorios` array. The only allowed fields are:

| Field                    | Description                             |
| ------------------------ | --------------------------------------- |
| `base`                   | Decision database                       |
| `subbase`                | Decision database subcategory           |
| `origem`                 | Origin of the decision                  |
| `uuid`                   | UUID identifier of the decision         |
| `identificador`          | Decision identifier                     |
| `identificadorOrdenacao` | Identifier used for sorting             |
| `processo`               | Case number                             |
| `nomeRelator`            | Judge rapporteur's name                 |
| `nomeRevisor`            | Reviewing judge's name                  |
| `nomeRelatorDesignado`   | Designated rapporteur's name            |
| `descricaoOrgaoJulgador` | Name of the adjudicating panel          |
| `dataJulgamento`         | Judgment date (format: `YYYY-MM-DD`)    |
| `dataPublicacao`         | Publication date (format: `YYYY-MM-DD`) |
| `descricaoClasseCnj`     | CNJ procedural class                    |

## JSON Request Example

```json
{
  "query": "Dano moral",
  "termosAcessorios": [
    {
      "campo": "nomeRelator",
      "valor": "CARMEN BITTENCOURT"
    }
  ],
  "pagina": 0,
  "tamanho": 10
}
```

## JSON Response Example

```json
{
  "hits": 1234,
  "agregações": {},
  "paginação": {},
  "registros": [
    {
      "sequencial": 1,
      "base": "decisoes",
      "subbase": "decisoes-monocraticas",
      "uuid": "29df78c5-af48-48ee-b8f4-7db0bea4cff6",
      "identificador": "70016492",
      "dataPublicacao": "2025-03-25T03:00:00.000Z",
      "ementa": "[texto extenso omitido]",
      "processo": "0710649-40.2025.8.07.0000",
      "nomeRelator": "CARMEN BITTENCOURT",
      "descricaoOrgaoJulgador": "8ª Turma Cível",
      "versao": "1",
      "codigoClasseCnj": 202,
      "codigoSistjOrgaoJulgador": 68,
      "inteiroTeor": "[texto extenso omitido]",
      "marcadores": {
        "ementa": ["[texto extenso omitido]"],
        "termosAuxiliares": [],
        "decisao": []
      },
      "jurisprudenciaEmFoco": [],
      "descricaoOrgao": "8ª Turma Cível",
      "possuiInteiroTeor": false
    }
  ]
}
```

## Notes

* The `hits` field represents the total number of decisions found for the search criteria used.
* The `agregações` field provides a list of rapporteurs, reviewing judges, and adjudicating panels, allowing the API user to identify the available filter domains.
