---
title: Позиция следующей выборки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- OLE DB rowsets, fetching
- next fetch position
- rowsets [OLE DB], fetching
ms.assetid: 9ef74b3f-c9c0-492f-9b93-d65738a61abd
author: rothja
ms.author: jroth
ms.openlocfilehash: fcc771eef4acf603148bc4b4318e810b1bd72302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729426"
---
# <a name="next-fetch-position"></a><span data-ttu-id="ee86e-102">Следующая позиция выборки</span><span class="sxs-lookup"><span data-stu-id="ee86e-102">Next Fetch Position</span></span>
  <span data-ttu-id="ee86e-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента отслеживает положение следующей выборки таким образом, что последовательность вызовов метода **GetNextRows** (без пропуска, изменения направления или промежуточных вызовов методов **FindNextRow**, **Seek**или **свойство RestartPosition** ) считывает весь набор строк без пропуска или повторения какой-либо строки.</span><span class="sxs-lookup"><span data-stu-id="ee86e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider keeps track of the next fetch position so that a sequence of calls to the **GetNextRows** method (without skips, changes of direction, or intervening calls to the **FindNextRow**, **Seek**, or **RestartPosition** methods) reads the whole rowset without skipping or repeating any row.</span></span> <span data-ttu-id="ee86e-104">Позиция следующей выборки меняется с помощью вызова методов **IRowset::GetNextRows**, **IRowset::RestartPosition** или **IRowsetIndex::Seek** либо вызовом **FindNextRow** со значением *pBookmark*, равным NULL.</span><span class="sxs-lookup"><span data-stu-id="ee86e-104">The next fetch position is changed either by calling **IRowset::GetNextRows**, **IRowset::RestartPosition**, or **IRowsetIndex::Seek**, or by calling **FindNextRow** with a null *pBookmark* value.</span></span> <span data-ttu-id="ee86e-105">Вызов **FindNextRow** со значением *pBookmark*, отличным от NULL, не влияет на позицию следующей выборки.</span><span class="sxs-lookup"><span data-stu-id="ee86e-105">Calling **FindNextRow** with a nonnull *pBookmark* value does not affect the next fetch position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee86e-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="ee86e-106">See Also</span></span>  
 [<span data-ttu-id="ee86e-107">Выборка строк</span><span class="sxs-lookup"><span data-stu-id="ee86e-107">Fetching Rows</span></span>](fetching-rows.md)  
  
  
