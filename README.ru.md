<p align="center">
  <img src="assets/logo.png" width="88" alt="Multitool">
</p>

<h1 align="center">Multitool Ads — MCP-сервер для Meta Ads</h1>

<p align="center">
  Подключите Claude, ChatGPT, Codex, Cursor, VS Code, Gemini CLI, Antigravity, OpenCode или любой
  MCP-клиент ко всем своим рекламным кабинетам Meta.
</p>

<p align="center">
  <a href="https://cursor.com/install-mcp?name=multitool&config=eyJ1cmwiOiJodHRwczovL21jcC5tdWx0aXRvb2xzLnByby9tY3AifQ%3D%3D"><img src="https://cursor.com/deeplink/mcp-install-dark.svg" alt="Add to Cursor" height="32"></a>
  <a href="https://vscode.dev/redirect/mcp/install?name=multitool&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.multitools.pro%2Fmcp%22%7D"><img src="https://img.shields.io/badge/VS_Code-Install_server-0098FF?style=for-the-badge" alt="Install in VS Code" height="32"></a>
  <a href="https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=Multitool%20Ads&connectorUrl=https%3A%2F%2Fmcp.multitools.pro%2Fmcp"><img src="https://img.shields.io/badge/Claude-Add_connector-D97757?style=for-the-badge&logo=claude&logoColor=white" alt="Add to Claude" height="32"></a>
</p>

<p align="center"><a href="README.md">English version</a></p>

---

Спрашивайте о расходе и результатах обычными словами, находите то, что не откручивается,
сравнивайте кампании и креативы, ставьте на паузу, запускайте и меняйте бюджеты. Каждое изменение
сначала показывается на предпросмотре и уходит в Мету только после вашего подтверждения.

| | |
|---|---|
| **Адрес сервера** | `https://mcp.multitools.pro/mcp` |
| **Транспорт** | Streamable HTTP |
| **Вход** | OAuth через аккаунт Multitool, без API-ключей |
| **Что нужно** | Аккаунт [Multitool](https://multitools.pro) с подключёнными профилями Facebook |

Любой способ ниже заканчивается одинаково: в браузере открывается Multitool — **войдите, выберите
воркспейс и нажмите «Разрешить»**.

## Установка

- [Cursor](#cursor) · [VS Code](#vs-code) · [Claude (сайт и приложение)](#claude-сайт-и-приложение) · [ChatGPT](#chatgpt)
- [Claude Code](#claude-code) · [Codex](#codex) · [Gemini CLI](#gemini-cli) · [OpenCode](#opencode)
- [Antigravity](#antigravity) · [Windsurf и другие клиенты](#windsurf-и-другие-клиенты)
- [Установка руками агента](#установка-руками-агента)

### Cursor

Нажмите **Add to Cursor** вверху страницы, затем **Install**. Откройте **Customize** на боковой
панели и войдите в `multitool`, когда Cursor попросит.

### VS Code

Нажмите **Install in VS Code** вверху страницы, затем **Install**. При первом подключении VS Code
сам откроет страницу входа. Нужен GitHub Copilot в режиме агента.

### Claude (сайт и приложение)

Нажмите **Add to Claude** вверху страницы, затем **Add** и **Connect**.

Вручную: **Customize → Connectors → Add custom connector**, название `Multitool Ads`, адрес
`https://mcp.multitools.pro/mcp`. В чате проверьте, что **Multitool Ads** включён в **+ → Connectors**.

### ChatGPT

Откройте [chatgpt.com/plugins](https://chatgpt.com/plugins), нажмите **+**, затем **Add custom MCP server**.
Название `Multitool Ads`, адрес `https://mcp.multitools.pro/mcp`, подтвердите предупреждение,
создайте и войдите.

### Claude Code

```shell
claude mcp add --transport http --scope user multitool https://mcp.multitools.pro/mcp
```

```shell
claude mcp login multitool
```

Плагином: `/plugin marketplace add multitool-ads/mcp`, затем
`/plugin install multitool@multitool-ads` и вход через `/mcp`.

### Codex

```shell
codex mcp add multitool --url https://mcp.multitools.pro/mcp
```

Codex сразу откроет страницу входа. Если не открыл, выполните `codex mcp login multitool`.

Плагином (Codex и приложение ChatGPT для компьютера): `codex plugin marketplace add multitool-ads/mcp`,
затем `codex plugin add multitool@multitool-ads`.

### Gemini CLI

```shell
gemini extensions install https://github.com/multitool-ads/mcp
```

Запустите `gemini`; если браузер не открылся сам, выполните `/mcp auth multitool`.

Без расширения: `gemini mcp add --scope user --transport http multitool https://mcp.multitools.pro/mcp`

### OpenCode

```shell
opencode mcp add multitool --global --url https://mcp.multitools.pro/mcp
```

```shell
opencode mcp auth multitool
```

### Antigravity

**Antigravity CLI** — одна команда, затем вход через `/mcp` внутри `agy`:

```shell
agy mcp add multitool https://mcp.multitools.pro/mcp
```

Плагином: `agy plugin install https://github.com/multitool-ads/mcp`

**Antigravity IDE и приложение Antigravity** — добавьте сервер и нажмите **Authenticate**:

1. Добавьте сервер в `~/.gemini/config/mcp_config.json` или вставьте подсказку ниже в чат агента.
   В IDE файл открывается так: `Ctrl+Shift+P` → **Manage MCP Servers** → **View raw config**:
   ```json
   {
     "mcpServers": {
       "multitool": { "serverUrl": "https://mcp.multitools.pro/mcp" }
     }
   }
   ```
   Серверы, которые уже есть в файле, оставьте.
2. Откройте список серверов:
   - **IDE:** нажмите `Ctrl+Shift+P` (`Cmd+Shift+P` на Mac) и выполните **Manage MCP Servers**.
   - **Приложение:** **Customizations → Installed → MCP Servers**.
3. Нажмите **Authenticate** рядом с `multitool` и войдите в Multitool в браузере.
4. Браузер покажет код авторизации. Скопируйте его, вставьте в поле **Enter authorization code**
   в Antigravity и нажмите **Submit**.

Подсказка для агента Antigravity:

```text
Добавь MCP-сервер в мой конфиг Antigravity. Открой файл ~/.gemini/config/mcp_config.json (создай, если его нет) и добавь внутрь "mcpServers" эту запись, не меняя остальные:
"multitool": { "serverUrl": "https://mcp.multitools.pro/mcp" }
Сохрани файл и проверь, что JSON корректный. Потом скажи мне ровно это: «Нажми Ctrl+Shift+P (Cmd+Shift+P на Mac), выполни Manage MCP Servers, нажми Authenticate рядом с multitool, войди, затем скопируй код из браузера в поле Enter authorization code и нажми Submit». Больше ничего не делай и не спрашивай API-ключ: его нет.
```

### Windsurf и другие клиенты

Подойдёт любой клиент, который умеет подключать удалённые MCP-серверы с OAuth. Добавьте сервер с
адресом `https://mcp.multitools.pro/mcp` (транспорт Streamable HTTP) и войдите, когда клиент
попросит. Клиент регистрируется сам: копировать идентификатор клиента или API-ключ не нужно.

Большинство клиентов понимают такой JSON:

```json
{
  "mcpServers": {
    "multitool": { "url": "https://mcp.multitools.pro/mcp" }
  }
}
```

В Windsurf вместо `url` пишется `serverUrl`, файл — `~/.codeium/windsurf/mcp_config.json`.

### Установка руками агента

Если не хочется ничего вводить, вставьте это в чат агента в своей программе. Текст написан так,
чтобы по шагам прошла даже слабая модель.

```text
Установи мне MCP-сервер Multitool Ads. Адрес: https://mcp.multitools.pro/mcp (Streamable HTTP, вход через OAuth, API-ключа нет). Сделай только шаг для той программы, в которой ты работаешь:
- Claude Code: выполни `claude mcp add --transport http --scope user multitool https://mcp.multitools.pro/mcp`, потом скажи мне выполнить `claude mcp login multitool`.
- Codex: выполни `codex mcp add multitool --url https://mcp.multitools.pro/mcp`; он сам откроет страницу входа. Если не открыл, скажи мне выполнить `codex mcp login multitool`.
- Gemini CLI: выполни `gemini mcp add --scope user --transport http multitool https://mcp.multitools.pro/mcp`, потом скажи мне перезапустить Gemini CLI и выполнить `/mcp auth multitool`.
- OpenCode: выполни `opencode mcp add multitool --global --url https://mcp.multitools.pro/mcp`, потом скажи мне выполнить `opencode mcp auth multitool`.
- Antigravity: добавь "multitool": { "serverUrl": "https://mcp.multitools.pro/mcp" } внутрь "mcpServers" в ~/.gemini/config/mcp_config.json, не трогая остальные записи; потом скажи мне нажать Ctrl+Shift+P, выполнить Manage MCP Servers, нажать Authenticate рядом с multitool и вставить код из браузера.
- Cursor: добавь "multitool": { "url": "https://mcp.multitools.pro/mcp" } внутрь "mcpServers" в ~/.cursor/mcp.json, не трогая остальные записи; потом скажи мне открыть Customize и войти в multitool.
- Windsurf: добавь "multitool": { "serverUrl": "https://mcp.multitools.pro/mcp" } внутрь "mcpServers" в ~/.codeium/windsurf/mcp_config.json, не трогая остальные записи; потом скажи мне обновить список MCP-серверов и войти.
После этого остановись. Других шагов не придумывай.
```

## Что можно спросить

- «Покажи расход и результаты за сегодня по всем кабинетам»
- «Какие кампании сегодня потратили больше $50 без результатов?»
- «Почему эта группа объявлений не откручивается?»
- «Отсортируй креативы по цене результата за последние 7 дней»
- «Поставь на паузу все объявления в кампании X» — агент сначала покажет предпросмотр и дождётся
  подтверждения

## Безопасность

- **Только ваш доступ.** Multitool видит лишь те рекламные кабинеты, к которым есть доступ у ваших
  подключённых профилей Facebook, а при входе вы сами выбираете воркспейс для клиента.
- **Предпросмотр перед каждым изменением.** Пауза, запуск, бюджеты, названия и креативы сначала
  показываются на предпросмотре; в Мету ничего не уходит без вашего подтверждения.
- **Отключить можно в любой момент** в Multitool: **Настройки → AI-подключения**, или выйти из
  сервера в самом клиенте.

## Если что-то не так

| Что видно | Что сделать |
|---|---|
| Сервер показывает *Unauthorized*, *needs authentication* или красную точку | Вход не завершён. Выполните шаг входа для своей программы выше: Authenticate, `/mcp`, `mcp login` или `mcp auth`. |
| После входа в чате нет инструментов Multitool | Начните новый чат или перезагрузите окно: часть клиентов загружает инструменты только в начале разговора. |
| Браузер пишет, что воркспейса нет | Создайте воркспейс на [multitools.pro](https://multitools.pro) и сначала подключите профиль Facebook. |
| За какой-то период пустые цифры | Спросите агента, обновлены ли данные: он сообщает о свежести, а не показывает нули. |

## О проекте

Multitool — рабочий кабинет Meta Ads для медиабайеров и агентств, которые ведут много рекламных
кабинетов и профилей Facebook. Сайт: [multitools.pro](https://multitools.pro) · Поддержка:
[support@multitools.pro](mailto:support@multitools.pro) ·
[Политика конфиденциальности](https://multitools.pro/privacy) · [Условия использования](https://multitools.pro/terms)

В этом репозитории — настройки клиентов (плагины и манифесты) для нашего сервера. Лицензия —
[MIT](LICENSE).
