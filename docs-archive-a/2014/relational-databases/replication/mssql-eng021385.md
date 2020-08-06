---
title: MSSQL_ENG021385 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021385 error
ms.assetid: a2c0444f-d97b-4760-8905-3574791c2e26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b73d3216f07cb44d750a37149634258648f1bd48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730497"
---
# <a name="mssql_eng021385"></a><span data-ttu-id="5ce0e-102">MSSQL_ENG021385</span><span class="sxs-lookup"><span data-stu-id="5ce0e-102">MSSQL_ENG021385</span></span>
    
## <a name="message-details"></a><span data-ttu-id="5ce0e-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="5ce0e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ce0e-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5ce0e-104">Product Name</span></span>|<span data-ttu-id="5ce0e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5ce0e-105">SQL Server</span></span>|  
|<span data-ttu-id="5ce0e-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5ce0e-106">Event ID</span></span>|<span data-ttu-id="5ce0e-107">21385</span><span class="sxs-lookup"><span data-stu-id="5ce0e-107">21385</span></span>|  
|<span data-ttu-id="5ce0e-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5ce0e-108">Event Source</span></span>|<span data-ttu-id="5ce0e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5ce0e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5ce0e-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5ce0e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="5ce0e-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5ce0e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="5ce0e-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5ce0e-112">Message Text</span></span>|<span data-ttu-id="5ce0e-113">Не удалось создать моментальный снимок для публикации "%s".</span><span class="sxs-lookup"><span data-stu-id="5ce0e-113">Snapshot failed to process publication '%s'.</span></span> <span data-ttu-id="5ce0e-114">Возможно, из-за изменений в схеме или из-за статей, добавленных во время создания снимка.</span><span class="sxs-lookup"><span data-stu-id="5ce0e-114">Possibly due to active schema change activity or new articles being added.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5ce0e-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5ce0e-115">Explanation</span></span>  
 <span data-ttu-id="5ce0e-116">Данная ошибка возникает, если агент моментальных снимков начинает работу во время выполняющихся изменений в базе данных публикации, включающих добавление или удаление статей и внесение изменений схемы в опубликованные объекты.</span><span class="sxs-lookup"><span data-stu-id="5ce0e-116">This error is raised if the Snapshot Agent starts running when there are ongoing changes to the publication database, including adding or dropping articles and performing schema changes on published objects.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5ce0e-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5ce0e-117">User Action</span></span>  
 <span data-ttu-id="5ce0e-118">После завершения изменений в базе данных публикации перезапустите агент моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="5ce0e-118">Restart the Snapshot Agent after changes to the publication database are complete.</span></span> <span data-ttu-id="5ce0e-119">Дополнительные сведения см. в статьях и [Запуск и остановка агента репликации (среда SQL Server Management Studio)](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) и [Основные понятия исполняемых файлов агента репликации](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="5ce0e-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce0e-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ce0e-120">See Also</span></span>  
 [<span data-ttu-id="5ce0e-121">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="5ce0e-121">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
