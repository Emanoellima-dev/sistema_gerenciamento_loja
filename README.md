# Sistema de Gerenciamento de Loja

Este é um projeto simples que utiliza MySQL para gerenciar os dados de uma loja fictícia. O banco de dados possui tabelas para Clientes, Produtos, Pedidos e Detalhes dos Pedidos.

## Funcionalidades

- **Clientes:** Cadastro de clientes com nome, email e telefone.
- **Produtos:** Registro de produtos com nome, preço e estoque.
- **Pedidos:** Associação entre clientes e os pedidos realizados.
- **Detalhes dos Pedidos:** Produtos e quantidades em cada pedido.

## Estrutura do Banco de Dados

### Tabelas
1. **clientes**  
   - `id` (Chave primária)  
   - `nome` (Nome do cliente)  
   - `email` (E-mail único)  
   - `telefone` (Telefone)

2. **produtos**  
   - `id` (Chave primária)  
   - `nome` (Nome do produto)  
   - `preco` (Preço do produto)  
   - `estoque` (Quantidade em estoque)

3. **pedidos**  
   - `id` (Chave primária)  
   - `cliente_id` (Relacionamento com `clientes`)  
   - `data_pedido` (Data do pedido)

4. **detalhes_pedidos**  
   - `id` (Chave primária)  
   - `pedido_id` (Relacionamento com `pedidos`)  
   - `produto_id` (Relacionamento com `produtos`)  
   - `quantidade` (Quantidade do produto no pedido)  
   - `preco_total` (Preço total dos produtos no pedido)

## Como Usar

1. Clone este repositório:
```bash
git clone https://github.com/seu-usuario/sistema_gerenciamento_loja.git```
```
3. entre no diretório:
```bash
cd sistema_gerenciamento_loja
```
3. Importe o arquivo schema.sql no seu banco de dados MySQL:
```bash
mysql -u seu_usuario -p < schema.sql
```
4. Utilize ferramentas como MySQL Workbench ou DBeaver para explorar e inserir dados nas tabelas.

## Banco de Dados Hospedado

O banco de dados deste projeto está hospedado na plataforma **Railway**.  
Se você deseja replicar este projeto, pode criar um banco semelhante no Railway ou outra plataforma de sua preferência.

## Observação
Este projeto foi feito apenas com o intuito de aprimorar meus conhecimentos em MySQL. por isso não aceito contribuições ao projeto no momento.
