
# Locadora de Veículos - Projeto MongoDB

Este repositório demonstra a modelagem e exploração de dados de uma locadora de veículos utilizando o banco de dados NoSQL MongoDB.

---

## 🗃️ Estrutura das Coleções

### **1. clientes**
Contém os dados dos clientes:
```json
{
  "codcliente": 1,
  "nome": "Ana Silva",
  "idade": 30,
  "estadocivil": "solteira",
  "sexo": "F",
  "estado": "RJ"
}
```

### **2. carros**
Contém os dados dos veículos:
```json
{
  "codcarro": 1,
  "modelo": "Onix",
  "marca": "Chevrolet",
  "valor": 150
}
```

### **3. aluguel**
Relação entre clientes e carros alugados:
```json
{
  "codaluguel": 1,
  "codcliente": 1,
  "codcarro": 1,
  "data_aluguel": "2023-04-01"
}
```

### **4. marcas** (opcional)
Caso a marca dos carros seja uma coleção separada:
```json
{
  "codcarro": 1,
  "marca": "Chevrolet"
}
```

---

## 🔎 Consultas Exemplares

### ✅ Clientes e Modelos de Carros Alugados:
```js
$lookup com clientes, carros e filtro por cidade:
- nome do cliente
- modelo do carro
- data do aluguel
```

### ✅ Modelos mais alugados:
```js
$group por modelo com $sum
```

### ✅ Clientes com mais de 1 aluguel:
```js
$group por codcliente
$match: { quantidade > 1 }
```

### ✅ Clientes e as cidades onde moram (que alugaram carros):
```js
$lookup com clientes, project nome + estado
```

---

## 📊 Ferramentas utilizadas
- MongoDB Atlas (Database as a Service)
- Python + PyMongo + Pandas
- Jupyter Notebook / Google Colab

---

## 💡 Sugestões de expansão
- Adicionar coleções para pagamento, devoluções e manutenções
- Criar API REST com Flask ou FastAPI
- Interface web com React

---

## 🧠 Autor
Este projeto foi conduzido como exercício de exploração em banco de dados NoSQL (MongoDB) com foco em modelagem de dados e consultas agregadas para uma locadora de veículos fictícia.

Sinta-se à vontade para clonar, testar e expandir! 🚗💨
