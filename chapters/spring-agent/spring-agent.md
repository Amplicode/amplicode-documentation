---
title: Spring Agent — подключение к AI-агентам
weight: 0
---

Spring Agent — это встроенный MCP Server в плагине Amplicode для IntelliJ IDEA / GigaIDE. Он предоставляет AI-агентам доступ к инструментам анализа и генерации кода для Spring-проектов непосредственно из вашей IDE.

## Шаг 1. Включение MCP Server

Перед подключением любого AI-агента необходимо запустить MCP Server:

1. Откройте настройки IDE: **File → Settings** (или **IntelliJ IDEA → Settings** на macOS)
2. Перейдите в **Tools → Amplicode → MCP Server**
3. Убедитесь, что флажок **Enable MCP Server** установлен

После включения рядом с флажком отобразится адрес сервера: `Running on http://127.0.0.1:64442/sse`

![enable-mcp-server.png](img/enable-mcp-server.png)

## Автоматическая конфигурация клиента

Для ряда клиентов Amplicode поддерживает автоматическую настройку. Если ваш клиент присутствует в разделе **Clients Auto-Configuration**, выполните следующие действия:

1. В панели **Tools → Amplicode → MCP Server** найдите раздел **Clients Auto-Configuration**
2. Найдите нужный клиент в списке
3. Нажмите **Auto-Configure** напротив него
4. После успешной настройки рядом появится статус **✓ Configured**

![auto-configure.png](img/auto-configure.png)

> Если после нажатия **Auto-Configure** отображается сообщение _«restart the client if changes aren't applied»_, перезапустите AI-клиент.

Автоматическая конфигурация поддерживается для следующих клиентов:

- [Claude Code](#claude-code)
- [Codex](#codex)
- [Continue](#continue)

Для остальных клиентов используйте [ручную конфигурацию](#ручная-конфигурация).

---

## Ручная конфигурация

Если ваш клиент не поддерживает автоматическую настройку, воспользуйтесь ручным способом:

1. В панели **Tools → Amplicode → MCP Server** найдите раздел **Manual Configuration**
2. Нажмите **Copy JSON SSE Config** — конфигурация будет скопирована в буфер обмена

![copy-config.png](img/copy-config.png)

Скопированная конфигурация имеет вид:

```json
"mcpServers": {
    "amplicode": {
        "type": "sse",
        "url": "http://127.0.0.1:64442/sse"
    }
}
```

Инструкции по добавлению этой конфигурации в каждый клиент описаны ниже.

---

## Claude Code

**Поддерживает Auto-Configure: да**

### Автоматически

Используйте кнопку **Auto-Configure** в панели **Tools → Amplicode → MCP Server**.

### Вручную

Выполните команду в терминале:

```bash
claude mcp add --transport sse amplicode http://127.0.0.1:64442/sse
```

Или добавьте конфигурацию вручную через:

```bash
claude mcp add amplicode --transport sse http://127.0.0.1:64442/sse
```

Для проверки подключения выполните:

```bash
claude mcp list
```

---

## Codex

**Поддерживает Auto-Configure: да**

### Автоматически

Используйте кнопку **Auto-Configure** в панели **Tools → Amplicode → MCP Server**.

### Вручную

Откройте файл конфигурации `~/.codex/config.yaml` и добавьте:

```yaml
mcpServers:
  amplicode:
    type: sse
    url: http://127.0.0.1:64442/sse
```

Если файл конфигурации использует формат JSON (`~/.codex/config.json`):

```json
{
  "mcpServers": {
    "amplicode": {
      "type": "sse",
      "url": "http://127.0.0.1:64442/sse"
    }
  }
}
```

---

## Continue

**Поддерживает Auto-Configure: да**

### Автоматически

Используйте кнопку **Auto-Configure** в панели **Tools → Amplicode → MCP Server**.

### Вручную

Откройте файл конфигурации Continue. Расположение по умолчанию:

- **Глобальная конфигурация**: `~/.continue/config.json`
- **Конфигурация проекта**: `.continue/config.json` в корне проекта

Добавьте в секцию `mcpServers`:

```json
{
  "mcpServers": [
    {
      "name": "amplicode",
      "transport": {
        "type": "sse",
        "url": "http://127.0.0.1:64442/sse"
      }
    }
  ]
}
```

После сохранения файла перезагрузите окно VS Code или перезапустите IDE.

---

## Cursor

**Поддерживает Auto-Configure: нет**

Откройте файл конфигурации MCP для Cursor. Расположение:

- **Глобальная конфигурация**: `~/.cursor/mcp.json`
- **Конфигурация проекта**: `.cursor/mcp.json` в корне проекта

Добавьте конфигурацию:

```json
{
  "mcpServers": {
    "amplicode": {
      "type": "sse",
      "url": "http://127.0.0.1:64442/sse"
    }
  }
}
```

Если файл `mcp.json` уже существует, добавьте `"amplicode"` в секцию `mcpServers`.

После сохранения перезапустите Cursor или откройте **Cursor Settings → MCP** и нажмите **Refresh**.

---

## OpenCode

**Поддерживает Auto-Configure: нет**

Откройте файл конфигурации OpenCode:

- **macOS / Linux**: `~/.config/opencode/config.json`
- **Windows**: `%APPDATA%\opencode\config.json`

Добавьте секцию `mcp`:

```json
{
  "mcp": {
    "amplicode": {
      "type": "sse",
      "url": "http://127.0.0.1:64442/sse"
    }
  }
}
```

Сохраните файл и перезапустите OpenCode.

---

## Kilo Code

**Поддерживает Auto-Configure: нет**

Kilo Code — расширение для VS Code. Откройте настройки расширения одним из способов:

**Через файл настроек VS Code** (`settings.json`):

```json
{
  "kilocode.mcpServers": {
    "amplicode": {
      "type": "sse",
      "url": "http://127.0.0.1:64442/sse"
    }
  }
}
```

**Через интерфейс Kilo Code:**

1. Откройте панель Kilo Code в боковой панели VS Code
2. Перейдите в **Settings → MCP Servers**
3. Нажмите **Add Server** и введите параметры подключения

После добавления перезагрузите окно VS Code (**Developer: Reload Window**).

---

## Gemini CLI

**Поддерживает Auto-Configure: нет**

Откройте файл конфигурации Gemini CLI:

- **macOS / Linux**: `~/.gemini/settings.json`
- **Windows**: `%USERPROFILE%\.gemini\settings.json`

Добавьте секцию `mcpServers`:

```json
{
  "mcpServers": {
    "amplicode": {
      "httpUrl": "http://127.0.0.1:64442/sse"
    }
  }
}
```

Сохраните файл. Изменения применяются при следующем запуске Gemini CLI.

---

## Veai

**Поддерживает Auto-Configure: нет**

Откройте файл конфигурации MCP вашего клиента Veai. Расположение файла конфигурации зависит от версии и платформы — обратитесь к официальной документации Veai.

Добавьте конфигурацию MCP Server в формате JSON:

```json
{
  "mcpServers": {
    "amplicode": {
      "type": "sse",
      "url": "http://127.0.0.1:64442/sse"
    }
  }
}
```

Сохраните файл и перезапустите клиент.

---

## KodaCode

**Поддерживает Auto-Configure: нет**

Откройте файл конфигурации KodaCode. Расположение файла зависит от платформы — обратитесь к официальной документации KodaCode.

Добавьте конфигурацию MCP Server:

```json
{
  "mcpServers": {
    "amplicode": {
      "type": "sse",
      "url": "http://127.0.0.1:64442/sse"
    }
  }
}
```

Сохраните файл и перезапустите клиент.

---

## Проверка подключения

После настройки любого клиента убедитесь в корректной работе MCP Server:

1. Убедитесь, что в панели **Tools → Amplicode → MCP Server** отображается статус **Running on http://127.0.0.1:64442/sse**
2. В вашем AI-клиенте проверьте, что инструменты Amplicode доступны (обычно отображаются как `amplicode/*` или `mcp__amplicode__*`)
3. Выполните тестовый запрос, например: _«Покажи структуру моего Spring-проекта»_

## Устранение неполадок

| Проблема | Решение |
|----------|---------|
| MCP Server не запускается | Убедитесь, что флажок **Enable MCP Server** установлен и IDE открыта с проектом |
| Клиент не видит инструменты | Перезапустите AI-клиент после изменения конфигурации |
| Порт 64442 занят | Проверьте, не запущен ли другой экземпляр IDE с Amplicode |
| Auto-Configure не применяется | Перезапустите AI-клиент; убедитесь, что клиент установлен и путь к нему доступен IDE |

## Связаться с командой Amplicode

Если у вас возникли вопросы или трудности с настройкой, обратитесь к нам:

- <a href="https://t.me/amplicode_chat" target="_blank" rel="noopener noreferrer">Telegram-чат</a>
- или через [форму на сайте](https://amplicode.io/contacts/)
