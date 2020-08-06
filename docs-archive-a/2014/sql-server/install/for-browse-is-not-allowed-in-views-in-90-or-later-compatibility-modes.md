---
title: ДЛЯ обзора не допускается в представлениях в режиме совместимости 90 или более поздней версии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], FOR BROWSE clause
- FOR BROWSE clause
ms.assetid: 8f49b1c1-d877-4c46-b988-f8cdd8ac0925
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 251e0ae2ff6f19dfcff3b0f8056f6697c1bfc40d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666394"
---
# <a name="for-browse-is-not-allowed-in-views-in-90-or-later-compatibility-modes"></a><span data-ttu-id="c94d3-102">Предложение FOR BROWSE не поддерживается для представлений в режиме совместимости 90 и выше</span><span class="sxs-lookup"><span data-stu-id="c94d3-102">FOR BROWSE is not allowed in views in 90 or later compatibility modes</span></span>
  <span data-ttu-id="c94d3-103">Помощник по обновлению обнаружил в представлении предложение FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="c94d3-103">Upgrade Advisor detected the use of the FOR BROWSE clause in a view.</span></span> <span data-ttu-id="c94d3-104">Предложение FOR BROWSE допускается (и не учитывается) в представлениях, если для базы данных задан режим совместимости 80.</span><span class="sxs-lookup"><span data-stu-id="c94d3-104">The FOR BROWSE clause is allowed (and ignored) in views when the database compatibility mode is set to 80.</span></span> <span data-ttu-id="c94d3-105">Предложение FOR BROWSE недопустимо в представлениях, если для базы данных задан режим совместимости 90 и выше.</span><span class="sxs-lookup"><span data-stu-id="c94d3-105">The FOR BROWSE clause is not allowed in views when the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c94d3-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="c94d3-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="c94d3-107">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="c94d3-107">Corrective Action</span></span>  
 <span data-ttu-id="c94d3-108">При обновлении пользовательские базы данных сохраняют свой режим совместимости.</span><span class="sxs-lookup"><span data-stu-id="c94d3-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="c94d3-109">До изменения режима совместимости базы данных на 90 или выше следует удалить из определений представлений предложение FOR BROWSE.</span><span class="sxs-lookup"><span data-stu-id="c94d3-109">Before you change the database compatibility mode to 90 or later, remove the FOR BROWSE clause from view definitions.</span></span> <span data-ttu-id="c94d3-110">Дополнительные сведения см. в разделе «sp_dbcmptlevel» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c94d3-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c94d3-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="c94d3-111">See Also</span></span>  
 <span data-ttu-id="c94d3-112">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c94d3-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c94d3-113">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="c94d3-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
