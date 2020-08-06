---
title: Развертывание модуля обработки данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: e5c0b5a9-1386-47cb-aade-96653ecfaa54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84fc2d2853ce7a6aae77f313ef0f4026ad2f35cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750503"
---
# <a name="deploying-a-data-processing-extension"></a>Развертывание модуля обработки данных
  После создания модуля обработки данных для служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] и компиляции его в библиотеку [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] необходимо сделать модуль доступным для обнаружения сервером отчетов и конструктором отчетов. Для этого нужно просто скопировать модуль в соответствующие каталоги и добавить записи в соответствующие файлы конфигурации служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].  
  
## <a name="configuration-file-extension-element"></a>Элемент Extension в файле конфигурации  
 Модули обработки данных, развертываемые на сервере отчетов или в конструкторе отчетов, необходимо вставить в файлы конфигурации в виде элементов **Extension**. Для сервера отчетов используется файл RSReportServer.config, а для конструктора отчетов — файл RSReportDesigner.config.  
  
 В следующей таблице описаны атрибуты элемента **Extension** для модулей обработки данных.  
  
|attribute|Description|  
|---------------|-----------------|  
|`Name`|Уникальное имя модуля, например «SQL» для модуля обработки данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или «OLEDB» для модуля обработки данных OLE DB. Длина атрибута `Name` не должна превышать 255 символов. Имя должно быть уникальным среди всех элементов, вложенных в элемент **Extension** файла конфигурации.|  
|`Type`|Список с разделителями-запятыми, содержащий полное пространство имен и имя сборки.|  
|`Visible`|Значение `false` показывает, что модуль обработки данных не должен отображаться в пользовательском интерфейсе. Если атрибут не указан, по умолчанию используется значение `true`.|  
  
 Дополнительные сведения о файлах RSReportServer.config и RSReportDesigner.config см. в разделе [Файлы конфигурации служб Reporting Services](../../report-server/reporting-services-configuration-files.md).  
  
## <a name="in-this-section"></a>в этом разделе  
  
|Раздел|Описание|  
|-----------|-----------------|  
|[Руководство. Развертывание модуля обработки данных на сервере отчетов](deploying-a-data-processing-extension-to-a-report-server.md)|Описывает развертывание модуля обработки данных на сервере отчетов.|  
|[Руководство. Развертывание модуля обработки данных в конструкторе отчетов](deploying-a-data-processing-extension-to-report-designer.md)|Описывает развертывание модуля обработки данных в конструкторе отчетов.|  
  
## <a name="see-also"></a>См. также:  
 [Расширения Reporting Services](../reporting-services-extensions.md)   
 [Реализация модуля обработки данных](implementing-a-data-processing-extension.md)   
 [Библиотека модулей служб Reporting Services](../reporting-services-extension-library.md)  
  
  
