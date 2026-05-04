# دليل نشر قاعدة معرفة مجموعة العزب

## 1. قبل النشر
نفّذ من جذر الحزمة:

```powershell
node .\mcp-server.cjs --self-test
powershell -ExecutionPolicy Bypass -File .\scripts\validate_knowledge_package.ps1
```

أو على Linux:

```bash
node ./mcp-server.cjs --self-test
bash ./scripts/validate_knowledge_package.sh
```

## 2. الدمج مع Rasa Pro
انسخ ملفات `rasa/domain/*.yml` إلى مسار مناسب داخل مشروع Rasa، ثم شغّل داخل بيئة Rasa الفعلية:

```bash
rasa data validate
```

## 3. الدمج مع RAG
استخدم `ingestion/enterprise_knowledge_corpus.jsonl` أو `ingestion/enterprise_knowledge_chunks.jsonl` أو `kb.corpus.json`.

## 4. شرط الحكم النهائي
لا يتم وصف الحزمة بأنها Production Ready إلا بعد نجاح JSON validation وManifest validation وMCP self-test وRasa validation عند استخدام Rasa.

**آخر تحديث:** 2026-05-04T04:39:45Z
