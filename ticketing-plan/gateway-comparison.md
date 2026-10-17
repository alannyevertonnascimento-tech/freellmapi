# Comparação de gateways: Mercado Pago, Stone (Pagar.me) e InfinitePay

**Data:** 2026-10-16. Pesquisa em 5 buscas. **Nenhuma das fontes de taxa é oficial**: usei agregadores e blogs, e os números conflitam entre si. Peça a proposta oficial de cada um antes de decidir.

**Critério decisivo:** a plataforma precisa de **split de pagamento** (o valor do ingresso vai direto ao organizador e só a sua taxa fica com você). Sem split, você recebe todo o dinheiro dos eventos na sua conta, o que cria risco regulatório (você passa a intermediar dinheiro de terceiros) e fiscal (o valor total vendido pode ser tributado como receita sua). Valide com um contador e um advogado.

## Resumo

| Critério | Mercado Pago | Stone (Pagar.me) | InfinitePay |
|---|---|---|---|
| Split para marketplace | **Sim, documentado**, com `application_fee` por pagamento | **Sim**, recebedores com conta virtual, você define quem arca com taxas e chargeback | **Não encontrei API ou split público** |
| Taxas publicadas | Parcialmente (agregadores) | **Não, só sob consulta** | Sim, na página de planos |
| Cartão à vista | ~2,82% a 3,08% (agregador) | Sob consulta | 2,69% a 3,15% na página de planos; 4,2% no canal link (blog de jun/2026) |
| Pix | Mais barato que cartão (blog oficial); um agregador lista como grátis | Sob consulta (Pix grátis só na conta Stone, e a Stone cobra na maquininha) | Grátis para o vendedor |
| Parcelamento 12x | ~17,9% a ~23% | Sob consulta | 8,99% a 12,40% (planos) ou 16,66% (link) |
| Onboarding | Autoatendimento, documentação aberta | **Comercial**, aprovação por proposta | Autoatendimento para vender, sem integração conhecida |
| Prazo do dinheiro | Varia por plano (mais rápido custa mais) | Cartão até 30 dias, Pix em segundos | Na hora ou D+1 |
| Organizador precisa de conta | **Sim**, conta Mercado Pago do organizador conectada por OAuth | Não, recebedor cadastrado por você | — |

## Mercado Pago

- **Pontos fortes:** split pronto e documentado, tanto no Checkout Pro quanto no Checkout Transparente. O parâmetro `application_fee` define a sua comissão em cada pagamento. É a opção mais fácil de começar sozinho(a).
- **Pontos fracos:**
  1. O split 1:1 só funciona entre contas Mercado Pago, então **cada organizador precisa ter e conectar uma conta**. Isso é atrito para atléticas e comissões.
  2. A taxa do Mercado Pago é descontada do valor do vendedor primeiro, e depois sai a sua comissão.
  3. Em reembolso, o valor é descontado proporcionalmente das duas contas, e o marketplace não consegue reembolsar integralmente se o vendedor não tiver saldo.
  4. A taxa de cartão depende da bandeira e do prazo de recebimento.
- **Fontes:** [documentação de split](https://www.mercadopago.com.br/developers/pt/docs/split-payments/split-1-1/integration-configuration/integrate-marketplace), [taxas (agregador)](https://www.calculadoradetaxas.com.br/public/mercado-pago/taxas), [Pix no checkout (blog oficial)](https://www.mercadopago.com.br/blog/o-pix-chegou-ao-checkout-transparente-do-mercado-pago).

## Stone (Pagar.me)

- **Pontos fortes:** o Pagar.me é o gateway do grupo Stone, voltado a e-commerce e marketplaces. O split paga cada recebedor em conta virtual e você escolhe quem arca com taxas e chargeback. O organizador **não precisa** ter conta própria.
- **Pontos fracos:** taxas **só sob consulta** (variam por faixa de faturamento e modelo de negócio), e a aprovação passa por contato comercial. Para uma operação sem faturamento inicial, a proposta pode sair cara ou demorar.
- **Fontes:** [Stone: por que vender com o Pagar.me](https://conteudo.stone.com.br/por-que-vender-com-o-pagarme/), [Pagar.me: taxas sob consulta (nfe.io)](https://nfe.io/blog/pagamentos/pagar-me-taxas), [Pix no e-commerce (Stone)](https://conteudo.stone.com.br/pix-no-ecommerce).

## InfinitePay

- **Pontos fortes:** taxas publicadas e competitivas (2,69% a 3,15% no cartão à vista, conforme faturamento, e Pix grátis), dinheiro na hora ou em D+1, link de pagamento simples.
- **Pontos fracos:** não encontrei API de integração nem split. Sem split, você teria de receber tudo e repassar manualmente, o que traz o risco regulatório e fiscal descrito acima e **não escala**. O blog oficial mostra ainda 4,2% à vista no canal de link, muito acima da página de planos, então confira qual tabela se aplica a cobranças online.
- **Fontes:** [planos por faturamento](https://www.infinitepay.io/lp/taxas-reduzidas-5), [link de pagamento](https://www.infinitepay.io/link-de-pagamento), [taxas (agregador)](https://www.calculadoradetaxas.com.br/public/infinitepay).

## Impacto na sua taxa (5% + R$ 1,00)

Cartão à vista, com a taxa de gateway em cada cenário (e Pix a 1% como hipótese; se for grátis, a margem sobe):

| Ingresso | Sua taxa | Margem com cartão a 2,8% | Margem com cartão a 3,2% | Margem com cartão a 4,2% (pior caso) |
|---|---|---|---|---|
| R$ 20 | R$ 2,00 | ~R$ 1,30 | ~R$ 1,22 | ~R$ 1,02 |
| R$ 50 | R$ 3,50 | ~R$ 1,86 | ~R$ 1,66 | ~R$ 1,16 |
| R$ 100 | R$ 6,00 | ~R$ 2,78 | ~R$ 2,38 | ~R$ 1,38 |
| R$ 200 | R$ 11,00 | ~R$ 4,63 | ~R$ 3,83 | ~R$ 1,83 |

Cálculo: taxa − impostos de 7% sobre a taxa (hipótese) − custo do gateway (percentual × preço). Não considerei custo fixo por transação, que os agregadores não informam. Com a regra `5% + R$ 1,00` a margem fica positiva mesmo com o pior caso de 4,2%.

## Recomendação

1. **MVP: Mercado Pago**, porque é a única opção com split documentado e autoatendimento, o que permite começar sozinho(a). Mitigue o atrito do OAuth com um passo guiado de "conectar conta Mercado Pago" durante o cadastro do organizador.
2. **Escala: pedir proposta ao Pagar.me (Stone)** assim que houver volume e histórico, para eliminar a exigência de conta do organizador e negociar taxas.
3. **InfinitePay: não usar como gateway do marketplace** enquanto não houver split público. Vale perguntar ao comercial deles se existe API para plataformas.
4. **Arquitetura:** isolar o gateway atrás de uma interface (`PaymentProvider`) no código, para trocar de provedor sem reescrever o checkout (ver PRD).

## Perguntas para a proposta comercial

- Qual a taxa de cartão à vista e parcelado, e de Pix, **para marketplace com split**?
- Há tarifa fixa por transação, por estorno ou por reembolso?
- Quem arca com chargeback e como funciona o saldo do recebedor?
- O recebedor (organizador) precisa de CNPJ ou aceita CPF e conta própria?
- Qual o prazo de liberação para o recebedor e é possível reter até o evento?
