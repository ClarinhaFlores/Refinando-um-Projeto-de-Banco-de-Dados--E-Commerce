# Desafio_E-commerce

O seguinte modelo conceitual, encontrado no arquivo "E-commerce.pdf", demonstra um squema de uma loja e-commerce. 
Nesse modelo temos como base as entidades: "Produto", "Fornecedor", "Estoque", "Terceiro-Vendedor", "Pedido" e "Cliente".
As relações base são: 
- "produto" pode ter 1 ou mais fornecedores, e o "fornecedor" pode fornecedr 1 ou mais produtos; 
- "produto" pode ter 1 ou mais terceiro-vendedores, e o "terceiro-vendedor" pode vender 1 ou mais produtos;
- "produto" pode ser guardado em 1 ou mais estoques, e o "estoque" pode guardar 1 ou mais produtos;
- "produto" pode ter 1 ou mais pedidos, e o "pedido" pode ter 1 ou mais produtos;
- "pedido" pode ter apenas 1 cliente, porém o "cliente" pode ter 1 ou mais pedidos;

Para o desafio, foi proposta a implementação de:
Cliente PJ e PF – Uma conta pode ser PJ ou PF, mas não pode ter as duas informações;
Pagamento – Pode ter cadastrado mais de uma forma de pagamento;
Entrega – Possui status e código de rastreio;

Para resolver foram adicionadas as seguintes entidades: "Pessoa", "Pessoa Fisica", "Pessoa Juridica", "Pagamento", "Cartao", "Boleto" e "Entrega"

Resultando nas seguintes relações:
- "pessoa" é uma generalização com informações base para "pessoa juridica" e "pessoa fisica", que para existirem precisam de uma "pessoa";
- "cliente" pode ser, ou, uma "pessoa juridica" ou uma "pessoa fisica", nunca os dois, portanto para isso ocorrer, um "cliente" precisa ser uma "pessoa", que terá seu id associado a apenas um dos dois;
- "pagamento" é uma generalização para "boleto" e "cartão";
- "cliente" pode ter 1 ou mais formas de pagamento, e uma forma de "pagamento" pode estar relacionada a 1 ou mais clientes;
- "pagamento" também está diretamente relacionado a "cliente" e "terceiro-vendedor", de modo que suas informações possam ser 'puxadas'/utilizadas ao gerar uma forma de pagamento;
- "pedido" só pode ter 1 entrega, já uma "entrega" pode ter 1 ou mais pedidos.