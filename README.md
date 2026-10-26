# shronshiki-proxy

Посредник между приложением [Shronshiki](https://github.com/NixSov/EXP1/tree/claude/shronshiki-voice-chat-7xg4o3/Shronshiki)
и Supabase для сетей, где `*.supabase.co` недоступен без VPN. Работает на Deno Deploy.

- Пересылает только `/auth/v1/*` и `/rest/v1/*` в один проект Supabase.
- `GET /health` — проверка (ответ `ok`).
- Ключей не хранит: приложение передаёт свой publishable key, как и при прямом подключении.

## Настройка в Deno Deploy

Переменная окружения (Settings → Environment Variables, контекст Production):

| Имя | Значение |
|---|---|
| `SUPABASE_URL` | `https://<проект>.supabase.co` |

Исходник и описание: `Shronshiki/proxy/` в репозитории EXP1.
