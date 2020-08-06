---
title: 'Новое расписание: страница изменения расписания (диспетчер отчетов) | Документация Майкрософт'
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 52a4d250-e185-4116-a29c-d809940a00fb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 701c1729eac1c2cf683c966dca58f47b88a2dd32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738021"
---
# <a name="new-schedule-edit-schedule-page-report-manager"></a>Новое расписание: страница изменения расписания (диспетчер отчетов)
  Используйте страницу «Создание расписания» / «Изменение расписания», чтобы создать расписание для отчета. Расписания используются с подписками для обновления кэшированных отчетов и для создания моментальных снимков в качестве отдельных элементов или в журнале отчета.  
  
> [!NOTE]  
>  Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).  
  
 Расписания можно создавать только для отчетов, исполняемых в автоматическом режиме. Для автоматического выполнения отчета учетные данные для доступа к источнику данных отчета необходимо сохранять в базе данных сервера отчетов. Дополнительные сведения см. на [странице свойств источников данных &#40;диспетчер отчетов&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md).  
  
 В одном расписании могут поддерживаться не все комбинации частоты событий. Например, если требуется запускать отчет в 12:00 и в 16:00 каждую пятницу, необходимо создать два ежедневных расписания, запускаемых в пятницу, и для одного указать время запуска 12:00, а для другого — 16:00.  
  
 Обработка по расписанию проводится на базе местного времени сервера отчетов, на котором размещается и обрабатывается расписание.  
  
## <a name="navigation"></a>Навигация  
 Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующие процедуры.  
  
### <a name="to-open-the-new-schedule-or-edit-schedule-page-from-the-execution-properties-page-of-a-report"></a>Открытие страницы «Создание расписания» или «Изменение расписания» из страницы свойств отчета «Выполнение»  
  
1.  Откройте диспетчер отчетов и найдите отчет, для которого необходимо настроить расписание.  
  
2.  Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.  
  
3.  В раскрывающемся меню выберите **Управление**. Откроется страница свойств модели «Общие».  
  
4.  Выберите вкладку **Выполнение** .  
  
5.  Выберите **Подготовить этот отчет для просмотра, используя снимок состояния выполнения отчета**. Затем выберите **Применить следующее расписание для добавления моментальных снимков в журнал отчета**и выберите **Расписание отчета**. Затем нажмите кнопку **Настройка**.  
  
### <a name="to-open-the-new-schedule-or-edit-schedule-page-from-the-history-properties-page-of-a-report"></a>Открытие страницы «Создание расписания» или «Изменение расписания» из страницы свойств отчета «Журнал»  
  
1.  Откройте диспетчер отчетов и найдите отчет, для которого необходимо настроить расписание.  
  
2.  Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.  
  
3.  В раскрывающемся меню выберите **Управление**. Откроется страница свойств модели «Общие».  
  
4.  Выберите вкладку **Журнал** .  
  
5.  Выберите **Применить следующее расписание для добавления моментальных снимков в журнал отчета**и выберите **Расписание отчета**. Затем нажмите кнопку **Настройка**.  
  
### <a name="to-open-the-new-schedule-or-edit-schedule-page-from-the-subscriptions-page"></a>Открытие страницы «Создание расписания» или «Изменение расписания» со страницы «Подписки»  
  
1.  Откройте диспетчер отчетов и найдите отчет, для которого необходимо настроить расписание.  
  
2.  Подведите курсор к отчету и щелкните стрелку раскрывающегося списка.  
  
3.  В раскрывающемся меню  
  
    -   Нажмите кнопку **Управление**. Откроется страница свойств отчета «Общие». Затем перейдите на вкладку **Подписки** .  
  
    -   Нажмите **Подписка**. Откроется страница свойств отчета **Подписки** .  
  
4.  На панели инструментов выберите **Создать подписку** или выберите существующую подписку, которую необходимо изменить.  
  
5.  В **Параметры обработки подписки**выберите **Создать расписание**.  
  
## <a name="options"></a>Варианты  
 **Подробности расписания**  
 Выберите параметры, определяющие время и частоту выполнения отчета. Параметры частоты состоят из уровней. Первый набор параметров позволяет задать категорию частоты (ежечасно, ежедневно, еженедельно и т.д.). Второй отображающийся набор параметров зависит от первоначального выбора пользователя.  
  
-   Параметр**Час** определяет расписание, выполняемое через часовые интервалы. Раздел **Даты начала и окончания** используется для задания дня запуска расписания.  
  
-   Параметр**День** определяет расписание, выполняемое в выбранные дни в конкретный час и минуту. Дни можно указать следующими способами: каждый \<*day*> , каждый рабочий день и каждый \<*number*> день. Выбор одного из подходов отменяет другие, даже если остальные дни отображаются выделенными.  
  
-   Параметр**Неделя** определяет расписание, выполняемое через недельные интервалы в конкретный час и минуту. Интервал может составлять полную неделю (например, каждые две недели) или дни в пределах недели.  
  
-   Параметр**Месяц** определяет расписание, выполняемое один раз в месяц. В пределах месяца можно выбрать день по шаблону (например, последнее воскресенье каждого месяца) или конкретные календарные даты (такие как 1 и 15, что означает первый и пятнадцатый день каждого месяца). При помощи запятых и дефисов можно задать несколько дней или их диапазоны, например 1, 5, 7-12, 21.  
  
-   Параметр**Однократно** определяет расписание, выполняемое только один раз. Раздел **Даты начала и окончания** используется для задания дня запуска расписания. Срок действия расписания истекает, как только оно обработано.  
  
 **Даты начала и окончания**  
 Задать начальную дату, определяющую начальное время действия расписания, и конечную дату, определяющую срок действия расписания.  
  
 Срок действия расписания истекает без уведомления. После даты окончания они более не выполняются. Расписания с истекшим сроком действия не удаляются. Расписания можно удалять только вручную. Таким образом, при необходимости продления расписания можно увеличить дату окончания.  
  
## <a name="see-also"></a>См. также:  
 [Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md)   
 [Создание, изменение и удаление расписаний](subscriptions/create-modify-and-delete-schedules.md)   
 [Справка F1 диспетчера отчетов](../../2014/reporting-services/report-manager-f1-help.md)  
  
  