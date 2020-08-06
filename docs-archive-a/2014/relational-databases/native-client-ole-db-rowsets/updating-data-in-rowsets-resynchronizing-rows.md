---
title: Повторная синхронизация строк | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- synchronization [OLE DB]
- IRowsetResynch interface
- resynchronizing rows
- data updates [SQL Server], OLE DB
ms.assetid: d2d30505-a878-4aa9-b821-53d8118a45a5
author: rothja
ms.author: jroth
ms.openlocfilehash: 47c628ae583f3e635f422d5146f64508372a1114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657086"
---
# <a name="resynchronizing-rows"></a><span data-ttu-id="93376-102">Повторная синхронизация строк</span><span class="sxs-lookup"><span data-stu-id="93376-102">Resynchronizing Rows</span></span>
  <span data-ttu-id="93376-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает **интерфейс irowsetresynch** только для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] наборов строк, поддерживаемых курсорами.</span><span class="sxs-lookup"><span data-stu-id="93376-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IRowsetResynch** on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursor-supported rowsets only.</span></span> <span data-ttu-id="93376-104">Интерфейс **IRowsetResynch** не предоставляется по требованию.</span><span class="sxs-lookup"><span data-stu-id="93376-104">**IRowsetResynch** is not available on demand.</span></span> <span data-ttu-id="93376-105">Пользователь должен запросить этот интерфейс перед открытием набора строк.</span><span class="sxs-lookup"><span data-stu-id="93376-105">The consumer must request the interface before opening the rowset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93376-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="93376-106">See Also</span></span>  
 [<span data-ttu-id="93376-107">Обновление данных в наборах строк</span><span class="sxs-lookup"><span data-stu-id="93376-107">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
  
