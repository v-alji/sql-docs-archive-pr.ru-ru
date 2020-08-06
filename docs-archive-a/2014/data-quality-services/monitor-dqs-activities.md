---
title: Мониторинг действий DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.administration.activitymonitoring.f1
helpviewer_keywords:
- monitoring activity
- activity monitoring
ms.assetid: 1d4c76f3-0d7b-498e-b792-4db4a0349814
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3adc4b94a75bf090f83062e18c1d31957891b79d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658408"
---
# <a name="monitor-dqs-activities"></a>Мониторинг операций DQS
  В этом разделе описывается централизованный мониторинг следующих действий в [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS): обнаружение знаний, управление доменами, политика сопоставления, очистка данных, сопоставление данных и очистка на базе служб SSIS.

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Перед началом

###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> Ограничения
 Только пользователи с ролью dqs_administrator в базе данных DQS_Main могут прерывать действие или останавливать процесс в составе действия.

###  <a name="security"></a><a name="Security"></a> безопасность

####  <a name="permissions"></a><a name="Permissions"></a> Permissions

-   Для просмотра действий DQS необходимо иметь роль dqs_kb_editor или dqs_kb_operator в базе данных DQS_MAIN.

-   Для завершения действия или остановки процесса в составе действия, помимо просмотра действий DQS, необходимо обладать ролью dqs_administrator в базе данных DQS_MAIN.

##  <a name="view-dqs-activities"></a><a name="View"></a> Просмотр действий DQS

1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)][Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).

2.  На главном экране [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] нажмите **Мониторинг активности**. Появится экран мониторинга активности.

     ![Экран наблюдения за активностью](../../2014/data-quality-services/media/dqs-activitymonitoring.gif "Экран наблюдения за активностью")

3.  На экране мониторинга активности отображаются сведения о каждом действии в сетке действий. В сетке действий показаны следующие сведения о каждом действии DQS:

    |Сведения|Описание|
    |-----------------|-----------------|
    |**Идентификатор**|Целочисленное значение. Уникальный номер действия, формируемый системой для мониторинга активности.|
    |**имя**;|Имя базы знаний или проекта служб DQS, используемого этим действием.|
    |**Активен**|Указывает, активно ли действие. Может иметь следующие значения.<br /><br /> **Активно**: действие выполняется в данный момент.<br /><br /> **Закончено**: действие завершено.<br /><br /> **Завершено**: действие было прервано с экрана мониторинга активности администратором служб DQS или отменено пользователем при запуске из соответствующей функциональной области в [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].|
    |**Тип**|Указывает тип действия. Отслеживаются следующие типы действий: **Управление знаниями**, **Проект DQ**и **Очистка SSIS**.|
    |**Подтип**|Указывает конкретный рабочий процесс, который выполняется для действия данного типа.<br /><br /> Тип действия **Управление знаниями** может инициировать следующие рабочие процессы или подтипы: **Обнаружение знаний**, **Управление доменами**и **Политика соответствия**.<br /><br /> Тип действия **Проект служб DQS** может инициировать следующие рабочие процессы или подтипы: **Очистка** и **Сопоставление**.<br /><br /> У типа действий **Очистка на базе служб SSIS** может быть рабочий процесс или подтип только типа **Очистка** .|
    |**Текущее состояние**|Указывает текущее состояние действия. Состояние действия определяется последним вычислительным процессом. Может иметь следующие значения.<br /><br /> **Запущенные**: вычислительный процесс выполняется.<br /><br /> **Выполнено**: перед запуском какого-либо вычислительного процесса действие имеет состояние **Выполнено**. После успешного завершения какого-либо вычислительного процесса действие также имеет состояние **Успешно завершено**.<br /><br /> **Ошибка**: вычислительный процесс завершился с ошибкой.<br /><br /> **Остановлен**: вычислительный процесс был приостановлен.<br /><br /> <br /><br /> Примечание. в одном действии может быть несколько вычислительных процессов, например запуск процесса обнаружения несколько раз (внутри действия обнаружения знаний). Таким образом, состояние в течение времени жизни действия может измениться несколько раз.|
    |**DQKB**|Имя базы знаний, используемой этим действием.|
    |**Пользователь**|Имя пользователя, который инициировал действие, либо последнего пользователя, который работал с действием (если они не совпадают).|
    |**Время начала действия**|Дата и время запуска действия.|
    |**Затраченное время**|Время, истекшее с момента запуска действия. Отображается в формате ЧЧ:ММ:СС.|
    |**Время окончания действия**|Дата и время завершения действия.|

##  <a name="filter-dqs-activity-information"></a><a name="Filter"></a> Фильтр сведений о действиях DQS
 С помощью панели фильтрации (**Фильтровать по**, **Значение**, **От даты**и **До даты**) на экране мониторинга активности можно фильтровать и просматривать необходимые действия по тому или иному критерию. Для фильтрации записей действий:

1.  Выберите критерий фильтрации: следует ли фильтровать записи действий по значению в одном из столбцов сетки действий (по значениям), по диапазону дат либо по обоим критериям.

    1.  **Фильтрация на основе значений**: выберите критерий фильтра в списке **Фильтровать по** , затем соответствующее значение для фильтра в списке **Значение** . После выбора параметра в списке **Фильтровать по** список **Значение** заполняется возможными значениями. Поддерживается фильтрация по следующим полям в записях о действиях: **Активность**, **Тип**, **Подтип**, **Текущее состояние**, **DQKB**и **Пользователь**.

    2.  **Фильтрация по диапазону дат**: выбор нужных дат в полях **От даты** и **До даты** . По умолчанию в поле **От даты** отображается дата на два дня раньше текущей, а в поле **До даты** — текущая дата. Фильтрация выполняется не по отдельным датам *От* и *До* , а по диапазону. Это означает, что будут отображены все действия, которые выполнялись в указанном диапазоне дат.

2.  Щелкните значок **Обновить список действий** , чтобы применить фильтрацию, затем просмотрите только отфильтрованные действия DQS.

##  <a name="view-dqs-activity-details"></a><a name="ActivityDetails"></a> Просмотр подробных сведений о действиях DQS
 На экране мониторинга активности можно просмотреть подробные сведения о действии DQS, например об этапах его выполнения, а также сведения профилировщика. Для этого выполните следующие действия.

1.  Выберите действие DQS в сетке действий (на верхней панели).

2.  На нижней панели отображаются подробные сведения о выбранном действии, они разбиты на две вкладки.

    -   **Этапы действия**: отображает сетку вычислительных процессов (этапов действия), связанных с выбранным действием. Для действия на этой вкладке может отображаться несколько шагов действия. Это может произойти в том случае, если один шаг действия в действии был выполнен несколько раз пользователем. Например, этап действия был остановлен, а затем снова запущен. Сетка на этой вкладке отображает следующие сведения по каждому этапу действия, связанному с действием: **Тип**, **Текущее состояние**, **Время начала**, **Затраченное время**и **Время окончания**.

    -   **Профилировщик**: отображает профилировочные сведения для текущих и выполнявшихся ранее действий. Для текущих действий он содержит неполные, но согласованные сведения. Профилировочные сведения о действии экспортируются в файл Excel при экспорте соответствующих подробных сведений о действии в файл Excel. Эти сведения доступны на листах **профилировщика-Source** и **Profiler-Fields** в экспортированном файле Excel.

##  <a name="export-dqs-activity-details"></a><a name="Export"></a> Экспорт подробных сведений о действиях DQS
 На экране мониторинга можно экспортировать в файл Excel свойства действий, процессы действий и профилировочные сведения для действия. Для этого выполните следующие действия.

1.  Выберите действие в сетке действий (на верхней панели).

2.  Щелкните значок **Экспортировать выбранное действие в Excel** . Можно также щелкнуть правой кнопкой мыши любое действие в сетке действий, а затем выбрать пункт **Экспортировать действие** в контекстном меню.

3.  Будет предложено указать имя и расположение сохраняемого файла Excel. Экспортированный файл Excel содержит следующие листы:

    |Имя листа|Описание|
    |----------------|-----------------|
    |Действие|Содержит сведения (столбцы) о действии, как в сетке действий.|
    |Процессы|Содержит сведения (столбцы) о процессах в действии, как на вкладке **Этапы действия** .|
    |Профилировщик — источник|Для подтипа **Очистка** содержит следующие сведения о действии: «Записи», «Правильные записи», «Исправленные записи» и «Недопустимые записи».<br /><br /> Для подтипов **Обнаружение знаний**, **Управление доменами**, **Политика сопоставления**и **Сопоставление** содержит следующие сведения о действии: «Записи», «Всего значений», «Новые значения», «Уникальные значения» и «Новые уникальные значения».|
    |Профилировщик — поля|Для подтипов **Очистка** и **Очистка SSIS** содержит следующие сведения о действии: «Поле», «Домен», «Исправленные значения», «Предложенные значения», «Полнота» и «Точность».<br /><br /> Для подтипов **Обнаружение знаний**, **Управление доменами**, **Политика сопоставления**и **Сопоставление** содержит следующие сведения о действии: «Поле», «Домен», «Новый», «Уникальный», «Действительный в домене» и «Полнота».|

##  <a name="terminate-a-dqs-activity"></a><a name="Terminate"></a> Прерывание действия DQS
 Администраторы служб DQS (роль dqs_administrator) могут прервать запущенное (активное) действие, которое не относится к типу **Очистка на базе служб SSIS**. При прерывании действия будут остановлены все запущенные процессы в действии и удалится все, что относится к данному действию. Отменить эту операцию невозможно. Прерывание действия на экране мониторинга активности равносильно отмене соответствующего действия нажатием кнопки **Отмена** при запуске его в функциональной области [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]. Прерывание действия:

1.  Выберите запущенное действие в сетке действий (на верхней панели).

2.  Щелкните значок **Завершить выбранное действие** . Можно также щелкнуть правой кнопкой мыши любое действие в сетке действий, затем выбрать пункт **Прервать действие** в контекстном меню.

3.  Появится сообщение с запросом на подтверждение. Нажмите кнопку **Да**.

##  <a name="stop-a-process-in-dqs-activity"></a><a name="Stop"></a> Остановка процесса в составе действия DQS
 Администраторы служб DQS (роль dqs_administrator) могут остановить запущенный (активный) процесс в действии, которое не относится к типу **Очистка на базе служб SSIS**. Остановка процесса в действии на экране мониторинга активности равносильна остановке процесса в соответствующем действии в функциональной области [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]. Например, это может быть остановка процесса автоматизированной очистки или остановка процесса сопоставления в составе действия сопоставления. Приостановленный процесс невозможно повторно запустить на экране мониторинга активности. Повторный запуск процесса возможен в соответствующей функциональной области [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]. В этом случае в сетку процессы на вкладке **шаги действия** добавляется дополнительная строка. Состояние остановленного процесса по экрану будет **остановлено**. Чтобы остановить процесс:

1.  Выберите запущенный процесс в сетке подробных сведений о действиях (на нижней панели).

2.  Щелкните значок **Остановить выбранный процесс** . Можно также щелкнуть правой кнопкой мыши любой процесс в сетке подробных сведений о действиях, затем выбрать пункт **Остановить процесс** в контекстном меню.

3.  Появится сообщение с запросом на подтверждение. Нажмите кнопку **Да**.

