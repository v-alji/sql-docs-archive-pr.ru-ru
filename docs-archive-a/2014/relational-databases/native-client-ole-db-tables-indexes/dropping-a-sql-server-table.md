---
title: Удаление таблицы SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- tables [OLE DB]
- deleting tables
- SQL Server Native Client OLE DB provider, tables
- removing tables
- dropping tables
ms.assetid: b6d6c4de-43c6-473e-92aa-34ffddd58cbe
author: rothja
ms.author: jroth
ms.openlocfilehash: 4d7bea98a3afcd0022f66117b6bde2d968a866b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665302"
---
# <a name="dropping-a-sql-server-table"></a><span data-ttu-id="76986-102">Удаление таблицы SQL Server</span><span class="sxs-lookup"><span data-stu-id="76986-102">Dropping a SQL Server Table</span></span>
  <span data-ttu-id="76986-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DBа собственного клиента предоставляет функцию **ITableDefinition::D роптабле** .</span><span class="sxs-lookup"><span data-stu-id="76986-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropTable** function.</span></span> <span data-ttu-id="76986-104">Это позволяет пользователям удалять [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицы из базы данных.</span><span class="sxs-lookup"><span data-stu-id="76986-104">This allows consumers to remove a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from a database.</span></span>  
  
 <span data-ttu-id="76986-105">Пользователь задает имя таблицы в виде символьной строки в Юникоде в элементе *pwszName* объединения *uName* в параметре *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="76986-105">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="76986-106">Элемент *eKind* параметра *pTableID* должен быть равен DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="76986-106">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76986-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="76986-107">See Also</span></span>  
 [<span data-ttu-id="76986-108">Таблицы и индексы</span><span class="sxs-lookup"><span data-stu-id="76986-108">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
