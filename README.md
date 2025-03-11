# 📡 **Speednet - API Produtos (Eletro)**  

API para consulta, comparação e obtenção de informações sobre dispositivos eletrônicos.  

📍 **Base URL:**  
```
https://apis.speednetssh.com.br/eletro/api.php
```

## 📌 **Índice**
- [Endpoints](#endpoints)
  - [🔍 Obter Detalhes do Dispositivo](#-obter-detalhes-do-dispositivo)
  - [⚖️ Comparar Dispositivos](#️-comparar-dispositivos)
  - [🔎 Pesquisar Dispositivos](#-pesquisar-dispositivos)
  - [📰 Obter Notícias](#-obter-notícias)
  - [⭐ Obter Reviews](#-obter-reviews)
- [📌 Formato das Respostas](#-formato-das-respostas)
- [📌 Exemplo de Uso](#-exemplo-de-uso)

---

## **Endpoints**  

### 🔍 **Obter Detalhes do Dispositivo**
- **Método:** `GET`
- **Endpoint:**  
  ```
  /eletro/api.php?action=device&id={device_id}
  ```
- **Descrição:** Retorna detalhes de um dispositivo específico.

#### ✅ **Parâmetros**
| Parâmetro | Tipo   | Obrigatório | Descrição                       |
|-----------|--------|-------------|---------------------------------|
| `id`      | `int`  | ✅          | ID único do dispositivo        |

#### 📤 **Exemplo de Requisição**
```bash
curl --location 'https://apis.speednetssh.com.br/eletro/api.php?action=device&id=11089'
```

#### 📥 **Resposta Esperada**
```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "device_information": [
      {
        "device_title": "Apple iPhone 13 Pro Max",
        "device_image": "https://example.com/iphone13.jpg",
        "device_ram": "128GB 6GB",
        "device_price": "$379.99",
        "device_buy_url": "https://www.amazon.com/dp/B09LPF4L55"
      }
    ]
  }
}
```

---

### ⚖️ **Comparar Dispositivos**
- **Método:** `POST`
- **Endpoint:**  
  ```
  /eletro/api.php?action=compare
  ```
- **Descrição:** Compara dois ou mais dispositivos.

#### ✅ **Parâmetros**
| Parâmetro | Tipo  | Obrigatório | Descrição                                     |
|-----------|------|-------------|-----------------------------------------------|
| `key`    | `string` | ✅        | Lista de chaves dos dispositivos separados por vírgula |

#### 📤 **Exemplo de Requisição**
```bash
curl --location 'https://apis.speednetssh.com.br/eletro/api.php?action=compare' \
--header 'Content-Type: application/json' \
--data '{"key": "apple_iphone_13_pro_max-11089,apple_iphone_12_pro_max-11088"}'
```

#### 📥 **Resposta Esperada**
```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "device_information": [
      {
        "device_title": "Apple iPhone 13 Pro Max",
        "device_price": "$379.99"
      },
      {
        "device_title": "Apple iPhone 12 Pro Max",
        "device_price": "$262.30"
      }
    ]
  }
}
```

---

### 🔎 **Pesquisar Dispositivos**
- **Método:** `GET`
- **Endpoint:**  
  ```
  /eletro/api.php?action=search&query={search_query}
  ```
- **Descrição:** Pesquisa dispositivos com base em um termo.

#### ✅ **Parâmetros**
| Parâmetro | Tipo   | Obrigatório | Descrição                       |
|-----------|--------|-------------|---------------------------------|
| `query`  | `string` | ✅        | Termo de pesquisa              |

#### 📤 **Exemplo de Requisição**
```bash
curl --location 'https://apis.speednetssh.com.br/eletro/api.php?action=search&query=iPhone'
```

#### 📥 **Resposta Esperada**
```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "devices": [
      {
        "device_title": "iPhone 13 Pro Max",
        "device_price": "$379.99"
      },
      {
        "device_title": "iPhone 12 Pro Max",
        "device_price": "$262.30"
      }
    ]
  }
}
```

---

### 📰 **Obter Notícias**
- **Método:** `GET`
- **Endpoint:**  
  ```
  /eletro/api.php?action=news
  ```
- **Descrição:** Obtém as últimas notícias de tecnologia.

#### 📤 **Exemplo de Requisição**
```bash
curl --location 'https://apis.speednetssh.com.br/eletro/api.php?action=news'
```

#### 📥 **Resposta Esperada**
```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "news": [
      {
        "title": "Novo iPhone 14 lançado!",
        "image": "https://example.com/news.jpg",
        "link": "https://technews.com/iphone14"
      }
    ]
  }
}
```

---

### ⭐ **Obter Reviews**
- **Método:** `GET`
- **Endpoint:**  
  ```
  /eletro/api.php?action=reviews
  ```
- **Descrição:** Retorna as últimas análises de dispositivos.

#### 📤 **Exemplo de Requisição**
```bash
curl --location 'https://apis.speednetssh.com.br/eletro/api.php?action=reviews'
```

#### 📥 **Resposta Esperada**
```json
{
  "status": 200,
  "message": "Success",
  "data": {
    "reviews": [
      {
        "title": "Review do iPhone 13 Pro Max",
        "image": "https://example.com/review.jpg",
        "link": "https://technews.com/review-iphone13"
      }
    ]
  }
}
```

---

## 📌 **Formato das Respostas**  

Todas as respostas seguem o formato JSON, incluindo:  

- `status`: Código HTTP da requisição.  
- `message`: Mensagem indicando o resultado da requisição.  
- `data`: Conteúdo retornado.  

#### 📥 **Exemplo de Resposta de Erro**
```json
{
  "status": 404,
  "message": "Device not found",
  "data": null
}
```

---

## 📌 **Exemplo de Uso**  

### 1️⃣ Obter detalhes de um dispositivo  
```bash
curl --location 'https://apis.speednetssh.com.br/eletro/api.php?action=device&id=11089'
```

### 2️⃣ Comparar dois dispositivos  
```bash
curl --location 'https://apis.speednetssh.com.br/eletro/api.php?action=compare' \
--header 'Content-Type: application/json' \
--data '{"key": "device1,device2"}'
```

### 3️⃣ Pesquisar dispositivos  
```bash
curl --location 'https://apis.speednetssh.com.br/eletro/api.php?action=search&query=iPhone'
```

### 4️⃣ Obter notícias  
```bash
curl --location 'https://apis.speednetssh.com.br/eletro/api.php?action=news'
```

---

📢 **Contribuição:** Caso tenha sugestões ou encontre bugs, envie um PR ou issue no repositório. 🚀
