# uLogin

Donate link: http://ulogin.ru  
Tags: ulogin, login, social, authorization  
Tested up to: 2.1.0.1  
Stable tag: 2.0.3  
License: GNU General Public License, version 2  

**uLogin** — это инструмент, который позволяет пользователям получить единый доступ к различным Интернет-сервисам без необходимости повторной регистрации,
а владельцам сайтов — получить дополнительный приток клиентов из социальных сетей и популярных порталов (Google, Яндекс, Mail.ru, ВКонтакте, Facebook и др.)


## Установка

- Распакуйте содержимое папки **upload** архива установки в корень сайта.  
- Активируйте модули **"uLogin - панель"** и **"uLogin - общие настройки"** в списке модулей.
- Модуль заработает сразу после активации с настройками по умолчанию.

При активации(установке) модуля *"uLogin - панель"* автоматически создаются дочерние модули и добавляются в макет *Account*.
При активации(установке) модуля *"uLogin - общие настройки"* создаётся группа клиентов *uLogin* для новых, регистрирующихся через uLogin клиентов.

Более детальную информацию смотрите на сайте https://ulogin.ru/help.php

## Модуль "uLogin - общие настройки"

В данном модуле задаются:  
**Значение поля uLogin ID** общее поле для всех виджетов uLogin, необязательный параметр (см. *"Настройки виджета uLogin"*);  
**Группа клиентов по умолчанию:** группа, присваиваемая пользователям, зарегистрированных с помощью uLogin. По умолчанию - группа *uLogin* - создаётся после установки модуля.  


## Модуль "uLogin - панель"

Здесь Вы можете указывать параметры для каждой панели uLogin отдельно.

Параметр модуля **Значение поля uLogin ID** - задаёт значение для виджета данной панели. Пустое поле - значение берётся из модуля "uLogin - общие настройки".  
Параметр **Тип формы** - влияет на отображение панели uLogin:  

- *Форма offline - авторизация* - форма для авторизации, отображается, когда пользователь онлайн. Место расположения определяется в макетах.
- *Форма online - синхронизация* - форма для связывания аккаунтов различных соцсетей, отображается, когда пользователь офлайн. Место расположения определяется в макетах.
- *Форма online - синхронизация в личном кабинете пользователя* - то же, что и *Форма online - синхронизация*,
за исключением того, что форма будет отображаться только в личном кабинете пользователя на странице редактирования данных только при добавлении модуля в макет *Account*.

При активации(установке) модуля *"uLogin - панель"* автоматически создаются два дочерних модуля и добавляются в макет *Account*.


## Настройки виджета uLogin

При установке расширения uLogin авторизация пользователей будет осуществляться с настройками по умолчанию.  
Для более детальной настройки виджетов uLogin Вы можете воспользоваться сервисом uLogin.  

Вы можете создать свой виджет uLogin и редактировать его самостоятельно:

для создания виджета необходимо зайти в Личный Кабинет (ЛК) на сайте http://ulogin.ru/lk.php,
добавить свой сайт к списку Мои сайты и на вкладке Виджеты добавить новый виджет. После этого вы можете отредактировать свой виджет.

**Важно!** Для успешной работы плагина необходимо включить в обязательных полях профиля поле **Еmail** в Личном кабинете uLogin.  
Заполнять поля в графе "Тип авторизации" не нужно, т.к. расширение uLogin настроено на автоматическое заполнение данных параметров.

Созданный в Личном Кабинете виджет имеет параметр **uLogin ID**.  
Скопируйте значение **uLogin ID** вашего виджета в соответствующее поле в настройках плагина на вашем сайте и сохраните настройки.   

Если всё было сделано правильно, виджет изменится согласно вашим настройкам.


## Особенности

Для ручного вывода панели авторизации в любом месте шаблона темы OpenCart необходимо следать следующее:

- Добавить контроллёр модуля в php файл шаблона, например, для вывода панели в хэдере, необходимо добавить этот код в файл `catalog/controller/common/header.php`:

        $data['ulogin_form_marker'] = $this->load->controller('module/ulogin');    
    Обратите внимание: добавить код нужно в начало метода index соответствующего контроллера.


- Добавить вывод панели в шаблоне `catalog/view/theme/default/template/common/header.tpl`, например после строки `<div class="collapse navbar-collapse navbar-ex1-collapse">`:

        <?php echo $ulogin_form_marker;?>

Панель синхронизации в личном кабинете пользователя и панель авториации на страницах входа и регистрации настраивается в **модулях uLogin - панель > account_lk_online** и **uLogin - панель > account_offline**.

## Изменения

####2.0.3
* Исправление ошибок

####2.0.2
* Добавлена совместимость с версией движка 2.1.0.1

####2.0.1
* Исправлен баг с выводом панели uLogin с использованием протокола https.
* Исправлен README.md.

####2.0.0
* Релиз.
