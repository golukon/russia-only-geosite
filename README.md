# Что это?

Этот проект каждый день в 00:00 UTC автоматически генерирует `geosite.dat` с доменами, **доступными внутри России**, для Proxy/VPN-приложений (Xray, V2Ray и др.). Таким образом, маршрут по умолчанию должен быть `proxy`, совпадение с доменом из файла — `direct`. Файл получается небольшим (около `13 Кб`, удобен для роутеров), также отпадает необходимость постоянно включать/выключать VPN.

Данные собираются из форков [@golukon](https://github.com/golukon):

- [@golukon/domains-only-russia](https://github.com/golukon/domains-only-russia) — `ru-available-only-inside`
- [@golukon/russia-mobile-internet-whitelist](https://github.com/golukon/russia-mobile-internet-whitelist) — `whitelist.txt`
- [@golukon/domain-list-community](https://github.com/golukon/domain-list-community) — `category-gov-ru`


### Содержимое geosite.dat

- `geosite:ru-inside` — домены, доступные внутри РФ (в т.ч. недоступные из-за границы, белые списки, госсервисы). Дублирование доменов отсутствует

## Смежные проекты

- [@golukon/russia-only-geoip](https://github.com/golukon/russia-only-geoip) — файл `geoip.dat` со всеми российскими IPv4-адресами

## Пример конфигурации для v2rayA (совместно с geoip.dat)

```
default: proxy
ip(geoip:private)->direct

# write your own rules below
ip(geoip:ru)->direct
domain(geosite:ru-inside)->direct
```

# Скачать

По ссылкам ниже всегда доступна последняя версия файлов.

- **github**
    - [https://raw.githubusercontent.com/golukon/russia-only-geosite/release/geosite.dat](https://raw.githubusercontent.com/golukon/russia-only-geosite/release/geosite.dat)
    - Hashsum: [https://raw.githubusercontent.com/golukon/russia-only-geosite/release/geosite.dat.sha256sum](https://raw.githubusercontent.com/golukon/russia-only-geosite/release/geosite.dat.sha256sum)
- **JSDelivr**
    - [https://cdn.jsdelivr.net/gh/golukon/russia-only-geosite@release/geosite.dat](https://cdn.jsdelivr.net/gh/golukon/russia-only-geosite@release/geosite.dat)
    - Hashsum: [https://cdn.jsdelivr.net/gh/golukon/russia-only-geosite@release/geosite.dat.sha256sum](https://cdn.jsdelivr.net/gh/golukon/russia-only-geosite@release/geosite.dat.sha256sum)
- **Fastly + JSDelivr**
    - [https://fastly.jsdelivr.net/gh/golukon/russia-only-geosite@release/geosite.dat](https://fastly.jsdelivr.net/gh/golukon/russia-only-geosite@release/geosite.dat)
    - Hashsum: [https://fastly.jsdelivr.net/gh/golukon/russia-only-geosite@release/geosite.dat.sha256sum](https://fastly.jsdelivr.net/gh/golukon/russia-only-geosite@release/geosite.dat.sha256sum)


## Благодарности

- [@v2fly/domain-list-community](https://github.com/v2fly/domain-list-community) — сборщик и `category-gov-ru`
- [@runetfreedom/russia-domains-list](https://github.com/runetfreedom/russia-domains-list) — список `ru-available-only-inside`
- [@hxehex/russia-mobile-internet-whitelist](https://github.com/hxehex/russia-mobile-internet-whitelist) — список `whitelist.txt`
