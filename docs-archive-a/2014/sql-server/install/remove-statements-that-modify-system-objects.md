---
title: Удалите инструкции, изменяющие системные объекты | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- direct system catalog updates [SQL Server]
- system catalogs [SQL Server]
ms.assetid: 221b46c2-c27e-4df8-bd8c-8b990d6d5e98
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 526181bc4bf7ab81df2eaa25f19e7627c9b7af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751707"
---
# <a name="remove-statements-that-modify-system-objects"></a><span data-ttu-id="c642d-102">Удаление инструкций, которые изменяют системные объекты</span><span class="sxs-lookup"><span data-stu-id="c642d-102">Remove statements that modify system objects</span></span>
  <span data-ttu-id="c642d-103">Советник по переходу обнаружил инструкции, производящие обновление системного каталога.</span><span class="sxs-lookup"><span data-stu-id="c642d-103">Upgrade Advisor detected statements that update the system catalog.</span></span> <span data-ttu-id="c642d-104">Непосредственное изменение системного каталога не допускается.</span><span class="sxs-lookup"><span data-stu-id="c642d-104">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="c642d-105">Измените свои SQL-скрипты так, чтобы они использовали официальные документированные функции API-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c642d-105">Modify your SQL scripts to use official and documented APIs.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c642d-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="c642d-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c642d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c642d-107">Description</span></span>  
 <span data-ttu-id="c642d-108">Непосредственное изменение системного каталога не допускается.</span><span class="sxs-lookup"><span data-stu-id="c642d-108">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="c642d-109">Любая попытка сделать это приведет к возникновению следующей ошибки.</span><span class="sxs-lookup"><span data-stu-id="c642d-109">Any attempt to do so will generate the following error:</span></span>  
  
 `Server: Msg 259, Level 16, State 1, Line 1`  
  
 `Ad hoc updates to system catalogs are not allowed.`  
  
## <a name="corrective-action"></a><span data-ttu-id="c642d-110">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="c642d-110">Corrective Action</span></span>  
 <span data-ttu-id="c642d-111">Измените свои SQL-скрипты так, чтобы они использовали официальные документированные функции API-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c642d-111">Modify your SQL scripts to use official and documented APIs.</span></span> <span data-ttu-id="c642d-112">Например, используйте инструкцию ALTER DATABASE *database_name* SET EMERGENCY вместо инструкции UPDATE в системной таблице **sysdatabases** .</span><span class="sxs-lookup"><span data-stu-id="c642d-112">For example, use ALTER DATABASE *database_name* SET EMERGENCY instead of running an UPDATE statement on the **sysdatabases** system table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c642d-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="c642d-113">See Also</span></span>  
 <span data-ttu-id="c642d-114">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c642d-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c642d-115">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="c642d-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
