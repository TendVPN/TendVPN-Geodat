# 🌐 TendVPN Geodat

Минималистичные **GeoIP** и **Geosite** для роутинга TendVPN: только нужные диапазоны и сервисы, без лишних списков.

## 📍 GeoIP · `geoip.dat`

Максимально уменьшенная база с кастомным списком **`geoip:direct`**.

### ➕ Что включено

- **Россия и Беларусь** — CIDR-диапазоны из трёх независимых геобаз: GeoLite2 (MaxMind), IPinfo и DB-IP.
- **VK Company, Yandex и CDNVideo** — кастомные IP-диапазоны, включая зарубежные активы.
- **Apple Push** — CIDR для корректной доставки уведомлений на iOS.

### ➖ Что исключено через DIFF

- **РКН-списки** из [Re:filter](https://github.com/1andrevich/Re-filter-lists) и [Antifilter.Network](https://antifilter.network) — для разблокировки сервисов.
- **Community-списки** из [Re:filter](https://github.com/1andrevich/Re-filter-lists), [Antifilter.Network](https://antifilter.network) и [Antifilter.Download](https://antifilter.download) — для проблемных, но не заблокированных сервисов: 4PDA, Cloudflare, аниме и других.
- **Зарубежные CDN** из [CDN-RuleSet](https://github.com/PentiumB/CDN-RuleSet), а также кастомные диапазоны Hetzner и ZeroCDN в России и Беларуси.
- **`0.0.0.0/8` из списка `private`** — для предотвращения утечки DNS на некоторых устройствах.

## 🗂️ Geosite · `geosite.dat`

Кастомная база на основе [roscomvpn-geosite](https://github.com/hydraponique/roscomvpn-geosite).

- **Актуальные списки сервисов** — оптимизированы под этот роутинг и очищены от дубликатов.
- **Минималистичный состав** — всё, что не используется в конфиге роутинга, удалено.
- **Меньше нагрузки на ядро** — без лишней фильтрации и include-редиректов.

## 📦 Файлы

| Файл | Назначение |
| --- | --- |
| [`geoip.dat`](./geoip.dat) | IP-диапазоны для маршрутизации |
| [`geosite.dat`](./geosite.dat) | Доменные списки сервисов |
