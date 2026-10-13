# iCOOL Trading

تحليل الانحياز فوق/تحت الافتتاح، قمم وقيعان جلسات آسيا ولندن ونيويورك، تأكيد الإغلاق (كسر مقابل اكتساح)،
مناطق دعم ومقاومة مصنّفة قوية/متوسطة/ضعيفة، إشارات بدرجة 0–100، حاسبة حجم صفقة، وتصدير مؤشر Pine Script v5.

## TradingView
زرّ «TradingView» فوق الرسم يعرض رسم TradingView الرسمي للأداة والإطار نفسيهما، مع رابط «فتح في TradingView».
رمز TradingView يُختار ليطابق مصدر بيانات التحليل (آجل أو فوري). ولاستعمال المنطق داخل TradingView نفسه انسخ كود Pine من اللوحة.

## البيانات
`/api/candles?s=XAUUSD&i=15m` — دالة Vercel بلا اعتماديات. الترتيب:
OANDA (نفس OANDA:XAUUSD في TradingView) ⇐ MetaApi (أسعار وسيطك) ⇐ Binance (رقمية) ⇐ Twelve Data ⇐ Yahoo ⇐ بيانات تجريبية معلنة.

**الأسهل:** افتح «ربط MetaApi» في المنصّة وأدخل التوكن ورقم الحساب — يُحفظان على جهازك فقط.

أو متغيّرات البيئة في Vercel (لا تُكتب في الكود أبداً):
| المتغيّر | الوصف |
|---|---|
| `OANDA_API_KEY` | توكن OANDA v20 (حساب تجريبي مجاني يكفي) |
| `OANDA_ENV` | اختياري: `live` للحساب الحقيقي، الافتراضي `practice` |
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
