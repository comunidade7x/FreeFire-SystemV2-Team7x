# Free Fire Apis For 7x'

Documentação dos endpoints HTTP públicos, com exemplos reais de requisição e resposta em **JSON**.

**Base URL**
```
https://7xhub-api.squareweb.app
```

---

## 🔥 Endpoints Gráficos & Status

<div align="center">
  <table>
    <tr>
      <th style="color:#00BFFF;">Numeração</th>
      <th style="color:#FFD700;">GET</th>
      <th style="color:#00BFFF;">Status</th>
    </tr>
    <tr>
      <td>#1</td>
      <td><b>/api/v2/search-player</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#2</td>
      <td><b>/api/v2/info-player</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#3</td>
      <td><b>/api/v2/search-guilda</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#4</td>
      <td><b>/api/v2/lista-desejos</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#5</td>
      <td><b>/api/v2/info-token</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#6</td>
      <td><b>/api/v2/tabela-pontos</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#7</td>
      <td><b>/api/v2/ranking-passe</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#8</td>
      <td><b>/api/v2/ranking-passe-global</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#9</td>
      <td><b>/api/v2/check-ban</b></td>
      <td>🟡 Manutenção</td>
    </tr>
    <tr>
      <td>#10</td>
      <td><b>/api/v2/version</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#11</td>
      <td><b>/api/v2/carteira-player</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#12</td>
      <td><b>/api/v2/carreira-cs</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#13</td>
      <td><b>/api/v2/carreira-br</b></td>
      <td>🟢 Online</td>
    </tr>
    <tr>
      <td>#14</td>
      <td><b>/api/v2/like</b></td>
      <td>🟢 Online</td>
    </tr>
  </table>
</div>

---


## 1) Buscar jogador por **Nickname**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/search-player?nickname=regis7x&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "quantidadeContas": 1,
  "contas": [
    {
      "idConta": "4245685047",
      "tipoConta": 1,
      "idEmblema": 1001000088,
      "idBanner": null,
      "idClan": null,
      "nomeClan": null,
      "nivel": 8,
      "experiencia": 4110,
      "curtidas": 19,
      "apelido": "regiskkkj",
      "regiao": "BR",
      "rank": 301,
      "pontosRank": 1000,
      "csRank": 301,
      "pontosCsRank": null,
      "ultimaVezOnline": "1681263139",
      "temporadaId": 47,
      "pinId": null
    }
  ]
}
```

**Erros**
- 404 `{
  "dev": "#Regiis7x",
  "mensagem": "404 - Jogador não encontrado",
  "sucesso": false
  }`
- 500 `{ erro: "Erro interno do servidor" }`
---

## 2) Informações do jogador (por **UID**)
**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/info-player?uid=1033857091&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "jogador": {
    "Foto": [
      "https://files.catbox.moe/p1t2q7.png",
      "https://files.catbox.moe/ehj2kh.jpeg"
    ],
    "infoBasica": {
      "accountId": "1033857091",
      "nickname": "@Totosoㅤ7x'",
      "region": "BR",
      "level": 71,
      "headPic": 902000121,
      "bannerId": 901000253,
      "avatars": null,
      /* demais campos da infoBasica */
    },
    "infoCapitao": { 
      /* todos os campos do infoCapitao */ 
    },
    "infoGuilda": { 
      /* todos os campos do infoGuilda */ 
    },
    "infoPontuacao": { 
      /* todos os campos do infoPontuacao */ 
    },
    "custoDiamantes": { 
      /* todos os campos do custoDiamantes */ 
    },
    "infoPet": { 
      /* todos os campos do infoPet */ 
    },
    "infoPerfil": { 
      /* todos os campos do infoPerfil incluindo roupas e habilidades */ 
    },
    "infoSocial": { 
      /* todos os campos do infoSocial */ 
    }
  }
}
```

**Erros**
- 404 `{
  "dev": "#Regiis7x",
  "mensagem": "404 - Jogador não encontrado",
  "sucesso": false
}`
- 500 `{ erro: "Erro interno do servidor" }`
---

## 3) Buscar **Guilda** por ID
**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/search-guilda?id=2056294718&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "guilda": {
    "idGuilda": "2056294718",
    "nomeGuilda": "Equipeㅤ7x'ㅤ☕",
    "nivelGuilda": 3,
    "idCapitao": "1033857091",
    "viceCapitaes": "[]",
    "capacidade": 30,
    "membrosAtuais": 8,
    "regiao": "BR",
    "entradaNivel": 50,
    "entradaRank": 19,
    "tipoEntrada": 2,
    "idEmblema": 1755814175,
    "idQuadro": 14,
    "inativos": 3726,
    "slogan": "Receba as boas-vindas!",
    "criadoEm": "1738886718",
    "ultimaModificacaoAviso": "20107",
    "usaEmblemaCustomizado": true
  }
}
```

**Erros**:
- 404 `{
  "dev": "#Regiis7x",
  "mensagem": "404 - Guilda não encontrada",
  "sucesso": false
}`.
- 500 `{ erro: "Erro interno do servidor" }`
---

## 4) **Lista do desejo** (itens do jogador)

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/lista-desejos?uid=1033857091&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "quantidade": 5,
  "wishlist": [
    {
      "itemId": 902000003,
      "releaseTime": "1749140626"
    },
    {
      "itemId": 909000006,
      "releaseTime": "1738622758"
    },
    {
      "itemId": 909035005,
      "releaseTime": "1738622975"
    },
    {
      "itemId": 909039014,
      "releaseTime": "1738623117"
    },
    {
      "itemId": 909045010,
      "releaseTime": "1738623338"
    }
  ]
}
```
**Erros**:
- 404 `{
  "dev": "#Regiis7x",
  "mensagem": "404 - Lista de desejos não encontrada",
  "sucesso": false
}`
- 500 `{ erro: "Erro interno do servidor" }`
---

## 5) **Inspecionar token**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/info-token?access_token=XXXX&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "tokenWeb": {
    "mensagem": "Informações do WebToken obtidas com sucesso",
    "experienciaJogador": 3356434,
    "idJogador": 1033857091,
    "nivelJogador": 71,
    "nicknameJogador": "@Totosoㅤ7x'",
    "regiaoJogador": "BR"
  },
  "tokenGame": {
    "mensagem": "Informações do token do jogo obtidas com sucesso",
    "infoBasicaToken": {
      "appId": 000000,
      "criadoEm": 1757252623,
      "expiraEm": 1762436630,
      "plataformaLogin": 11,
      "tipoLogin": 1,
      "plataformaPrincipalAtiva": 11,
      "openId": "XXXXXXX-XXXXXXX-XXXXX",
      "plataforma": 3,
      "escopos": [
        "get_user_info",
        "get_friends",
        "payment",
        "send_request"
      ],
      "uid": 118544852727996
    }
  }
}
```
**Erros**:
- 401 `{
  "dev": "#Regiis7x",
  "mensagem": "Token inválido",
  "sucesso": false
}`
- 500 `{ erro: "Erro interno do servidor" }`
---

## 6) **Tabela de classificação (Pontos)**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/tabela-pontos?auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "quantidade": 2,
  "leaderboard": [
    {
      "idJogador": "12345678",
      "nickname": "JogadorX",
      "pontos": 4500,
      "posicao": 1
    },
    {
      "idJogador": "87654321",
      "nickname": "JogadorY",
      "pontos": 4300,
      "posicao": 2
    }
  ]
}
```
**Erros**:
- 400 `{
  "dev": "#Regiis7x",
  "mensagem": "Região não implementada",
  "sucesso": false
}`
- 404 `{
  "dev": "#Regiis7x",
  "mensagem": "Nenhum jogador encontrado",
  "sucesso": false
}`
- 500 `{ erro: "Erro interno do servidor" }`
---

## 7) **Ranking Passe (Regional)**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/ranking-passe?auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "quantidade": 2,
  "leaderboardPass": [
    {
      "nickname": "JogadorX",
      "passLevel": 8200,
      "posicao": 1,
      "regiao": "BR"
    },
    {
      "nickname": "JogadorY",
      "passLevel": 7800,
      "posicao": 2,
      "regiao": "BR"
    }
  ]
}
```
**Erros**:
- 404 `{
  "dev": "#Regiis7x",
  "mensagem": "Nenhum jogador encontrado",
  "sucesso": false
}`
- 500 `{ erro: "Erro interno do servidor" }`
---

## 8) **Ranking Passe (Global)**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/ranking-passe-global?auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "quantidade": 2,
  "leaderboardPass": [
    {
      "nickname": "JogadorX",
      "passLevel": 55555,
      "posicao": 1,
      "regiao": "BR"
    },
    {
      "nickname": "JogadorY",
      "passLevel": 15542,
      "posicao": 2,
      "regiao": "US"
    }
  ]
}
```
**Erros**:
- 404 `{
  "dev": "#Regiis7x",
  "mensagem": "Nenhum jogador encontrado",
  "sucesso": false
}`
- 500 `{ erro: "Erro interno do servidor" }`
---

## 9) **Check ban**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/check-ban?uid=1033857091&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "jogador": {
    "nivel": 71,
    "curtidas": 7507,
    "nickname": "@Totosoㅤ7x'",
    "regiao": "BR",
    "periodoBan": 0,
    "estaBanido": "no"
  }
}
```
**Erros**:
- 502/503 `{
  "dev": "#Regiis7x",
  "mensagem": "Erro interno do servidor",
  "sucesso": false
}`
---

## 10) **Versão do jogo/servidor**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/version?auth=SEU_TOKEN_API
```


**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "versaoFF": {
    "versaoRelease": "OB50",
    "urlServidor": "https://...",
    "versaoCliente": "..."
  },
  "statusServidor": {
    "emRevisao": false/true,
    "servidorAberto": true/false,
    "versaoServidor": "..."
  }
}
```
**Erros**:
- 502/503 `{
  "dev": "#Regiis7x",
  "mensagem": "Erro interno do servidor",
  "sucesso": false
}`
---

## 11) **Carteira do jogador**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/carteira-player?access_token=XXXXX&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "diamantesAtuais": 5,
  "ouroAtual": 867,
  "ultimoRecarregadoEm": "1756043254",
  "nickname": "@Totosoㅤ7x'",
  "totalDiamantes": "14953"
}
```

**Erros**:
- 401 `{
  "dev": "#Regiis7x",
  "mensagem": "Token de acesso inválido",
  "sucesso": false
}`
- 500 `{ erro: "Erro interno do servidor" }`
---

## 12) **Carreira do CS**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/carreira-cs?uid=1033857091&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "uid": "1033857091",
  "stats": {
    "clash_squad": { "..." : "..." },
    "cs_career": { "..." : "..." },
    "cs_ranked": { "..." : "..." }
  }
}
```
**Erros**:
- 500 `500 { erro: "Erro interno do servidor" }`
- 400/403/404 `{ erro: "mensagem erro" }`
---
## 13) **Carreira do BR**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/carreira-br?uid=1033857091&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "dev": "#Regiis7x",
  "sucesso": true,
  "uid": "1033857091",
  "stats": {
    "BR_CAREER": {
      "solo_stats": { "...": "..." },
      "duo_stats": { "...": "..." },
      "squad_stats": { "...": "..." }
    },
    "BR_CLASSIC": {
      "solo_stats": {
        "detailed_stats": { "...": "..." }
      },
      "duo_stats": {
        "detailed_stats": { "...": "..." }
      },
      "squad_stats": {
        "detailed_stats": { "...": "..." }
      }
    },
    "BR_RANKED": {
      "solo_stats": { "...": "..." },
      "duo_stats": { "...": "..." },
      "squad_stats": { "...": "..." }
    }
  }
}
```
**Erros**:
- 500 `500 { erro: "Erro interno do servidor" }`
- 400/403/404 `{ erro: "mensagem erro" }`
--
## 14) **Likes Diários**

**Exemplo**
```
GET https://7xhub-api.squareweb.app/api/v2/like?uid=1033857091&auth=SEU_TOKEN_API
```

**Resposta (200)**
```json
{
  "status": "success",
  "mensagem": "Likes processados com sucesso.",
  "data": {
    "player": {
      "nickname": "@Totosoㅤ7x'",
      "region": "BR",
      "level": 72,
      "exp": "3,373,088",
      "uid": "1033857091"
    },
    "likes": {
      "antes": "8,482",
      "depois": "8,482",
      "adicionados": "0",
      "limite_diario": "✅"
    }
  }
}
```
**Erros**:
- 404 `{"status":"not_found","mensagem":"Não foi possível localizar o jogador com o UID fornecido."}`
- 500 `500 { erro: "Erro interno do servidor" }`
