# Pricing Strategy para Ingresso Campus (nome provisório)

**Decisão (16/10/2026):** taxa de **5% + R$ 1,00 por ingresso pago, sem teto**, paga pelo comprador. Esta versão substitui as anteriores (faixas fixas e depois 5% com teto de R$ 2,50). A regra de 5% com teto foi descartada porque a margem ficava negativa em ingressos baratos e em ingressos caros pagos no cartão.

## Regra da taxa

```
taxa_por_ingresso = 5% × preço_do_ingresso + R$ 1,00      (ingresso gratuito: R$ 0)
```

| Ingresso | Sympla (10%, mín. R$ 2,50) | **Sua taxa** | Você cobra |
|---|---|---|---|
| R$ 10 | R$ 2,50 | **R$ 1,50** | 40% menos |
| R$ 20 | R$ 2,50 | **R$ 2,00** | 20% menos |
| R$ 30 | R$ 3,00 | **R$ 2,50** | 17% menos |
| R$ 50 | R$ 5,00 | **R$ 3,50** | 30% menos |
| R$ 100 | R$ 10,00 | **R$ 6,00** | 40% menos |
| R$ 200 | R$ 20,00 | **R$ 11,00** | 45% menos |

- **Fonte da taxa da Sympla:** [Qual a taxa do Sympla?](https://vocepergunta.com/library/artigo/read/425154-qual-a-taxa-do-sympla), página de terceiros. Confira a tabela oficial antes de usar a comparação em material de venda.
- **Quem paga:** o comprador, de forma visível no checkout. O organizador pode optar por absorver a taxa.
- **Reembolso:** a taxa é devolvida integralmente em qualquer reembolso (a Sympla foi multada pelo Procon-MG por reter a taxa em cancelamentos).
- **Mensagem honesta:** "20% a 45% menos que as grandes plataformas". Evite "metade" e "5%", porque a taxa efetiva só chega perto de 5% em ingressos caros.

## Por que essa regra nunca fica negativa

A margem de uma venda é `taxa − impostos − custo do gateway`. Com taxa `a × P + b` e gateway `c × P`, a margem é `(a − c) × P + b`, **positiva para qualquer preço desde que a > c**. Aqui `a = 5%` e o cartão à vista custa entre ~2,7% e ~4,2% nas fontes que encontrei, então sobra margem em qualquer preço. O valor fixo `b = R$ 1,00` protege os ingressos baratos.

Margem por ingresso com impostos de 7% sobre a taxa (hipótese) e cartão à vista em três cenários de custo:

| Ingresso | Cartão 2,8% | Cartão 3,2% | Cartão 4,2% (pior caso) |
|---|---|---|---|
| R$ 20 | R$ 1,30 | R$ 1,22 | R$ 1,02 |
| R$ 50 | R$ 1,86 | R$ 1,66 | R$ 1,16 |
| R$ 100 | R$ 2,78 | R$ 2,38 | R$ 1,38 |
| R$ 200 | R$ 4,63 | R$ 3,83 | R$ 1,83 |

No Pix a margem é maior (custo de 0% a ~1%). Os custos do gateway vêm de agregadores e blogs, não de tabelas oficiais (ver `gateway-comparison.md`). Não incluí custo fixo por transação, porque as fontes não informam.

**Regra para recalibrar:** com o contrato real, mantenha o percentual da taxa **pelo menos 1,5 ponto acima do custo do cartão** e o valor fixo **pelo menos R$ 0,50 acima do custo fixo do gateway**.

## Perdas que a fórmula não cobre

1. **Reembolso:** a taxa é devolvida, mas o gateway pode não devolver o custo dele. Mantenha uma reserva de 2% a 3% da receita de taxas.
2. **Chargeback de cartão:** você pode perder o valor do ingresso mais a tarifa. Use antifraude, retenha o repasse até o evento e limite o cartão em ingressos caros.
3. **Juros de parcelamento:** repasse ao comprador em linha separada. O parcelamento em 12x custa de ~9% a ~23% nas fontes, o que consumiria toda a sua receita.
4. **Impostos:** a conta usa 7% sobre a taxa como hipótese. Confirme com um contador, inclusive o tratamento do dinheiro de terceiros no split.

## Planos do organizador (sem desconto na taxa)

| Plano | Preço | Para quem | Inclui |
|---|---|---|---|
| Essencial | R$ 0/mês | Atléticas e centros acadêmicos com 1 ou 2 eventos por semestre | Ingressos e lotes, Pix e cartão, QR code, check-in, relatório, repasse em D+3 |
| Pro (herói) | R$ 47/mês ou R$ 449/ano (cerca de 20% off) | Empresas juniores e entidades com eventos o ano todo | Tudo do Essencial, certificados automáticos, cupons por turma, repasse em D+2, marca na página, suporte prioritário por WhatsApp |
| Congresso | R$ 197/mês ou R$ 1.890/ano (cerca de 20% off) | Congressos e semanas científicas com várias trilhas | Tudo do Pro, submissão de trabalhos, várias trilhas, repasse antecipado parcial, API e exportação, onboarding assistido |

Os planos vendem recursos e não reduzem a taxa. O plano do meio é o herói, e o Congresso funciona como âncora. Gatilhos de upgrade: segundo evento no semestre, necessidade de certificado, pedido de repasse mais rápido e submissão de trabalhos.

## Unidade econômica e ponto de equilíbrio (hipótese)

Ingresso médio de R$ 40, 70% das vendas por Pix (custo ~1%) e 30% por cartão à vista (custo ~3,2%), impostos de 7% sobre a taxa:
- taxa média: R$ 3,00 (a Sympla cobraria R$ 4,00, ou seja, 25% menos)
- margem média: R$ 3,00 − R$ 0,21 de imposto − (0,7 × R$ 0,40 + 0,3 × R$ 1,28) = **~R$ 2,13 por ingresso**

| Custo fixo anual | Ingressos para empatar | Valor vendido (GMV) |
|---|---|---|
| R$ 60 mil (só infraestrutura e ferramentas, sem salário) | ~28 mil | ~R$ 1,1 milhão |
| R$ 180 mil | ~85 mil | ~R$ 3,4 milhões |
| R$ 300 mil | ~141 mil | ~R$ 5,6 milhões |

| Cenário (hipótese) | Ingressos/ano | Margem total | Custo fixo | Resultado |
|---|---|---|---|---|
| Ano 1 (validação) | ~15 mil | ~R$ 32 mil | R$ 60–120 mil | prejuízo |
| Ano 2 | ~100 mil | ~R$ 213 mil | R$ 150–250 mil | perto do zero |
| Ano 3 | ~400 mil | ~R$ 852 mil | R$ 400–600 mil | lucro de R$ 250–450 mil |

Se o ticket médio subir, a margem por ingresso também sobe. Planos pagos somam receita à parte: 50 assinantes Pro rendem ~R$ 28 mil por ano.

## Posicionamento e psicologia

- **Mensagem:** "Taxa transparente, bem menor que as grandes plataformas, e você recebe rápido." Mostre sempre o preço final (ingresso + taxa).
- **Cuidado:** na Sympla os 10% já incluem o processador. Deixe claro o que a sua taxa cobre, para não ser acusado de taxa oculta.
- **Táticas:** simulador de taxa na página do organizador (quanto ele recebe e quanto o comprador paga), plano do meio como herói, desconto anual de cerca de 20%.

## Maior risco de preço

**Margem sensível ao custo real do gateway.** Se o contrato vier com tarifa fixa por transação ou cartão acima de ~4,5%, a margem dos ingressos baratos some. Mitigação: conseguir a proposta oficial antes do lançamento, priorizar Pix, repassar juros de parcelamento ao comprador, usar antifraude, reter o repasse até o evento e acompanhar semanalmente a margem real por ingresso.
