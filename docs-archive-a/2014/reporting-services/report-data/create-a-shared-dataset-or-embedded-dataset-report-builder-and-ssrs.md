---
title: Создание общего или внедренного набора данных (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d1d7bc71-f0e9-4ce5-b3ad-6fee54388a31
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fca74e1ba7965eeef6ce562e79e378af5bb9e145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729113"
---
# <a name="create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs"></a>Создание общего или внедренного набора данных (построитель отчетов и службы SSRS)
  Можно создавать внедренные наборы данных для использования в отдельных отчетах или общие наборы данных для сохранения на сервере отчетов и использования в нескольких отчетах. Для создания набора данных необходим внедренный или общий источник данных.

 Используйте построитель отчетов для выполнения следующих задач:

-   Создание общих наборов данных в режиме конструктора наборов данных. Общие наборы данных должны использовать опубликованные общие источники данных.

-   Создание внедренных наборов данных в режиме конструктора отчетов.

-   Сохранение наборов данных непосредственно на сервере отчетов или сайте SharePoint.

 Используйте конструктор отчетов среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] для выполнения следующих задач:

1.  Создание общего набора данных в обозревателе решений. Общие наборы данных должны использовать источники данных из папки «Общие источники данных» в обозревателе решений.

2.  Создание внедренного набора данных в области данных отчета.

3.  При необходимости разверните общие наборы данных и общие источники данных в отчете. Используйте свойства проекта для указания путей к папкам на сервере отчетов или сайте SharePoint для каждого типа элементов.

 Дополнительные сведения см. в разделе [Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-open-report-builder-and-create-a-shared-dataset"></a>Открытие построителя отчетов и создание общего набора данных

1.  Откройте построитель отчетов. Откроется панель **Создание отчета или набора данных** , как показано на следующих рисунках.

     ![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")

    > [!NOTE]
    >   Если страница **Создание панели отчета или набора данных** не откроется с помощью кнопки построителя отчетов, выберите **Создать**.

2.  На левой панели в **Создать набор данных**выберите **Общий набор данных**.

3.  На правой панели выберите **Обзор** , чтобы выбрать общий источник данных на сервере отчетов, а затем выберите **Создать**. Откроется конструктор запросов, связанный с общим источником данных.

4.  В конструкторе запросов укажите поля, которые необходимо включить в набор данных.

5.  Нажмите кнопку **выполнить** (**!**), чтобы выполнить запрос.

6.  На кнопке **Построитель отчетов** выберите **Сохранить** или **Сохранить как** , чтобы сохранить общий набор данных на сервере отчетов.

7.  Для выхода из построителя отчетов выберите **Построитель отчетов**, а затем выберите **Выйти из построителя отчетов**. Для работы с отчетами выберите **Построитель отчетов**и нажмите кнопку **Создать** или **Открыть**.

### <a name="to-set-query-parameter-options"></a>Задание настроек параметров запросов

1.  Откройте построитель отчетов.

2.  Нажмите кнопку **Открыть**.

3.  Перейдите к серверу отчетов и выберите папку общего источника данных.

4.  В раскрывающемся списке поля **Элементы типа**выберите наборы данных (*.rsd).

5.  Выберите общий набор данных, а затем щелкните **Открыть**. Откроется связанный конструктор запросов.

6.  На ленте выберите **Свойства набора данных**.

7.  Нажмите **Параметры**. На этой странице задайте значение по умолчанию для константы или выражения, пометьте параметр как доступный "только для чтения", допускающий значения NULL или имеющий состояние **Не указывать в запросе**. Дополнительные сведения см. в статье [Диалоговое окно "Свойства набора данных" — "Параметры" (построитель отчетов)](../dataset-properties-dialog-box-parameters-report-builder.md).

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]


### <a name="to-create-a-dataset-from-a-sql-server-relational-database"></a>Создание набора данных в реляционной базе данных SQL Server

1.  В области данных отчета щелкните правой кнопкой мыши имя источника данных и выберите команду **Добавить набор данных**. Откроется страница **Запрос** диалогового окна **Свойства набора данных** .

2.  В поле **Имя**введите имя для набора данных или примите имя по умолчанию.

    > [!NOTE]
    >  Имя набора данных используется внутри запроса. В целях упорядочивания рекомендуется называть набор данных именем, описывающим данные, возвращаемые запросом.

3.  В поле **Источник данных**перейдите и выберите существующий общий источник данных либо нажмите кнопку **Создать** , чтобы создать новый внедренный источник данных.

4.  Задайте значение для параметра **Тип запроса** . Параметры зависят от типа источника данных.

    -   Выберите **Текст** для записи запроса, использующего язык запросов источника данных.

    -   Выберите **Таблица** , чтобы возвратить все поля в таблице реляционной базы данных.

    -   Выберите **StoredProcedure** , чтобы выполнить хранимую процедуру по имени.

5.  В поле **Запрос**введите имя запроса,z хранимой процедуры или таблицы. Также можно нажать кнопку **Конструктор запросов** , чтобы открыть графический или текстовый редактор запросов, либо кнопку **Импорт** , чтобы импортировать запрос из существующего отчета.

     В некоторых случаях указанную в запросе коллекцию полей можно определить, выполнив запрос к источнику данных. Например, хранимая процедура может возвратить в результирующем наборе переменный набор полей. Нажмите кнопку **Обновить поля** , чтобы выполнить запрос к источнику данных и получить имена полей, необходимые для заполнения коллекции полей набора данных в области данных отчета. Коллекция полей появится в узле набора данных после того, как диалоговое окно **Свойства набора данных** будет закрыто.

6.  В поле **Время ожидания**введите, сколько секунд сервер отчетов должен ждать ответа базы данных. Значение по умолчанию — 0 секунд. Если значение времени ожидания равно 0 секунд, то время ожидания запроса не будет ограничено.

7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     Набор данных и его коллекция полей появляются в области данных отчета под узлом источника данных.

## <a name="see-also"></a>См. также:
 [Внедренные и общие наборы данных отчетов &#40;построитель отчетов и службы ssrs&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [коллекции полей набора строк &#40;построитель отчетов и SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [конструкторы запросов &#40;](../query-designers-report-builder.md) построитель отчетов&#41;[Справка по диалоговым окнам, панелям и мастерам](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Добавление данных в отчет построитель отчетов &#40;и SSRS построитель отчетов подключения к](report-datasets-ssrs.md) [данным, источники данных и строки подключения в&#41;](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [внедренных и общих наборах данных построитель отчетов &#40;и SSRS](embedded-and-shared-datasets-report-builder-and-ssrs.md) построитель отчетов

