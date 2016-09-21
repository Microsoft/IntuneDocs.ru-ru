---
title: "Подключения Wi-F с PSK | Microsoft Intune"
description: "Сведения об использовании настраиваемой конфигурации для создания профиля Wi-Fi с общим ключом."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bf8da72092a2380e73cfbed2a693831706b40d23
ms.openlocfilehash: c005a1b38289580b1543e0e62cbb4cd00cb22c47



---
# Создание профиля Wi-Fi с общим ключом
В этом разделе содержатся сведения об использовании **настраиваемой конфигурации** Intune для создания профиля Wi-Fi с общим ключом. Здесь также приводится пример создания профиля Wi-Fi на основе EAP.

> [!NOTE]
-   Возможно, вам будет проще скопировать код с компьютера, подключенного к этой сети, как описано ниже.
- Для Android можно использовать [генератор PSK Android](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) от Джонатона Бирсака (Johnathon Biersack).
-   Чтобы добавить несколько сетей и ключи, можно добавить дополнительные параметры OMA-URI.
-  Чтобы настроить профиль для устройств iOS, используйте Apple Configurator на компьютере Mac. Можно также воспользоваться генератором [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) от Джонатона Бирсака.


1.  Чтобы создать профиль Wi-Fi с общим ключом для Windows или Android или профиль Wi-Fi на основе EAP, при создании политики вместо профиля Wi-Fi выберите **Настраиваемая конфигурация** для этой платформы устройства.

2.  Укажите имя и введите описание.
3.  Добавление нового параметра OMA URI

   а.   Введите имя для этого параметра сети Wi-Fi.

   b.   Введите описание параметра OMA-URI или оставьте поле пустым.

   в.   **Тип данных**: в качестве значения задайте String(XML).

   г.   **OMA-URI**:

    - **Для Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
    - **Для Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

    > [!NOTE]
В начале обязательно должна стоять точка.

    SSID — это SSID, для которого создается политика. Например,
    `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`

  д. **Поле значения** служит для вставки XML-кода. Вот пример. Каждое значение должно быть адаптировано для параметров сети. Некоторые сведения приведены в разделе комментариев кода.
4. Нажмите кнопку **ОК**, а затем сохраните и разверните политику.

    > [!NOTE]
Эта политика может быть развернута только для групп пользователей.

При каждой следующей регистрации устройства применяется политика и на устройстве создается профиль Wi-Fi. Устройство будет автоматически подключено к сети.
## Профиль Wi-Fi для Android или Windows

Ниже приведен пример XML-кода для профиля Wi-Fi для Android или Windows:

    <!--
    <Name of wifi profile> = Name of profile
    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
    <nonBroadcast><true/false></nonBroadcast>
    <Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
    <Type of encryption> = Type of encryption used by the network
    <protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
    <password> = Password to connect to the network
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

## Профиль Wi-Fi на основе EAP
Ниже приведен пример XML-кода для профиля Wi-Fi на основе EAP.

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

## Создание XML-файла из существующего подключения Wi-Fi
Можно также создать XML-файл из существующего подключения Wi-Fi.
1. На компьютере, который подключен или недавно был подключен к беспроводной сети, откройте следующую папку: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.

    Рекомендуется использовать компьютер, подключенный к небольшому числу беспроводных сетей, так как вам придется просмотреть каждый профиль, чтобы найти нужный.
3.     Выполните поиск в XML-файлах, чтобы найти нужный файл.
4.     После нахождения нужного XML-файла скопируйте и вставьте XML-код в поле данных на странице параметров OMA-URI.

## Развертывание политики

1.  В рабочей области **Политика** выберите политику, которую требуется развернуть, а затем щелкните **Управление развертыванием**.

2.  В диалоговом окне **Управление развертыванием** выполните следующие действия.

    -   **Чтобы развернуть политику**, выберите одну или несколько групп для развертывания, а затем нажмите кнопку **Добавить** &gt; **ОК**.

    -   **Чтобы закрыть диалоговое окно, не развертывая политику**, нажмите кнопку **Отмена**.

При выборе развернутой политики можно просмотреть дополнительные сведения о развертывании в нижней части списка политик.

### См. также
[Подключения Wi-Fi в Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


