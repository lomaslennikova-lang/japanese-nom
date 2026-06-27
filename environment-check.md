# Environment Check

Шаблон для перевірки робочого середовища перед запуском або демонстрацією проекту.

## Cursor

- [ ] Cursor встановлено
- [ ] Відкрито правильну папку проекту
- [ ] Розширення/плагіни проекту встановлено
- [ ] Термінал у Cursor відкривається без помилок
- [ ] Команди проекту запускаються з кореневої папки

Команди для перевірки:

```powershell
Get-Location
Get-ChildItem
code --version
```

Нотатки:

```text
Перевірено: 2026-06-26 20:47:41 -04:00.
Поточна папка: C:\Users\lomas\Workspace\japanese-nom.
У папці є README.md, environment-check.md, VibeCoding_Masliennikova_HW01.txt, VibeCoding_Masliennikova_HW02.txt.
Cursor CLI доступний: 3.8.23 x64.
Команда code --version також працює: 1.125.1 x64.
Під час запуску cursor/code є попередження Crashpad: CreateFile: Access is denied (0x5), але версія виводиться.
```

## AI-помічник

- [ ] AI-помічник доступний у Cursor
- [ ] Обрано потрібну модель
- [ ] AI-помічник бачить файли проекту
- [ ] Перевірено базову команду або запит
- [ ] Немає проблем із доступом або авторизацією

Команди/дії для перевірки:

```text
1. Відкрити чат AI-помічника у Cursor.
2. Поставити запит: "Покажи структуру цього проекту".
3. Перевірити, що помічник бачить README.md та інші файли проекту.
```

Нотатки:

```text
Автоматично з терміналу перевірити доступність AI-помічника в інтерфейсі Cursor неможливо.
Потрібна ручна перевірка в Cursor: відкрити чат, поставити запит про структуру проекту і переконатися, що AI бачить файли проекту.
```

## Docker

- [ ] Docker встановлено
- [ ] Docker Desktop запущено
- [ ] Команда `docker --version` працює
- [ ] Команда `docker compose version` працює
- [ ] Контейнери проекту збираються без помилок
- [ ] Контейнери проекту запускаються без помилок

Команди для перевірки:

```powershell
docker --version
docker compose version
docker info
docker ps
docker compose config
docker compose up --build
```

Нотатки:

```text
Docker CLI встановлений: Docker version 29.5.3, build d1c06ef.
Docker Compose встановлений: Docker Compose version v5.1.4.
docker info бачить client/plugins, але Server недоступний: permission denied while trying to connect to the docker API at npipe:////./pipe/docker_engine.
docker ps також завершується з permission denied до docker_engine.
Є попередження Docker config: C:\Users\lomas\.docker\config.json: Access is denied.
docker compose config не знаходить compose-файл у проекті: no configuration file provided: not found.
Висновок: Docker CLI є, але Docker Engine/доступ до нього зараз не готовий для запуску контейнерів з цього терміналу.
```

## Localhost

- [ ] Локальний сервер запускається
- [ ] Відомий порт запуску проекту
- [ ] Сторінка відкривається у браузері
- [ ] Немає конфлікту портів
- [ ] Основні сторінки/ендпоінти відповідають

Команди для перевірки:

```powershell
netstat -ano | findstr :3000
netstat -ano | findstr :5173
curl http://localhost:3000
curl http://localhost:5173
```

URL:

```text
http://localhost:
```

Нотатки:

```text
Порти 3000 і 5173 зараз не слухають: netstat не знайшов активних процесів.
http://localhost:3000 недоступний: curl failed to connect.
http://localhost:5173 недоступний: curl failed to connect.
Висновок: локальний сервер проекту зараз не запущений.
```

## Tunnel

- [ ] Обрано інструмент для тунелю
- [ ] Тунель запускається без помилок
- [ ] Публічний URL відкривається з іншого пристрою/мережі
- [ ] Тунель веде на правильний локальний порт
- [ ] Після перезапуску оновлено актуальний URL

Команди для перевірки:

```powershell
ngrok version
ngrok http 3000
```

Альтернатива, якщо використовується Cloudflare Tunnel:

```powershell
cloudflared --version
cloudflared tunnel --url http://localhost:3000
```

Публічний URL:

```text

```

Нотатки:

```text
ngrok команда знайдена, але не запускається: Program 'ngrok.exe' failed to run: The file cannot be accessed by the system.
cloudflared не встановлений або не доданий у PATH: command not recognized.
Висновок: tunnel-інструмент зараз не готовий до використання без додаткового налаштування.
```

## Git

- [ ] Git встановлено
- [ ] Команда `git --version` працює
- [ ] Налаштовано `user.name`
- [ ] Налаштовано `user.email`
- [ ] Репозиторій має правильний remote
- [ ] Команди `git status`, `git add`, `git commit` працюють
- [ ] Зміни можна відправити у віддалений репозиторій

Команди для перевірки:

```powershell
git --version
git status
git config --global user.name
git config --global user.email
git remote -v
git branch
```

Remote:

```text

```

Нотатки:

```text
Git встановлений: git version 2.54.0.windows.1.
Поточна гілка: environment/setup.
user.name: Liliia.
user.email: lomaslennikova@gmail.com.
Remote origin: git@github.com:lomaslennikova-lang/japanese-nom.git.
git status показує незакомічену зміну: M environment-check.md.
Висновок: Git налаштований і репозиторій підключений до remote.
```
