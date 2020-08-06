---
title: Параметр конфигурации сервера "disallow results from triggers" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], result sets
- result sets [SQL Server], triggers
- disallow results from triggers option
ms.assetid: 47149073-307d-47a5-b7d2-66a737d3231d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f162a6e06706561d861bfc54a1ae4027f2c3466e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727346"
---
# <a name="disallow-results-from-triggers-server-configuration-option"></a><span data-ttu-id="049b8-102">Параметр конфигурации сервера «disallow results from triggers»</span><span class="sxs-lookup"><span data-stu-id="049b8-102">disallow results from triggers Server Configuration Option</span></span>
  <span data-ttu-id="049b8-103">Параметр **disallow results from triggers** предназначен, чтобы определить, разрешается ли триггерам возвращать результирующие наборы.</span><span class="sxs-lookup"><span data-stu-id="049b8-103">Use the **disallow results from triggers** option to control whether triggers return result sets.</span></span> <span data-ttu-id="049b8-104">Триггеры, возвращающие результирующие наборы, могут привести к непредвиденному поведению приложений, не предназначенных для работы с ними.</span><span class="sxs-lookup"><span data-stu-id="049b8-104">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="049b8-105">Рекомендуется установить это значение равным 1.</span><span class="sxs-lookup"><span data-stu-id="049b8-105">We recommend that you set this value to 1.</span></span>  
  
 <span data-ttu-id="049b8-106">При установке в значение 1 параметр **disallow results from triggers** включается (ON).</span><span class="sxs-lookup"><span data-stu-id="049b8-106">When set to 1, the **disallow results from triggers** option is set to ON.</span></span> <span data-ttu-id="049b8-107">Значение по умолчанию для этого параметра равно 0 (OFF).</span><span class="sxs-lookup"><span data-stu-id="049b8-107">The default setting for this option is 0 (OFF).</span></span> <span data-ttu-id="049b8-108">Если этот параметр равен 1 (ON), любая попытка триггера вернуть результирующий набор завершается неудачей и пользователь получает следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="049b8-108">If this option is set to 1 (ON), any attempt by a trigger to return a result set fails, and the user receives the following error message:</span></span>  
  
 <span data-ttu-id="049b8-109">"Сообщение 524, уровень 16, состояние 1, процедура \<Procedure Name>, строка \<Line#></span><span class="sxs-lookup"><span data-stu-id="049b8-109">"Msg 524, Level 16, State 1, Procedure \<Procedure Name>, Line \<Line#></span></span>  
  
 <span data-ttu-id="049b8-110">«Триггер возвратил результирующий набор при параметре сервера "disallow results from triggers", равном True».</span><span class="sxs-lookup"><span data-stu-id="049b8-110">"A trigger returned a resultset and the server option 'disallow_results_from_triggers' is true."</span></span>  
  
 <span data-ttu-id="049b8-111">Параметр **disallow results from triggers** применяется на уровне экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], то есть определяет работу всех триггеров, существующих в данном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="049b8-111">The **disallow results from triggers** option is applied at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level, and it will determine behavior for all existing triggers within the instance.</span></span>  
  
 <span data-ttu-id="049b8-112">Параметр **disallow results from triggers** является дополнительным.</span><span class="sxs-lookup"><span data-stu-id="049b8-112">The **disallow results from triggers** option is an advanced option.</span></span> <span data-ttu-id="049b8-113">Изменить значение этого параметра при помощи системной хранимой процедуры **sp_configure** можно только при условии, если параметр **show advanced options** имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="049b8-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change disallow results from triggers only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="049b8-114">Параметр вступает в силу сразу без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="049b8-114">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="049b8-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="049b8-115">See Also</span></span>  
 <span data-ttu-id="049b8-116">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="049b8-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="049b8-117">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="049b8-117">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="049b8-118">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="049b8-118">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
