# Equity Due Diligence

A reusable Codex skill for evidence-based research on publicly traded stocks. It supports Arabic and English requests and prioritizes instruments available through Baraka when relevant.

> Research framework, not a trading bot or a promise of returns. It uses lawful public information and does not place orders.

## Why I made it

I wanted a consistent way to investigate an investment idea beyond a ticker, chart, or headline price-to-earnings ratio. Public filings can reveal one-off gains, cash-flow pressure, debt, dilution, related-party transactions, and risks that a simple stock screen misses. The skill makes those checks repeatable and asks for a source and date behind each important claim.

## How I made it

I worked with Codex to:

1. Define the investor's decision frame: market access, horizon, loss capacity, currency, and constraints.
2. Build a source hierarchy led by exchange and regulator filings, company investor-relations reports, and dated market quotes.
3. Add a claim-level evidence ledger so figures and calculations can be checked later.
4. Compare business quality, cash generation, balance-sheet risk, valuation, and investor fit, with different measures for different sectors.
5. Challenge the leading thesis and allow an honest **no attractive candidate** result.

The skill was checked with the bundled `quick_validate.py` validator and exercised on a small public-stock comparison. That test caught an example of large non-operating gains making a headline earnings multiple misleading. The test was a workflow check, not evidence that the skill can predict returns.

## What the skill produces

- A dated, sourced shortlist with clear selection criteria.
- An evidence ledger for decision-driving numbers and disagreements.
- Base, optimistic, and adverse scenarios with explicit assumptions.
- Reasons a candidate could fail and observations that would change the ranking.
- Clear limits when prices, account availability, or filings cannot be verified.

## Use in Codex

Clone or copy this repository into `~/.codex/skills/equity-due-diligence/`, then ask:

```text
Use $equity-due-diligence to compare stocks available in Baraka for a long-term investor. Show the filing sources, key calculations, risks, and what would reverse the ranking.
```

The skill reads its detailed [research method](references/diligence-method.md) when valuing or investigating a candidate and its [official source guide](references/official-sources.md) when locating filings. Source links and platform terms must be checked again at the time of each research run.

## License

Released under the [MIT License](LICENSE).

## Files

| File | Purpose |
|---|---|
| [`SKILL.md`](SKILL.md) | Core instructions and decision boundaries |
| [`references/diligence-method.md`](references/diligence-method.md) | Metrics, investigation prompts, and evidence ledger |
| [`references/official-sources.md`](references/official-sources.md) | Starting points for official disclosures and market access |
| [`agents/openai.yaml`](agents/openai.yaml) | Codex display metadata |
| [`LICENSE`](LICENSE) | Terms for reuse and modification |

## العربية

### لماذا أنشأتها؟

أردت طريقة منتظمة لفحص فكرة استثمارية تتجاوز اسم السهم أو الرسم البياني أو مضاعف الربحية وحده. قد تكشف الإفصاحات عن أرباح غير متكررة، وضعف في التدفقات النقدية، وديون أو تخفيف لملكية المساهمين؛ لذلك صممت المهارة لتُظهر مصدر كل معلومة مهمة وتاريخها وحسابها.

### كيف أنشأتها؟

حددت هدف البحث، ثم عملت مع Codex على تحويله إلى خطوات قابلة للتكرار: البدء بالإفصاحات الرسمية، وتوثيق الأدلة، ومقارنة جودة النشاط والتدفقات النقدية والمخاطر والتقييم، ثم اختبار الفرضية المضادة. تحققت من بنية المهارة بأداة التحقق، وجرّبت سير العمل على مقارنة محدودة لأسهم عامة. هذه التجربة تختبر طريقة البحث ولا تثبت القدرة على توقع العوائد.

قد تنتهي المهارة إلى عدم وجود فرصة جذابة. وهي تستخدم المعلومات العامة المتاحة قانونيًا ولا تنفذ أوامر تداول.
