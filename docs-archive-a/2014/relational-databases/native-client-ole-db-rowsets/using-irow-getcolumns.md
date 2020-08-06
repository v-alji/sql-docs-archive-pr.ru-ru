---
title: Использование метода IRow::GetColumns | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- GetColumns method
ms.assetid: 1f5d2e03-e6fe-4ea1-b71d-55d02b5d59ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f323dda790946565bc0dbd63c9e1f9d17ac7494b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657081"
---
# <a name="using-irowgetcolumns"></a><span data-ttu-id="3c0a5-102">Использование метода IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="3c0a5-102">Using IRow::GetColumns</span></span>
  <span data-ttu-id="3c0a5-103">Реализация интерфейса **IRow** позволяет перемещаться только вперед с последовательным доступом к столбцам.</span><span class="sxs-lookup"><span data-stu-id="3c0a5-103">The **IRow** implementation allows forward-only sequential access to the columns.</span></span> <span data-ttu-id="3c0a5-104">Столбцы этой строки можно получить либо полностью одним вызовом метода **IRow::GetColumns**, либо по частям, несколько раз вызывая метод **IRow::GetColumns** при доступе к нескольким столбцам строки.</span><span class="sxs-lookup"><span data-stu-id="3c0a5-104">You can either access all the columns in the row with a single call to **IRow::GetColumns** or call **IRow::GetColumns** multiple times every time that you access several columns in the row.</span></span>  
  
 <span data-ttu-id="3c0a5-105">Если метод **IRow::GetColumns** вызывается несколько раз, эти вызовы не должны перекрываться.</span><span class="sxs-lookup"><span data-stu-id="3c0a5-105">The multiple calls to **IRow::GetColumns** should not overlap.</span></span> <span data-ttu-id="3c0a5-106">Например, если первый вызов метода **IRow::GetColumns** возвращает столбцы 1, 2 и 3, то второй вызов **IRow::GetColumns** будет возвращать столбцы 4, 5 и 6.</span><span class="sxs-lookup"><span data-stu-id="3c0a5-106">For example, if the first call to **IRow::GetColumns** retrieves columns 1, 2, and 3, the second call to **IRow::GetColumns** should call for columns 4, 5, and 6.</span></span> <span data-ttu-id="3c0a5-107">Если последующие вызовы **IRow::GetColumns** пересекаются, то флажку состояния (полю dwstatus в DBCOLUMNACCESS) присваивается значение DBSTATUS_E_UNAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3c0a5-107">If later calls to **IRow::GetColumns** overlap, the status flag (dwstatus field in DBCOLUMNACCESS) is set to DBSTATUS_E_UNAVAILABLE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0a5-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c0a5-108">See Also</span></span>  
 [<span data-ttu-id="3c0a5-109">Выборка одной строки с помощью интерфейса IRow</span><span class="sxs-lookup"><span data-stu-id="3c0a5-109">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
  
