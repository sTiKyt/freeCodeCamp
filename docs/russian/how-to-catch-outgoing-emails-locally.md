# Как поймать исходящий email локально (Для рабочих процессов электронной почты)

> **Заметка:** Это **необязательный** шаг - Нужен только при работе с рабочими процессами электронной почты.

## Введение

Некоторые рабочие процессы почты, такие как обновление почты пользователя, требуют back-end api-server'a для отправки писем. Во время разработки вы можете использовать инструменты для получения этих писем локально, без использования провайдера, и отправлять фактическое письмо. MailHog один из средств тестирования электронной почты для разработчиков, который будет получать электронные письма, отправленные вашим экземпляром freeCodeCamp.

## Установка MailHog

Как установить и запустить MailHog зависит от вашей ОС

- [Установка MailHog для macOS](#Установка-mailhog-для-macos)
- [Установка MailHog для Windows](#Установка-mailhog-для-windows)
- [Установка MailHog для Linux](#Установка-mailhog-для-linux)

### Установка MailHog для macOS

Здесь описано как установить MailHog для macOS с помощью [Homebrew](https://brew.sh/):

```bash
brew install mailhog
brew services start mailhog
```

Это запустит сервисы mailhog в фоновом режиме.

Затем вы можете перейти к [использованию MailHog](#Использование-mailhog).

### Установка MailHog для Windows

Загрузите последнюю версию MailHog с [MailHog's official repository](https://github.com/mailhog/MailHog/releases). Нажмите по ссылке для вашей версии Windows (32 или 64 разрядная) и .exe файл будет загружен на ваш компьютер.

Когда он закончит загрузку, запустите файл. Вероятно, вы получите предупреждение от защитника Windows где вам нужно будет подтвердить доступ MailHog'a. Как только вы это сделаете, откроется стандартная командная строка Windows вместе с запущеным MailHog'ом.

Для закрытия MailHog'a достаточно закрыть командную строку. Для повторного запуска откройте тот-же .exe файл. Не нужно скачивать его заново.

Затем вы можете перейти к [использованию MailHog](#Использование-mailhog).

### Установка MailHog для Linux

Сначала установите [Go](https://golang.org).

Для Debian-основанных систем вроде Ubuntu и Linux Mint, запустите:

```bash
sudo apt-get install golang
```

Для CentOS, Fedora, Red Hat Linux, и других RPM-основанных систем, запустите:

```bash
sudo dnf install golang
```

Или:

```bash
sudo yum install golang
```

Установите путь для Go:

```bash
echo "export GOPATH=$HOME/go" >> ~/.profile
echo 'export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin' >> ~/.profile
source ~/.profile
```

Затем установите и запустите MailHog:

```bash
go get github.com/mailhog/MailHog
sudo cp /home/$(whoami)/go/bin/MailHog /usr/local/bin/mailhog
mailhog
```

Затем вы можете перейти к [Использованию MailHog](#использование-mailhog).

## Использование MailHog

После установки и запуска MailHog'a вам нужно открыть почтовый ящик MailHog в браузере, открыть новое окно или вкладку и перейти к [http://localhost:8025](http://localhost:8025).
теперь вы должны увидеть такой экран:

![MailHog Screenshot 1](images/mailhog/1.jpg)

Когда ваш freeCodeCamp отправляет сообщение, оно появляется здесь, как показано ниже:

![MailHog Screenshot 2](images/mailhog/2.jpg)

После открытия почты вы должны увидеть 2 вкладки, в которых вы можете найти содержимое - текст и источник. Убедитесь, что вы на вкладке с текстом.

![MailHog Screenshot 3](images/mailhog/3.jpg)

Любые ссылки должны быть доступны для просмотра.

## Полезные ссылки

- Для других вопросов связанных с MailHog или инструкций по пользовательской настройке, проверьте [MailHog](https://github.com/mailhog/MailHog) репозиторий.
