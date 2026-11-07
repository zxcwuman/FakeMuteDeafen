# FakeMuteDeafen
Показывает окружающим что вы фулл муте но вы можете слышать их и говорите 
Нужны Node.js LTS, Git и pnpm. В терминале (PowerShell или CMD) по одной команде:
открываем cmd
вставляем
winget install OpenJS.NodeJS.LTS
winget install Git.Git
npm install -g pnpm
После установки закрой и снова открой cmd, чтобы команды подхватились. Проверка:
node -v
git --version
pnpm -v
Теперь нужно Скачать исходники Vencord
Открываем cmd пишем
cd %USERPROFILE%\Documents
git clone https://github.com/Vendicated/Vencord
cd Vencord
pnpm install --frozen-lockfile
Первый pnpm install занимает несколько минут — это нормально.
Создать папку и скопировать туда скачанный файл fakeMuteDeafen_index.tsx, переименовав его в index.tsx
открываем cmd
mkdir src\userplugins\fakeMuteDeafen
copy путь\к\fakeMuteDeafen_index.tsx src\userplugins\fakeMuteDeafen\index.tsx
Важно: в папке src\userplugins не должно остаться никаких .bak, .txt и пустых папок — Vencord пытается собрать всё, что там лежит, и падает от лишних файлов. Внутри каждого плагина должен быть рабочий index.tsx
Теперь собираем и внедряем командами в cmd 
pnpm build
pnpm inject
