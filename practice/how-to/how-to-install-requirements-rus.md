# Установка необходимого ПО

### В данном курсе нам понадобятся:
* Visual Studio Code - наш основной редоктор кода
* OpenJDK 11 - набор инструментов для разработки на Java

### [Установка на Windows 10](https://www.youtube.com/)
### [Установка на Ubuntu 20.04](https://www.youtube.com/)
### Установка на Linux Mint/Kali Linux:

В данном разделе мы описываем только процесс установки! \
Процесс настройки описан в видеоролике посвещенном Ubuntu 20.04.

* Установим для начала Visual Studio Code:
    1. Переходим на сайт: https://code.visualstudio.com/Download
    2. Скачиваем .deb версию.
    3. Переходим в каталог со скачанным пакетом.
    4. Запускаем в терминале команду:
       
            sudo apt install ./<pkg-name>.deb
            Где <pkg-name> - название скачанного ранее пакета
    
* Установим OpenJDK 11:
    1. Откроем терминал.
    2. Обновляемся командой:
       
            sudo apt update
    3. Проверим установлена ли Java и, если установлена, посмотрим её версию командой:
    
            java -version
        Если Java не установлена мы увидим следующий вывод:
            
            Command 'java' not found, but can be installed with:

            sudo apt install openjdk-11-jre-headless  # version 11.0.9.1+1-0ubuntu1~20.04, or
            sudo apt install default-jre              # version 2:1.11-72
            sudo apt install openjdk-8-jre-headless   # version 8u275-b01-0ubuntu1~20.04
            sudo apt install openjdk-13-jre-headless  # version 13.0.4+8-1~20.04
            sudo apt install openjdk-14-jre-headless  # version 14.0.2+12-1~20.04

    4. Установим Java следующей командой:
    
            sudo apt install default-jdk
        Проверим версию следующей командой:
       
            javac -version
        Мы должны увидеть подобную строку:
            
            javac 11.0.7


### Установка на Fedora Linux:

В данном разделе мы описываем только процесс установки! \
Процесс настройки описан в видеоролике посвещенном Ubuntu 20.04.

* Установим для начала Visual Studio Code:
    1. Запускаем в терминале команду, добавляющую yum репозитоории Microsoft:

           sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
           sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
    2. Обновим пакетный кэш и установим пронрамму с помощью dnf (Для версий Fedora 22 и выше):
            
            sudo dnf check-update
            sudo dnf install code
    3. Для более ранних версий используется yum.
* Установим OpenJDK 11:
    1. Откроем терминал.
    2. Обновляемся командой:

           sudo dnf update
    3. Проверим установлена ли Java и, если установлена, посмотрим её версию командой:

            java -version
       Если Java не установлена мы увидим следующий вывод:

            Command 'java' not found
        
    4. Установим Java следующей командой:

            sudo dnf install java-11-openjdk.x86_64
       Проверим версию следующей командой:

            javac -version
       Мы должны увидеть подобную строку:

            javac 11.0.7

### Установка на Manjaro Linux:

В данном разделе мы описываем только процесс установки! \
Процесс настройки описан в видеоролике посвещенном Ubuntu 20.04.

* Установим для начала Visual Studio Code:
  
        Важное замечание! В инструкции будет использоваться AUR (Arch user repository).
        Выполняйте действия максимально осторожно.
    1. Скачаем сборку из AUR:
    
            curl -L -O https://aur.archlinux.org/cgit/aur.git/snapshot/visual-studio-code-bin.tar.gz
    2. Распакуем скачанный архив:
       
            tar -xvf visual-studio-code-bin.tar.gz
    3. Перейдем в распакованный каталог:
       
            cd visual-studio-code-bin
    4. Собираем пакет:
    
            makepkg -si
    
* Установим OpenJDK 11:
    1. Откроем терминал
    2. Обновляемся командой:

            sudo pacman -Syu
                
    3. Проверим установлена ли Java и, если установлена, посмотрим её версию командой:

            java -version
       Если Java не установлена мы увидим следующий вывод:

            Command 'java' not found
  4. Установим Java следующей командой:
     
            sudo pacman -S jre11-openjdk-headless jre11-openjdk jdk11-openjdk openjdk11-doc openjdk11-src

     Проверим версию следующей командой:

          javac -version
     Мы должны увидеть подобную строку:

          javac 11.0.7