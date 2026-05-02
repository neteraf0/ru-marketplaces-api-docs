# ru-marketplaces-api-docs

Offline API docs for Russian marketplaces, structured for [Context7]([https://context7.com/](https://context7.com/neteraf0/ru-marketplaces-api-docs) / devrag.

Each endpoint lives in its own Markdown file — one file, one API call, no noise.

## Sources

| Source | Type | Coverage |
|--------|------|----------|
| **Wildberries** | OpenAPI (RSC extraction via Chrome) | 12 sections, ~300 endpoints |
| **Ozon** | OpenAPI (manual download) | ~430 endpoints, 52 tags |
| **Yandex Market** | OpenAPI YAML (git clone) | Full partner API |
| **Bitrix24** | Markdown (git clone) | Full REST docs |

## Structure

```
{source}/{tag}/index.md          — tag overview + endpoint list
{source}/{tag}/{METHOD}_{path}.md — one file per endpoint
{source}/{tag}/examples/*.json   — request/response examples
{source}/_shared/examples/*.json — deduplicated shared examples
```

Example: `wb/orders-fbs/POST__api_v3_orders_stickers.md`

## Using with Context7 / devrag

Point your devrag config at this repo root. Each endpoint file is self-contained:
- HTTP method + path in the heading
- Parameters table
- Request body schema
- Response schemas with examples

## Updating docs

Requires Python 3.11+ on `$PATH`. The script self-bootstraps its own venv on first run.

```bash
./update-docs          # interactive menu
./update-docs wb ym    # specific sources only
./update-docs --force  # ignore cache, re-process everything
```

**WB** — opens Chrome (real browser needed for antibot). Headless by default, add `--headed` if you want to see it.

**Ozon** — requires manual download:
1. Open https://docs.ozon.ru/api/seller/swagger.json in your browser
2. Save the file (`Cmd+S` → `seller.json`)
3. Pass the path when the script asks, or use `--ozon-json ~/Downloads/seller.json`

The script validates the file before accepting it (checks for ~430 endpoints, ~52 tags).

**Yandex Market** and **Bitrix24** — just git clone/pull, no browser needed.

## State file

`.fetch-state.json` tracks SHA256 of each processed endpoint. Re-runs only write files whose content changed.
