# CCache
Маленький класс для работы с кэшированием<br>
Позволяет сохранять и использовать данные.<br>
Будет полезно для кэширования запросов к API сторонних сайтов, а так же для кэширования результатов выборки из базы данных<br>
Применений масса, данный класс можно использовать где угодно и как угодно - полет фантазии не ограничен.<br>
Теперь данный класс умеет использовать Memcache к качестве хранилища.<br>
<br>
# Описание методов
Все методы статические, создавать экземпляр класса не требуется<br>
## CCache::init('/folder/', 3600, true);<br>
Установка дирректории для хранения кэша. Указывать со слешами в начале и в конце. Время жизни кэша в секундах и флаг использования кэширования.<br>
## CCache::check($name);
Выполняет проверку наличия кэша в базе. Принимает в качестве аргумента идентификатор элемента $name. Если элемент присутствует в кэше - вернет true, иначе - false.
## CCache::get($name);
Получает элемент из кэша, возвращает массив. Если элемент в кэше не найден - вернет false.
## CCache::write($name, $arValue);
Запись данных в кэш. Принимает два аргумента: имя элемента $name и данные $arValue. В свою очередь данные $arValue должны являться массивом. При наличии элемента в кэше он будет перезаписан.
## CCache::flush();
Метод полностью очищает кэш. Вернет false в случае ошибки.
## CCache::del($name);
Метод удаляет конкретный элемент из кэша, принимает имя элемента $name в качестве аргумента. Вернет false в сллучае ошибки удаления.
## CCache::getSize($name)
Метод возвращает размер элемента $name в байтах. Если элемент в кэше не найден - вернет false.
## CCache::getCacheSize()
Метод возвращает размер кэша в байтах
## CCache::getAge($name)
Метод возвращает количество секунд, прошедших с момента кэширования элемента $name. При отсутствии элемента в кэше вернет false.
