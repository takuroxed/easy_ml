EasyML - Библиотека для MoonLoader

EasyML - это мощная и удобная библиотека для MoonLoader, упрощающая разработку скриптов для GTA:SA и SA:MP. Она предоставляет множество функций для работы с игроками, транспортом, текстом, памятью, сетевыми событиями, анимациями, звуком, камерой и многим другим. Основная цель - сократить количество кода и сделать разработку быстрее и проще.
Установка

    Скачайте файл easy_ml.lua.
    Поместите его в папку moonloader/lib/.
    В вашем скрипте добавьте:
    lua

    local eml = require 'easy_ml'

Зависимости

    MoonLoader
    SA:MP (для сетевых функций)
    Библиотеки ffi, samp.events, memory (входят в MoonLoader)

Возможности
Управление игроком

    Проверка активности: eml.isPlayerActive()
    Установка/получение позиции: eml.pos(), eml.getPos()
    Здоровье, броня, деньги: eml.setHealth(), eml.setArmor(), eml.setMoney()
    Бессмертие: eml.god()
    Скин и розыск: eml.setSkin(), eml.setWanted()

Переменные

    Установка, получение, изменение: eml.varSet(), eml.varGet(), eml.varInc(), eml.varDec(), eml.varClear()

Текст

    Отрисовка текста: eml.text()
    Текстовые метки: eml.mapText(), eml.drawMap()

Память

    Чтение/запись: eml.memWrite(), eml.memRead()
    Заполнение, копирование, строки, HEX: eml.memFill(), eml.memCopy(), eml.memStr(), eml.memHex()

Чат и команды SA:MP

    Отправка сообщений: eml.chat(), eml.say(), eml.me(), eml.shout()
    Обработка сообщений: eml.onChat(), eml.onChatMsg()
    Команды: eml.sendCmd(), eml.onCmd()

Сетевые функции

    События SA:MP: eml.onTextDraw(), eml.onPlayerJoin(), eml.onPlayerSpawn(), eml.onPlayerDeath(), eml.onVehicleSpawn(), eml.onDialog()
    Управление игроками: eml.getPlayerName(), eml.getPlayerPos(), eml.kickPlayer(), eml.banPlayer(), eml.setPlayerPos(), eml.giveWeapon()

Игровые утилиты

    Спавн транспорта: eml.spawnVeh()
    Анимации: eml.playAnim()
    Погода и время: eml.setWeather(), eml.setTime()
    Звук: eml.playSound()
    Камера: eml.setCamPos(), eml.pointCamAt(), eml.restoreCam()
    Педы и объекты: eml.createPed(), eml.createObj()
    Транспорт: eml.setVehColor(), eml.setVehHealth(), eml.fixVeh(), eml.explodeVeh()
    Гравитация и скорость: eml.setGravity(), eml.setGameSpeed()
    HUD и радар: eml.toggleHud(), eml.toggleRadar()

Листенер

    Условное выполнение: eml.listen()

Примеры использования

Смотрите файл example_usage.lua для полного списка примеров. Основные:
lua
local eml = require 'easy_ml'

-- Телепортация
eml.pos('-x', 1000) -- Установить X = 1000
eml.pos('4st') -- Телепорт к казино

-- Переменные
eml.varSet('score', 100)
eml.varInc('score', 10) -- score = 110

-- Текст
eml.text('Hello', 'center', 0.5, 0.5, 0xFF0000FF) -- Красный текст
eml.mapText(1, 'Zone', 0.5, 0.5) -- Текстовая метка
eml.drawMap() -- Отрисовка меток

-- Чат
eml.chat('Hi!')
eml.me('waves') -- /me waves
eml.onChat('test', function() eml.chat('Test detected!') end)

-- Память
eml.memWrite(0xB7CEE4, 4, 10000) -- Установить деньги

-- Сетевые функции
eml.onPlayerJoin(0, function(id) eml.chat('Player joined!') end)
eml.giveWeapon(1, 24, 100) -- Дать игроку Desert Eagle

-- Игровое
eml.god(true) -- Бессмертие
eml.spawnVeh(411) -- Спавн Infernus
eml.playAnim('WAVE', 'PED') -- Анимация
eml.setWeather(9) -- Дождь
eml.setCamPos(1000, 1000, 50) -- Позиция камеры
eml.createPed(7, 1000, 1000, 10) -- Создать педа
eml.setGravity(0.004) -- Низкая гравитация
Лицензия

MIT License. Используйте свободно, но с указанием авторства.
