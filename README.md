# EcoTrax Public Emission Factors

**Version:** 2026-02
**Licence:** [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
**Maintained by:** [EcoTrax](https://ecotrax-events.vercel.app) — Geneva, Switzerland

---

A curated, open-source subset of the emission factors used by [EcoTrax](https://ecotrax-events.vercel.app) to calculate the carbon footprint of corporate events. Published for transparency and to support the broader sustainability community.

## What's included

`emission-factors-public.json` contains base emission factors across three categories:

| Category | Items | Scope | Source |
|---|---|---|---|
| Food & Beverage | 22 items (beef, chicken, fish, dairy, legumes, grains, beverages…) | Scope 3 — cradle-to-plate | [Agribalyse 3.1](https://agribalyse.ademe.fr/) (ADEME) |
| Transport | 13 modes (car petrol/diesel/EV, train, short/long-haul flight, coach…) | Scope 3 — well-to-wheel | [Mobitool.ch 2023](https://www.mobitool.ch/) / DEFRA 2023 |
| Waste Treatment | 10 methods (landfill, composting, recycling, incineration…) | Scope 3 — gate-to-grave | [WRAP UK 2023](https://www.wrap.ngo/) |
| Utilities | 12 factors (electricity by grid, natural gas, LPG, diesel generator, water, district heating) | Scope 1 & 2 | DEFRA 2023 / [SFOE](https://www.bfe.admin.ch/) / Ecoinvent 3.9 / ADEME |

All values are in **kg CO₂e** per unit (kg of food served, passenger-km, or tonne of waste).

## What's NOT included

The complete EcoTrax emission factor library also includes:

- Proprietary adjustment multipliers (organic sourcing, import penalties, venue-type modifiers)
- Venue energy factors (SFOE Swiss grid, HVAC, kitchen appliances)
- Packaging and decor lifecycle factors (Carbon Trust, Ecoinvent 3.9)
- Staff commute and logistics vehicle factors
- AV and lighting power factors

These remain internal. For the full methodology, see [ecotrax-events.vercel.app/methodology](https://ecotrax-events.vercel.app/methodology).

## Usage

```js
const factors = await fetch(
  'https://raw.githubusercontent.com/pyingzhu/ecotrax-emission-factors/main/emission-factors-public.json'
).then(r => r.json());

// kg CO₂e for 10kg of beef
const footprint = 10 * factors.food_beverage.beef; // → 269.42 kg CO₂e
```

## Attribution

If you use this data, please cite:

> EcoTrax (2026). *Public Emission Factors — Curated Subset* (v2026-02). Geneva, Switzerland. Derived from Agribalyse 3.1 (ADEME), Mobitool.ch 2023, WRAP UK 2023. https://github.com/pyingzhu/ecotrax-emission-factors

## Primary Sources

- **Agribalyse 3.1** — ADEME (French Agency for Ecological Transition) — [agribalyse.ademe.fr](https://agribalyse.ademe.fr/)
- **Mobitool.ch 2023** — Swiss transport emission factors — [mobitool.ch](https://www.mobitool.ch/)
- **DEFRA 2023** — UK government emission conversion factors — [gov.uk](https://www.gov.uk/government/collections/government-conversion-factors-for-company-reporting)
- **WRAP UK 2023** — Waste treatment emission factors — [wrap.ngo](https://www.wrap.ngo/)

## Versioning & Changelog

See [CHANGELOG.md](CHANGELOG.md) for a full history of additions and corrections.

Each release is tagged (e.g. `v2026-02`) and listed under [GitHub Releases](https://github.com/pyingzhu/ecotrax-emission-factors/releases).

> **Note:** A Zenodo DOI for formal citation in academic and ESG reports is planned for v2026-06.

## Licence

[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International](LICENSE)

You may share and adapt this data for non-commercial purposes with attribution. See [LICENSE](LICENSE) for full terms.

---

For commercial use or the complete emission factor library, contact [hello@ecotrax.ch](mailto:hello@ecotrax.ch).
