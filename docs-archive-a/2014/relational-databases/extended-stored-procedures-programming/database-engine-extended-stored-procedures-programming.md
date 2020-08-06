---
title: Программирование расширенных хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- gateway applications [SQL Server]
- extended stored procedures [SQL Server], about extended stored procedures
- Open Data Services [SQL Server]
- ODS [SQL Server]
ms.assetid: 561305cd-c803-48af-9eec-2c19f4d311ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 30792cc2b431e35a8f7df5ff7bbb2c228892d5c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666615"
---
# <a name="programming-extended-stored-procedures"></a><span data-ttu-id="b1e5e-102">Программирование расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="b1e5e-102">Programming Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="b1e5e-103">Используйте вместо этого интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b1e5e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="b1e5e-104">В прошлом службы Open Data Services использовались для создания серверных приложений, таких как шлюзы к СУБД, отличных от SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1e5e-104">In the past, Open Data Services was used to write server applications, such as gateways to non-SQL Server database environments.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="b1e5e-105">не [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает устаревшие части API Open Data Services.</span><span class="sxs-lookup"><span data-stu-id="b1e5e-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support the obsolete portions of the Open Data Services API.</span></span> <span data-ttu-id="b1e5e-106">Единственная часть исходного API-интерфейса служб Open Data Services, все еще поддерживаемая [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], это функции расширенных хранимых процедур, поэтому API-интерфейс был переименован в API-интерфейс расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="b1e5e-106">The only part of the original Open Data Services API still supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are the extended stored procedure functions, so the API has been renamed to the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="b1e5e-107">После возникновения более новых и более мощных технологий, таких как распределенные запросы и интеграция со средой CLR, потребность в приложениях API-интерфейса расширенных хранимых процедур значительно снизилась.</span><span class="sxs-lookup"><span data-stu-id="b1e5e-107">With the emergence of newer and more powerful technologies, such as distributed queries and CLR Integration, the need for Extended Stored Procedure API applications has largely been replaced.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1e5e-108">При наличии существующих приложений шлюзов нельзя использовать библиотеку opends60.dll, поставляемую с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], для запуска приложений.</span><span class="sxs-lookup"><span data-stu-id="b1e5e-108">If you have existing gateway applications, you cannot use the opends60.dll that ships with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run the applications.</span></span> <span data-ttu-id="b1e5e-109">Приложения шлюзов больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b1e5e-109">Gateway applications are no longer supported.</span></span>  
  
## <a name="extended-stored-procedures-vs-clr-integration"></a><span data-ttu-id="b1e5e-110">Расширенные хранимые процедуры и интеграция со средой CLR</span><span class="sxs-lookup"><span data-stu-id="b1e5e-110">Extended Stored Procedures vs. CLR Integration</span></span>  
 <span data-ttu-id="b1e5e-111">В более ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] расширенные хранимые процедуры представляли собой единственный доступный механизм, позволяющий разработчикам баз данных создавать логику на стороне сервера, которую трудно или невозможно написать с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1e5e-111">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], extended stored procedures (XPs) provided the only mechanism that was available for database application developers to write server-side logic that was either hard to express or impossible to write in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b1e5e-112">Интеграция со средой CLR более надежна, чем использование таких хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="b1e5e-112">CLR Integration provides a more robust alternative to writing such stored procedures.</span></span> <span data-ttu-id="b1e5e-113">Более того, благодаря интеграции со средой CLR, логика, ранее создаваемая в виде хранимых процедур, зачастую лучше выражается возвращающими табличные значения функциями, что позволяет выполнять к результатам такой функции запросы в виде инструкций SELECT, внедряя их в предложение FROM.</span><span class="sxs-lookup"><span data-stu-id="b1e5e-113">Furthermore, with CLR Integration, logic that used to be written in the form of stored procedures is often better expressed as table-valued functions, which allow the results constructed by the function to be queried in SELECT statements by embedding them in the FROM clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e5e-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1e5e-114">See Also</span></span>  
 <span data-ttu-id="b1e5e-115">[Общие сведения об интеграции&#41; среды CLR &#40;](../clr-integration/common-language-runtime-integration-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b1e5e-115">[Common Language Runtime &#40;CLR&#41; Integration Overview](../clr-integration/common-language-runtime-integration-overview.md) </span></span>  
 [<span data-ttu-id="b1e5e-116">Функции среды CLR с табличным значением</span><span class="sxs-lookup"><span data-stu-id="b1e5e-116">CLR Table-Valued Functions</span></span>](../clr-integration-database-objects-user-defined-functions/clr-table-valued-functions.md)  
  
  
