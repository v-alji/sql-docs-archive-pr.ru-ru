---
title: Обновление данных в наборах строк | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- updating data [SQL Server]
- rowsets [OLE DB], updating data
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, updating data
- SQL Server Native Client OLE DB provider, data updates
- data updates [SQL Server], OLE DB
ms.assetid: 37769b1c-c480-419a-8c54-5cc420bf73db
author: rothja
ms.author: jroth
ms.openlocfilehash: 993cfb67d4e6b72eec7cc0537e9b47371e94af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734034"
---
# <a name="updating-data-in-rowsets"></a><span data-ttu-id="76765-102">Обновление данных в наборах строк</span><span class="sxs-lookup"><span data-stu-id="76765-102">Updating Data in Rowsets</span></span>
  <span data-ttu-id="76765-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента обновляет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] данные, когда потребитель обновляет изменяемый набор строк, содержащий эти данные.</span><span class="sxs-lookup"><span data-stu-id="76765-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider updates [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data when a consumer updates a modifiable rowset that contains that data.</span></span> <span data-ttu-id="76765-104">Набор строк, который можно изменять, создается, если потребитель запрашивает поддержку либо для интерфейса **IRowsetChange**, либо для интерфейса **IRowsetUpdate**.</span><span class="sxs-lookup"><span data-stu-id="76765-104">A modifiable rowset is created when the consumer requests support for either the **IRowsetChange** or **IRowsetUpdate** interface.</span></span>  
  
 <span data-ttu-id="76765-105">Все [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственные наборы строк, изменяемые поставщиком OLE DB клиента, используют [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] курсоры для поддержки набора строк.</span><span class="sxs-lookup"><span data-stu-id="76765-105">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider-modifiable rowsets use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors to support the rowset.</span></span> <span data-ttu-id="76765-106">Свойство DBPROP_LOCKMODE набора строк изменяет поведение управления параллелизмом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в курсорах, а также определяет поведение выборки строки из набора строк и создание ошибок целостности данных в наборах строк, которые можно обновлять.</span><span class="sxs-lookup"><span data-stu-id="76765-106">The rowset property DBPROP_LOCKMODE alters [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency control behavior in cursors and determines the behavior of rowset row fetching and data integrity error generation in updatable rowsets.</span></span>  
  
 <span data-ttu-id="76765-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает синхронизацию строк до или после обновления.</span><span class="sxs-lookup"><span data-stu-id="76765-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports row synchronization before or after an update.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76765-108">Интерфейс IRowChange::SetColumns может установить значения одного или более именованных столбцов объекта-строки.</span><span class="sxs-lookup"><span data-stu-id="76765-108">IRowChange::SetColumns is available to set the values of one or more named columns of a row object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76765-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="76765-109">In This Section</span></span>  
  
-   [<span data-ttu-id="76765-110">Обновление данных в курсорах SQL Server</span><span class="sxs-lookup"><span data-stu-id="76765-110">Updating Data in SQL Server Cursors</span></span>](updating-data-in-sql-server-cursors.md)  
  
-   [<span data-ttu-id="76765-111">Повторная синхронизация строк</span><span class="sxs-lookup"><span data-stu-id="76765-111">Resynchronizing Rows</span></span>](updating-data-in-rowsets-resynchronizing-rows.md)  
  
## <a name="see-also"></a><span data-ttu-id="76765-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="76765-112">See Also</span></span>  
 [<span data-ttu-id="76765-113">Наборы строк</span><span class="sxs-lookup"><span data-stu-id="76765-113">Rowsets</span></span>](rowsets.md)  
  
  
