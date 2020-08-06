---
title: Результирующие наборы OLE-автоматизации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- data types [SQL Server], OLE Automation
- two-dimensional arrays
- one-dimensional arrays
- result sets [SQL Server], OLE Automation
- OLE Automation [SQL Server], result sets
- arrays [SQL Server]
ms.assetid: b2f99e33-2303-427c-94b9-9d55f8e2a6ab
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7c9bdc4d51d989db2d4d676b29e0824c0e5b59a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669383"
---
# <a name="ole-automation-result-sets"></a><span data-ttu-id="50d3e-102">Результирующие наборы OLE-автоматизации</span><span class="sxs-lookup"><span data-stu-id="50d3e-102">OLE Automation Result Sets</span></span>
  <span data-ttu-id="50d3e-103">Если свойство или метод OLE-автоматизации возвращает данные в одномерный или двухмерный массив, то массив возвращается клиенту как результирующий набор следующего вида.</span><span class="sxs-lookup"><span data-stu-id="50d3e-103">If an OLE Automation property or method returns data in an array with one or two dimensions, the array is returned to the client as a result set:</span></span>  
  
-   <span data-ttu-id="50d3e-104">Одномерный массив возвращается клиенту как результирующий набор, состоящий из одной строки, в которой число столбцов соответствует количеству элементов массива.</span><span class="sxs-lookup"><span data-stu-id="50d3e-104">A one-dimensional array is returned to the client as a single-row result set with as many columns as there are elements in the array.</span></span> <span data-ttu-id="50d3e-105">Например, массив array(10) возвращается как одна строка с 10 столбцами.</span><span class="sxs-lookup"><span data-stu-id="50d3e-105">For example, an array(10) is returned as a single row of 10 columns.</span></span>  
  
-   <span data-ttu-id="50d3e-106">Двумерный массив возвращается клиенту в виде результирующего набора с числом столбцов, равным числу элементов первого измерения массива, и числом строк, равным числу элементов второго измерения массива.</span><span class="sxs-lookup"><span data-stu-id="50d3e-106">A two-dimensional array is returned to the client as a result set with as many columns as there are elements in the first dimension of the array and with as many rows as there are elements in the second dimension of the array.</span></span> <span data-ttu-id="50d3e-107">Например, массив array(2,3) возвращается как 2 столбца в 3 строках.</span><span class="sxs-lookup"><span data-stu-id="50d3e-107">For example, an array(2,3) is returned as 2 columns in 3 rows.</span></span>  
  
 <span data-ttu-id="50d3e-108">Если значение возвращаемого свойства или метода является массивом, процедура sp_OAGetProperty или sp_OAMethod возвращает результирующий набор клиенту.</span><span class="sxs-lookup"><span data-stu-id="50d3e-108">When a property return value or method return value is an array, sp_OAGetProperty or sp_OAMethod returns a result set to the client.</span></span> <span data-ttu-id="50d3e-109">(Выходные параметры метода не могут быть массивами.) Эти процедуры просматривают все значения в массиве для определения подходящих типов данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и их длин для каждого столбца результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="50d3e-109">(Method output parameters cannot be arrays.) These procedures scan all the data values in the array to determine the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and data lengths to use for each column in the result set.</span></span> <span data-ttu-id="50d3e-110">Для каждого отдельного столбца эти процедуры используют тип и длину данных, необходимые для представления всех значений данных этого столбца.</span><span class="sxs-lookup"><span data-stu-id="50d3e-110">For a particular column, these procedures use the data type and length required to represent all data values in that column.</span></span>  
  
 <span data-ttu-id="50d3e-111">Если все значения данных в столбце имеют один и тот же тип данных, этот тип используется для всего столбца.</span><span class="sxs-lookup"><span data-stu-id="50d3e-111">When all data values in a column share the same data type, that data type is used for the whole column.</span></span> <span data-ttu-id="50d3e-112">Когда значения данных в столбце принадлежат к различным типам данных, тип данных всего столбца определяется, как указано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="50d3e-112">When data values in a column are different data types, the data type of the whole column is chosen based on the following table.</span></span> <span data-ttu-id="50d3e-113">В следующей таблице определите положение одного типа данных на оси строк слева и другого типа данных на оси столбцов сверху.</span><span class="sxs-lookup"><span data-stu-id="50d3e-113">To use the following table, find one data type along the left row axis and a second data type along the top column axis.</span></span> <span data-ttu-id="50d3e-114">В пересечении строки и столбца описывается тип данных столбца результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="50d3e-114">The intersection of the row and column describes the data type of the result set column.</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
||`int`|`float`|`money`|`datetime`|`varchar`|`nvarchar`|  
|`int`|`int`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`float`|`float`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`money`|`money`|`money`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`datetime`|`varchar`|`varchar`|`varchar`|`datetime`|`varchar`|`nvarchar`|  
|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`nvarchar`|  
|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|  
  
## <a name="related-content"></a><span data-ttu-id="50d3e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="50d3e-115">Related Content</span></span>  
 [<span data-ttu-id="50d3e-116">Хранимые процедуры OLE-автоматизации (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="50d3e-116">OLE Automation Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/ole-automation-stored-procedures-transact-sql)  
  
 [<span data-ttu-id="50d3e-117">Параметр конфигурации сервера «Ole Automation Procedures»</span><span class="sxs-lookup"><span data-stu-id="50d3e-117">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
  
