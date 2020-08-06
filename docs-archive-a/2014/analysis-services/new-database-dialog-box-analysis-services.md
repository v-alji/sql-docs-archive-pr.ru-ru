---
title: Диалоговое окно «Создание базы данных» (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.newdatabase.f1
ms.assetid: ddc7804b-acb0-4ae4-a88f-e8cdf704c341
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07eeee6136965671b000923dc3f240de06ce0bd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664558"
---
# <a name="new-database-dialog-box-analysis-services"></a>Диалоговое окно «Создание базы данных» (службы Analysis Services)
  Используйте диалоговое окно **Создание базы данных** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для создания новой пустой базы данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] . Чтобы открыть диалоговое окно **Создание базы данных** , щелкните правой кнопкой мыши папку **Базы данных** экземпляра служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в **обозревателе объектов** и выберите команду **Создать базу данных**.  
  
## <a name="options"></a>Варианты  
  
|Термин|Определение|  
|----------|----------------|  
|**Имя базы данных**|Введите имя новой базы данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .|  
|**Использовать указанные имя пользователя и пароль**|Если выбран этот параметр, база данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] будет использовать учетные данные указанной учетной записи пользователя. Заданные учетные данные будут использоваться для обработки данных, запросов ROLAP, внешних привязок, локальных кубов, моделей интеллектуального анализа данных, удаленных секций, связанных объектов и синхронизации цели с источником. Однако для DMX-инструкций OPENQUERY будут использоваться учетные данные текущего пользователя.|  
|**User name**|Домен и имя учетной записи пользователя, которую будет использовать выбранная база данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] . Используйте следующий формат:<br /><br /> *\<Domain name>* **\\** *\<User account name>*<br /><br /> Примечание. Этот параметр доступен только в том случае, если выбран параметр **Использовать указанные имя пользователя и пароль** .|  
|**Пароль**|Пароль для учетной записи пользователя, указанной в поле **Имя пользователя**.|  
|**Использовать учетную запись службы**|Если выбран этот параметр, база данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] будет использовать учетные данные, связанные со службами [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , управляющими базой данных. Учетные данные учетной записи службы будут использоваться для обработки данных, запросов ROLAP, удаленных секций, связанных объектов и синхронизации цели с источником. Для DMX-инструкций OPENQUERY, локальных кубов и моделей интеллектуального анализа данных будут использоваться учетные данные текущего пользователя. Этот параметр не поддерживается для внешних привязок.|  
|**Использовать учетные данные текущего пользователя**|Если выбран этот параметр, база данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] будет использовать учетные данные безопасности текущего пользователя для внешних привязок, DMX-инструкций OPENQUERY, локальных кубов и моделей интеллектуального анализа данных. Этот параметр не поддерживается для обработки данных, запросов ROLAP, удаленных секций, связанных объектов и синхронизации цели с источником.|  
|**Default**|Если выбран этот параметр, база данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]будет использовать учетные данные учетной записи пользователя по умолчанию. Этот параметр использует настройки по умолчанию базы данных для обработки объектов, синхронизации серверов и выполнения инструкций интеллектуального анализа данных **Open Query** . Дополнительные сведения об указании параметров по умолчанию на уровне базы данных см. в разделе [Задание свойств многомерной базы данных (службы Analysis Services)](multidimensional-models/set-multidimensional-database-properties-analysis-services.md).<br /><br /> По умолчанию `DataSourceImpersonationInfo` для свойства базы данных задано значение **использовать учетную запись службы**. Независимо от значения свойства `DataSourceImpersonationInfo`, учетные данные текущего пользователя будут использоваться для внешних привязок, запросов ROLAP, локальных кубов и моделей интеллектуального анализа данных.|  
|**Описание**|Введите описание новой базы данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .|  
  
## <a name="see-also"></a>См. также:  
 [Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)   
 [Базы данных многомерных моделей (службы SSAS)](multidimensional-models/multidimensional-model-databases-ssas.md)  
  
  