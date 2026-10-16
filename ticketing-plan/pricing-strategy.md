# Pricing Strategy para Ingresso Campus (nome provisório)

**Premissas assumidas:** B2B2C (organizador vende ao estudante), modelo transacional com plano opcional, moeda em reais, margem bruta alvo acima de 60% após gateway, cliente sensível a preço (estudante e atlética), estágio pré-receita. Os preços abaixo são hipóteses a validar com os primeiros organizadores. Os custos de gateway são estimativas minhas (cerca de 1% no Pix e de 3% a 5% no cartão), então confira o contrato real.

**Strategy type:** Hybrid (taxa fixa por ingresso + assinatura opcional para organizadores recorrentes).
**Por que essa estrutura:** o organizador universitário quase não paga mensalidade e prefere pagar só quando vende. Já o comprador aceita uma taxa pequena e visível. A assinatura entra para quem organiza vários eventos e quer reduzir a taxa e liberar recursos acadêmicos. Taxa fixa e não percentual segue a crítica de Procons e do IDEC a taxas percentuais e diferencia do modelo de 10% da Sympla.

## Taxa de serviço por ingresso (paga pelo comprador, valor fixo)

| Faixa de preço do ingresso | Taxa fixa | Taxa no plano Pro | Taxa no plano Congresso |
|---|---|---|---|
| Gratuito | R$ 0 | R$ 0 | R$ 0 |
| Até R$ 30,00 | R$ 2,90 | R$ 1,90 | R$ 1,50 |
| R$ 30,01 a R$ 80,00 | R$ 4,90 | R$ 3,90 | R$ 2,90 |
| R$ 80,01 a R$ 150,00 | R$ 7,90 | R$ 6,90 | R$ 5,90 |
| Acima de R$ 150,00 | R$ 9,90 | R$ 8,90 | R$ 7,90 |

**Justificativa:** num ingresso de R$ 50, a taxa de R$ 4,90 equivale a cerca de 10%, no nível da Sympla, mas fixa e visível. A faixa mais barata (R$ 2,90) mantém festas universitárias de ticket baixo competitivas. Se o organizador preferir absorver a taxa, ela é descontada do repasse com o mesmo valor, sem acréscimo.

## Planos do organizador

### Essencial (grátis)
- **Preço:** R$ 0/mês
- **Para quem:** atléticas e centros acadêmicos que fazem 1 ou 2 eventos por semestre.
- **Inclui:** páginas de evento, ingressos e lotes ilimitados, Pix e cartão, QR code, check-in pelo celular, relatório financeiro, repasse em D+3 após o evento.
- **Fica de fora (para estimular upgrade):** certificados, cupons avançados, repasse antecipado, domínio próprio.
- **Justificativa:** sem barreira de entrada. O custo para a plataforma é zero se não houver venda.

### Pro (herói do catálogo)
- **Preço:** R$ 47/mês | R$ 449/ano (economiza cerca de 20%)
- **Para quem:** atléticas e empresas juniores com eventos o ano todo, e semanas acadêmicas de cursos grandes.
- **Inclui:** tudo do Essencial, mais certificados automáticos ilimitados, cupons e lotes por turma, taxa reduzida em R$ 1,00 por ingresso, repasse em D+2, marca e logo da organização na página, suporte prioritário por WhatsApp.
- **Justificativa:** o desconto de R$ 1,00 por ingresso paga a assinatura a partir de cerca de 47 ingressos por mês. Anchoring: ao lado do plano Congresso, o Pro parece a escolha razoável. O preço R$ 47 soa menos redondo que R$ 50 e transmite cálculo.

### Congresso
- **Preço:** R$ 197/mês | R$ 1.890/ano (economiza cerca de 20%)
- **Para quem:** congressos, simpósios e semanas científicas de universidades e sociedades, com várias trilhas e submissão de trabalhos.
- **Inclui:** tudo do Pro, mais submissão e avaliação de trabalhos, programação com várias trilhas, taxa reduzida em R$ 2,00 a R$ 2,50 por ingresso, repasse antecipado parcial, API e exportação de dados, onboarding assistido.
- **Justificativa:** concorre com a Even3 e entrega valor maior por evento. Com milhares de inscritos por edição, a taxa reduzida mais que paga a assinatura.

## Posicionamento e psicologia

- **Posição de mercado:** valor líder no nicho universitário. Mais barato e mais transparente que Sympla e Ingresse para eventos pequenos, e mais simples que a Even3 para eventos de entretenimento.
- **Táticas:** taxa fixa em reais (ancora no preço final e evita a sensação de "porcentagem escondida"), plano do meio como herói, desconto anual de cerca de 20% (aversão à perda), preço final exibido desde o início.
- **Gatilhos de upgrade:** o segundo evento no semestre, a necessidade de certificados, o volume passar de ~47 ingressos por mês, e o pedido de repasse antecipado.

## Otimização de receita

1. **Antecipação de repasse:** cobrar 2% a 3% sobre o valor antecipado, um serviço que os organizadores pedem muito.
2. **Taxa de certificado extra** para eventos no plano Essencial (por exemplo, R$ 0,50 por certificado emitido).
3. **Totem e equipe de credenciamento** em eventos grandes, cobrados à parte.
4. **Patrocínio:** vender destaque na vitrine de eventos a marcas que querem falar com universitários (com consentimento, conforme a LGPD).

## Unidade econômica de exemplo (hipótese)

Ingresso de R$ 50 no plano Essencial com cartão: o comprador paga R$ 54,90. A taxa de R$ 4,90 menos o custo do gateway (~R$ 2,00 a R$ 2,20 em cartão, estimativa) deixa ~R$ 2,70 de margem. Com Pix, o custo cai para ~R$ 0,50 e a margem sobe para ~R$ 4,40. Incentivar o Pix melhora a rentabilidade, por exemplo com um pequeno desconto na taxa.

## Maior risco de preço

**Estorno e fraude de cartão consumindo a margem.** Com margem de ~R$ 2,70 por ingresso, um único estorno de R$ 54,90 apaga a margem de 20 ingressos. Mitigação: privilegiar o Pix, usar antifraude do gateway, limitar o cartão em lotes de alto valor, reter o repasse até o evento e acompanhar a taxa de estorno semanalmente desde o primeiro evento.
