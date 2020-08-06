---
title: Поддержка UTF-16 в SQL Server Native Client 11,0 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: f2520424-8ef4-409f-8147-d83da5076e96
author: rothja
ms.author: jroth
ms.openlocfilehash: af8581071400db888fb508b88f8e8ae93bc71f70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666531"
---
# <a name="utf-16-support-in-sql-server-native-client-110"></a><span data-ttu-id="6b6cc-102">Поддержка UTF-16 в собственном клиенте SQL Server версии 11.0</span><span class="sxs-lookup"><span data-stu-id="6b6cc-102">UTF-16 Support in SQL Server Native Client 11.0</span></span>
  <span data-ttu-id="6b6cc-103">Начиная с [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , при предоставлении буфера фиксированной длины при привязке результата или выходного параметра столбца, а также если `wchar` символ, записанный в буфер перед завершающим символом, является старшим замещающим кодовым точкой суррогатной пары, а следующий символ является младшим кодовым точкой-заместителем `wchar` , [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственный клиент не будет добавлять старшую кодовую точку в буфер.</span><span class="sxs-lookup"><span data-stu-id="6b6cc-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], if you supply a fixed-length buffer when binding a column result or output parameter and if the `wchar` character written into the buffer before the terminating character is a high surrogate code point of a surrogate pair, and if the next `wchar` character is a low surrogate code point, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will not add the high surrogate code point to the buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b6cc-104">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b6cc-104">See Also</span></span>  
 [<span data-ttu-id="6b6cc-105">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="6b6cc-105">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
