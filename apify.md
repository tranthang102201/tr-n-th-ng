# Apify – Ghi chú & cấu hình

> ⚠️ KHÔNG dán token thật vào file này nếu repo được commit/push. Hãy dùng biến môi trường hoặc file `.env` (đã được bỏ qua bởi git).

## Tài khoản
- Trang quản lý: https://console.apify.com
- Email đăng nhập: `<email>`
- Gói (plan): `<Free / Starter / Scale>`

## API Token
- Lấy tại: Console → Settings → Integrations → API tokens
- Biến môi trường: `APIFY_TOKEN=<your_token_here>`

## Actors đang dùng
| Tên Actor | ID (user/actor) | Mục đích | Ghi chú |
|-----------|-----------------|----------|---------|
| `<ví dụ>` | `apify/web-scraper` | Thu thập dữ liệu web | |
|           |                 |          | |

## Input mẫu (JSON)
```json
{
  "startUrls": [{ "url": "https://example.com" }],
  "maxRequestsPerCrawl": 100
}
```

## Gọi bằng API
```bash
curl -X POST "https://api.apify.com/v2/acts/<user~actor>/runs?token=$APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Gọi bằng Python
```python
from apify_client import ApifyClient

client = ApifyClient("<APIFY_TOKEN>")
run = client.actor("apify/web-scraper").call(run_input={
    "startUrls": [{"url": "https://example.com"}],
})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Datasets / Kết quả đã lưu
| Ngày | Actor | Dataset ID | Mô tả |
|------|-------|------------|-------|
|      |       |            |       |

## Ghi chú khác
-
