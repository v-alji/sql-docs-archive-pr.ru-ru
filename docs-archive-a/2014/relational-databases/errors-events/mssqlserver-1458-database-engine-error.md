---
title: MSSQLSERVER_1458 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1458 (Database Engine error)
ms.assetid: adc78c59-a6f2-432b-9a07-fdd1dc2b9026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: efa45177a92402b25099be5bb3e3dcc91a5fa6d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667170"
---
# <a name="mssqlserver_1458"></a><span data-ttu-id="faecb-102">MSSQLSERVER_1458</span><span class="sxs-lookup"><span data-stu-id="faecb-102">MSSQLSERVER_1458</span></span>
    
## <a name="details"></a><span data-ttu-id="faecb-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="faecb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="faecb-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="faecb-104">Product Name</span></span>|<span data-ttu-id="faecb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="faecb-105">SQL Server</span></span>|  
|<span data-ttu-id="faecb-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="faecb-106">Event ID</span></span>|<span data-ttu-id="faecb-107">1458</span><span class="sxs-lookup"><span data-stu-id="faecb-107">1458</span></span>|  
|<span data-ttu-id="faecb-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="faecb-108">Event Source</span></span>|<span data-ttu-id="faecb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="faecb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="faecb-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="faecb-110">Component</span></span>|<span data-ttu-id="faecb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="faecb-111">SQLEngine</span></span>|  
|<span data-ttu-id="faecb-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="faecb-112">Symbolic Name</span></span>|<span data-ttu-id="faecb-113">DBM_FAILREDO_ON_PRIMARY</span><span class="sxs-lookup"><span data-stu-id="faecb-113">DBM_FAILREDO_ON_PRIMARY</span></span>|  
|<span data-ttu-id="faecb-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="faecb-114">Message Text</span></span>|<span data-ttu-id="faecb-115">В основной копии базы данных «%.\*ls» обнаружена ошибка %d, состояние %d, серьезность %d.</span><span class="sxs-lookup"><span data-stu-id="faecb-115">The principal copy of the '%.\*ls' database encountered error %d, status %d, severity %d.</span></span> <span data-ttu-id="faecb-116">Зеркальное отображение базы данных приостановлено.</span><span class="sxs-lookup"><span data-stu-id="faecb-116">Database mirroring has been suspended.</span></span> <span data-ttu-id="faecb-117">Попробуйте устранить причины ошибки и возобновите зеркальное отображение.</span><span class="sxs-lookup"><span data-stu-id="faecb-117">Try to resolve the error condition, and resume mirroring.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="faecb-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="faecb-118">Explanation</span></span>  
 <span data-ttu-id="faecb-119">Это сообщение указывает, что в основной базе данных произошла ошибка, вызвавшая временную приостановку зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="faecb-119">This messages indicates that the principal database encountered an error that caused database mirroring to be suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="faecb-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="faecb-120">User Action</span></span>  
 <span data-ttu-id="faecb-121">В большинстве случаев ошибка устраняется без вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="faecb-121">Most cases of this error are self correcting.</span></span> <span data-ttu-id="faecb-122">Если проблема будет повторяться, то рекомендуется перезапустить базу данных или экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="faecb-122">If the problem persists, restarting the database or server instance typically corrects the problem.</span></span> <span data-ttu-id="faecb-123">Дополнительные сведения см. в журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на всех участниках, где произошла ошибка, предшествующая сообщению.</span><span class="sxs-lookup"><span data-stu-id="faecb-123">For more information, look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on each partner for the associated error that preceded this message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faecb-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="faecb-124">See Also</span></span>  
 [<span data-ttu-id="faecb-125">Наблюдение за зеркальным отображением базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="faecb-125">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
