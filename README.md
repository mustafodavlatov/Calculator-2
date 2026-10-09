# Calculator-2
def calculate_stars_conversion(
    stars: int,
    ton_price_usd: float = 5.20,     # Текущая цена 1 TON в USD
    usd_rub_rate: float = 85.10,     # Текущий курс USD к RUB
    star_rate_usd: float = 0.013     # Оценка 1 Звезды в USD (вывод через Fragment)
):
    # 1. Стоимость в долларах
    total_usd = stars * star_rate_usd
    
    # 2. Стоимость в рублях
    total_rub = total_usd * usd_rub_rate
    
    # 3. Эквивалент в TON
    total_ton = total_usd / ton_price_usd if ton_price_usd > 0 else 0

    return {
        "stars": stars,
        "usd": round(total_usd, 2),
        "rub": round(total_rub, 2),
        "ton": round(total_ton, 4)
    }

# Пример использования:
stars_count = 1000
result = calculate_stars_conversion(stars_count)

print(f"Количество Звёзд: {result['stars']}")
print(f"В долларах (USD): ${result['usd']}")
print(f"В рублях (RUB):   {result['rub']} ₽")
print(f"В TON:            {result['ton']} TON")
