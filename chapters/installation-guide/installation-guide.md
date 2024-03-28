---
title: Установка
weight: 0
---

## Amplicode для IntelliJ IDEA

Amplicode для IntelliJ IDEA включает в себя поддержку экосистемы Spring и связанных технологий, а также предоставляет
инструменты для работы с Docker и Docker Compose файлами.

**Мы крайне рекомендуем ознакомиться со следующим видео, чтобы получить наиболее полное представление о возможностях 
Amplicode, доступных в IntelliJ IDEA.**

<div class="youtube">
   <iframe 
      width="560" 
      height="315" 
      src="https://www.youtube.com/embed/g5kzePtZ9FQ" 
      title="YouTube video player" 
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
      allowfullscreen
   ></iframe>
</div>

### Поддерживаемые версии IntelliJ IDEA

Amplicode может быть установлен в IntelliJ IDEA одной из следующих версий:

* 2022.3.X
* 2023.2.X
* 2023.3.X

Для того чтобы посмотреть версию IntelliJ IDEA:
1. Откройте окно Find Action (Cmd+Shift+A для MacOS, Ctrl+Shift+A для Win/Linux)
2. Найдите и выберите действие _About_

![about.png](img/about.png)

Если вы используете отличную от перечисленных выше версию IntelliJ IDEA и не можете обновиться на одну из поддерживаемых Amplicode, пожалуйста, [свяжитесь с нами](#связаться-с-командой-amplicode) и мы постараемся найти выход из сложившейся ситуации!

### Рекомендуемый способ установки

Для того чтобы установить Amplicode для IntelliJ IDEA и автоматически получать обновления, необходимо:

1. Открыть настройки IntelliJ IDEA и перейти в секцию **Plugins**
   ![settings-plugins.png](img/settings-plugins.png)
2. Нажать на иконку шестерёнки и выбрать пункт **Manage Plugin Repositories**
   ![manage-plugin-repositories.png](img/manage-plugin-repositories.png)
3. В открывшемся окне вставить `https://storage.yandexcloud.net/amplicode-marketplace/friday/updatePlugins-friday.xml`
   ![custom-pligin-repository.png](img/custom-pligin-repository.png)
   И нажать **ОК**
4. Ввести `Amplicode` в секции **Marketplace** и нажать **Install**
   ![install.png](img/install.png)
5. Перезапустить IntelliJ IDEA
   ![restart.png](img/restart.png)

### Установка Amplicode вручную (через .zip файл)

Для того чтобы установить Amplicode вручную, необходимо:

1. Скачать архив с Amplicode для одной из [поддерживаемых версий IntelliJ IDEA](#поддерживаемые-версии-intellij-idea)

   | IntelliJ IDEA | Amplicode                                                                                                                         |
      |---------------|-----------------------------------------------------------------------------------------------------------------------------------|
   | 2022.3.X      | [2023.2.3-PRIVATE.zip](https://storage.yandexcloud.net/amplicode-marketplace/friday/Amplicode/amplicode-2023.2.3-223-PRIVATE.zip) |
   | 2023.2.X      | [2023.2.3-PRIVATE.zip](https://storage.yandexcloud.net/amplicode-marketplace/friday/Amplicode/amplicode-2023.2.3-232-PRIVATE.zip) |
   | 2023.3.X      | [2023.2.3-PRIVATE.zip](https://storage.yandexcloud.net/amplicode-marketplace/friday/Amplicode/amplicode-2023.2.3-233-PRIVATE.zip) |

2. Открыть настройки IntelliJ IDEA и перейти в секцию **Plugins**
   ![settings-plugins.png](img/settings-plugins.png)
3. Нажать на иконку шестерёнки и выбрать пункт **Install Plugin from Disk...**
   ![install-plugin-from-disk.png](img/install-plugin-from-disk.png)
4. Выбрать файл с архивом Amplicode и нажать **OK**
5. Перезапустить IntelliJ IDEA
   ![restart.png](img/restart.png)

### Активация Amplicode

После успешной установки, при первом открытие проекта на Spring Boot, Amplicode необходимо будет активировать, нажав на кнопку **Enable Amplicode**.

![enable-amplicode.png](img/enable-amplicode.png)

Если к проекту не подключен ни один из модулей <a href="https://spring.io/projects/spring-data" target="_blank" rel="noopener noreferrer">Spring Data</a>, Amplicode предложит настроить проект:

![project-configuration.png](img/project-configuration.png)

Для успешной активации Amplicode **необходимо** в один из модулей проекта добавить один из доступных **Spring Data** модулей. **Опционально**, можно улучшить любой из доступных модулей, подключив наиболее популярные стартеры/библиотеки которые помогут сделать разработку более комфортной и эффективной с расширенной поддержкой от Amplicode.

После успешной активации, вы сможете увидеть панель **Amplicode Explorer** (1), а также контекстно-зависимые панели **Editor Toolbar** (2) и **Amplicode Designer** (3) для поддерживаемых файлов.

![plugin-installed.png](img/plugin-installed.png)

## Amplicode для VS Code

Amplicode для VS Code включает в себя поддержку React и связанных технологий. На данный момент Amplicode для VS Code находится в фазе активной разработки и в ближайшее время станет доступен в EAP (Early Access Program) формате. Если вы хотите попробовать Amplicode для VS Code уже сейчас, пожалуйста, [свяжитесь с нами](#связаться-с-командой-amplicode). 

## Связаться с командой Amplicode

В случае, если у вас возникли трудности на любом из этапов в процессе установки Amplicode или любые другие вопросы, пожалуйста, напишите нам в:
* <a href="https://t.me/amplicode" target="_blank" rel="noopener noreferrer">Telegram</a>
* <a href="https://vk.com/amplicode" target="_blank" rel="noopener noreferrer">ВКонтакте</a>
* или на почту, через [форму на сайте](https://amplicode.io/contacts/)
