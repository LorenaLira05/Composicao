# Sistema de Pedidos - Estudo de Composição em Java

Este repositório contém um projeto prático desenvolvido para consolidar os fundamentos de **Composição de Objetos** (relação "Tem-um"). O objetivo é simular o fluxo de um sistema de vendas, desde o cadastro do cliente até a geração de um sumário detalhado do pedido.

## Sobre o Projeto
A aplicação demonstra como conectar diferentes entidades (`Order`, `Client`, `OrderItem` e `Product`) de forma que cada uma possua sua própria responsabilidade, mas trabalhem juntas para calcular o total de uma venda e exibir informações formatadas.

## Estrutura de Composição Aplicada
O projeto foi estruturado com base nos seguintes níveis de composição:
* **Order → Client**: Composição simples (Um pedido possui um cliente).
* **Order → OrderItem**: Composição de coleção (Um pedido possui vários itens).
* **OrderItem → Product**: Composição simples (Cada item aponta para um produto específico).

## Conceitos Técnicos Utilizados
* **Composição de Objetos**: Design de classes baseado em relacionamentos.
* **Enumerações (Enums)**: Para representar de forma tipada o status do pedido.
* **Tratamento de Datas**: Uso de `Date` e `SimpleDateFormat`.
* **Manipulação de Coleções**: Uso de `List` e `ArrayList` para gerenciar itens.
* **StringBuilder**: Utilizado para otimizar a concatenação de strings no relatório final.
* **Delegação**: Prática onde o `Order` delega ao `OrderItem` o cálculo do seu próprio subtotal.

## Exemplo de Saída no Console
```text
Enter client data:
Name: Alex Green
Email: alex@gmail.com
Birth date (DD/MM/YYYY): 15/03/1985

Enter order data:
Status: PROCESSING
How many items to this order? 2

Enter #1 item data:
Product name: TV
Product price: 1000.00
Quantity: 1

Enter #2 item data:
Product name: Mouse
Product price: 40.00
Quantity: 2

ORDER SUMMARY:
Order moment: 20/04/2024 11:25:09
Order status: PROCESSING
Client: Alex Green (15/03/1985) - alex@gmail.com
Order items:
TV, $1000.00, Quantity: 1, Subtotal: $1000.00
Mouse, $40.00, Quantity: 2, Subtotal: $80.00
Total price: $1080.00
