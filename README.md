# Удаленная консультация. Клиент.
Программа для удаленного интерактивного подключения к клиенту с возможностью управления на удаленном компьютере мышью, клавиатурой, двухсторонней передачей буфера обмена, файлов. Подключение осуществляется на выделенный сервер Удаленной консультации, позволяя организовать организовать доступ через интеренет.

# Параметры командной строки
Взаимодействие между консультантом и пользователем осуществляется через клиентскую часть. Подключение к клиенту выполняет по номеру, который автоматически выдается при подключении к серверу. Номер к клиенту не привязывается. Из одного приложение можно выполнить подключение к одному клиенту. Клиентских приложений можно запустить неограниченное количество.

При клиентском взаимодействии можно управлять клавиатурой, мышью, обмен файлами и буфером обмена. Других функций нет. Функция обмена файлами поддерживает только обмен файлами за одну операцию.

Настройка качества передаваемого изображения представлена в двух вариантах настройках канала связи:

    нормальный (изображение с палитрой 8 bit). Данный вариант рекомендуемый;
    отличный (изображение с палитрой 16 bit).

Программа не сохраняет параметры подключения, для этого необходимо использовать параметры запуска. Эти же параметры можно использовать и при интеграции с приложениями, которые могут вызывать внешние программы, например 1С:

    ip – указывает сервер для подключения, пример, ip=localhost
    url - адрес страницы на доступном сайте, которая возвращает строку с адресом сервера для подключения, например, url=mysite/server. Возвращаемая строка должна иметь следующий вид:ip=myserver. Параметр ip имеет приоритет на url.
    client – параметры, указывает, что приложение запускается на клиенте, при этом все элементы на форме неактивны  и по окончании сеанса, клиентское приложение закроется автоматически. Пример, client=true;
    palette - определяет размерность палитры передачи данных, напрямую зависит от качества канала связи. Возможные параметры 8, 16. Пример, palette=8.
    resolution - определяет разрешение экрана, на которое будет отображаться экран клиента. Используются для сжатия изображения для более удобной работы. Нижнее ограничение 1024x768, верхнее ограничение - это исходное изображение экрана клиента. Пример, resolution= 1440x900
    mouse - определяет отрисовывать ли курсор клиента или нет. Если параметр не установлен, то курсор клиента  отрисовывается. Если значение false, то все изменения в состоянии курсора клиента отражаются на стороне консультанта в его текущем курсоре, то есть оба управляют одним курсором. Пример,  mouse=false. По умолчанию значение параметра true.
    mouse_move - определяет передавать ли данные о движении курсора на клиент. При низкоскоростном канале отключение данного параметра уменьшит нагрузку на канал связи. Пример,  mouse_move=false. По умолчанию значение параметра true, то есть данные о движении курсора передаются.
    user_data - любая последовательность символов, определяющих пользовательские данные. Данные затем можно получить командой list к серверу и использовать для анализа подключенных клиентов. Пример user_data="ФИО:Иванов Иван Иванович;ИНН=1122334455;Конфигурация: Управление торговлей"
