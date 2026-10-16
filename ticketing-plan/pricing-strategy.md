# Pricing Strategy para Ingresso Campus (nome provisório)

**Decisão do fundador (16/10/2026):** taxa de **5% por ingresso, com teto de R$ 2,50 por ingresso**, em vez dos 10% da Sympla. Este documento substitui a versão anterior (taxa fixa por faixa de preço).

## Regra da taxa

```
taxa_por_ingresso = min(5% × preço_do_ingresso, R$ 2,50)
```

| Preço do ingresso | Taxa | Taxa efetiva |
|---|---|---|
| R$ 10 | R$ 0,50 | 5,0% |
| R$ 20 | R$ 1,00 | 5,0% |
| R$ 30 | R$ 1,50 | 5,0% |
| R$ 50 | R$ 2,50 | 5,0% (ponto onde o teto começa) |
| R$ 80 | R$ 2,50 | 3,1% |
| R$ 150 | R$ 2,50 | 1,7% |
| R$ 300 | R$ 2,50 | 0,8% |
| Gratuito | R$ 0 | — |

- **Quem paga:** o comprador, de forma visível no checkout (preço do ingresso + taxa de serviço = total). O organizador pode optar por absorver a taxa.
- **Comparação:** a Sympla cobra 10% com mínimo de R$ 2,50 por ingresso (página de terceiros, conferir no site oficial: [Qual a taxa do Sympla?](https://vocepergunta.com/library/artigo/read/425154-qual-a-taxa-do-sympla)). Observação: o "R$ 2,50" da Sympla é o **mínimo**. No seu modelo, R$ 2,50 é o **máximo**, o que é uma proposta bem mais agressiva.
- **Reembolso:** a taxa é devolvida integralmente em qualquer reembolso (a Sympla foi multada pelo Procon-MG por reter a taxa em cancelamentos).

## Alerta de viabilidade

A taxa de 5% com teto de R$ 2,50 funciona bem em ingressos baratos pagos por Pix, mas **dá prejuízo em ingressos caros pagos no cartão**.

**Custos do gateway não confirmados:** não consegui a tabela oficial de Pagar.me nem de Asaas. Como referência, a tabela do PagBank de julho de 2026 mostra Pix grátis, crédito à vista a partir de 2,92% e crédito em 12x a partir de 12,36% ([calculadoradetaxas.com.br](https://www.calculadoradetaxas.com.br/pagseguro/taxas)), e variam conforme faturamento e prazo. Os números abaixo usam **3% no cartão à vista e 1% no Pix**, como hipótese. Substitua pelo contrato real.

| Ingresso | Taxa | Gateway Pix (1%) | Sobra no Pix | Gateway cartão (3%) | Sobra no cartão |
|---|---|---|---|---|---|
| R$ 20 | R$ 1,00 | R$ 0,20 | **R$ 0,80** | R$ 0,60 | **R$ 0,40** |
| R$ 50 | R$ 2,50 | R$ 0,50 | **R$ 2,00** | R$ 1,50 | **R$ 1,00** |
| R$ 100 | R$ 2,50 | R$ 1,00 | **R$ 1,50** | R$ 3,00 | **-R$ 0,50** |
| R$ 200 | R$ 2,50 | R$ 2,00 | **R$ 0,50** | R$ 6,00 | **-R$ 3,50** |

Um único estorno de cartão (o valor integral do ingresso mais a tarifa do gateway) apaga a margem de dezenas de vendas.

### Como proteger a margem mantendo "5%, máximo R$ 2,50"

1. **Parcelamento e juros do cartão por conta do comprador.** Os juros de parcelamento são repassados ao comprador, separados da taxa de serviço. O PagBank, por exemplo, lista 12,36% para crédito em 12x, o que consumiria toda a receita.
2. **Incentivar o Pix:** destacar o Pix como opção principal e oferecer o cartão só em ingressos até um valor-limite (por exemplo, R$ 150).
3. **Piso para ingressos muito baratos:** sugiro um mínimo de R$ 1,00 por ingresso pago. A taxa de R$ 0,50 num ingresso de R$ 10 não cobre o custo fixo de gateway, e isso contraria a regra pura de 5%, então é uma decisão sua.
4. **Receitas extras (fora da taxa de 5%):** antecipação de repasse (2% a 3% sobre o valor antecipado), assinatura dos planos abaixo e patrocínio na vitrine.

## Planos do organizador (sem desconto na taxa)

Como o teto já deixa pouca margem, os planos **não reduzem a taxa por ingresso**. Eles vendem recursos.

| Plano | Preço | Para quem | Inclui |
|---|---|---|---|
| Essencial | R$ 0/mês | Atléticas e centros acadêmicos com 1 ou 2 eventos por semestre | Ingressos e lotes, Pix e cartão, QR code, check-in, relatório, repasse em D+3 |
| Pro (herói) | R$ 47/mês ou R$ 449/ano (cerca de 20% off) | Empresas juniores e entidades com eventos o ano todo | Tudo do Essencial, certificados automáticos, cupons por turma, repasse em D+2, marca na página, suporte prioritário por WhatsApp |
| Congresso | R$ 197/mês ou R$ 1.890/ano (cerca de 20% off) | Congressos e semanas científicas com várias trilhas | Tudo do Pro, submissão de trabalhos, várias trilhas, repasse antecipado parcial, API e exportação, onboarding assistido |

- **Justificativa dos preços:** R$ 47 e R$ 197 cobrem o custo de suporte e certificados e dão receita previsível independente do volume de vendas. O plano do meio é o herói, e o Congresso funciona como âncora.
- **Gatilhos de upgrade:** segundo evento no semestre, necessidade de certificado, pedido de repasse mais rápido e submissão de trabalhos.

## Unidade econômica e ponto de equilíbrio (hipótese)

Ingresso médio de R$ 40, 70% das vendas por Pix e 30% por cartão à vista:
- taxa média: R$ 2,00 por ingresso
- custo médio de gateway: 0,7 × R$ 0,40 + 0,3 × R$ 1,20 = R$ 0,64
- **margem média: ~R$ 1,36 por ingresso (cerca de 3,4% do valor vendido)**

| Custo fixo anual | Ingressos para empatar | Valor vendido (GMV) |
|---|---|---|
| R$ 60 mil (só infraestrutura e ferramentas, sem salário) | ~44 mil | ~R$ 1,8 milhão |
| R$ 180 mil | ~132 mil | ~R$ 5,3 milhões |
| R$ 300 mil | ~220 mil | ~R$ 8,8 milhões |

Isso é **cerca de 2,5 vezes mais volume** que no modelo anterior (taxa fixa por faixa), porque a taxa por ingresso é bem menor. Os planos pagos ajudam: 50 assinantes Pro rendem ~R$ 28 mil por ano.

| Cenário (hipótese) | Ingressos/ano | Margem após gateway | Custo fixo | Resultado |
|---|---|---|---|---|
| Ano 1 (validação) | ~15 mil (R$ 600 mil) | ~R$ 20 mil | R$ 60–120 mil | prejuízo |
| Ano 2 | ~125 mil (R$ 5 milhões) | ~R$ 170 mil | R$ 150–250 mil | perto do zero |
| Ano 3 | ~500 mil (R$ 20 milhões) | ~R$ 680 mil | R$ 400–600 mil | lucro modesto |

Se o ticket médio subir para R$ 100 ou mais, a margem por ingresso **cai**, porque o teto de R$ 2,50 limita a receita enquanto o gateway cobra percentual.

## Posicionamento e psicologia

- **Mensagem:** "Metade da taxa das outras plataformas, no máximo R$ 2,50 por ingresso" e "Sem taxa escondida".
- **Cuidado de comunicação:** na Sympla os 10% já incluem o processador. Deixe claro o que a sua taxa cobre (gateway incluído ou não) para não ser acusado de taxa oculta.
- **Táticas:** teto como âncora (ingresso caro quase não paga mais), preço final visível desde o início, plano do meio como herói.

## Maior risco de preço

**Margem muito fina com cartão e estorno.** Com ~R$ 1,36 de margem média e teto de R$ 2,50, qualquer estorno, ingresso caro no cartão ou parcelamento mal repassado vira prejuízo. Mitigação: negociar tarifas do gateway antes do lançamento, priorizar Pix, repassar juros de parcelamento ao comprador, usar antifraude, reter o repasse até o evento e acompanhar semanalmente a margem real por ingresso.
