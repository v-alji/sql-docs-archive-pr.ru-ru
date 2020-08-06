---
title: Закладки | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bookmarks [OLE DB]
- SQL Server Native Client OLE DB provider, bookmarks
- rowsets [OLE DB], bookmarks
- OLE DB rowsets, bookmarks
ms.assetid: 7d9076f2-bf9c-452e-b816-70371a0c1644
author: rothja
ms.author: jroth
ms.openlocfilehash: be8e5486e5a442ddafa133a9cbd3f408d30a50d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738255"
---
# <a name="bookmarks"></a><span data-ttu-id="4e2c3-102">Закладки</span><span class="sxs-lookup"><span data-stu-id="4e2c3-102">Bookmarks</span></span>
  <span data-ttu-id="4e2c3-103">Закладки позволяют потребителю быстро вернуться к конкретной строке.</span><span class="sxs-lookup"><span data-stu-id="4e2c3-103">Bookmarks let consumers quickly return to a row.</span></span> <span data-ttu-id="4e2c3-104">Потребитель может получать доступ к произвольной строке с помощью закладок.</span><span class="sxs-lookup"><span data-stu-id="4e2c3-104">With bookmarks, consumers can access rows randomly based on the bookmark value.</span></span> <span data-ttu-id="4e2c3-105">Столбец закладок является столбцом номер 0 в наборе строк.</span><span class="sxs-lookup"><span data-stu-id="4e2c3-105">The bookmark column is column 0 in the rowset.</span></span> <span data-ttu-id="4e2c3-106">Потребитель присваивает полю dwFlag в структуре привязки значение DBCOLUMNSINFO_ISBOOKMARK, чтобы указать, что столбец используется как закладка.</span><span class="sxs-lookup"><span data-stu-id="4e2c3-106">The consumer sets the dwFlag field value of the binding structure to DBCOLUMNSINFO_ISBOOKMARK to indicate that the column is used as a bookmark.</span></span> <span data-ttu-id="4e2c3-107">Пользователь также присваивает свойству набора строк DBPROP_BOOKMARKS значение VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="4e2c3-107">The consumer also sets the rowset property DBPROP_BOOKMARKS to VARIANT_TRUE.</span></span> <span data-ttu-id="4e2c3-108">Это позволяет столбцу с номером 0 присутствовать в наборе строк. </span><span class="sxs-lookup"><span data-stu-id="4e2c3-108">This lets column 0 be present in the rowset.</span></span> <span data-ttu-id="4e2c3-109">Затем для получения строк, начиная со строки, заданной отступом от закладки, используется метод **IRowsetLocate::GetRowsAt**.</span><span class="sxs-lookup"><span data-stu-id="4e2c3-109">The **IRowsetLocate::GetRowsAt** method is then used to fetch rows, starting with the row specified as an offset from a bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2c3-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e2c3-110">See Also</span></span>  
 [<span data-ttu-id="4e2c3-111">Наборы строк</span><span class="sxs-lookup"><span data-stu-id="4e2c3-111">Rowsets</span></span>](rowsets.md)  
  
  
