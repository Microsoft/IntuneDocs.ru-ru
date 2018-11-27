---
title: Создание профиля Wi-Fi с общим ключом в Microsoft Intune — Azure | Документация Майкрософт
description: Использование пользовательского профиля для создания профиля Wi-Fi с общим ключом и получение примера XML-кода профилей Wi-Fi для Android, Windows и профилей Wi-Fi на основе EAP в Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 59736ad188cf88c994ff93b4a505731afad8f550
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186330"
---
# <a name="use-a-custom-device-profile-to-create-a-wifi-profile-with-a-pre-shared-key---intune"></a>Использование пользовательского профиля устройства для создания профиля Wi-Fi с общим ключом в Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Как правило, общие ключи используются для аутентификации пользователей в сетях Wi-Fi и беспроводных сетях. Вы можете создать профиль Wi-Fi с общим ключом с помощью Intune. Чтобы создать профиль, используйте функцию **пользовательского профиля устройства** в Intune. В этой статье также представлено несколько примеров того, как создать профиль Wi-Fi на основе EAP.

> [!IMPORTANT]
>- Использование общего ключа в Windows 10 приводит к появлению ошибки исправления в Intune. В этом случае профиль Wi-Fi правильно назначается устройству и работает должным образом.
>- При экспорте профиля Wi-Fi, который содержит общий ключ, убедитесь, что файл защищен. Ключ указан в виде обычного текста, поэтому вы должны защитить его.

## <a name="before-you-begin"></a>Подготовка к работе

- Возможно, будет проще скопировать код с компьютера, подключенного к этой сети, как описано ниже в этой статье.
- Кроме того, для Android можно использовать [генератор PSK Android](http://intunepskgenerator.johnathonb.com/).
- Чтобы добавить несколько сетей и ключи, можно добавить дополнительные параметры OMA-URI.
- Чтобы настроить профиль для устройств iOS, используйте Apple Configurator на компьютере Mac. Также вы можете воспользоваться генератором [iOS PSK Mobile Config Generator](http://intunepskgenerator.johnathonb.com/).
- PSK требуется строка из 64 шестнадцатеричных цифр или парольная фраза из 8–63 печатных символов ASCII. Некоторые символы, такие как символ звездочки (*), не поддерживаются.

## <a name="create-a-custom-profile"></a>Создание настраиваемого профиля
Можно создать пользовательский профиль Wi-Fi с общим ключом для Windows или Android либо профиль Wi-Fi на основе EAP. Сведения о том, как создать профиль на портале Azure, см. в статье [Создайте профиль с настраиваемыми параметрами в Intune](custom-settings-configure.md). Когда создаете профиль устройства, выберите для платформы устройства тип **Пользовательский**. Не выбирайте профиль Wi-Fi. Выбрав тип "Пользовательский", сделайте следующее: 

1. Введите имя и описание профиля.
2. Добавьте новый параметр OMA-URI со следующими свойствами: 

   a. Введите имя для этого параметра сети Wi-Fi.

   b. (Необязательно.) Введите описание параметра OMA-URI или оставьте поле пустым.

   c. Для параметра **Тип данных** задайте значение **Строка**.

   d. **OMA-URI**:

   - **Для Android**: ./Vendor/MSFT/WiFi/Profile/SSID/Settings
   - **Для Windows**: ./Vendor/MSFT/WiFi/Profile/SSID/WlanXml

     > [!NOTE]
     > В начале обязательно должна стоять точка.

     SSID — это SSID, для которого создается политика. Например, введите `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`.

   д. **Поле значения** служит для вставки XML-кода. См. примеры в этой статье. Обновите каждое значение в соответствии с параметрами сети. Некоторые сведения содержатся в разделе комментариев кода.
3. Нажмите кнопку **ОК**, а затем сохраните и назначьте политику.

    > [!NOTE]
    > Эту политику можно назначить только для групп пользователей.

Политика применяется при каждой следующей регистрации устройства, и на нем создается профиль Wi-Fi. Устройство сможет автоматически подключиться к сети.

## <a name="android-or-windows-wi-fi-profile-example"></a>Пример профиля Wi-Fi для Android или Windows

В следующем примере приведен XML-код профиля Wi-Fi для Android или Windows. В примере показан правильный формат и предоставлены дополнительные сведения. Этот пример не предназначен для использования в качестве рекомендуемой конфигурации для вашей среды.

> [!IMPORTANT]
>
> Для `<protected>false</protected>` нужно задать значение **false**. Если установить значение **true**, устройство будет ожидать передачи зашифрованного пароля, а затем попытается расшифровать его, что может привести к сбою подключения.
>
>  `<hex>53534944</hex>` должно быть присвоено шестнадцатеричное значение `<name><SSID of wifi profile></name>`.
>  На устройствах с Windows 10 может отображаться ложное сообщение об ошибке *0x87D1FDE8: сбой исправления*. При этом устройство все равно будет содержать профиль.

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
x>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
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
        <keyType>networkKey</keyType>
        <protected>false</protected>
        <keyMaterial>MyPassword</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

## <a name="eap-based-wi-fi-profile-example"></a>Пример профиля Wi-Fi на основе EAP
В следующем примере приведен XML-код профиля Wi-Fi на основе EAP. В нем показан правильный формат и предоставлены дополнительные сведения. Этот пример не предназначен для использования в качестве рекомендуемой конфигурации для вашей среды.


```
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
Кроме того, можно создать XML-файл из существующего подключения Wi-Fi. Для этого сделайте следующее: 

1. На компьютере, который подключен или недавно был подключен к беспроводной сети, откройте папку `\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}`.

   Рекомендуем использовать компьютер, подключенный к небольшому числу беспроводных сетей. Иначе придется просмотреть каждый профиль, чтобы найти нужный.

2. Выполните поиск по XML-файлам, чтобы найти нужный.
3. Когда найдете нужный XML-файл, скопируйте и вставьте XML-код в поле **Данные** на странице параметров OMA-URI.

## <a name="best-practices"></a>Советы и рекомендации
- Прежде чем развертывать профиль Wi-Fi с использованием PSK, убедитесь, что устройство может напрямую подключиться к конечной точке.

- При смене ключей (паролей или парольных фраз) возможны простои. Учитывайте это при развертываниях. Рекомендуется распространять новые профили Wi-Fi в нерабочее время. Кроме того, предупредите пользователей о возможных проблемах с подключением.

- Чтобы во время перехода не возникало перебоев, устройство пользователя должно иметь дополнительное подключение к Интернету. Например, у пользователя должна быть возможность переключиться на гостевую (или другую) сеть Wi-Fi или подключиться к Intune по сотовой связи. Благодаря дополнительному подключению пользователь будет получать обновления политики во время обновления корпоративного профиля Wi-Fi на устройстве.
