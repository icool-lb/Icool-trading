# iCOOL Trading

تحليل الانحياز فوق/تحت الافتتاح، قمم وقيعان جلسات آسيا ولندن ونيويورك، تأكيد الإغلاق (كسر مقابل اكتساح)،
مناطق دعم ومقاومة مصنّفة قوية/متوسطة/ضعيفة، إشارات بدرجة 0–100، حاسبة حجم صفقة، وتصدير مؤشر Pine Script v5.

## البيانات
`/api/candles?s=XAUUSD&i=15m` — دالة Vercel بلا اعتماديات. الترتيب:
MetaApi (أسعار وسيطك) ⇐ Binance (رقمية) ⇐ Twelve Data ⇐ Yahoo ⇐ بيانات تجريبية معلنة.

متغيّرات البيئة في Vercel (لا تُكتب في الكود أبداً):
| المتغيّر | الوصف |
|---|---|
| `METAAPI_TOKEN` | توكن MetaApi |
| `METAAPI_ACCOUNT_ID` | رقم حساب MetaTrader في MetaApi |
| `METAAPI_REGION` | اختياري، الافتراضي `new-york` |
| `METAAPI_SUFFIX` | اختياري، لاحقة رموز الوسيط مثل `.m` |
| `METAAPI_SYMBOLS` | اختياري، JSON مثل `{"NAS100":"USTEC"}` |
| `TWELVEDATA_API_KEY` | اختياري |

## اختبار
```bash
NODE_PATH=$(npm root -g) node test/trading.js
```

للتحليل والتعليم فقط — ليست نصيحة مالية.
