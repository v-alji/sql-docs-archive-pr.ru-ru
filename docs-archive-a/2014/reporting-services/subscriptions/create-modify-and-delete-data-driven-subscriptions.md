---
title: Создание, изменение и удаление управляемой данными подписки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- query-based subscriptions [Reporting Services]
- queries [Reporting Services], data-driven subscriptions
- subscriptions [Reporting Services], data-driven
- data-driven subscriptions
ms.assetid: 0ba2093e-9393-4eb6-af06-9da10988cfaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ec7fad729e5a7bd0f75d7a524ba315b4511a7a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666949"
---
# <a name="create-modify-and-delete-a-data-driven-subscription"></a>Create, Modify, and Delete a Data-Driven Subscription
  Управляемая данными подписка — это подписка на основе запроса, которая получает необходимые данные во время выполнения. При запуске такой подписки обрабатывается запрос на получение обновленной информации о получателях, параметрах доставки отчета, форматах подготовки и установки параметров. Результаты запроса объединены с определением подписки для создания динамической подписки, использующей данные, которые уже введены в базу данных служащего, клиента или любую другую базу данных, содержащую информацию, которая может использоваться как данные подписчика.  
  
||  
|-|  
|**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в собственном режиме | в режиме интеграции с SharePoint|  
  
 **В этом разделе:**  
  
-   [Создание и изменение подписки, управляемой данными](#bkmk_create_and_modify)  
  
-   [Формирование запроса для получения информации о подписке](#bkmk_define_query)  
  
-   [Запуск подписки](#bkmk_run_subscription)  
  
-   [Управление и удаление для управляемых данными подписок](#bkmk_manage_and_delete)  
  
##  <a name="create-and-modify-a-data-driven-subscription"></a><a name="bkmk_create_and_modify"></a>Создание и изменение управляемой данными подписки  
 Чтобы создать новую управляемую данными подписку или изменить существующую, откройте страницы «Создание управляемой данными подписки» диспетчера отчетов. Эти страницы содержат пошаговые инструкции для создания или изменения параметров подписки. Чтобы получить доступ к подписке после ее создания, используйте страницу «Мои подписки» и список «Подписки» в отчете. Сведения о создании управляемой данными подписки см. в разделе [Создание управляемой данными подписки (учебник по службам SSRS)](../create-a-data-driven-subscription-ssrs-tutorial.md).  
  
 Для создания управляемой данными подписки выберите отчет, который или использует хранимые учетные данные, или не использует учетные данные. При создании управляемой данными подписки рекомендуется использовать контекст именования для поля описания, чтобы легко отличать стандартные подписки от управляемых данными подписок.  
  
#### <a name="to-create-a-data-driven-subscription-native-mode"></a>Создание управляемой данными подписки (собственный режим)  
  
1.  В диспетчере отчетов перейдите к папке, где находится отчет, наведите курсор на отчет, откройте меню параметров и выберите пункт **Управление**.  
  
2.  Перейдите на вкладку **Подписки** .  
  
3.  Нажмите кнопку **Создать управляемую данными подписку** .  
  
#### <a name="to-create-a-data-driven-subscription-sharepoint-mode"></a>Создание управляемой данными подписки (режим интеграции с SharePoint)  
  
1.  В библиотеке документов SharePoint наведите указатель мыши на отчет, откройте меню параметров и выберите пункт **Управление подписками**.  
  
2.  Нажмите кнопку **Добавить управляемую данными подписку**.  
  
#### <a name="to-modify-an-existing-data-driven-subscription-native-mode"></a>Создание и изменение существующей, управляемой данными подписки (собственный режим)  
  
1.  В диспетчер отчетов перейдите к папке, содержащей отчет, наведите указатель на отчет, откройте меню Параметры и выберите пункт **Управление**.  
  
2.  Перейдите на вкладку **подписки** . в качестве альтернативы щелкните ссылку **Мои подписки** на верхней части диспетчера отчетов.  
  
3.  Выберите подписку, которую хотите изменить. Следующий значок обозначает управляемую данными подписку: ![значок управляемой данными подписки](../media/hlp-16subscriptiondd.gif "Значок подписки, управляемой данными")  
  
#### <a name="to-modify-an-existing-data-driven-subscription-sharepoint-mode"></a>Создание и изменение существующей, управляемой данными подписки (режим интеграции с SharePoint)  
  
1.  В библиотеке документов SharePoint наведите указатель мыши на отчет, откройте меню параметров и выберите пункт **Управление подписками**.  
  
2.  Выберите подписку, которую хотите изменить.  
  
> [!NOTE]  
>  Можно изменить любое значение, которое уже определено. Все значения представлены в том виде, в котором были заданы изначально, за исключением пароля, который используется для доступа к хранилищу данных подписчика. Пароль должен вводиться вновь каждый раз при изменении значений на второй или на любой последующей странице.  
  
 Перед созданием управляемой данными подписки необходимо убедиться в выполнении перечисленных далее требований.  
  
-   **Требования отчета.** Для получения данных во время выполнения у отчета либо должны быть хранимые учетные данные, либо он должен работать без учетных данных. Нельзя подписаться на отчет, который использует олицетворенные или делегированные учетные данные для соединения с внешним источником данных; учетные данные пользователя, который создает подписку или владеет ею, будут недоступны при обработке подписки. Хранимые учетные данные могут быть или учетной записью Windows, или учетной записью базы данных. Дополнительные сведения см. в статье [Задание учетных данных и сведениях о соединении для источников данных отчета](../report-data/specify-credential-and-connection-information-for-report-data-sources.md).  
  
     Нельзя подписаться на отчет построителя отчетов, который в качестве источника данных использует модель, содержащую настройки безопасности элементов модели. Только отчеты, использующие безопасность элементов модели отчета, входят в это ограничение.  
  
     Нельзя создать управляемую данными подписку на отчет, содержащий выражение `User!UserID` .  
  
-   **Требования к данным.** Необходимо иметь доступ к внешнему источнику данных, содержащему данные подписчика.  
  
-   **Требования к пользователю.** Автор подписки должен обладать разрешениями «Управление отчетами» и «Управление всеми подписками». Дополнительные сведения о разрешениях задачи уровня элемента см. в разделе [Задачи и разрешения](../security/tasks-and-permissions.md). Автор должен также иметь необходимые учетные данные для доступа к внешним источникам данных, содержащим сведения о подписчиках.  
  
##  <a name="define-a-query-that-retrieves-subscription-information"></a><a name="bkmk_define_query"></a>Определение запроса, получающего сведения о подписке  
 Управляемая данными подписка должна указывать запрос или команду, которая получает сведения о подписчике. Запрос должен сформировать одну строку для каждого из подписчиков. Если используется модуль доставки по электронной почте, то запрос должен вернуть корректный почтовый псевдоним для каждого подписчика. Число попыток доставки основано на количестве строк, возвращенных запросом. Если набор строк состоит из 10 000 строк, то подписка доставит 10 000 отчетов.  
  
 Выполняя длительный запрос, можно увеличить продолжительность тайм-аута, чтобы сделать возможной дополнительную обработку.  
  
 На этом шаге перед продолжением необходимо проверить корректность запроса. Проверка правильности не выполняет запрос, однако возвращает список всех столбцов, которые находятся в наборе строк, что позволяет создать ссылки на столбцы при последующем выборе. Если запрос некорректен, перейти к следующему шагу нельзя. Запрос некорректен, если используемый синтаксис запроса некорректен, а также в случае некорректности подключения к источнику данных. Используйте кнопку **Назад** для исправления подключения к источнику данных.  
  
##  <a name="run-a-subscription"></a><a name="bkmk_run_subscription"></a>Запуск подписки  
 Вы можете настроить условия для обработки подписки. Можно настроить расписание либо вызвать подписку по событию, чтобы синхронизироваться с созданием снимков для отчетов.  
  
 ![Примечание](../media/rs-fyinote.png "Примечание.") . Хотя в пользовательском интерфейсе нет функции, которую можно использовать для немедленного запуска подписки, можно использовать простой сценарий Windows PowerShell для запуска подписки. Дополнительные сведения см. в подразделе "сценарий: запуск (пожар) одной подписки" статьи [Использование PowerShell для изменения и перечисления Reporting Services владельцев подписок и запуска подписки](manage-subscription-owners-and-run-subscription-powershell.md).  
  
 Расписание и условия запуска управляемых данными подписок такие же, как и для обработки обычных подписок.  
  
##  <a name="manage-and-delete-a-data-driven-subscription"></a><a name="bkmk_manage_and_delete"></a>Управление и удаление управляемой данными подписки  
 Находящуюся в процессе выполнения управляемую данными подписку можно остановить или удалить на странице «Управление заданиями» диспетчера отчетов. Такую подписку удобно запускать с помощью общего расписания, поскольку для того, чтобы временно приостановить обработку подписки, достаточно приостановить запускающее эту подписку расписание. Дополнительные сведения см. в разделе [Создание подписок для работающих в основном режиме серверов отчетов и управление этими подписками](../create-manage-subscriptions-native-mode-report-servers.md).  
  
 Чтобы удалить управляемую данными подписку, ее следует выбрать на странице "Мои подписки" или на странице "Подписки" отчета, а затем щелкнуть **Удалить**.  
  
 Инструкции по отмене выполнения управляемой данными подписки см. в разделе [Управление запущенным процессом](manage-a-running-process.md).  
  
## <a name="see-also"></a>См. также:  
 [Создание, изменение и удаление стандартных подписок &#40;Reporting Services в основном режиме&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md)   
 [Подписки и доставка (службы Reporting Services)](subscriptions-and-delivery-reporting-services.md)   
 [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md)   
 [Создание подписок для работающих в основном режиме серверов отчетов и управление этими подписками](../create-manage-subscriptions-native-mode-report-servers.md)   
 [Диспетчер отчетов &#40;страницы подписок&#41;](../subscriptions-page-report-manager.md)   
 [Страница "Мои подписки" (диспетчер отчетов)](../my-subscriptions-page-report-manager.md)  
  
  