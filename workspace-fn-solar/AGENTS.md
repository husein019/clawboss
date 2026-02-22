# AGENTS.md — Solar EPC Engineering Playbook

## Load Calculation
- Toplam yük: `P_total = Σ P_i`
- Görünən güc: `S = P / PF`
- 3 faza cərəyanı: `I_3φ = (P * 1000) / (1.732 * 400 * 0.9)`

## Solar Sizing
- DC gücü: `P_dc = panel_power * qty`
- İllik enerji: `Energy_year = P_dc(kWp) * 1600 * (1 - 0.14)`

## String Design
- Soyuq şəraitdə gərginlik: `Voc_cold = Voc * (1 + (-0.0035 * ΔT))`
- Qaydalar: String `Voc` inverterin max DC gərginliyindən az olmalıdır; `Vmp_total` MPPT pəncərəsi daxilində saxlanmalıdır.

## DC Kabel Seçimi
- Cərəyan: `I_dc = Isc * 1.25`
- Gərginlik itkisi hədəfi: `< 2%`

## AC Kabel Seçimi
- `ΔV% ≈ (1.732 * I * R * L) / V`
- Hədəf: `< 5%`

## Mühafizə Avadanlıqları
- **DC:**
  - DC izolyatoru
  - SPD Type II
  - Paralel string varsa string sığortası
- **AC:**
  - MCCB
  - AC SPD Type II
  - Tələbdən asılı olaraq RCD

## BOM Tərtibatı
| Item | Description | Spec | Qty | Unit |
- DC materiallarını və AC materiallarını ayrı göstər
- Kabellərə +5–10% ehtiyat əlavə et

## Yield & ROI
- İllik qənaət: `Savings = Energy_year * tariff`

## Self Check
- Mühafizə cərəyanı ≥ kabel ampacitəti
- Gərginlik itkiləri limit daxilindədir
- Bütün qəbul edilən fərziyyələr siyahıda göstərilib
