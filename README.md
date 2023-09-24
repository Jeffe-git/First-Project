# Primeira fase


## Sistema de Autoatendimento de Fast Food

1. Contexto do Domínio
Uma lanchonete local está expandindo devido ao seu grande sucesso. Para atender à demanda crescente e evitar confusões no atendimento, identificou-se a necessidade de um sistema de controle de pedidos eficiente. O sistema permitirá que os clientes selecionem e façam pedidos sem interagir diretamente com um atendente, otimizando a eficiência e satisfação do cliente no back-end.

2. Entidades e Agregações

- Entidades:
  - Consumidor
  - Item de Menu
  - Requisição
  - Registro Financeiro

- Agregações:
  - Componentes da Requisição (agrupa itens de menu específicos sob uma Requisição)
  - Equipe de Preparo (conjunto de profissionais encarregados de montar os itens de menu)

3. Objetos de Valor
- Segmento de Item
- Estágio da Requisição
- Estágio de Transação

4. Eventos de Domínio
- PedidoColocado: Ocorre quando um Consumidor faz uma Requisição.
- PedidoPreparado: Ocorre quando a Equipe de Preparo finaliza uma Requisição.
- PagamentoRealizado: Ocorre quando um Consumidor completa o processo de pagamento.
- PagamentoRecusado: Ocorre quando há um problema com a transação de pagamento.

5. Restrições e Regras de Negócio
- Cada Requisição deve ter pelo menos um Item de Menu.
- A transição do Estágio da Requisição só pode ocorrer em uma sequência específica: PedidoColocado -> PedidoPreparado.
- O PagamentoRealizado deve preceder a entrega da Requisição ao Consumidor.

6. Relacionamentos
- Um Consumidor pode fazer várias Requisições, mas cada Requisição pertence a apenas um Consumidor.
- Uma Requisição pode ter vários Itens de Menu, mas cada Item de Menu pode estar em apenas uma Requisição de cada vez.

7. Interfaces de Bounded Contexts
(Como não tenho detalhes sobre contextos delimitados, vou supor um exemplo aqui)
- **Modulo de Gestão de Estoque**: Interage com o sistema principal para verificar a disponibilidade de itens e ingredientes.

8. Consistência e Transações
- Quando um Consumidor coloca uma Requisição, a disponibilidade do Item de Menu é verificada no Módulo de Gestão de Estoque.
- Todas as transações de pagamento são registradas e têm um status associado para rastreabilidade.

9. Glossário
- **Consumidor**: Indivíduo que realiza a solicitação de produtos no estabelecimento.
- **Item de Menu**: Alimento ou bebida oferecido pelo local.

