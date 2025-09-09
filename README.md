# Trabalho — Definição do Dataset

## 1. Nome do Dataset
**Brazilian E-Commerce Public Dataset by Olist**

---

## 2. Fonte
**Plataforma:** Kaggle  
**Link:** https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

---

## 3. Justificativa
Este dataset é altamente relevante para a pergunta de negócio:

> **“Quais fatores (tempo de entrega, valor do frete, número de parcelas no pagamento, categoria do produto, avaliação do vendedor) estão mais associados a avaliações positivas (4 ou 5 estrelas) e maior probabilidade de recompra pelos clientes?”**

Ele contém dados detalhados sobre:
- **Pedidos e entregas** (datas, status, prazos, frete)
- **Pagamentos** (formas, número de parcelas, valores)
- **Produtos** (categorias, descrição, medidas)
- **Avaliações** (notas de 1 a 5 e comentários de clientes)
- **Vendedores** (origem, características)

Essas variáveis permitem investigar tanto a **satisfação do cliente** (via avaliações) quanto **fatores de retenção e recompra**.

---

## 4. Dicionário de Dados (Preliminar)

| Campo | Tipo | Descrição |
|---|---|---|
| `order_id` | Categórico/ID | Identificador único do pedido. |
| `customer_id` | Categórico/ID | Identificador único do cliente. |
| `order_status` | Categórico | Status do pedido (ex.: delivered, shipped, canceled). |
| `order_purchase_timestamp` | Temporal | Data e hora da compra. |
| `order_delivered_customer_date` | Temporal | Data de entrega ao cliente. |
| `order_estimated_delivery_date` | Temporal | Data estimada para a entrega. |
| `payment_type` | Categórico | Forma de pagamento (ex.: boleto, cartão). |
| `payment_installments` | Numérico/Inteiro | Número de parcelas do pagamento. |
| `payment_value` | Numérico/Moeda | Valor total pago pelo cliente. |
| `freight_value` | Numérico/Moeda | Valor do frete. |
| `product_id` | Categórico/ID | Identificador único do produto. |
| `product_category_name` | Categórico | Categoria do produto. |
| `review_score` | Numérico/Ordinal | Nota de avaliação do cliente (1 a 5). |
| `review_comment_message` | Texto Livre | Comentário textual do cliente. |
| `seller_id` | Categórico/ID | Identificador único do vendedor. |
| `seller_zip_code_prefix` | Categórico/Geográfico | Prefixo de CEP do vendedor (localização). |

> **Observação:** O dataset possui tabelas relacionadas (orders, payments, products, reviews, sellers, customers etc.). Os campos acima representam os principais atributos a serem utilizados na análise.

---

## 5. Desafios Previstos
- **Valores ausentes:** especialmente em datas de entrega (ex.: pedidos cancelados).
- **Padronização de datas:** diferentes colunas de datas exigem conversão e alinhamento para cálculo de prazos.
- **Texto livre:** comentários de clientes requerem pré-processamento (tokenização, limpeza) para análise de sentimentos.
- **Categorias inconsistentes:** nomes de categorias podem variar e demandam normalização.
- **Volume de dados:** mais de 100 mil registros; requer atenção a desempenho (amostragem, índices, processamento incremental).

---
