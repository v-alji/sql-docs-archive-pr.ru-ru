---
title: Результаты сообщения SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], SQL Server message results
- OLE DB error handling, SQL Server message results
ms.assetid: 6663c6f9-def1-4d9e-845b-2085e5efc401
author: rothja
ms.author: jroth
ms.openlocfilehash: aa63445b81ec89b87523fa29c50817e128d48515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667056"
---
# <a name="sql-server-message-results"></a><span data-ttu-id="42b4f-102">Результаты сообщения SQL Server</span><span class="sxs-lookup"><span data-stu-id="42b4f-102">SQL Server Message Results</span></span>
  <span data-ttu-id="42b4f-103">Следующие [!INCLUDE[tsql](../../includes/tsql-md.md)] инструкции не создают [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственные наборы строк поставщика OLE DB клиента или число затронутых строк при выполнении:</span><span class="sxs-lookup"><span data-stu-id="42b4f-103">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements do not generate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets or a count of affected rows when executed:</span></span>  
  
-   <span data-ttu-id="42b4f-104">PRINT</span><span class="sxs-lookup"><span data-stu-id="42b4f-104">PRINT</span></span>  
  
-   <span data-ttu-id="42b4f-105">RAISERROR (со степенью серьезности 10 или ниже)</span><span class="sxs-lookup"><span data-stu-id="42b4f-105">RAISERROR with a severity of 10 or lower</span></span>  
  
-   <span data-ttu-id="42b4f-106">DBCC</span><span class="sxs-lookup"><span data-stu-id="42b4f-106">DBCC</span></span>  
  
-   <span data-ttu-id="42b4f-107">SET SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="42b4f-107">SET SHOWPLAN</span></span>  
  
-   <span data-ttu-id="42b4f-108">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="42b4f-108">SET STATISTICS</span></span>  
  
 <span data-ttu-id="42b4f-109">Эти инструкции либо возвращают одно или несколько информационных сообщений, либо дают указание [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] вернуть информационные сообщения вместо набора строк или результатов вычислений.</span><span class="sxs-lookup"><span data-stu-id="42b4f-109">These statements either return one or more informational messages or cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to return informational messages in place of rowset or count results.</span></span> <span data-ttu-id="42b4f-110">При успешном выполнении [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщик собственного клиента OLE DB возвращает S_OK, и сообщения становятся доступными [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребителю поставщика собственного клиента OLE DB.</span><span class="sxs-lookup"><span data-stu-id="42b4f-110">On successful execution, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK, and the messages are available to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer.</span></span>  
  
 <span data-ttu-id="42b4f-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента возвращает S_OK и имеет одно или несколько информационных сообщений, доступных после выполнения множества [!INCLUDE[tsql](../../includes/tsql-md.md)] инструкций или выполнения пользовательской [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] функции-члена поставщика собственного клиента OLE DB.</span><span class="sxs-lookup"><span data-stu-id="42b4f-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK and has one or more informational messages available following the execution of many [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or the consumer execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function.</span></span>  
  
 <span data-ttu-id="42b4f-112">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Потребитель поставщика OLE DB собственного клиента, который разрешает динамической спецификации текста запроса, должен проверять интерфейсы ошибок после каждого выполнения функции-члена независимо от значения кода возврата, наличия или отсутствия возвращенной ссылки на интерфейс **IRowset** или **IMultipleResults** или количества затронутых строк.</span><span class="sxs-lookup"><span data-stu-id="42b4f-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer allowing dynamic specification of query text should check error interfaces after every member function execution regardless of the value of the return code, the presence or absence of a returned **IRowset** or **IMultipleResults** interface reference, or a count of affected rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b4f-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="42b4f-113">See Also</span></span>  
 [<span data-ttu-id="42b4f-114">ошибки</span><span class="sxs-lookup"><span data-stu-id="42b4f-114">Errors</span></span>](errors.md)  
  
  
