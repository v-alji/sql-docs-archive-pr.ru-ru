---
title: Проектирование хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services], designing
- dependent assemblies [Analysis Services]
- assemblies [Analysis Services]
ms.assetid: af4e7bd5-041b-4a40-9942-0ef6a3af46c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 42b33873d6bdf28f7f702bcf186d681f57d6024d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732161"
---
# <a name="designing-stored-procedures"></a><span data-ttu-id="d5643-102">Конструирование хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="d5643-102">Designing Stored Procedures</span></span>
  <span data-ttu-id="d5643-103">В хранимых процедурах доступны как административная объектная модель объектов AMO, так и ориентированная на клиентов объектная модель объектов [!INCLUDE[msCoName](../../includes/msconame-md.md)] ADO Multidimensional.</span><span class="sxs-lookup"><span data-stu-id="d5643-103">Both the administrative object model Analysis Management Objects (AMO) and the client oriented object model [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® Data Objects (Multidimensional) (ADO MD) are available in stored procedures.</span></span>  
  
 <span data-ttu-id="d5643-104">Для возможности вызова хранимые процедуры должны быть в области (сервер или база данных), видимой на уровне многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="d5643-104">Stored procedures must be in scope (either the server or the database) to be visible at the Multidimensional Expressions (MDX) level to be called.</span></span> <span data-ttu-id="d5643-105">Однако после вызова хранимой процедуры ее область не ограничивается действиями под своим родителем.</span><span class="sxs-lookup"><span data-stu-id="d5643-105">However, once a stored procedure is invoked, its scope is not limited to actions under its parent.</span></span> <span data-ttu-id="d5643-106">Хранимая процедура может вносить изменения или правки в любом месте сервера при условии соблюдения ограничений безопасности, налагаемых вызывающим пользовательским процессом, или ограничений транзакции, в составе которой такая процедура функционирует.</span><span class="sxs-lookup"><span data-stu-id="d5643-106">A stored procedure may make changes or modifications anywhere on the server, subject only to the security limitations of the user process that invokes it or to the limitations of the transaction in which it is operating.</span></span>  
  
 <span data-ttu-id="d5643-107">Процедуры серверной области доступны во всех контекстах на сервере.</span><span class="sxs-lookup"><span data-stu-id="d5643-107">Server scope procedures are available in all contexts on the server.</span></span> <span data-ttu-id="d5643-108">Хранимые процедуры области базы данных видимы только в контексте базы данных, в которой они определены.</span><span class="sxs-lookup"><span data-stu-id="d5643-108">Database scope stored procedures are visible only in the database context of the database in which they are defined.</span></span>  
  
 <span data-ttu-id="d5643-109">Как и любая другая функция многомерных выражений, хранимая процедура должна быть разрешена до продолжения сеанса многомерных выражений. Во время выполнения хранимые процедуры блокируют сеансы многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="d5643-109">As with any MDX function, stored procedure must be resolved before an MDX session can continue; stored procedures lock MDX sessions while executing.</span></span> <span data-ttu-id="d5643-110">Если не существует конкретной причины для остановки сеанса многомерных выражений в ожидании пользовательского взаимодействия, то пользовательские взаимодействия (например, диалоговые окна) не рекомендуются. </span><span class="sxs-lookup"><span data-stu-id="d5643-110">Unless a specific reason exists to halt an MDX session pending user interaction, then user interactions (such as dialog boxes) are discouraged.</span></span>  
  
## <a name="dependent-assemblies"></a><span data-ttu-id="d5643-111">Зависимые сборки</span><span class="sxs-lookup"><span data-stu-id="d5643-111">Dependent Assemblies</span></span>  
 <span data-ttu-id="d5643-112">Все зависимые сборки должны быть загружены в экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], чтобы их обнаружила среда CLR.</span><span class="sxs-lookup"><span data-stu-id="d5643-112">All dependent assemblies must be loaded into an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to be found by the common language runtime (CLR).</span></span> <span data-ttu-id="d5643-113">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] хранят зависимые сборки в папке главной сборки, так что среда CLR автоматически разрешает все ссылки на функции в этих сборках.</span><span class="sxs-lookup"><span data-stu-id="d5643-113">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stores the dependent assemblies in the same folder as the main assembly, so the CLR automatically resolves all function references to functions in those assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5643-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5643-114">See Also</span></span>  
 <span data-ttu-id="d5643-115">[Управление сборками многомерной модели](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="d5643-115">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="d5643-116">Определение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="d5643-116">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
