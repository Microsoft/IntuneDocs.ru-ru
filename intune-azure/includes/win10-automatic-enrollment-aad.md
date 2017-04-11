## <a name="set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium"></a>Настройка автоматической регистрации Windows 10 и Windows 10 Mobile с помощью Azure Active Directory Premium

Автоматическая регистрация позволяет пользователям регистрировать принадлежащие организации или личные компьютеры с Windows 10 и устройства с Windows 10 Mobile в Intune, добавив рабочую или учебную учетную запись и дав согласие на управление. Проще простого. Устройство пользователя в фоновом режиме регистрируется и присоединяется к Azure Active Directory. После регистрации устройство управляется с помощью Intune.

**Предварительные требования**
- Подписка Azure Active Directory Premium ([пробная подписка](http://go.microsoft.com/fwlink/?LinkID=816845))
- Подписка Microsoft Intune


### <a name="configure-automatic-mdm-enrollment"></a>Настройка автоматической регистрации MDM

1. На [портале управления Azure](https://portal.azure.com) (https://manage.windowsazure.com) перейдите к узлу **Active Directory** и выберите свой каталог.

2. Выберите вкладку **Приложения**. В списке приложений будет **Microsoft Intune**.

    ![Управление приложениями Azure AD с помощью Microsoft Intune](../media/aad-intune-app.png)

3. Щелкните стрелку рядом с **Microsoft Intune**. Откроется страница, на которой можно настроить Microsoft Intune.

4. Щелкните **Настройка**, чтобы приступить к настройке автоматической регистрации MDM с помощью Microsoft Intune.

5. Используйте значения по умолчанию для следующих URL-адресов:

  - **регистрация в MDM**;
  - **условия использования MDM**; 
  - **соответствие MDM**.

6.  Укажите устройства пользователей, которыми требуется управлять с помощью Microsoft Intune. Устройства Windows 10 этих пользователей будут автоматически регистрироваться для управления в Microsoft Intune.

  - **Все**
  - **Группы**
  - **Нет**

7. Выберите **Сохранить**.
