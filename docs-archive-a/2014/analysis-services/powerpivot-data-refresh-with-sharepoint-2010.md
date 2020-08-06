---
title: Обновление данных PowerPivot с SharePoint 2010 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: 01b54e6f-66e5-485c-acaa-3f9aa53119c9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 01874bf521055d1441b695a238d09440021d2718
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735553"
---
# <a name="powerpivot-data-refresh-with-sharepoint-2010"></a>Обновление данных PowerPivot с SharePoint 2010
  Обновление данных [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] представляет собой плановую операцию на сервере, при выполнении которой отправляются запросы внешним источникам данных для обновления внедренных данных [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] в книге Excel 2010, хранящейся в библиотеке содержимого.

 Обновление данных — встроенная функция [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] для SharePoint, однако для ее использования необходимо наличие специальных служб и заданий таймера на ферме SharePoint 2010. Дополнительные шаги администрирования, такие как установка поставщиков данных и проверка разрешений баз данных, зачастую являются обязательными для выполнения обновления данных.

 **[!INCLUDE[applies](../includes/applies-md.md)]** SharePoint 2010

> [!NOTE]
>  [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] и SharePoint Server 2013 Excel Services используется другая архитектура для обновления сведений в моделях данных [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] . Новая архитектура в качестве основного компонента для загрузки моделей данных PowerPivot использует службы Excel. В прежней архитектуре обновления данных для загрузки моделей данных использовался сервер с PowerPivot System Service и [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в режиме SharePoint. Дополнительные сведения см. [в разделе PowerPivot Data Refresh with SharePoint 2013](power-pivot-sharepoint/power-pivot-data-refresh-with-sharepoint-2013.md).

 **В этом разделе:**

 [Шаг 1. Включение служба Secure Store и создание главного ключа](#bkmk_services)

 [Шаг 2. Отключение параметров учетных данных, которые не требуется поддерживать](#bkmk_creds)

 [Шаг 3. Создание целевых приложений для хранения учетных данных, используемых при обновлении данных](#bkmk_stored)

 [Шаг 4. Настройка масштабируемого обновления данных на сервере](#bkmk_scale)

 [Шаг 5. Установка поставщиков данных, используемых для импорта данных PowerPivot](#bkmk_installdp)

 [Шаг 6. Предоставление разрешений на создание расписаний и доступ к внешним источникам данных](#bkmk_accounts)

 [Шаг 7. Включение обновления данных в книге](#bkmk_upgradewrkbk)

 [Шаг 8. Проверка конфигурации обновления данных](#bkmk_verify)

 [Изменение параметров конфигурации для обновления данных](#bkmk_config)

 [Изменение расписания для задания таймера обновления данных PowerPivot](#configTimerJob)

 [Отключение задания таймера обновления данных](#bkmk_disableDR)

 После того как среда и разрешения сервера настроены, обновление данных готово к использованию. Чтобы обновить данные, пользователь SharePoint должен создать расписание для книги PowerPivot, в котором будет указано, как часто должно происходить обновление данных. Создание расписания обычно выполняется владельцем книги или автором, опубликовавшим файл на SharePoint. Пользователь должен создать расписание обновления данных для принадлежащих ему книг и управлять созданными расписаниями. Дополнительные сведения см. [в разделе планирование &#40;обновления данных PowerPivot для SharePoint&#41;](schedule-a-data-refresh-powerpivot-for-sharepoint.md).

##  <a name="step-1-enable-secure-store-service-and-generate-a-master-key"></a><a name="bkmk_services"></a>Шаг 1. Включение служба Secure Store и создание главного ключа
 Обновление данных PowerPivot зависит от служб Secure Store, которые хранят учетные данные, используемые для запуска заданий обновления данных и для соединения с внешними источниками данных, в которых хранятся эти учетные данные.

 При установке PowerPivot для SharePoint в режиме «Новый сервер» служба Secure Store настраивается автоматически. При любом другом варианте установки необходимо создать и настроить приложение службы и создать главный ключ шифрования для службы Secure Store.

> [!NOTE]
>  Чтобы настроить службу Secure Store, следует иметь права администратора или делегировать управление службой Secure Store другому пользователю. Чтобы настроить или изменить параметры после включения службы, необходимо иметь права администратора приложения службы.

1.  В разделе «Управление приложениями» центра администрирования выберите пункт **Управление приложениями служб**.

2.  На ленте приложения службы в поле Создать щелкните **создать.**

3.  Выберите **Служба Secure Store**.

4.  На странице **Создание приложения Secure Store** введите имя приложения.

5.  В поле **база данных**укажите экземпляр SQL Server, в котором будет размещена база данных для этого приложения службы. Значением по умолчанию является экземпляр компонента SQL Server Database Engine, в котором размещены базы данных конфигураций фермы.

6.  В поле **имя базы данных**введите имя базы данных приложения службы. Значение по умолчанию — Secure_Store_Service_DB_ \<guid> . Имя, используемое по умолчанию, соответствует используемому по умолчанию имени приложения службы. Если было введено уникальное имя приложения службы, следуйте аналогичным соглашениях об именах при выборе имени базы данных, чтобы ими можно было управлять совместно.

7.  В списке **Проверка подлинности базы данных**по умолчанию выбрано значение «Проверка подлинности Windows». Если выбран параметр «Проверка подлинности SQL», то рекомендации по использованию проверки подлинности этого типа см. в руководстве администратора SharePoint.

8.  В списке пул приложений выберите **создать новый пул приложений.** Укажите описательное имя, которое поможет другим администраторам понять, как используется этот пул приложений.

9. Выберите учетную запись безопасности для пула приложений. Укажите управляемую учетную запись, которая будет использовать учетную запись пользователя домена.

10. Примите остальные значения по умолчанию и нажмите кнопку **ОК.** Приложение службы появится рядом с другими управляемыми службами в списке приложений служб фермы.

11. Щелкните приложение службы Secure Store в списке.

12. На ленте приложения службы щелкните **Управление**.

13. В разделе Управление ключами щелкните **создать новый ключ**.

14. Введите, а затем подтвердите парольную фразу. Эта фраза будет использоваться для добавления других общих приложений служб безопасных хранилищ.

15. Нажмите кнопку **ОК**.

 Прежде чем станет доступным ведение журналов аудита операций службы Secure Store, которое может оказаться полезным для целей отладки, его необходимо включить. Дополнительные сведения о том, как включить ведение журнала, см. в разделе [Configure служба Secure Store (SharePoint 2010)](https://go.microsoft.com/fwlink/p/?LinkID=223294).

##  <a name="step-2-turn-off-credential-options-that-you-do-not-want-to-support"></a><a name="bkmk_creds"></a>Шаг 2. Отключение параметров учетных данных, которые не требуется поддерживать
 Обновление данных PowerPivot предусматривает три режима использования учетных данных в расписании. Когда владелец книги планирует обновление данных, он выбирает один из трех вариантов, определяя таким образом учетную запись, от которой будут запускаться задания обновления данных. Как администратор вы можете определить, какие варианты использования учетных данных будут доступны владельцам расписания.

 Для обновления данных должен быть доступен хотя бы один вариант.

 ![SSAS_PowerpivotKJ_DataRefreshCreds](media/ssas-powerpivotkj-datarefreshcreds.gif "SSAS_PowerpivotKJ_DataRefreshCreds")

 Вариант 1. **Используйте учетную запись обновления данных, настроенную администратором**, всегда отображается на странице Определение расписания, но работает только при настройке учетной записи автоматического обновления данных. Дополнительные сведения о создании учетной записи см. в статье [Настройка учетной записи автоматического обновления данных PowerPivot &#40;PowerPivot для SharePoint&#41;](configure-unattended-data-refresh-account-powerpivot-sharepoint.md).

 Вариант 2, **Connect с использованием следующих учетных данных Windows**, всегда отображается на странице, но работает только при включении параметра **Разрешить пользователям вводить пользовательские учетные данные Windows** на странице Конфигурация приложения службы. Этот параметр включен по умолчанию, но его можно отключить, если минусы его использования превышают плюсы (см. ниже).

 Вариант 3. **подключение с использованием учетных данных, сохраненных в Служба Secure Store**, всегда отображается на странице, но работает только в том случае, если владелец расписания предоставляет допустимое целевое приложение. Администратор должен предварительно создать это целевое приложение и сообщить его имя создателю расписания обновления данных. Дополнительные сведения о создании целевого приложения для операций обновления данных см. в статье [Настройка сохраненных учетных данных для &#40;обновления данных PowerPivot PowerPivot для SharePoint&#41;](configure-stored-credentials-data-refresh-powerpivot-sharepoint.md).

 **Настройка параметра учетных данных 2 "подключение с использованием следующих учетных данных пользователя Windows"**

 Приложение службы PowerPivot включает параметр учетных данных, который позволяет владельцу расписания ввести произвольные имя пользователя и пароль Windows для запуска задания обновления данных. Это второй параметр на странице определения расписания:

 ![SSAS_PPS_ScheduleDataRefreshCreds](media/ssas-pps-scheduledatarefreshcreds.gif "SSAS_PPS_ScheduleDataRefreshCreds")

 Этот вариант учетных данных включен по умолчанию. Если он включен, то системная служба PowerPivot сформирует в службе Secure Store целевое приложение для хранения имени и пароля, введенных владельцем расписания. Созданное целевое приложение создается с использованием этого соглашения об именовании: PowerPivotDataRefresh_ \<guid> . Для каждого набора учетных данных Windows создается одно целевое приложение. Если существует целевое приложение, принадлежащее системной службе PowerPivot и хранящее имя пользователя и пароль, введенные пользователем, которым было определено расписание, то системная служба PowerPivot будет использовать это приложение, а не создаст новое.

 Главное преимущество использования этого варианта хранения учетных данных — простота. Предварительная работа сводится к минимуму, так как целевые приложения создаются автоматически. Кроме того, запуск обновления данных от учетных данных владельца расписания (который, скорее всего, является и создателем книги) упрощает выполнение требований к передаче разрешений. Скорее всего, этот пользователь уже имеет разрешения для целевой базы данных. Когда обновление данных выполняется с учетными данными пользователя Windows этого пользователя, любые подключения к данным, указывающие "текущий пользователь", будут работать автоматически.

 Недостатком являются ограниченные возможности управления. Хотя целевое приложение создается автоматически, оно не обновляется и не удаляется при изменении учетной записи. Применение политик истечения срока действия паролей может привести к тому, что целевые приложения станут неактуальными. Задания обновления данных, сроки действия учетных данных которых истекли, не смогут запуститься. В этом случае владельцу расписания необходимо обновить учетные данные, указав имя пользователя и пароль в расписании обновления данных. Тогда будет создано новое целевое приложение. По мере того как пользователи добавляют и корректируют информацию об учетных данных в своих расписаниях обновления данных, может сложиться такая ситуация, когда в системе имеется великое множество автоматически созданных целевых приложений.

 В настоящее время не существует способа определить, активно ли то или иное целевое приложение. Не существует также и способа отслеживания конкретного целевого приложения из создавшего его задания обновления данных. Лучше не трогать целевые приложения, так как их удаление может привести к прекращению работы расписаний обновления данных. Удаление целевого приложения, которое по-прежнему используется, приведет к сбою обновления данных с сообщением "целевое приложение не найдено", отображаемое на странице журнала обновления данных книги.

 Отключив этот параметр, можно безопасно удалить целевые приложения, созданные для обновления данных PowerPivot.

 **Отключение использования произвольных учетных данных Windows в расписаниях обновления данных**

1.  В центре администрирования в окне "Управление приложениями" выберите **Управление приложения службы**.

2.  Щелкните имя приложения службы PowerPivot. Откроется панель мониторинга PowerPivot.

3.  В меню действия выберите **настроить параметры приложения службы** , чтобы открыть страницу Параметры приложения службы PowerPivot.

4.  В разделе Обновление данных снимите флажок **Разрешить пользователям вводить настраиваемые учетные данные Windows** .

     ![SSAS_PowerPivotDatarefreshOptions_AllowUser](media/ssas-powerpivotdatarefreshoptions-allowuser.gif "SSAS_PowerPivotDatarefreshOptions_AllowUser")

##  <a name="step-3-create-target-applications-to-store-credentials-used-in-data-refresh"></a><a name="bkmk_stored"></a>Шаг 3. Создание целевых приложений для хранения учетных данных, используемых при обновлении данных
 После завершения настройки службы Secure Store администраторы SharePoint смогут создавать целевые приложения для обеспечения доступности сохраненных учетных данных при обновлениях, включая учетную запись автоматического обновления данных PowerPivot и другие учетные записи, которые используются для выполнения задания или соединения с внешними источниками данных.

 Ранее уже говорилось, что для использования учетных данных необходимо создать целевые приложения. В частности, необходимо создать целевые приложения для учетной записи автоматического обновления PowerPivot, а также для всех необходимых учетных данных, использование которых планируется в операциях обновления данных.

 Дополнительные сведения о создании целевых приложений, содержащих сохраненные учетные данные, см. [в статьях Настройка учетной записи автоматического обновления данных powerpivot &#40;PowerPivot для SharePoint&#41;](configure-unattended-data-refresh-account-powerpivot-sharepoint.md) и [Настройка сохраненных учетных данных для &#40;обновления данных PowerPivot PowerPivot для SharePoint&#41;](configure-stored-credentials-data-refresh-powerpivot-sharepoint.md).

##  <a name="step-4-configure-the-server-for-scalable-data-refresh"></a><a name="bkmk_scale"></a>Шаг 4. Настройка масштабируемого обновления данных на сервере
 По умолчанию каждая установка PowerPivot для SharePoint поддерживает обновление по запросу и по расписанию.

 Для каждой установки можно указать, будет ли поддерживать экземпляр служб Analysis Services обновление данных обоими способами, или будет привязан к какому-то конкретному типу операций. Если на ферме имеется несколько установок PowerPivot для SharePoint и задания обновления данных выполняются долго или с ошибками, то можно подумать над установкой выделенного сервера, который будет заниматься только операциями обновления данных.

 Кроме того, можно увеличить число параллельно выполняющихся заданий обновления, если оборудование это позволяет. По умолчанию число одновременно выполняемых заданий вычисляется исходя из объема системной памяти, но его можно увеличить, если мощности ЦП достаточно для этого.

 Дополнительные сведения см. в статьях [Настройка выделенного обновления данных или обработка только запросов &#40;PowerPivot для SharePoint&#41;](configure-dedicated-data-refresh-query-only-processing-powerpivot-sharepoint.md).

##  <a name="step-5-install-data-providers-used-to-import-powerpivot-data"></a><a name="bkmk_installdp"></a>Шаг 5. Установка поставщиков данных, используемых для импорта данных PowerPivot
 Операция обновления данных по сути является повторным выполнением операции импорта, при которой извлекаются исходные данные. Это означает, что поставщики данных, которые используются для импорта данных в клиентские приложения PowerPivot, также должны быть установлены на сервере PowerPivot.

 Поставщиков данных на сервере Windows могут устанавливать только локальные администраторы. При установке дополнительных данных необходимо убедиться, что они установлены на компьютере в ферме SharePoint, где установлен PowerPivot для SharePoint. Если в ферме имеется несколько серверов PowerPivot, то поставщики необходимо установить на всех серверах.

 Помните, что серверы SharePoint являются 64-разрядными приложениями. Убедитесь, что установлена 64-разрядная версия поставщиков данных — именно эти поставщики используются для операций обновления данных.

##  <a name="step-6-grant-permissions-to-create-schedules-and-access-external-data-sources"></a><a name="bkmk_accounts"></a>Шаг 6. Предоставление разрешений на создание расписаний и доступ к внешним источникам данных
 Владельцы книг или авторы должны иметь разрешение **Участие** , чтобы иметь возможность создавать расписание обновления данных для книги. Учитывая этот уровень разрешений, он может открыть и изменить страницу настройки обновления данных книги, чтобы указать учетные данные и расписание, используемое для обновления данных.

 Чтобы во время обновления данных учетным записям хватило прав доступа, необходимых для выполнения операции, помимо разрешений SharePoint необходимо также проверить разрешения для внешних источников данных. Определение необходимых разрешений потребует внимательности с вашей стороны, так как разрешения, которые необходимо предоставить, в большой степени зависят от строки подключения, заданной в книге, и удостоверения пользователя, с которым запускается задание обновления данных.

 **Почему существующие строки подключения в книге PowerPivot влияют на операции обновления данных PowerPivot**

 При запуске обновления данных сервер отправляет внешнему источнику данных запрос на соединение через строку подключения, созданную во время первоначального импорта данных. Размещение сервера, имя базы данных и параметры проверки подлинности, указанные в строке подключения, будут повторно использованы для доступа к тем же источникам данных. Строку подключения и ее общую конструкцию нельзя изменить для целей обновления. Она просто повторно используется во время обновления данных. В некоторых случаях, если для соединения с источником данных используется проверка подлинности, отличная от Windows, можно переопределить имя пользователя и пароль, указанные в строке подключения. Подробности приведены ниже в этом разделе.

 Для большинства рабочих нагрузок при соединении вариантом проверки подлинности по умолчанию является использование доверительных соединений или встроенной проверки подлинности Windows, когда строка подключения содержит `SSPI=IntegratedSecurity` или `SSPI=TrustedConnection`. Если эта строка подключения используется во время обновления данных, учетная запись, используемая для запуска задания обновления данных, становится "текущим пользователем". Этой учетной записи и нужны разрешения на чтение любых источников данных, доступ к которым производится через доверительное соединение.

 **Включена ли учетная запись автоматического обновления PowerPivot?**

 Если да, то необходимо предоставить этой учетной записи разрешения на чтение источников данных, доступ к которым производится во время обновления данных. Причина, по которой этой учетной записи требуются разрешения на чтение, заключается в том, что в книге, использующей параметры проверки подлинности по умолчанию, учетная запись автоматической установки будет "текущий пользователь" во время обновления данных. Если владелец расписания переопределяет учетные данные в строке подключения, то этой учетной записи потребуются разрешения на чтение источников данных, активно используемых в вашей организации.

 **Используется ли второй вариант учетных данных, который позволяет владельцу расписания вводить имя и пароль пользователя Windows?**

 Как правило, пользователь, который создал книгу PowerPivot, уже имеет достаточно разрешений, так как он уже выполнял первоначальный импорт данных. Если такой пользователь впоследствии настроит обновление данных на запуск от собственной учетной записи пользователя Windows, который подошел для базы данных, то он будет использоваться и для получения данных во время обновления. Существующих разрешений должно быть достаточно.

 **Используется ли третий вариант учетных данных: использование целевых приложений службы Secure Store для хранения удостоверения пользователя для запуска заданий обновления данных?**

 Любая учетная запись для запуска задания обновления данных должна иметь разрешения на чтение по тем же причинам, которые описаны выше для учетной записи автоматического обновления PowerPivot.

 **Как проверить строку подключения и определить, можно ли переопределить указанные в ней учетные данные для обновления данных**

 Как уже отмечалось, на уровне задания обновления данных можно указать другое имя пользователя и пароль, если в строке соединения указана проверка подлинности, отличная от Windows (например, проверка подлинности SQL Server). Учетные данные, отличные от Windows, передаются в строке соединения в параметрах User ID и Password. Если в книге содержится строка подключения с этими параметрами, то можно указать другие имя пользователя и пароль для обновления данных из источника данных.

 В следующих шагах объясняется, как определить, допускает ли строка подключения переопределение имени пользователя и пароля.

1.  Откройте книгу в Excel.

2.  Откройте окно PowerPivot (щелкните PowerPivot на ленте Excel).

3.  Нажмите кнопку **конструктор**.

4.  Щелкните **существующие соединения**.

     Все подключения, используемые в книге, перечислены в разделе **подключения к данным PowerPivot**.

5.  Выберите соединение и нажмите кнопку **изменить**, а затем — **Дополнительно**. Строка подключения находится в нижней части страницы.

 Если в строке подключения отображается **Integrated Security = SSPI** , то нельзя переопределить учетные данные в строке подключения. Соединение всегда будет использовать учетные данные текущего пользователя. Любые указанные учетные данные не будут использоваться.

 Если вы видите параметр **сохранить сведения о безопасности = false, Password = \* \* \* \* \* \* \* \* \* \* \* , \<userlogin> UserID =**, то у вас есть строка подключения, которая будет принимать переопределения учетных данных. Учетные данные в строке подключения (UserID и Password) являются не учетными данными Windows, а именем входа базы данных или зарегистрированной учетной записью на целевом источнике данных.

 **Как переопределить учетные данные в строке подключения**

 Переопределение учетных данных выполняется путем указания учетных данных источника данных в расписании обновления данных. Пользователь с правами администратора может указать целевое приложение в службе Secure Store, которое сопоставляет учетные данные для доступа к внешним данным. После этого владелец расписания может ввести идентификатор целевого приложения в расписание обновления данных, определенное им же. Дополнительные сведения о создании этого целевого приложения см. в статье [Настройка сохраненных учетных данных для &#40;обновления данных PowerPivot PowerPivot для SharePoint&#41;](configure-stored-credentials-data-refresh-powerpivot-sharepoint.md).

 В качестве альтернативы владелец расписания может ввести набор учетных данных, которые будут использоваться для соединения с источниками данных во время обновления данных. На следующей иллюстрации показан параметр источника данных на странице определения расписания.

 ![SSAS_PowerPivotKJ_DataRefreshDSOptions](media/ssas-powerpivotkj-datarefreshdsoptions.gif "SSAS_PowerPivotKJ_DataRefreshDSOptions")

 **Определение требований доступа к данным**

 Как уже говорилось, учетная запись для запуска обновления данных и учетная запись для соединения с внешними источниками данных часто означают одно и то же. Учетная запись для доступа к внешним источникам данных определяется параметрами, заданными на этой странице расписания обновления данных. Это может быть учетная запись автоматического обновления данных PowerPivot, учетная запись Windows конкретного пользователя или учетная запись, которая хранится в предопределенном целевом приложении.

 ![SSAS_PowerpivotKJ_DataRefreshCreds](media/ssas-powerpivotkj-datarefreshcreds.gif "SSAS_PowerpivotKJ_DataRefreshCreds")

 В тех случаях, когда учетная запись, используемая для запуска обновления данных, отличается от учетной записи, используемой для импорта данных (например, учетная запись автоматического обновления данных PowerPivot по первому варианту или какой-либо другой набор сохраненных учетных данных по третьему варианту), для этой учетной записи придется создать новое имя входа в базе данных и предоставить ему разрешения на чтение во внешних источниках данных.

 Разобравшись, каким учетным записям требуется доступ к данным, можно проверить разрешения в источниках данных, наиболее часто используемых в книгах PowerPivot. Начните с хранилищ данных и баз данных отчетов, которые чаще всего используются, а также выясните у наиболее активных пользователей PowerPivot, какими источниками данных они пользуются. Составив список источников данных, можно их один за другим проверить и убедиться, правильно ли для них настроены разрешения.

##  <a name="step-7-enable-workbook-upgrade-for-data-refresh"></a><a name="bkmk_upgradewrkbk"></a>Шаг 7. Включение обновления данных в книге
 По умолчанию книги, созданные с помощью версии [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] PowerPivot для Excel, нельзя настроить для планового обновления данных на [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] PowerPivot для SharePoint. При размещении более новых и более поздних версий книг PowerPivot в среде SharePoint следует сначала обновить книги [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], прежде чем создавать расписание для автоматического обновления данных на сервере.

##  <a name="step-8-verify-data-refresh-configuration"></a><a name="bkmk_verify"></a>Шаг 8. Проверка конфигурации обновления данных
 Чтобы проверить обновление данных, необходима книга PowerPivot, опубликованная на сайте SharePoint. Вы должны иметь разрешения на участие для этой книги, а также разрешения на доступ к любым источникам данных, включенных в расписание обновления данных.

 При создании расписания установите флажок **также обновлять как можно скорее** , чтобы немедленно запустить обновление данных. Затем можно на странице журнала обновления данных книги проверить, правильно ли оно запустилось. Помните, что задание таймера обновления данных PowerPivot запускается раз в минуту. То есть подтверждение о запуске обновления данных может потребоваться подождать в течение этого времени.

 Обязательно попробуйте все варианты учетных данных, поддержка которых планируется. Например, если настроена учетная запись автоматического обновления данных PowerPivot, то нужно проверить, успешно ли выполняется обновление данных в этом режиме. Дополнительные сведения о планировании и просмотре сведений о состоянии см. в статьях [планирование &#40;обновления данных PowerPivot для SharePoint&#41;](schedule-a-data-refresh-powerpivot-for-sharepoint.md) и [Просмотр журнала обновления данных &#40;PowerPivot для SharePoint&#41;](power-pivot-sharepoint/view-data-refresh-history-power-pivot-for-sharepoint.md).

 Если обновление данных завершается неудачно, обратитесь к странице [Устранение неполадок обновления данных PowerPivot](https://go.microsoft.com/fwlink/?LinkID=223279) на вики-сайте TechNet, чтобы получить возможные решения.

##  <a name="modify-configuration-settings-for-data-refresh"></a><a name="bkmk_config"></a>Изменение параметров конфигурации для обновления данных
 Каждое приложение службы PowerPivot имеет параметры конфигурации, используемые в операциях обновления данных. В этом разделе описано, как изменить эти параметры.

###  <a name="set-business-hours-to-determine-off-hours-processing"></a><a name="procIntervals"></a>Задайте "рабочие часы", чтобы определить обработку в нерабочее время
 Пользователи SharePoint, создающие расписания для операций обновления данных, могут задать самое раннее время запуска «По окончании рабочего дня». Это может быть полезно, если нужно получить данные бизнес-транзакций, накопленные за рабочий день. Администратор фермы может задать временной диапазон, наиболее точно характеризующий начало и конец рабочего дня на данном предприятии. Если задать начало рабочего дня в 04:00 и конец в 20:00, то обработка обновления данных, для которой задано время запуска «По окончании рабочего дня», начнется в 20:01.

 Запросы обновления данных, запущенные вне рабочих часов, добавляются в очередь в порядке получения запроса. Индивидуальные запросы обрабатываются по мере высвобождения ресурсов сервера.

1.  В центре администрирования в окне "Управление приложениями" выберите **Управление приложения службы**.

2.  Щелкните имя приложения службы PowerPivot. Откроется панель мониторинга PowerPivot.

3.  В меню действия выберите **настроить параметры приложения службы** , чтобы открыть страницу Параметры приложения службы PowerPivot.

4.  В разделе «Обновление данных» в поле «Часы работы» введите начальное и конечное время, которое определяет период обработки данных по окончании рабочего дня.

     Если не нужно задавать период, в который обработка не производится, можно задать одно и то же значение для «Времени начала» и «Времени окончания», например 12:00 для обоих полей. Однако следует помнить, что на страницах определения расписания сайтов SharePoint по-прежнему будет значиться параметр «По окончании рабочего дня». Пользователи, выбирающие этот параметр на ферме, где не задан период, в который обработка данных не производится, будут получать ошибки обновления данных, так как задачи по обработке не будут запускаться.

5.  Нажмите кнопку **ОК**.

###  <a name="limit-how-long-data-refresh-history-is-retained"></a><a name="usagehist"></a>Ограничение времени хранения журнала обновления данных
 Журнал обновления данных представляет собой подробную регистрацию накапливаемых со временем сообщений об успехе и неудаче операций обновления данных. Данные журнала собираются и управляются через существующую на ферме систему сбора данных об использовании. Все ограничения, наложенные на журнал данных об использовании, применяются также и к журналу обновления данных. Поскольку отчеты об использовании извлекают данные из различных мест системы PowerPivot, единая настройка журнала управляет хранением данных как для журнала обновления данных, так и для любых других собираемых и хранимых данных об использовании.

1.  В центре администрирования в окне "Управление приложениями" выберите **Управление приложения службы**.

2.  Щелкните имя приложения службы PowerPivot. Откроется панель мониторинга PowerPivot.

3.  В меню действия выберите **настроить параметры приложения службы** , чтобы открыть страницу Параметры приложения службы PowerPivot.

4.  В разделе «Сбор данных об использовании» в поле «Журнал данных об использовании» введите число дней, в течение которых должны сохраняться записи об операциях обновления данных для каждой книги.

     Значение по умолчанию — 365 суток. Минимальное значение — 1 сутки, максимальное — 5 000 суток. 0 означает неограниченный срок хранения, данные не удаляются. Обратите внимание, что для отключения журнала параметра нет.

5.  Нажмите кнопку **ОК**.

 Сведения из журнала доступны пользователям SharePoint при выборе параметра «Управление обновлением данных» в книге, в которой совершались операции обновления данных. Эти сведения также используются на панели мониторинга PowerPivot, с помощью которой администраторы фермы управляют работой службы PowerPivot. Дополнительные сведения см. в разделе [Просмотр журнала обновления данных &#40;PowerPivot для SharePoint&#41;](power-pivot-sharepoint/view-data-refresh-history-power-pivot-for-sharepoint.md).

 Для долговременного физического хранения данных журнала для приложения службы PowerPivot используется база данных приложения службы PowerPivot. Дополнительные сведения о сборе и хранении данных об использовании см. в разделе [PowerPivot Usage Data Collection](power-pivot-sharepoint/power-pivot-usage-data-collection.md).

##  <a name="reschedule-the-powerpivot-data-refresh-timer-job"></a><a name="configTimerJob"></a>Изменение расписания для задания таймера обновления данных PowerPivot
 Запланированное обновление данных запускается заданием таймера обновления данных PowerPivot, которая с интервалом в 1 минуту считывает сведения о расписании из базы данных приложения службы PowerPivot. Когда по расписанию должно начаться обновление данных, задание таймера добавляет запрос в очередь обработки на доступном сервере PowerPivot.

 Для оптимизации производительности можно увеличить продолжительность интервалов между сканированиями. Можно также отключить задание таймера для временной приостановки операций обновления данных на время отладки системы.

 Значение по умолчанию — одна минута. Это минимальное значение, которое можно задать. Рекомендуется использовать именно это значение, поскольку оно обеспечивает наиболее прогнозирующий результат для расписаний, задающих выполнение задач в произвольные моменты в течение дня. Например, если пользователь указывает, что обновление данных должно начаться в 16:15, и задание таймера сканирует расписания ежеминутно, запрос на запланированное обновление данных будет обнаружен в 16:15 и его выполнение начнется самое большее через несколько минут.

 Если значительно увеличить интервал сканирования (например, указать, что сканирование должно производиться раз в сутки в полночь), то все операции обновления данных, запланированные к запуску в этом интервале, будут добавлены в очередь обработки одновременно, что может привести к перегрузке сервера и лишить другие приложения системных ресурсов. В зависимости от количества запланированных обновлений очередь обработки операций обновления данных может разрастись настолько, что не все задания смогут завершиться. Запросы обновления данных, попавшие в конец очереди, могут быть отменены, если попадут в следующий интервал обработки.

 Если позволяет оборудование, можно уменьшить этот риск, указав дополнительные процессоры, которые понадобятся для параллельного запуска большего числа заданий обновления данных. Дополнительные сведения см. в статьях [Настройка выделенного обновления данных или обработка только запросов &#40;PowerPivot для SharePoint&#41;](configure-dedicated-data-refresh-query-only-processing-powerpivot-sharepoint.md). Дополнительные сведения об обнаружении запросов на обновление данных, добавлении их в очередь и обработке см. в разделе [PowerPivot Data Refresh](power-pivot-sharepoint/power-pivot-data-refresh.md).

1.  В центре администрирования нажмите **Наблюдение**.

2.  Щелкните **проверить определения заданий**.

3.  Выберите **Задание таймера обновления данных PowerPivot**.

4.  Измените указанную в расписании частоту, с которой задание таймера сканирует сведения о расписании обновления данных.

##  <a name="disable-the-data-refresh-timer-job"></a><a name="bkmk_disableDR"></a>Отключение задания таймера обновления данных
 Задание таймера обновления данных PowerPivot представляет собой задание таймера уровня фермы, которое можно либо включить, либо отключить для всех экземпляров сервера PowerPivot в пределах фермы. Оно не привязано к конкретному веб-приложению или приложению службы PowerPivot. Его нельзя отключить на отдельных серверах фермы для ускорения обработки обновления данных на других серверах этой фермы.

 Если отключить задание таймера обновления данных PowerPivot, запросы, которые уже попали в очередь, будут обработаны, но новые запросы не будут добавляться в очередь, пока задание не будет снова включено. Запросы, момент запуска которых по расписанию прошел, запускаться не будут.

 Отключение задания таймера не влияет на доступность функций на страницах приложения. Спрятать или убрать функцию обновления данных в веб-приложениях невозможно. Пользователи, имеющие разрешения уровня «Участие» или выше, смогут создавать новые расписания для операций обновления данных, даже если задание таймера постоянно отключено.

## <a name="see-also"></a>См. также:
 [Запланируйте обновление данных &#40;PowerPivot для SharePoint&#41;](schedule-a-data-refresh-powerpivot-for-sharepoint.md) [настроить выделенное обновление данных или обработку только для запросов &#40;PowerPivot для SharePoint&#41;](configure-dedicated-data-refresh-query-only-processing-powerpivot-sharepoint.md) [настроить учетную запись автоматического обновления данных PowerPivot &#40;](configure-unattended-data-refresh-account-powerpivot-sharepoint.md) PowerPivot для SharePoint&#41;[Настройка сохраненных учетных данных для обновления данных PowerPivot &#40;](configure-stored-credentials-data-refresh-powerpivot-sharepoint.md) PowerPivot для SharePoint&#41;

