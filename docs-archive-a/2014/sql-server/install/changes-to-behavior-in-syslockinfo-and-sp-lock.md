---
title: Изменения в поведении в syslockinfo и sp_lock | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- syslockinfo
- sp_lock
ms.assetid: b9892ae3-ac15-48be-8b52-78dbed6467ed
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65ace190004cab911dd8996642720620eba94935
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659234"
---
# <a name="changes-to-behavior-in-syslockinfo-and-sp_lock"></a><span data-ttu-id="dea6b-102">Изменение в работе представления syslockinfo и процедуры sp_lock</span><span class="sxs-lookup"><span data-stu-id="dea6b-102">Changes to behavior in syslockinfo and sp_lock</span></span>
  <span data-ttu-id="dea6b-103">Представление**syslockinfo** и хранимая процедура **sp_lock** могут возвратить непредвиденные значения.</span><span class="sxs-lookup"><span data-stu-id="dea6b-103">**syslockinfo** and **sp_lock** may return unexpected values.</span></span> <span data-ttu-id="dea6b-104">Кроме того, они могут вернуть дополнительные строки, в то время как предыдущие версии представления **syslockinfo** и хранимой процедуры **sp_lock** возвращали не более двух строк на каждый ресурс блокировки.</span><span class="sxs-lookup"><span data-stu-id="dea6b-104">They may also return additional rows, whereas previous versions of **syslockinfo** and **sp_lock** returned a maximum of two rows per lock resource.</span></span>  
  
 <span data-ttu-id="dea6b-105">Для доступа к информации представления **syslockinfo** или запуска хранимой процедуры **sp_lock** необходимо разрешение VIEW SERVER STATE на сервере.</span><span class="sxs-lookup"><span data-stu-id="dea6b-105">To access information from **syslockinfo** or execute **sp_lock** requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="component"></a><span data-ttu-id="dea6b-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="dea6b-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="dea6b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dea6b-107">Description</span></span>  
 <span data-ttu-id="dea6b-108">В [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]столбцы **rsc_objid** и **rsc_indid** в таблице **syslockinfo** , а также столбцы **objid** и **indid** в хранимой процедуре **sp_lock** в обязательном порядке возвращают идентификатор объекта и идентификатор индекса.</span><span class="sxs-lookup"><span data-stu-id="dea6b-108">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the **rsc_objid** and **rsc_indid** columns in **syslockinfo** and the **objid** and **indid** columns in **sp_lock** consistently return the object ID and index ID.</span></span> <span data-ttu-id="dea6b-109">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]может быть возвращено нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="dea6b-109">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a value of 0 may be returned.</span></span>  
  
 <span data-ttu-id="dea6b-110">В [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]представление **syslockinfo** и хранимая процедура **sp_lock** возвращают не более двух строк на каждый отдельный ресурс блокировки в отдельной транзакции.</span><span class="sxs-lookup"><span data-stu-id="dea6b-110">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], **syslockinfo** and **sp_lock** return a maximum of two rows for any given lock resource in a single transaction.</span></span> <span data-ttu-id="dea6b-111">Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], если включено секционирование блокировок, может быть возвращено несколько строк для одного и того же ресурса, выполняющегося в рамках одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="dea6b-111">Starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], when lock partitioning is enabled, multiple rows for the same resource running under one transaction may be returned.</span></span> <span data-ttu-id="dea6b-112">Может возвращаться до N + 1 строк, где N — число ЦП.</span><span class="sxs-lookup"><span data-stu-id="dea6b-112">There may be up to N + 1 rows returned, where N is the number of CPUs.</span></span> <span data-ttu-id="dea6b-113">Кроме того, теперь запросы GRANTED и WAITING могут отображаться для одного ресурса, что было невозможно в [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dea6b-113">Also, it is now possible to have GRANTED and WAITING requests displayed for the same resource, which was not possible in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="dea6b-114">Разрешения</span><span class="sxs-lookup"><span data-stu-id="dea6b-114">Permissions</span></span>  
 <span data-ttu-id="dea6b-115">необходимо разрешение VIEW SERVER STATE на сервере.</span><span class="sxs-lookup"><span data-stu-id="dea6b-115">Requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea6b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="dea6b-116">See Also</span></span>  
 <span data-ttu-id="dea6b-117">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="dea6b-117">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="dea6b-118">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="dea6b-118">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
