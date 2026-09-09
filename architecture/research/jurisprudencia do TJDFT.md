# Documentação da API Pública de Consulta à Jurisprudência do TJDFT

## Finalidade

A API de jurisprudência do TJDFT tem como finalidade oferecer um ponto de acesso estruturado e padronizado aos acórdãos e decisões disponíveis para consulta pública, promovendo transparência, acessibilidade e eficiência. Por meio dela, usuários podem realizar consultas programáticas utilizando termos de pesquisa e filtros específicos. A API é especialmente útil para outros tribunais, pesquisadores, advogados e desenvolvedores que desejam integrar suas aplicações ou rotinas de análise de dados.

## Endpoint

```
POST https://jurisdf.tjdft.jus.br/api/v1/pesquisa
```

## Formato da Requisição

A requisição deve ser enviada com o método `POST` e corpo em JSON.

### Parâmetros obrigatórios

| Parâmetro | Descrição | Tipo |
|---|---|---|
| `query` | Termo principal da pesquisa | string |
| `pagina` | Número da página | inteiro (começando do 0) |
| `tamanho` | Número de resultados por página | inteiro |

### Parâmetro opcional

- **`termosAcessorios`**: lista de filtros adicionais, cada um com:
  - `campo`: nome do campo (string)
  - `valor`: valor do filtro (string ou data)

## Campos disponíveis para filtros (`termosAcessorios`)

Os filtros devem ser passados dentro do array `termosAcessorios`. Os únicos campos permitidos são:

| Campo | Descrição |
|---|---|
| `base` | Base de dados da decisão |
| `subbase` | Subbase de dados |
| `origem` | Origem da decisão |
| `uuid` | Identificador UUID da decisão |
| `identificador` | Identificador da decisão |
| `identificadorOrdenacao` | Identificador para ordenação |
| `processo` | Número do processo |
| `nomeRelator` | Nome do relator |
| `nomeRevisor` | Nome do revisor |
| `nomeRelatorDesignado` | Nome do relator designado |
| `descricaoOrgaoJulgador` | Nome do órgão julgador |
| `dataJulgamento` | Data do julgamento (formato: `YYYY-MM-DD`) |
| `dataPublicacao` | Data da publicação (formato: `YYYY-MM-DD`) |
| `descricaoClasseCnj` | Classe processual CNJ |

## Exemplo de Requisição JSON

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

## Exemplo de Resposta JSON

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

## Observações

- O campo `hits` representa a quantidade total de decisões encontradas para os critérios de busca utilizados.
- O campo `agregações` traz a lista de relatores, revisores e órgãos julgadores, possibilitando que o usuário da API conheça o domínio dos filtros.