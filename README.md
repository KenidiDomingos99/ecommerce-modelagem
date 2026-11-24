# Modelagem de banco de dados - E-commerce

Projeto de modelagem de banco de dados para um e-commerce, feito no MySQL Workbench. O modelo cobre fornecedores, produtos, estoque, vendedores terceiros, clientes, pedidos, pagamento e entrega.

## O que tem no modelo

- **Fornecedor**: quem fornece os produtos para a loja.
- **Produto**: categoria, descrição e valor.
- **Estoque**: onde os produtos ficam guardados. Um produto pode estar em mais de um estoque.
- **Terceiro - Vendedor**: vendedores externos que também vendem produtos na plataforma.
- **Cliente**: quem faz os pedidos.
- **Pedido**: status, descrição e frete.

## Refinamentos feitos

### Cliente PF e PJ

Uma conta de cliente pode ser pessoa física ou jurídica, nunca as duas ao mesmo tempo. Por isso separei os dados em três tabelas:

- `Cliente`: dados comuns (nome, endereço e tipo)
- `Cliente_PF`: CPF e data de nascimento
- `Cliente_PJ`: CNPJ, razão social e inscrição estadual

As tabelas `Cliente_PF` e `Cliente_PJ` usam o próprio `idCliente` como chave primária e estrangeira, então cada cliente tem no máximo um registro em uma delas.

### Pagamento

O cliente pode ter mais de uma forma de pagamento cadastrada (cartão, boleto ou Pix) e, no pedido, é guardada qual delas foi usada. Para cartão, só os quatro últimos dígitos ficam salvos.

### Entrega

Cada entrega tem status (preparando, enviado, em trânsito, entregue ou devolvido) e código de rastreio. Um pedido pode ter mais de uma entrega, já que produtos de terceiros podem ser enviados separadamente.

## Arquivos

- E COMMERCE REFINADO.png`: imagem do diagrama
- `ecommercesql..mwb`: modelo para abrir no MySQL Workbench

## Como usar

Para ver ou editar o modelo, abra o arquivo `ecommerce.mwb` no MySQL Workbench.
## Autor

SEU NOME - https://github.com/SEU_USUARIO
