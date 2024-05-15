---
title: Amplicode для IntelliJ IDEA
weight: 0
---

Amplicode для IntelliJ IDEA включает в себя поддержку экосистемы Spring и связанных технологий, а также предоставляет
инструменты для работы с Docker и Docker Compose файлами.

**Мы крайне рекомендуем ознакомиться со следующим видео, чтобы получить наиболее полное представление о возможностях
Amplicode, доступных в IntelliJ IDEA.**

<div class="youtube">
   <iframe 
      width="560" 
      height="315" 
      src="https://www.youtube-nocookie.com/embed/7vIX8vbT3kM" 
      title="YouTube video player" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen
   ></iframe>
</div>

## Рекомендуемый способ установки

Для того чтобы установить Amplicode для IntelliJ IDEA и автоматически получать обновления, необходимо:

1. Открыть настройки IntelliJ IDEA и перейти в секцию **Plugins**
   ![settings-plugins.png](img/ij-settings-plugins.png)
2. Нажать на иконку шестерёнки и выбрать пункт **Manage Plugin Repositories**
   ![manage-plugin-repositories.png](img/ij-manage-plugin-repositories.png)
3. В открывшемся окне вставить `https://amplicode.ru/jetbrains-marketplace`
   ![custom-pligin-repository.png](img/ij-custom-pligin-repository.png)
   И нажать **ОК**
4. Ввести `Amplicode` в секции **Marketplace** и нажать **Install**
   ![install.png](img/ij-install.png)
5. Перезапустить IntelliJ IDEA
   ![restart.png](img/ij-restart.png)

## Установка Amplicode вручную (через .zip файл)

Для того чтобы установить Amplicode вручную, необходимо:

1. Скачать архив с Amplicode для одной из поддерживаемых версий IntelliJ IDEA:

   | IntelliJ IDEA | Amplicode                                                                                                                     |
   |---------------|-------------------------------------------------------------------------------------------------------------------------------|
   | 2022.1.X      | Релиз запланирован на 01.05.2024                                                                                              |
   | 2022.2.X      | Релиз запланирован на 01.05.2024                                                                                              |
   | 2022.3.Х      | <a href="https://amplicode.ru/Amplicode/amplicode-2024.1.1-223-EAP.zip" target="_blank" rel="noopener noreferrer">Скачать</a> |
   | 2023.2.Х      | <a href="https://amplicode.ru/Amplicode/amplicode-2024.1.1-232-EAP.zip" target="_blank" rel="noopener noreferrer">Скачать</a> |
   | 2023.3.Х      | <a href="https://amplicode.ru/Amplicode/amplicode-2024.1.1-233-EAP.zip" target="_blank" rel="noopener noreferrer">Скачать</a> |
   | 2024.1.X      | <a href="https://amplicode.ru/Amplicode/amplicode-2024.1.1-241-EAP.zip" target="_blank" rel="noopener noreferrer">Скачать</a> |

2. Открыть настройки IntelliJ IDEA и перейти в секцию **Plugins**
   ![settings-plugins.png](img/ij-settings-plugins.png)
3. Нажать на иконку шестерёнки и выбрать пункт **Install Plugin from Disk...**
   ![install-plugin-from-disk.png](img/ij-install-plugin-from-disk.png)
4. Выбрать файл с архивом Amplicode (**распаковывать архив не нужно**) и нажать **OK**
5. Перезапустить IntelliJ IDEA
   ![restart.png](img/ij-restart.png)

## Активация Amplicode

После успешной установки при первом открытии проекта на Spring Boot необходимо активировать Amplicode, нажав на
Кнопку **Enable Amplicode**.

![enable-amplicode.png](img/ij-enable-amplicode.png)

Если к проекту не подключен ни один из
модулей <a href="https://spring.io/projects/spring-data" target="_blank" rel="noopener noreferrer">Spring Data</a>,
Amplicode предложит настроить проект:

![project-configuration.png](img/ij-project-configuration.png)

Для успешной активации Amplicode **необходимо** в один из модулей проекта добавить один из доступных **Spring Data**
модулей. Сделать это можно в окне **"Project Configuration"**. Для этого, выберите модуль и одно из значений в выпадающем списке для поля **"Spring Data"**.

![ij-project-configuration-dropdown.png](img/ij-project-configuration-dropdown.png)

**Опционально** можно улучшить любой из доступных модулей, подключив наиболее популярные стартеры/библиотеки, 
которые помогут сделать разработку более комфортной и эффективной с расширенной поддержкой от Amplicode.

После успешной активации вы увидите панель **Amplicode Explorer** (1), а также контекстно-зависимые панели **Editor Toolbar** (2) и **Amplicode Designer** (3) для поддерживаемых файлов.

![plugin-installed.png](img/ij-plugin-installed.png)

Также Amplicode сгенерирует файл `amplicode.xml` в корневой директории проекта. В нём будут сохранены пользовательские настройки Amplicode.

## Поддерживаемые версии IntelliJ IDEA

В настоящее время **все возможности Amplicode доступны бесплатно**. Ниже вы можете найти таблицу с версиями Amplicode,
IntelliJ IDEA и датами, до которых лицензионная политика для соответствующих версий Amplicode не изменится. В будущем мы
можем изменить лицензионную политику, но обязуемся предупредить об этом **не менее чем за 3 месяца** до вступления
изменений в силу.

| Версия Amplicode | Версия IntelliJ IDEA                           | Прекращение поддержки | Лицензионная политика |
|------------------|------------------------------------------------|-----------------------|-----------------------|
| 2023.2.X-PRIVATE | 2022.3.X<br/>2023.2.X<br/>2023.3.X             | 03.06.2024            | Бесплатно             |
| 2024.1.X-EAP     | 2022.Х*<br/>2023.2.X<br/>2023.3.X<br/>2024.1.X | 01.10.2024            | Бесплатно             |
| 2024.2.X-EAP     | 2023.2.X<br/>2023.3.X<br/>2024.1.X             | 12.01.2025            | Бесплатно             |

__*_ – Мы планируем выпустить поддержку IntelliJ IDEA 2022.X для указанных версий Amplicode к 01.05.2024._

_**Прекращение поддержки**: начиная с указанной даты, все возможности Amplicode станут недоступны до момента
обновления на более свежую версию. За месяц до указанной даты Amplicode начнёт напоминать о скором прекращении
поддержки._

Для того чтобы посмотреть версию IntelliJ IDEA:

1. Откройте окно Find Action (Cmd+Shift+A для MacOS, Ctrl+Shift+A для Win/Linux)
2. Найдите и выберите действие _About_

![about.png](img/ij-about.png)

Если вы используете отличную от перечисленных выше версию IntelliJ IDEA и не можете обновиться на одну из поддерживаемых
Amplicode, пожалуйста, [свяжитесь с нами](#svyazatsya-s-komandoi-amplicode), и мы постараемся найти выход из сложившейся
ситуации!

## Связаться с командой Amplicode

В случае если у вас возникли трудности на любом из этапов в процессе установки Amplicode или любые другие вопросы,
пожалуйста, напишите нам в:

* <a href="https://t.me/amplicode_chat" target="_blank" rel="noopener noreferrer">Telegram-чат</a>
* <a href="https://vk.me/join/bO2OWNz17GZs_xpynqla/QJLPH/ZRERxvDY=" target="_blank" rel="noopener noreferrer">VK-чат</a>
* или на почту, через [форму на сайте](https://amplicode.io/contacts/)
