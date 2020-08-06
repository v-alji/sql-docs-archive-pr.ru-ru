---
title: План обслуживания (управление соединениями) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.connections.f1
ms.assetid: 95ad9375-6584-423e-b9de-0e86782f8017
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b6b9f0c1652ead2f21567634b758ce81485b47b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658243"
---
# <a name="maintenance-plan-manage-connections"></a><span data-ttu-id="e041d-102">План обслуживания (управление соединениями)</span><span class="sxs-lookup"><span data-stu-id="e041d-102">Maintenance Plan (Manage Connections)</span></span>
  <span data-ttu-id="e041d-103">Используйте диалоговое окно **Управление соединениями** , чтобы задать свойства соединений, используемых планами обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e041d-103">Use the **Manage Connections** dialog box to specify the properties of connections used by maintenance plans.</span></span> <span data-ttu-id="e041d-104">При создании плана обслуживания устанавливается локальное соединение с сервером, на котором создается план.</span><span class="sxs-lookup"><span data-stu-id="e041d-104">When you create a maintenance plan, a local connection to the server where you created the plan is created.</span></span> <span data-ttu-id="e041d-105">Используйте это соединение, чтобы создать задачи, работающие по данному локальному соединению.</span><span class="sxs-lookup"><span data-stu-id="e041d-105">Use this connection to create tasks that perform work on this local connection.</span></span> <span data-ttu-id="e041d-106">При необходимости используйте диалоговое окно **Управление соединениями** , чтобы добавить их.</span><span class="sxs-lookup"><span data-stu-id="e041d-106">When needed, use the **Manage Connections** dialog box to add them.</span></span> <span data-ttu-id="e041d-107">Как только дополнительные соединения будут настроены, они будут появляться в окне соединений для каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="e041d-107">When additional connections are configured they appear in the connections box for each task.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e041d-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="e041d-108">Options</span></span>  
 <span data-ttu-id="e041d-109">**Server**</span><span class="sxs-lookup"><span data-stu-id="e041d-109">**Server**</span></span>  
 <span data-ttu-id="e041d-110">Экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="e041d-110">The server instance.</span></span>  
  
 <span data-ttu-id="e041d-111">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="e041d-111">**Authentication**</span></span>  
 <span data-ttu-id="e041d-112">Указывает, используется ли при соединении проверка подлинности Windows или проверка подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e041d-112">Indicates whether the connection is made with Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e041d-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="e041d-113">See Also</span></span>  
 [<span data-ttu-id="e041d-114">Планы обслуживания</span><span class="sxs-lookup"><span data-stu-id="e041d-114">Maintenance Plans</span></span>](maintenance-plans.md)  
  
  
