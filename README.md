# Sistema de Gerenciamento de Loja Avançado

Este projeto é um sistema avançado de gerenciamento de uma loja utilizando MySQL. Ele contém várias tabelas inter-relacionadas para controlar informações sobre **clientes**, **produtos**, **categorias**, **pedidos**, **fornecedores**, **vendas**, **estoque** e **relatórios de vendas**.

## Funcionalidades

- **Clientes:** Gerenciamento de informações sobre clientes, como nome, e-mail, telefone e endereço.
- **Categorias:** Organização dos produtos por categorias, como eletrônicos, vestuário, etc.
- **Produtos:** Registro e controle de produtos, incluindo informações sobre preço, estoque, categoria e fornecedor.
- **Fornecedores:** Cadastro de fornecedores com dados como nome, telefone e endereço.
- **Pedidos:** Registro de pedidos realizados pelos clientes, com status (Pendente, Concluído, Cancelado).
- **Detalhes dos Pedidos:** Registro dos produtos incluídos em cada pedido.
- **Vendas:** Registro de vendas realizadas, com informações de pagamento e valor total.
- **Estoque Histórico:** Registro de movimentações de estoque (entrada e saída de produtos).
- **Relatórios de Vendas:** Relatórios mensais de vendas, com total de vendas e produtos vendidos.

## Estrutura do Banco de Dados

### Tabelas

1. **clientes**  
   - `id`: Chave primária  
   - `nome`: Nome do cliente  
   - `email`: E-mail único do cliente  
   - `telefone`: Telefone do cliente  
   - `endereco`: Endereço do cliente  
   - `data_cadastro`: Data de cadastro do cliente

2. **categorias**  
   - `id`: Chave primária  
   - `nome`: Nome da categoria (exemplo: Eletrônicos, Roupas)  
   - `descricao`: Descrição da categoria

3. **produtos**  
   - `id`: Chave primária  
   - `nome`: Nome do produto  
   - `descricao`: Descrição do produto  
   - `preco`: Preço do produto  
   - `estoque`: Quantidade em estoque  
   - `categoria_id`: ID da categoria do produto  
   - `fornecedor_id`: ID do fornecedor

4. **fornecedores**  
   - `id`: Chave primária  
   - `nome`: Nome do fornecedor  
   - `telefone`: Telefone do fornecedor  
   - `email`: E-mail único do fornecedor  
   - `endereco`: Endereço do fornecedor

5. **pedidos**  
   - `id`: Chave primária  
   - `cliente_id`: ID do cliente  
   - `data_pedido`: Data e hora do pedido  
   - `status`: Status do pedido (Pendente, Concluído, Cancelado)

6. **detalhes_pedidos**  
   - `id`: Chave primária  
   - `pedido_id`: ID do pedido  
   - `produto_id`: ID do produto  
   - `quantidade`: Quantidade do produto no pedido  
   - `preco_total`: Preço total dos produtos no pedido

7. **vendas**  
   - `id`: Chave primária  
   - `pedido_id`: ID do pedido  
   - `data_venda`: Data e hora da venda  
   - `valor_total`: Valor total da venda  
   - `status`: Status de pagamento (Pago, Não Pago)

8. **estoque_historico**  
   - `id`: Chave primária  
   - `produto_id`: ID do produto  
   - `quantidade`: Quantidade movida no estoque  
   - `tipo_movimento`: Tipo de movimento (Entrada ou Saída)  
   - `data_movimento`: Data e hora do movimento

9. **relatorios_vendas_mensais**  
   - `id`: Chave primária  
   - `mes`: Mês do relatório  
   - `ano`: Ano do relatório  
   - `total_vendas`: Total de vendas realizadas no mês  
   - `total_produtos_vendidos`: Quantidade total de produtos vendidos

### Explicações sobre o Projeto

- **Relacionamentos entre tabelas:** O banco de dados inclui chaves estrangeiras para estabelecer relacionamentos entre as tabelas, como entre clientes e pedidos, produtos e categorias, pedidos e detalhes de pedidos, entre outros.
  
- **Controle de Estoque e Movimentação:** A tabela `estoque_historico` permite acompanhar as entradas e saídas de produtos, enquanto a tabela `vendas` registra transações realizadas.

- **Relatórios de Vendas:** A tabela `relatorios_vendas_mensais` oferece uma visão consolidada das vendas por mês, útil para análises.

## Como Usar

1. Clone este repositório:
```bash
git clone https://github.com/seu-usuario/sistema_gerenciamento_loja.git
```
2. acesse o diretório:
```bash
cd sistema_gerenciamento_loja
```
3. Importe o arquivo [schema.sql](https://github.com/Emanoellima-dev/sistema_gerenciamento_loja/blob/main/schema.sql) que está neste repositório no seu banco de dados MySQL:
```bash
mysql -u seu_usuario -p < schema.sql
```
4. Utilize ferramentas como MySQL Workbench ou DBeaver para explorar e inserir dados nas tabelas.

## Banco de Dados Hospedado
O banco de dados deste projeto está hospedado na plataforma **Railway**.
Se você deseja replicar este projeto, pode criar um banco semelhante no Railway ou outra plataforma de sua preferência.

## Observação
Este projeto foi feito apenas com o intuito de aprimorar meus conhecimentos em MySQL. por isso não aceito contribuições ao projeto no momento.
