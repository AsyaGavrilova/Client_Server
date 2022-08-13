## Что такое HTTP и HTTPS

***HTTP (Hypertext Transfer Protocol)*** – это прикладной протокол для передачи гипертекстовых документов, таких как HTML. Он создан для связи между веб-браузерами и веб-серверами, хотя в принципе HTTP может использоваться и для других целей. Протокол следует классической клиент-серверной модели, когда клиент открывает соединение для создания запроса, а затем ждёт ответа. HTTP - это протокол без сохранения состояния, то есть сервер не сохраняет никаких данных (состояние) между двумя парами "запрос-ответ". Несмотря на то, что HTTP основан на TCP/IP, он также может использовать любой другой протокол транспортного уровня с гарантированной доставкой.</br>

HTTP — это протокол, позволяющий получать различные ресурсы, например HTML-документы. Протокол HTTP лежит в основе обмена данными в Интернете. HTTP является протоколом клиент-серверного взаимодействия, что означает инициирование запросов к серверу самим получателем, обычно веб-браузером. Полученный итоговый документ может состоять из различных поддокументов, являющихся частью итогового документа: например, из отдельно полученного текста, описания структуры документа, изображений, видео-файлов, скриптов и многого другого.</br>

Клиенты и серверы взаимодействуют, обмениваясь одиночными сообщениями (а не потоком данных). Сообщения, отправленные клиентом, обычно веб-браузером, называются запросами, а сообщения, отправленные сервером, называются ответами.</br>

Хотя HTTP был разработан ещё в начале 1990-х годов, за счёт своей расширяемости в дальнейшем он все время совершенствовался. HTTP является протоколом прикладного уровня, который чаще всего использует возможности другого протокола - TCP (или TLS - защищённый TCP) - для пересылки своих сообщений, однако любой другой надёжный транспортный протокол теоретически может быть использован для доставки таких сообщений. Благодаря своей расширяемости, он используется не только для получения клиентом гипертекстовых документов, изображений и видео, но и для передачи содержимого серверам, например, с помощью HTML-форм. HTTP также может быть использован для получения только частей документа с целью обновления веб-страницы по запросу (например, посредством AJAX запроса).</br>
***

***HTTPS (HyperText Transfer Protocol Secure)*** – это безопасный протокол передачи данных, который поддерживает шифрование посредством криптографических протоколов SSL и TLS, и является расширенной версией протокола HTTP.</br>

HTTPS работает благодаря SSL/TLS-сертификату. SSL/TLS-сертификат ― это цифровая подпись сайта. С её помощью подтверждается его подлинность. Перед тем как установить защищённое соединение, браузер запрашивает этот документ и обращается к центру сертификации, чтобы подтвердить легальность документа. Если он действителен, то браузер считает этот сайт безопасным и начинает обмен данными. Вот откуда взялась и что означает S в HTTPS.</br>
***

***SSL (Secure Socket Layer) и TLS (Transport Layer Security)*** – сетевые криптографические протоколы, обеспечивающие аутентификацию и защиту от несанкционированного доступа, нарушения целостности передаваемых данных. Протоколы SSL/TLS предназначены для исключения подмены идентификатора на клиентской или серверной стороне, раскрытия или искажения данных. Для этих целей используется надежный метод аутентификации, применяются шифрование канала связи и коды целостности сообщений. Стандартным портом, устанавливаемым по умолчанию для SSL/TLS, является порт 443 для HTTPS, 465 для SMTPS (электронная почта).</br>

По своей сути обе технологии занимаются одним делом – защитой пользовательской информации от злоумышленников. 
Их отличие состоит лишь только в том, что TLS основан на уже действующей спецификации SSL 3.0. А сам SSL уже давно устарел, разработчики редко его используют как единственную защиту. Чаще всего можно увидеть связку двух сертификатов SSL/TLS. Такая поддержка обеспечивает работу как с новыми, так и со старыми устройствами.


## HTTP методы</br>

***Методы Метод HTTP (англ. HTTP Method)*** — последовательность из любых символов, кроме управляющих и разделителей, указывающая на основную операцию над ресурсом. Обычно метод представляет собой короткое английское слово, записанное заглавными буквами.</br>

***Безопасный метод*** — метод HTTP является безопасным, если он не меняет состояние сервера. Другими словами, безопасный метод проводит операции "только чтение" (read-only). Несколько следующих методов HTTP безопасные: GET, HEAD или OPTIONS. Все безопасные методы являются также идемпотентными, как и некоторые другие, но при этом небезопасные, такие как PUT или DELETE.</br>

***Идемпотентный метод*** - метод HTTP является идемпотентным, если повторный идентичный запрос, сделанный один или несколько раз подряд, имеет один и тот же эффект, не изменяющий состояние сервера. Другими словами, идемпотентный метод не должен иметь никаких побочных эффектов (side-effects), кроме сбора статистики или подобных операций. Корректно реализованные методы GET, HEAD, PUT и DELETE идемпотентны, но не метод POST. Также все безопасные методы являются идемпотентными.
***

***GET*** — используется для запроса содержимого указанного ресурса. Клиент может передавать параметры выполнения запроса в URI целевого ресурса после символа «?»:

    GET /path/resource?param1=value1&param2=value2 HTTP/1.1
        
Запрос GET идемпотентный, безопасный, не имеет тела.
***

***POST*** — используется для отправки сущностей к определённому ресурсу. При этом передаваемые данные включаются в тело запроса. Аналогично с помощью метода POST обычно загружаются файлы на сервер.</br>

В отличие от метода GET, метод POST не считается идемпотентным, то есть многократное повторение одних и тех же запросов POST может возвращать разные результаты (например, после каждой отправки комментария будет появляться очередная копия этого комментария).</br>

Метод POST не идемпотентный, не безопасный.
***

***PUT*** — создаёт новый ресурс или заменяет представление целевого ресурса, данными представленными в теле запроса.</br>

Разница между PUT и POST в том, что PUT является идемпотентным, т.е. единичный и множественные вызовы этого метода, с идентичным набором данных, будут иметь тот же результат выполнения (без сторонних эффектов), в случае с POST, множественный вызов с идентичным набором данных может повлечь за собой сторонние эффекты.</br>

Метод PUT идемпотентный, не безопасный.
***

***PATCH*** — применяет частичные изменения к ресурсу.</br>

Метод PATCH не идемпотентный, не безопасный.
***

***DELETE*** — удаляет указанный ресурс.</br>

Метод DELETE идемпотентный, не безопасный.
