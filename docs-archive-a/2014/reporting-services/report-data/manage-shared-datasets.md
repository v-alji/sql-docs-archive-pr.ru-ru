---
title: Управление общими наборами данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2cbb1fa3-959e-4df6-9887-ebc93cc1b686
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 37830ff2c523abe21a9762e17f2b00592435fb31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656169"
---
# <a name="manage-shared-datasets"></a>Управление общими наборами данных
  В службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]общие наборы данных получают данные из общих источников данных, которые подключены к внешним источникам данных. Общий набор данных предоставляет способ совместного использования запроса в целях предоставления согласованного набора данных для нескольких отчетов. Запрос к набору данных может включать параметры набора данных. Общий набор данных можно настроить для кэширования результатов запроса для конкретных сочетаний параметров при первом использовании или по расписанию. Кэширование общего набора данных можно использовать в сочетании с кэшированием отчета и потоками данных отчета в целях управления доступом к источнику данных.  
  
 Общие наборы данных используют только общие источники данных, но не внедренные источники данных. Общий набор данных может быть основан на любом источнике данных для поддерживаемого модуля обработки данных служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] или на модели отчета.  
  
## <a name="creating-and-using-shared-datasets"></a>Создание и использование общих наборов данных  
 Чтобы создать общий набор данных, необходимо использовать приложение, которое создает файл определения общего набора данных (RSD-файл). Для создания общего набора данных можно воспользоваться одним из следующих приложений.  
  
-   Построитель отчетов. Используйте режим конструктора общего набора данных и сохраните общий набор данных на сервере отчетов или на сайте SharePoint.  
  
-   Конструктор отчетов в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] . Создайте общие наборы данных в папке «Общий набор данных» обозревателя решений. Чтобы опубликовать общий набор данных, разверните его на сервере отчетов или на сайте SharePoint.  
  
-   Передача определения общего набора данных (RSD-файла). Можно передать файл на сервер отчетов или на сайт SharePoint. На сайте SharePoint. Переданный файл не проверяется по схеме до тех пор, пока общий набор данных не будет кэширован или использован в отчете.  
  
 Определение общего набора данных включает запрос, параметры набора данных, включая значения по умолчанию, параметры данных, такие как чувствительность к регистру, и фильтры набора данных. Значения, заданные в определении, используются каждый раз при включении общего набора данных в отчет.  
  
 Чтобы использовать общий набор данных в отчете, необходимо открыть приложение, такое как построитель отчетов, перейти на сервер отчетов или на сайт SharePoint и выбрать общий набор данных. При этом экземпляр общего набора данных добавляется в отчет. Нельзя просматривать или изменять запрос или общий источник данных для общего набора данных в отчете. Можно указать дополнительный набор значений свойств набора данных, которые применяются к экземпляру в отчете. Например, можно добавить фильтр или изменить параметры данных, такие как чувствительность к регистру. Дополнительные сведения см. в разделе [Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) в [документации по построителю отчетов](https://go.microsoft.com/fwlink/?LinkId=154494) на сайте msdn.microsoft.com.  
  
## <a name="managing-shared-datasets"></a>Управление общими наборами данных  
 Управление опубликованным общим набором данных производится при помощи диспетчера отчетов для сервера отчетов, работающего в собственном режиме, или страницы приложения на сайте SharePoint, если сервер отчетов развернут в режиме интеграции с SharePoint. Задачи, которые могут быть выполнены пользователем применительно к общему набору данных, зависят от его назначений ролей и от разрешений на уровне сайта и уровня элемента, в том числе от разрешений для доступа к папке, если включено наследование разрешений. Безопасность на уровне элементов для общих наборов данных следует той же модели, что и безопасность на уровне элементов для отчетов. Дополнительные сведения см. в разделе [Защита элементов общего набора данных](../security/secure-shared-dataset-items.md).  
  
 Можно управлять свойствами элемента общего набора данных, включая предназначенный для использования общий источник данных, независимо из отчета, в котором используется общий набор данных или общий источник данных, от которого он зависит. Чтобы изменить запрос или другие свойства набора данных, которые являются частью определения общего набора данных, необходимо изменить само определение.  
  
### <a name="manage-shared-dataset-item-properties"></a>Управление свойствами элемента общего набора данных  
 Свойства элемента общего набора данных, которые могут быть изменены, перечислены в следующей таблице.  
  
|||  
|-|-|  
|Изменение имени|Изменение имени общего набора данных. Все ссылки от зависимых элементов продолжат работать.|  
|Изменение описания|Изменение описания общего набора данных.|  
|Истечение времени ожидания выполнения запроса|Устанавливается время ожидания выполнения запроса в секундах. Величина в нуль (0) секунд означает отсутствие времени ожидания. Определяет количество секунд до завершения запроса к набору данных по истечению времени ожидания. Чтобы указать на отсутствие времени ожидания, укажите 0. Дополнительные сведения см. в разделе [Задание значений времени ожидания при обработке отчетов и общих наборов данных (SSRS)](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md).|  
|Просмотр зависимых элементов|Служит для просмотра элементов, использующих этот общий набор данных: опубликованные элементы отчетов, общие источники данных и отчеты.|  
  
 Следующие дополнительные свойства общего набора данных настраиваются автоматически.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|HasDataSourceCredentials|Указывает, имеет ли связанный общий источник данных учетные данные, хранящиеся на сервере отчетов.|  
|HasUserProfileDependencies|Указывает, содержит ли отчет ссылку на пользовательскую глобальную коллекцию в своем запросе или в выражениях фильтра.|  
  
## <a name="viewing-or-changing-the-shared-dataset-definition"></a>Просмотр или изменение определения общего набора данных  
 Определение общего набора данных включает свойства общего набора данных, в том числе запрос, параметры набора данных, значения по умолчанию, фильтры набора данных и такие параметры данных, как параметры сортировки и чувствительности к регистру. При наличии достаточных разрешений пользователь может просматривать и изменять это определение.  
  
 Чтобы просмотреть или изменить определение общего набора данных, измените общий набор данных в режиме конструктора общего набора данных в таком приложении, как построитель отчетов. После внесения изменений сохраните определение общего набора данных на сервере или на сайте.  
  
 Еще один способ просмотра определения общего набора данных в виде XML-кода состоит в использовании синтаксиса доступа через URL-адрес в диспетчере отчетов. Например, чтобы просмотреть значения по умолчанию для каждого параметра набора данных, можно применить следующую команду доступа через URL-адрес для отображения определения общего набора данных с именем DataSet1 с сервера отчетов:  
  
```  
http://localhost/reportserver/?/DataSet1&rs:command=GetShareddatasetDefinition  
```  
  
## <a name="controlling-access-to-the-shared-dataset-definition"></a>Управление доступом к определению общего набора данных  
 По умолчанию следующие задачи применяются к операциям на общих наборах данных.  
  
-   **Просмотр отчетов.** Просмотр элементов общего набора данных и свойств элементов.  
  
-   **Использование отчетов.** Чтение определений общего набора данных.  
  
-   **Управление отчетами.** Создание и удаление общих наборов данных и изменение свойств общего набора данных.  
  
-   **Установка безопасности элементов.** Просмотр и изменение параметров безопасности для общих наборов данных.  
  
 Дополнительные сведения о том, какие задачи и разрешения управляют доступом к свойствам источников данных на сервере отчетов, работающем в собственном режиме, см. в разделе [Защита элементов общего набора данных](../security/secure-shared-dataset-items.md).  
  
 Разрешения на просмотр и изменение свойств элементов в библиотеке SharePoint определяются администратором сайта. Дополнительные сведения см. в разделе [Справочная таблица по разрешениям на сайты SharePoint и списки для элементов сервера отчетов](../security/sharepoint-site-and-list-permission-reference-for-report-server-items.md).  
  
## <a name="how-to-work-with-shared-dataset-properties-on-a-report-server"></a>Как работать со свойствами общего набора данных на сервере отчетов  
 Для работы с общими наборами данных можно использовать ряд средств. В следующей таблице приведено краткое описание подходов и средств со ссылками на дополнительные инструкции.  
  
|Задача|Инструмент|Ссылка|  
|----------|----------|----------|  
|Добавление общего набора данных или изменение свойств определения общего набора данных.|Сохранение в построителе отчетов.<br /><br /> Развертывание в конструкторе отчетов.<br /><br /> Передача RSD-файла в диспетчере отчетов|[Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) в [документации по построителю отчетов](https://go.microsoft.com/fwlink/?LinkId=154494) на сайте msdn.microsoft.com.<br /><br /> [Страница "Передача файла" (диспетчер отчетов)](../upload-file-page-report-manager.md)<br /><br /> Если передача общего набора данных осуществляется перед публикацией общего источника данных, от которого он зависит, то необходимо вручную связать общий набор данных с общим источником данных. Дополнительные сведения см. в разделе [Страница "Общие свойства" — "Общие наборы данных" (диспетчер отчетов)](../general-properties-page-shared-datasets-report-manager.md).|  
|Изменение свойств элемента общего набора данных.|Диспетчер отчетов|[Страница "Общие свойства" — "Общие наборы данных" (диспетчер отчетов)](../general-properties-page-shared-datasets-report-manager.md)|  
|Указание дополнительных свойств общего набора данных для экземпляра общего набора данных в отчете.|Конструктор отчетов построителя отчетов|[Диалоговое окно «Свойства набора данных» — «Запрос»](../dataset-properties-dialog-box-query.md)|  
|Привязка к другому общему источнику данных для общего набора данных.|Диспетчер отчетов|[Страница "Выбор источника данных" (диспетчер отчетов)](../data-source-selection-page-report-manager.md)|  
|Проверка значений по умолчанию для параметров набора данных.|Открытие в построителе отчетов или использование синтаксиса доступа через URL-адрес.|Пример:<br /><br /> `http://localhost/reportserver/?/DataSet1&rs:command=GetShareddatasetDefinition`|  
|Включение кэширования|Диспетчер отчетов|[Общие наборы данных в кэше (службы SSRS)](../report-server/cache-shared-datasets-ssrs.md)<br /><br /> [Страница "Кэширование", "Общие наборы данных" (диспетчер отчетов)](../caching-page-shared-datasets-report-manager.md)|  
|Создание или изменение плана обновления кэша|Диспетчер отчетов|[Параметры обновления кэша (диспетчер отчетов)](../cache-refresh-options-report-manager.md)|  
|Просмотр схемы определения общего набора данных.|Диспетчер отчетов|`http://<reportserver>/shareddatasetdefinition.xsd`|  
|В режиме интеграции с SharePoint синхронизация определения общего набора данных между сервером отчетов и сайтом SharePoint|Страницы приложения SharePoint|Изменение свойств элемента общего набора данных<br /><br /> Изменение параметров кэша<br /><br /> Изменение общего источника данных|  
  
## <a name="comparing-shared-datasets-with-other-report-server-items"></a>Сравнение общих наборов данных с другими элементами сервера отчетов  
 При управлении несколькими типами элементов на сервере отчетов это помогает понять, в чем элементы схожи и чем они отличаются от других элементов сервера отчетов.  
  
 Общие наборы данных похожи на общие источники данных и отчеты в следующих аспектах.  
  
-   Как и общие источники данных, общие наборы данных управляются независимо от отчетов, в которых они используются. Частью управления общим набором данных на сервере отчетов является возможность сменить общий источник данных, от которого зависит этот набор данных, не меняя определение общего набора данных.  
  
-   Как и отчеты, общие наборы данных могут кэшироваться. Учетные данные, которые требуются для источника данных, должны соответствовать ограничениям кэширования, и для каждого параметра должны быть указаны значения по умолчанию. Дополнительные сведения см. в разделе [Общие наборы данных в кэше (службы SSRS)](../report-server/cache-shared-datasets-ssrs.md).  
  
-   Как и в отчетах, каждый раз, когда происходит обработка, используется текущее определение элемента на сервере отчетов. Если в общий набор данных внесены изменения, то при обработке каждого отчета, использующего этот набор данных, будет использоваться его текущее определение на сервере отчетов. Если для общего набора данных включено кэширование и внесены изменения в определение общего набора данных, то эти изменения не используются до истечения срока действия данных в кэше. Чтобы обеспечить предоставление согласованного набора данных для нескольких отчетов, можно использовать планы обновления кэша.  
  
 Общие наборы данных отличаются от опубликованных элементов отчетов в следующих аспектах.  
  
-   В отличие от опубликованных элементов отчета, изменения в определении общего набора данных на сервере отчетов не активизируют уведомления об обновлениях при открытии отчета в клиенте разработки отчетов. При запуске отчета используются данные из текущего определения общего набора данных на сервере отчетов.  
  
 Общие наборы данных схожи с подписками в следующих аспектах.  
  
-   В общих наборах данных для кэширования могут использоваться расписания элементов и общие расписания.  
  
-   Общие наборы данных следуют тем же правилам указания значений параметров, что и подписки.  
  
## <a name="see-also"></a>См. также  
 [Управление содержимым сервера отчетов (службы Reporting Services в основном режиме)](../report-server/report-server-content-management-ssrs-native-mode.md)   
 [Предоставление разрешений на сервер отчетов в собственном режиме](../security/granting-permissions-on-a-native-mode-report-server.md)  
  
  