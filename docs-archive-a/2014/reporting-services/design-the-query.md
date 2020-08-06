---
title: Создать запрос | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735094"
---
# <a name="design-the-query"></a>Создание запроса
  На этой странице мастера отчетов можно создать запрос: ввести его вручную, воспользоваться построителем запросов для интерактивного создания запроса или импортировать запрос из другого отчета.  
  
 Какие именно запросы могут быть введены на этой странице, зависит от выбора типа источника данных на странице «Выбор источника данных» (на предыдущей странице мастера отчетов). Например, если тип источника данных — [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , можно ввести [!INCLUDE[tsql](../includes/tsql-md.md)] инструкции или имена хранимых процедур. Если тип источника данных — [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , панель запросов отключается, и нельзя вводить запрос напрямую. Задать запрос можно только при помощи построителя запросов.  
  
## <a name="options"></a>Варианты  
 **Строка запроса**  
 Введите запрос получения данных, которые будут использованы в отчете.  
  
 **Построитель запросов**  
 Нажмите кнопку **Построитель запросов** , чтобы открыть конструктор запросов применительно к источнику данных, либо импортировать запрос из другого отчета.  
  
 Дополнительные сведения о конструкторах запросов см. в разделе [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).  
  
## <a name="example"></a>Пример  
 Для типа источника данных **Microsoft SQL Server**следующий запрос получает список фамилий из [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] таблицы базы данных `Person` .  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 Для типа источника данных **Microsoft SQL Server**следующий запрос выполняет [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] хранимую процедуру `uspGetEmployeeManagers` для сотрудника с идентификационным номером 1:  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a>См. также:  
 [Справка мастера отчетов](../../2014/reporting-services/report-wizard-help.md)   
 [Внедренные и общие наборы данных отчета &#40;построитель отчетов и службы SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)   
 [Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-data/report-datasets-ssrs.md)  
  
  
