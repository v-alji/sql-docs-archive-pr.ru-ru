---
title: Новый столбец в выходных данных sp_helptrigger может повлиять на приложения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sp_helptrigger
ms.assetid: b7c42a8f-f2e0-4fa3-b046-3cf39c854c47
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b1f5e936843ed84a5c6b88e2f3685e7a4272bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668032"
---
# <a name="new-column-in-output-of-sp_helptrigger-may-impact-applications"></a><span data-ttu-id="60f2b-102">Новый столбец, возвращаемый процедурой sp_helptrigger, может повлиять на работу приложений</span><span class="sxs-lookup"><span data-stu-id="60f2b-102">New column in output of sp_helptrigger may impact applications</span></span>
  <span data-ttu-id="60f2b-103">trigger_schemaias последний столбец в результирующем наборе, возвращенном системной хранимой процедурой sp_helptrigger.</span><span class="sxs-lookup"><span data-stu-id="60f2b-103">trigger_schemaias the last column in the result set returned by the sp_helptrigger system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="60f2b-104">Чтобы получить сведения о триггерах, определенных для конкретной таблицы, нужно выполнить запрос к представлению каталога sys.triggers.</span><span class="sxs-lookup"><span data-stu-id="60f2b-104">To obtain information about triggers defined on a particular table, query the sys.triggers catalog view.</span></span>  
  
## <a name="component"></a><span data-ttu-id="60f2b-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="60f2b-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="60f2b-106">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="60f2b-106">Corrective Action</span></span>  
 <span data-ttu-id="60f2b-107">Проверьте использование в приложениях хранимой процедуры sp_helptrigger.</span><span class="sxs-lookup"><span data-stu-id="60f2b-107">Review the use of sp_helptrigger in applications.</span></span> <span data-ttu-id="60f2b-108">Возможно, придется изменить приложения для обработки дополнительного столбца.</span><span class="sxs-lookup"><span data-stu-id="60f2b-108">You may need to modify your applications to accommodate the additional column.</span></span> <span data-ttu-id="60f2b-109">Можно также воспользоваться представлением каталога sys.triggers.</span><span class="sxs-lookup"><span data-stu-id="60f2b-109">Alternatively, you can use the sys.triggers catalog view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f2b-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="60f2b-110">See Also</span></span>  
 <span data-ttu-id="60f2b-111">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="60f2b-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="60f2b-112">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="60f2b-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
