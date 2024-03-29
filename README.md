# Primeira fase


Sistema de Controle de Pedidos de Lanchonete

1. Contexto do Domínio
Com o crescimento de uma lanchonete local, surge a necessidade de otimizar e organizar o processo de pedidos e entregas. Para garantir a eficiência e a satisfação dos clientes, desenvolvemos um sistema de controle de pedidos que aborda desde a escolha do produto até a retirada do pedido.

2. Entidades e Agregações
Entidades:

Cliente
Produto
Pedido
Fatura
Agregações:

Itens do Pedido (agrupa produtos específicos sob um Pedido)
Cozinha (conjunto de profissionais e equipamentos dedicados à preparação dos produtos)

3. Objetos de Valor
Categoria de Produto
Status do Pedido
Status de Pagamento

4. Eventos de Domínio
PedidoRealizado: Ocorre quando um Cliente faz um Pedido.
PedidoPreparado: Ocorre quando a Cozinha finaliza os Itens do Pedido.
PagamentoConfirmado: Ocorre quando o pagamento é efetivamente registrado.
PagamentoRecusado: Ocorre quando há um problema com a transação de pagamento.

5. Restrições e Regras de Negócio
Cada Pedido deve conter pelo menos um Produto.
A transição do Status do Pedido deve ocorrer em uma sequência definida, como: PedidoRealizado -> PedidoEmPreparo -> PedidoPronto -> PedidoEntregue.
A confirmação da Fatura precede a entrega do Pedido ao Cliente.


6. Relacionamentos
Um Cliente pode fazer vários Pedidos, mas cada Pedido pertence a apenas um Cliente.
Um Pedido pode conter vários Produtos, mas cada Produto pode ser parte de diversos Pedidos.


7. Consistência e Transações
A disponibilidade de um Produto é verificada ao realizar o Pedido.
Todos os pagamentos são registrados em uma Fatura e têm um Status de Pagamento associado para rastreabilidade.


8. Glossário
Cliente: Indivíduo que realiza a solicitação de produtos na lanchonete.
Produto: Alimento ou bebida que é oferecido pela lanchonete.
Categoria: Classificação de um Produto conforme suas características (por exemplo, bebidas, lanches etc)

Diagramas de fluxo
Foram utilizadas técnicas de Domain Driven Design para definição dos fluxos:

Realização do pedido e pagamento

![image](https://github.com/Jeffe-git/First-Project/assets/40615923/13a08458-d713-4738-886f-426ad2e3c720)


Preparação e Entrega do Pedido
![Preparacao_EntregaPedido](https://github.com/Jeffe-git/First-Project/assets/40615923/fb7c901d-e6c9-4f90-8c6e-f508ba67557e)
