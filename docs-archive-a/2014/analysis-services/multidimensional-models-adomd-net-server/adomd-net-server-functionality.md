---
title: Функции сервера ADOMD.NET | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- functionality [ADOMD.NET]
- ADOMD.NET, functionality
ms.assetid: b74c6957-3f64-4e09-aa09-d06ee93f82fa
author: minewiskan
ms.author: owend
ms.openlocfilehash: f00215c6bcc0104c920be29e0837288a469b252e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728918"
---
# <a name="adomdnet-server-functionality"></a><span data-ttu-id="e6c56-102">Функциональные возможности сервера ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="e6c56-102">ADOMD.NET Server Functionality</span></span>
  <span data-ttu-id="e6c56-103">Все серверные объекты ADOMD.NET предоставляют доступ только для чтения к данным и метаданным на сервере.</span><span class="sxs-lookup"><span data-stu-id="e6c56-103">All ADOMD.NET server objects provide read-only access to the data and metadata on the server.</span></span> <span data-ttu-id="e6c56-104">Чтобы извлечь данные и метаданные, необходимо использовать модель серверных объектов ADOMD.NET, поскольку модель серверных объектов не поддерживает наборы строк схемы.</span><span class="sxs-lookup"><span data-stu-id="e6c56-104">To retrieve data and metadata, you use the ADOMD.NET server object model as the server object model does not support schema rowsets.</span></span>  
  
 <span data-ttu-id="e6c56-105">С помощью объектов ADOMD.NET Server можно создать определяемую пользователем функцию (UDF) или хранимую процедуру для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6c56-105">With ADOMD.NET server objects, you can create a user defined function (UDF) or a stored procedure for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e6c56-106">Эти внутрипроцессные методы вызываются при помощи инструкций запроса, создаваемых на таких языках, как MDX, DMX или SQL.</span><span class="sxs-lookup"><span data-stu-id="e6c56-106">These in-process methods are called through query statements created in languages such as Multidimensional Expressions (MDX), Data Mining Extensions (DMX), or SQL.</span></span> <span data-ttu-id="e6c56-107">Кроме того, эти внутрипроцессные методы обеспечивают дополнительные возможности без задержек, связанных с обменом данными по сети.</span><span class="sxs-lookup"><span data-stu-id="e6c56-107">These in-process methods also provide added functionality without the latencies associated with network communications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6c56-108">Объект [Microsoft. AnalysisServices. того объектная AdomdServer. AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) поддерживает только расширения интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="e6c56-108">The [Microsoft.AnalysisServices.AdomdServer.AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) object only supports DMX.</span></span>  
  
## <a name="what-is-a-udf"></a><span data-ttu-id="e6c56-109">Что такое определяемая пользователем функция?</span><span class="sxs-lookup"><span data-stu-id="e6c56-109">What is a UDF?</span></span>  
 <span data-ttu-id="e6c56-110">*UDF* — это метод, который имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="e6c56-110">A *UDF* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="e6c56-111">Определяемую пользователем функцию можно вызывать в контексте запроса.</span><span class="sxs-lookup"><span data-stu-id="e6c56-111">You can call the UDF in the context of a query.</span></span>  
  
-   <span data-ttu-id="e6c56-112">Определяемая пользователем функция может принимать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="e6c56-112">The UDF can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="e6c56-113">Определяемая пользователем функция может возвращать различные типы данных.</span><span class="sxs-lookup"><span data-stu-id="e6c56-113">The UDF can return various types of data.</span></span>  
  
 <span data-ttu-id="e6c56-114">Следующий пример иллюстрирует применение вымышленной определяемой пользователем функции, `FinalSalesNumber`.</span><span class="sxs-lookup"><span data-stu-id="e6c56-114">The following example uses the fictional UDF, `FinalSalesNumber`:</span></span>  
  
```  
SELECT SalesPerson.Name ON ROWS,  
       FinalSalesNumber() ON COLUMNS  
FROM SalesModel  
```  
  
## <a name="what-is-a-stored-procedure"></a><span data-ttu-id="e6c56-115">Что такое хранимая процедура?</span><span class="sxs-lookup"><span data-stu-id="e6c56-115">What is a Stored Procedure?</span></span>  
 <span data-ttu-id="e6c56-116">*Хранимая процедура* — это метод, который имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="e6c56-116">A *stored procedure* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="e6c56-117">Вы вызываете хранимую процедуру самостоятельно с помощью инструкции MDX [Call](/sql/mdx/mdx-data-manipulation-call) .</span><span class="sxs-lookup"><span data-stu-id="e6c56-117">You call a stored procedure on its own with the MDX [CALL](/sql/mdx/mdx-data-manipulation-call) statement.</span></span>  
  
-   <span data-ttu-id="e6c56-118">Хранимая процедура может принимать любое количество параметров.</span><span class="sxs-lookup"><span data-stu-id="e6c56-118">A stored procedure can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="e6c56-119">Хранимая процедура может возвращать набор данных, модуль `IDataReader` или пустой результат.</span><span class="sxs-lookup"><span data-stu-id="e6c56-119">A stored procedure can return a dataset, an `IDataReader`, or an empty result.</span></span>  
  
 <span data-ttu-id="e6c56-120">В следующем примере используется вымышленная хранимая процедура, `FinalSalesNumbers`:</span><span class="sxs-lookup"><span data-stu-id="e6c56-120">The following example uses the fictional stored procedure, `FinalSalesNumbers`:</span></span>  
  
```  
CALL FinalSalesNumbers()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6c56-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6c56-121">See Also</span></span>  
 [<span data-ttu-id="e6c56-122">Программирование сервера ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="e6c56-122">ADOMD.NET Server Programming</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-programming)  
  
  
