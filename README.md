# 📡 **Speednet - API Produtos (Eletro)**  

API para consulta, comparação e obtenção de informações sobre dispositivos eletrônicos.

## Endpoints

### `GET /eletro/api.php?action=device-list`

Retorna a lista de dispositivos de acordo com as informações obtidas da API do Google.

#### Parâmetros de consulta

- **action**: Ação a ser realizada pela API. O valor esperado é `device-list`.

#### Exemplo de requisição

```bash
GET https://apis.speednetssh.com.br/eletro/api.php?action=device-list
```

#### Exemplo de resposta

```json
{
  "status": 200,
  "message": "Success",
  "data": [
    {
      "brand_id": 1,
      "brand_name": "Nokia",
      "key": "nokia",
      "device_list": [
        {
          "device_id": 13688,
          "device_name": "150 Music",
          "device_type": "150Music 150M",
          "device_image": "https://fdn2.gsmarena.com/vv/bigpic/nokia-150-music-2025.jpg",
          "key": "nokia_150_music-13688"
        },
        {
          "device_id": 12381,
          "device_name": "G42",
          "device_type": "5G Notch g42 5g",
          "device_image": "https://fdn2.gsmarena.com/vv/bigpic/nokia-g42-5g.jpg",
          "key": "nokia_g42-12381"
        },
        {
          "device_id": 12139,
          "device_name": "C32",
          "device_type": "Notch",
          "device_image": "https://fdn2.gsmarena.com/vv/bigpic/nokia-c32-2023.jpg",
          "key": "nokia_c32-12139"
        }
      ]
    }
  ]
}
```

### Descrição dos Campos

#### Raiz da Resposta

- **status**: Código HTTP de status da resposta. Um valor de `200` indica sucesso.
- **message**: Mensagem descritiva sobre o status da resposta. Exemplo: `"Success"`.
- **data**: Lista de marcas e dispositivos.

#### Detalhes de cada Marca

- **brand_id**: ID único da marca.
- **brand_name**: Nome da marca do fabricante.
- **key**: Chave única da marca, usada para filtrar ou identificar a marca.
- **device_list**: Lista de dispositivos associados à marca.

#### Detalhes de cada Dispositivo

- **device_id**: ID único do dispositivo.
- **device_name**: Nome do dispositivo.
- **device_type**: Tipo do dispositivo (opcional).
- **device_image**: URL da imagem do dispositivo.
- **key**: Chave única do dispositivo.

---

## Como usar

1. Faça uma requisição `GET` para o endpoint `/eletro/api.php?action=device-list`.
2. A resposta será um JSON contendo a lista de dispositivos agrupada por marca.
3. Para adicionar mais funcionalidades, basta expandir o arquivo `api.php` com novas rotas e lógica.
---
