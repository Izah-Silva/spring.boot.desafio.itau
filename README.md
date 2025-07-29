# 💰 Desafio Itaú - API de Transações Financeiras

Este projeto é uma API RESTful desenvolvida em Java com Spring Boot como parte de um desafio técnico. O objetivo é permitir o registro de transações financeiras e disponibilizar estatísticas em tempo real dos últimos 60 segundos.

---

## 🚀 Tecnologias utilizadas

- Java 17  
- Spring Boot  
- Maven  
- JUnit 5  
- Postman (para testes manuais)  
- Git & GitHub  

---

## 🧠 Conceitos aplicados

- Programação orientada a objetos (POO)  
- Boas práticas de organização de pacotes  
- Tratamento de exceções  
- API RESTful  
- Testes automatizados com JUnit  
- Separação entre camadas: Controller, Service, DTO e Model  

---

## 📁 Estrutura do projeto

src/
├── main/
│ ├── java/desafio/itau/springboot/
│ │ ├── controller/ # Camada de entrada da API
│ │ ├── model/ # Modelos de dados
│ │ ├── model/dto/ # Objetos de transferência de dados (DTOs)
│ │ ├── service/ # Regras de negócio
│ │ └── SpringbootApplication.java
│ └── resources/
│ └── application.properties
└── test/
└── java/desafio/itau/springboot/


---

## 📌 Funcionalidades

- **POST /transactions**  
  Cadastra uma nova transação, contendo valor e timestamp.

- **GET /statistics**  
  Retorna estatísticas em tempo real (últimos 60 segundos) das transações:
  - Soma
  - Média
  - Máximo
  - Mínimo
  - Quantidade

---

## ✅ Regras de negócio

- Transações com mais de 60 segundos são ignoradas.
- Transações futuras (timestamp posterior ao horário atual) são rejeitadas com `422 Unprocessable Entity`.
- Valores negativos são rejeitados com `400 Bad Request`.
- Timestamp inválido ou ausente gera erro `400 Bad Request`.

---

## 🧪 Testes

Os testes automatizados estão localizados em:  
`src/test/java/desafio/itau/springboot/`

Incluem verificações para:

- Regras de tempo da transação  
- Cálculo estatístico correto  
- Respostas HTTP esperadas  

### Para executar os testes:

```bash
./mvnw test
