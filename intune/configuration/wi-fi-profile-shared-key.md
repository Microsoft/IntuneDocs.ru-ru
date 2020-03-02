---
title: Создание профиля Wi-Fi с предварительным общим ключом в Microsoft Intune — Azure | Документация Майкрософт
description: Использование пользовательского профиля для создания профиля Wi-Fi с общим ключом и получение примера XML-кода профилей Wi-Fi для Android, Windows и профилей Wi-Fi на основе EAP в Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b83367bb2f1d3622a1fc4e11eedd88f3f26ee8dd
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77510611"
---
# <a name="use-a-custom-device-profile-to-create-a-wifi-profile-with-a-pre-shared-key-in-intune"></a>Создание профиля Wi-Fi с общим ключом в Intune с помощью пользовательского профиля устройства



Как правило, общие ключи используются для аутентификации пользователей в сетях Wi-Fi и беспроводных сетях. Вы можете создать профиль Wi-Fi с общим ключом с помощью Intune. Чтобы создать профиль, используйте функцию **пользовательского профиля устройства** в Intune. В этой статье также представлено несколько примеров того, как создать профиль Wi-Fi на основе EAP.

Эта функция поддерживает:

- Администратор устройства с Android
- Windows
- Wi-Fi на основе EAP

> [!IMPORTANT]
> - Использование общего ключа в Windows 10 приводит к появлению ошибки исправления в Intune. В этом случае профиль Wi-Fi правильно назначается устройству и работает должным образом.
> - При экспорте профиля Wi-Fi, который содержит общий ключ, убедитесь, что файл защищен. Ключ указан в виде обычного текста, поэтому вы должны защитить его.

## <a name="before-you-begin"></a>Подготовка к работе

- Возможно, будет проще скопировать код с компьютера, подключенного к этой сети, как описано ниже в этой статье.
- Чтобы добавить несколько сетей и ключи, можно добавить дополнительные параметры OMA-URI.
- Чтобы настроить профиль для устройств iOS/iPadOS, используйте Apple Configurator на компьютере Mac.
- PSK требуется строка из 64 шестнадцатеричных цифр или парольная фраза из 8–63 печатных символов ASCII. Некоторые символы, например звездочка (*), не поддерживаются.

## <a name="create-a-custom-profile"></a>Создание настраиваемого профиля

1. Войдите в [центр администрирования диспетчера конечных точек (Майкрософт)](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Выберите **Устройства** > **Профили конфигурации** > **Создать профиль**.
3. Укажите следующие свойства.

    - **Имя** — Введите описательное имя для политики. Назначьте имена политикам, чтобы их можно было легко найти в последствии. Например, хорошее имя политики — **Настраиваемые параметры OMA URI профиля Wi-Fi для устройств Android**.
    - **Описание**. Введите описание профиля. Этот параметр является необязательным, но мы рекомендуем его использовать.
    - **Платформа**. Выберите свою платформу.
    - **Тип профиля**. Выберите **Пользовательский**.

4. В меню **Параметры** выберите **Добавить**. Введите новый параметр OMA-URI со следующими свойствами:

    1. **Имя** — Введите имя параметра OMA-URI.
    2. **Описание**. Введите описание параметра OMA-URI. Этот параметр является необязательным, но мы рекомендуем его использовать.
    3. **OMA-URI**: Укажите один из следующих методов:

        - **Для Android**: `./Vendor/MSFT/WiFi/Profile/SSID/Settings`
        - **Для Windows**: `./Vendor/MSFT/WiFi/Profile/SSID/WlanXml`

        > [!NOTE]
        > В начале обязательно должна стоять точка.

        SSID — это SSID, для которого создается политика. Например, если Wi-Fi имеет имя `Hotspot-1`, введите `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`.

    4. **Тип данных**: Выберите **Строка**.

    5. **Значение**. Вставьте XML-код. См. [примеры](#android-or-windows-wi-fi-profile-example) в этой статье. Обновите каждое значение в соответствии с параметрами сети. Некоторые сведения содержатся в разделе комментариев кода.

5. По завершении нажмите **ОК** > **Создать**, чтобы сохранить изменения.

Ваш профиль отображается в списке профилей. [Назначьте его](../device-profile-assign.md) группам пользователей. Эту политику можно назначить только для групп пользователей.

Политика применяется при каждой следующей регистрации устройства, и на нем создается профиль Wi-Fi. Устройство сможет автоматически подключиться к сети.

## <a name="android-or-windows-wi-fi-profile-example"></a>Пример профиля Wi-Fi для Android или Windows

В следующем примере приведен XML-код профиля Wi-Fi для Android или Windows. В примере показан правильный формат и предоставлены дополнительные сведения. Этот пример не предназначен для использования в качестве рекомендуемой конфигурации для вашей среды.

### <a name="what-you-need-to-know"></a>Что необходимо знать

- Для `<protected>false</protected>` нужно задать значение **false**. Если установить значение **true**, устройство будет ожидать передачи зашифрованного пароля, а затем попытается расшифровать его, что может привести к сбою подключения.

- `<hex>53534944</hex>` должно быть присвоено шестнадцатеричное значение `<name><SSID of wifi profile></name>`. На устройствах с Windows 10 может отображаться ложное сообщение об ошибке `x87D1FDE8 Remediation failed`. При этом устройство все равно будет содержать профиль.

- XML содержит специальные символы, такие как `&` (амперсанд). Использование специальных символов может помешать XML работать должным образом. 

### <a name="example"></a>Пример

``` xml
<!--
<hex>53534944</hex> = The hexadecimal value of <name><SSID of wifi profile></name>
<Name of wifi profile> = Name of profile shown to users. It could be <name>Your Company's Network</name>.
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped. It could be <name>Your Company's Network</name>.
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network, such as AES.
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Plain text of the password to connect to the network
-->

<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>
    </SSID>
    <nonBroadcast>false</nonBroadcast>
  </SSIDConfig>
  <connectionType>ESS</connectionType>
  <connectionMode>auto</connectionMode>
  <autoSwitch>false</autoSwitch>
  <MSM>
    <security>
      <authEncryption>
        <authentication><Type of authentication></authentication>
        <encryption><Type of encryption></encryption>
        <useOneX>false</useOneX>
      </authEncryption>
      <sharedKey>
        <keyType>passPhrase</keyType>
        <protected>false</protected>
        <keyMaterial>password</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

### <a name="eap-based-wi-fi-profile-example"></a>Пример профиля Wi-Fi на основе EAP
В следующем примере приведен XML-код профиля Wi-Fi на основе EAP: В примере показан правильный формат и предоставлены дополнительные сведения. Этот пример не предназначен для использования в качестве рекомендуемой конфигурации для вашей среды.


```xml
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                <EapMethod>
                  <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
                  <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
                  <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
                  <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
                </EapMethod>
                <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
                  <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
                    <Type>13</Type>
                    <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
                      <CredentialsSource>
                        <CertificateStore>
                          <SimpleCertSelection>true</SimpleCertSelection>
                        </CertificateStore>
                      </CredentialsSource>
                      <ServerValidation>
                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
                        <ServerNames></ServerNames>
                      </ServerValidation>
                      <DifferentUsername>false</DifferentUsername>
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>Создание XML-файла из существующего подключения Wi-Fi

Можно также создать XML-файл из существующего подключения Wi-Fi. На компьютере с Windows выполните следующие действия:

1. Создайте локальную папку для экспортированных профилей Wi-Fi, например, c:\WiFi.
2. Откройте командную строку от имени администратора (щелкните правой кнопкой мыши `cmd` > **Запуск от имени администратора**).
3. Выполнить команду `netsh wlan show profiles`. Названия всех профилей перечислены.
4. Выполнить команду `netsh wlan export profile name="YourProfileName" folder=c:\Wifi`. Эта команда создает файл с именем `Wi-Fi-YourProfileName.xml` в c:\Wifi.

    - При экспорте профиля Wi-Fi, содержащего предварительный общий ключ, добавьте `key=clear` в команду:
  
        `netsh wlan export profile name="YourProfileName" key=clear folder=c:\Wifi`

        `key=clear` экспортирует ключ в виде обычного текста, который необходим для успешного использования профиля.

Получив файл XML, скопируйте и вставьте синтаксис XML в параметры OMA-URI > **Тип данных**. [Создание пользовательского профиля](#create-a-custom-profile) (в этой статье) перечисляются шаги.

> [!TIP]
> `\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}` также включает все профили в формате XML.

## <a name="best-practices"></a>Рекомендации

- Прежде чем развертывать профиль Wi-Fi с использованием PSK, убедитесь, что устройство может напрямую подключиться к конечной точке.

- При смене ключей (паролей или парольных фраз) возможны простои. Учитывайте это при развертываниях. Рекомендуется распространять новые профили Wi-Fi в нерабочее время. Кроме того, предупредите пользователей о возможных проблемах с подключением.

- Для плавного перехода убедитесь, что устройство конечного пользователя имеет альтернативное подключение к Интернету. Например, конечный пользователь может переключиться обратно на гостевой WiFi (или другую сеть WiFi) или подключиться к Intune по сотовой сети. Благодаря дополнительному подключению пользователь будет получать обновления политики во время обновления корпоративного профиля Wi-Fi на устройстве.

## <a name="next-steps"></a>Дальнейшие шаги

Обязательно изучите статьи [Назначение профилей пользователей и устройств в Microsoft Intune](device-profile-assign.md) и [Мониторинг профилей устройств в Microsoft Intune](device-profile-monitor.md).
