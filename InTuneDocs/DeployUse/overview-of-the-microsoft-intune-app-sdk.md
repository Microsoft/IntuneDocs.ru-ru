---
title: Общие сведения о пакете SDK для приложений Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
author: Msmbaldwin
---
# Общие сведения о пакете SDK для приложений Microsoft Intune
Пакет SDK для приложений Intune доступен как для платформы Android, так и для платформы iOS и предоставляет возможности управления мобильными приложениями с помощью Microsoft Intune. Кроме того, мы постарались уменьшить объем изменений кода, которые необходимо внести разработчику. Вы обнаружите, что большинство функций SDK можно включить без изменения поведения приложения. В целях улучшения взаимодействия с конечными пользователями и администраторами можно воспользоваться нашими API, чтобы настроить поведение приложения для тех функций, которые требуют содействия со стороны приложения. 

После предоставления возможностей в вашем приложении ИТ-администраторы могут развернуть политики для приложений, управляемых Intune, и воспользоваться преимуществами этих функций для защиты корпоративных данных.

# Функции
## Контроль перемещения корпоративных документов пользователями
ИТ-администраторы могут управлять перемещением файлов корпоративных документов в управляемых приложениях Intune. Например, они могут развернуть политику, запрещающую приложениям резервного копирования файлов копировать корпоративные данные в облако.  

## Настройка ограничений для буфера обмена
ИТ-администраторы могут настроить работу буфера обмена в приложениях, управляемых Intune. Например, они могут развернуть политику, запрещающую конечным пользователям использовать буфер обмена для вырезания или копирования данных из приложения, управляемого Intune, и их вставки в неуправляемое приложение.

## Настройка ограничений снимков экрана
ИТ-администраторы могут запретить пользователям делать снимки экрана, пока отображается управляемое Intune приложение. Такое ограничение позволяет предотвратить фиксацию и раскрытие конфиденциальных материалов компании. Эта функция доступна только для устройств Android. 

## Принудительное шифрование для сохраненных данных
Администраторы могут принудительно применить политику, которая обеспечивает шифрование данных, сохраненных приложением на устройстве.

## Удаленная очистка корпоративных данных
ИТ-администраторы могут выполнить удаленную очистку корпоративных данных из приложения, управляемого Intune, при отмене регистрации этого устройства в Microsoft Intune. Эта функция основана на удостоверениях и удаляет только файлы, относящиеся к корпоративному удостоверению конечного пользователя. Для этого данной функции требуется содействие со стороны приложения. Приложение может указать удостоверение, для которого должна быть выполнена очистка, на основании параметров пользователя. Если приложение не предоставляет такие параметры пользователя, по умолчанию выполняется очистка каталога приложения, а пользователь уведомляется о прекращении доступа к ресурсам компании. 

## Принудительное использование управляемого браузера
ИТ-администраторы могут задать принудительное использование управляемого браузера при открытии ссылок из приложений, управляемых Intune. Использование управляемого браузера Microsoft Intune позволяет гарантировать, что ссылки, отображаемые в сообщениях электронной почты (которые находятся в управляемом Intune почтовом клиенте), хранятся в пределах области действия приложений, управляемых Intune.

## Принудительное использование политики запроса ПИН-кода
Администраторы могут принудительно применять политику запроса ПИН-кода при запуске приложения, управляемого Intune. Эта политика позволяет убедиться, что пользователи, которые зарегистрировали свои устройства в Microsoft Intune, и пользователи, которые запускают приложения, являются одними и теми же людьми. Когда конечные пользователи настраивают свой ПИН-код, пакет SDK для приложений Intune использует Azure Active Directory для проверки учетных данных пользователей, сравнивая их с учетными данными регистрации устройства. 

## Запрос на ввод учетных данных пользователя перед запуском приложений
ИТ-администраторы могут потребовать от пользователей вводить свои учетные данные перед запуском приложений, управляемых Intune. Пакет SDK для приложений Intune использует Azure Active Directory для обеспечения единого входа, когда введенные один раз учетные данные используются повторно для последующих входов в систему. Кроме того, поддерживается проверка подлинности решений по управлению удостоверениями, [объединенных в федерацию с Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx). 

## Проверка работоспособности и соответствия устройства
ИТ-администраторы могут проверять работоспособность устройства и его соответствие корпоративным политикам, прежде чем конечные пользователи получат доступ к приложениям, управляемым Intune. На платформе iOS эта политика проверяет, имеет ли устройство снятую защиту. На платформе Android эта политика проверяет, получен ли на устройстве административный доступ.  




<!--HONumber=Apr16_HO4-->

