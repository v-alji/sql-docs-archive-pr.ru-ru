---
title: Упреждающее кэширование (диалоговое окно "Свойства секции") (SSMS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.partitionproperties.proactivecaching.f1
ms.assetid: ecba72a3-703f-4ede-9d85-9a3318a749e5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8dae559ad1229407ca39744e52d8ee6842069075
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750267"
---
# <a name="proactive-caching-partition-properties-dialog-box-ssms"></a>Упреждающее кэширование (диалоговое окно «Свойства секции») (среда SSMS)
  Страница **Упреждающее кэширование** диалогового окна **Свойства секции** среды SQL Server Management Studio позволяет устанавливать свойства хранения и упреждающего кэширования секции в группе мер для куба в базе данных служб [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .  
  
## <a name="options"></a>Варианты  
 **Стандартные настройки**  
 Выберите, чтобы задействовать ползунок **Стандартные настройки** и использовать предопределенные настройки режима хранения и возможностей упреждающего кэширования.  
  
 **Стандартные настройки**  
 Установите на одно из предопределенных значений, перечисленных в следующей таблице.  
  
|Параметр|Описание|  
|-------------|-----------------|  
|**ROLAP в реальном времени**|Выберите, чтобы использовать следующие параметры хранения и упреждающего кэширования:<br /><br /> Режим хранения ROLAP.<br /><br /> Включает упреждающее кэширование.<br /><br /> Удаляет устаревшие данные из кэш-памяти с периодом задержки в 0 секунд.<br /><br /> Немедленно переводит объект в режим в сети.|  
|**HOLAP в реальном времени**|Выберите, чтобы использовать следующие параметры хранения и упреждающего кэширования:<br /><br /> Режим хранения HOLAP.<br /><br /> Включает упреждающее кэширование.<br /><br /> Удаляет устаревшие данные из кэш-памяти с периодом задержки в 0 секунд.<br /><br /> Обновляет содержимое кэш-памяти при изменении данных с интервалом бездействия в 0 секунд и без интервала прерывания бездействия.<br /><br /> Немедленно переводит объект в режим в сети.|  
|**MOLAP с небольшой задержкой**|Выберите, чтобы использовать следующие параметры хранения и упреждающего кэширования:<br /><br /> Режим хранения MOLAP.<br /><br /> Включает упреждающее кэширование.<br /><br /> Сбрасывает устаревший кэш с периодом задержки в 30 минут.<br /><br /> Обновляет кэш при изменении данных с интервалом бездействия в 10 секунд и интервалом прерывания бездействия в 10 минут.<br /><br /> Обновляет кэш при изменении данных с интервалом бездействия в 10 секунд и интервалом прерывания бездействия в 10 минут.<br /><br /> Немедленно переводит объект в режим в сети.|  
|**MOLAP со средней задержкой**|Немедленное Усебрингс объекта в режим «в сети».<br /><br /> следующие параметры хранения и упреждающего кэширования:<br /><br /> Режим хранения MOLAP.<br /><br /> Включает упреждающее кэширование.<br /><br /> Сбрасывает устаревший кэш с периодом задержки в 4 часа.<br /><br /> Обновляет кэш при изменении данных с интервалом бездействия в 10 секунд и интервалом прерывания бездействия в 10 минут.<br /><br /> Немедленно переводит объект в режим в сети.|  
|**Автоматический MOLAP**|Выберите, чтобы использовать следующие параметры хранения и упреждающего кэширования:<br /><br /> Режим хранения MOLAP.<br /><br /> Включает упреждающее кэширование.<br /><br /> Обновляет содержимое кэш-памяти при изменении данных с интервалом бездействия в 0 секунд и без интервала прерывания бездействия.|  
|**Запланированный MOLAP**|Выберите, чтобы использовать следующие параметры хранения и упреждающего кэширования:<br /><br /> Режим хранения MOLAP<br /><br /> Разрешить упреждающее кэширование<br /><br /> Периодически обновляет кэш с интервалом перестроения в 1 день|  
|**MOLAP**|Выберите, чтобы использовать следующие параметры хранения и упреждающего кэширования:<br /><br /> Режим хранения MOLAP.|  
  
 **Пользовательские настройки**  
 Выберите, чтобы явно установить параметры режима хранения, упреждающего кэширования и уведомлений.  
  
 **Параметры**  
 Щелкните, чтобы вывести диалоговое окно **Параметры хранилища** и явно задать параметры режима хранения, упреждающего кэширования и уведомлений. Дополнительные сведения о диалоговом окне **Параметры хранилища** см. в разделе [Диалоговое окно "Параметры хранилища" (службы Analysis Services — многомерные данные)](storage-options-dialog-box-analysis-services-multidimensional-data.md).  
  
## <a name="see-also"></a>См. также:  
 [Упреждающее кэширование &#40;секций&#41;](multidimensional-models-olap-logical-cube-objects/partitions-proactive-caching.md)   
 [Диалоговое окно «Свойства секции» &#40;SSMS&#41;](partition-properties-dialog-box-ssms.md)   
 [Диалоговое окно «Выбор &#40;свойств секции»&#41; &#40;SSMS&#41;](selection-partition-properties-dialog-box-ssms.md)   
 [Диалоговое окно "Общие &#40;свойства секции"&#41; &#40;SSMS&#41;](general-partition-properties-dialog-box-ssms.md)   
 [Конфигурация ошибок при обработке кубов, секций и измерений &#40;SSAS — многомерные&#41;](multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md)  
  
  