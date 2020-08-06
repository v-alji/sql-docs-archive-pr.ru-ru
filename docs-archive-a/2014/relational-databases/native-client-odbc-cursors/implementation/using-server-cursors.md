---
title: Использование серверных курсоров | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, cursors
- cursors [ODBC], server cursors
- ODBC cursors, server cursors
- server cursors [SQL Server]
ms.assetid: 8a6d99b7-10b8-4474-8639-4914b25ba170
author: rothja
ms.author: jroth
ms.openlocfilehash: e596af3c46849313d813ce2d7f1dab2a7425c090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657779"
---
# <a name="using-server-cursors"></a><span data-ttu-id="ce795-102">Использование серверных курсоров</span><span class="sxs-lookup"><span data-stu-id="ce795-102">Using Server Cursors</span></span>
  <span data-ttu-id="ce795-103">Если приложение ODBC устанавливает для любого из атрибутов курсора ODBC значение, отличное от значений по умолчанию, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента запрашивает сервер для реализации серверного курсора API того же типа.</span><span class="sxs-lookup"><span data-stu-id="ce795-103">If an ODBC application sets any of the ODBC cursor attributes to anything other than the defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver requests the server to implement an API server cursor of the same type.</span></span> <span data-ttu-id="ce795-104">Использование серверных курсоров API-интерфейса обеспечивает высвобождение памяти клиента и может существенно сократить объем сетевого трафика между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="ce795-104">Using API server cursors frees memory on the client and can significantly reduce network traffic between the client and server.</span></span>  
  
 <span data-ttu-id="ce795-105">Возможным недостатком серверных курсоров API является то, что они в настоящее время поддерживают не все инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="ce795-105">A potential drawback of API server cursors is that they currently do not support all SQL statements.</span></span> <span data-ttu-id="ce795-106">Серверные курсоры API-интерфейса не могут быть использованы для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="ce795-106">API server cursors cannot be used to execute:</span></span>  
  
-   <span data-ttu-id="ce795-107">пакеты или хранимые процедуры, которые возвращают несколько результирующих наборов;</span><span class="sxs-lookup"><span data-stu-id="ce795-107">Batches or stored procedures that return multiple result sets.</span></span>  
  
-   <span data-ttu-id="ce795-108">инструкции SELECT, которые содержат предложения COMPUTE, COMPUTE BY, FOR BROWSE или INTO;</span><span class="sxs-lookup"><span data-stu-id="ce795-108">SELECT statements that contain COMPUTE, COMPUTE BY, FOR BROWSE, or INTO clauses.</span></span>  
  
-   <span data-ttu-id="ce795-109">инструкцию EXECUTE, которая содержит ссылку на удаленную хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="ce795-109">An EXECUTE statement referencing a remote stored procedure.</span></span>  
  
 <span data-ttu-id="ce795-110">При подключении к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] выполнение инструкции с данными характеристиками с помощью серверного курсора приводит к тому, что курсор преобразуется в принимаемый по умолчанию результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="ce795-110">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], executing a statement with these characteristics using a server cursor causes the cursor being converted to a default result set.</span></span> <span data-ttu-id="ce795-111">При подключении к более ранним версиям [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ce795-111">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it causes an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce795-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce795-112">See Also</span></span>  
 [<span data-ttu-id="ce795-113">Способы реализации курсоров</span><span class="sxs-lookup"><span data-stu-id="ce795-113">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
