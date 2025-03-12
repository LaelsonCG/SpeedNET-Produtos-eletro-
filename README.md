# 📡 **Speednet - API Produtos (Eletro)**  

API para consulta, comparação e obtenção de informações sobre dispositivos eletrônicos.

---

## **Documentação da API**

### **1. Listar Dispositivos**

**URL**:  
`https://apis.speednetssh.com.br/eletro/api.php?action=device-list`

**Método**:  
`GET`

**Parâmetros**:  
Nenhum.

**Descrição**:  
Retorna a lista de dispositivos disponíveis, incluindo o nome da marca, ID da marca e os dispositivos com seus respectivos detalhes.

**Exemplo de resposta**:
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
        }
        ...
      ]
    }
  ]
}
```

---

### **2. Pesquisa de Dispositivos**

**URL**:  
`https://apis.speednetssh.com.br/eletro/api.php?action=search&query={query}`

**Método**:  
`GET`

**Parâmetros**:
- `query` (obrigatório): Termo de busca para pesquisar dispositivos.

**Descrição**:  
Retorna a lista de dispositivos que correspondem ao termo de pesquisa fornecido.

**Exemplo de requisição**:
```bash
GET https://apis.speednetssh.com.br/eletro/api.php?action=search&query=Samsung%20tab%20s7+
```

**Exemplo de resposta**:
```json
{
  "status": 200,
  "message": "Success",
  "data": [
    {
      "device_id": 13688,
      "device_name": "Samsung Galaxy Tab S7+",
      "device_type": "Tablet",
      "device_image": "https://example.com/samsung-tab-s7+.jpg",
      "key": "samsung_tab_s7+-13688"
    }
  ]
}
```

---

### **Erros Comuns**

- **400 Bad Request**: Quando o parâmetro `query` não é fornecido para a pesquisa.
- **500 Internal Server Error**: Quando ocorre um erro ao fazer a requisição ou processar a resposta.

---

