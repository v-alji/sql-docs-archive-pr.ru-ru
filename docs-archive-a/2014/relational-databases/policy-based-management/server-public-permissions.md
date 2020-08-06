---
title: Разрешения роли сервера public | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 9a276caa-ea38-473d-92bc-26302bfcf660
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7913c4715f47b8105b72b1c817dbe77e52d40539
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749755"
---
# <a name="server-public-permissions"></a><span data-ttu-id="908d0-102">Разрешения роли сервера public</span><span class="sxs-lookup"><span data-stu-id="908d0-102">Server public Permissions</span></span>
  <span data-ttu-id="908d0-103">Это правило определяет, имеет ли роль сервера public разрешения на сервер.</span><span class="sxs-lookup"><span data-stu-id="908d0-103">This rule determines whether the public server role has server permissions.</span></span> <span data-ttu-id="908d0-104">Каждое создающееся на сервере имя входа является членом роли сервера public.</span><span class="sxs-lookup"><span data-stu-id="908d0-104">Every login that is created on the server is a member of the public server role.</span></span> <span data-ttu-id="908d0-105">Если это условие выполняется, все имена входа на сервере будут иметь разрешение на сервер.</span><span class="sxs-lookup"><span data-stu-id="908d0-105">If this condition is met, every login on the server will have server permissions.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="908d0-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="908d0-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="908d0-107">Не предоставляйте серверной роли public разрешения на сервер.</span><span class="sxs-lookup"><span data-stu-id="908d0-107">Do not grant server permissions to the server public role.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="908d0-108">После завершения установки роль **Public** имеет `CONNECT` разрешение на все конечные точки, кроме **выделенного административного соединения**.</span><span class="sxs-lookup"><span data-stu-id="908d0-108">After setup completes the **PUBLIC** role has `CONNECT` permission on all the endpoints except the **Dedicated Admin Connection**.</span></span> <span data-ttu-id="908d0-109">Это нормально, и в обычных ситуациях не нуждается в изменении.</span><span class="sxs-lookup"><span data-stu-id="908d0-109">This is normal and should not be normally changed.</span></span> <span data-ttu-id="908d0-110">(Управление доступом осуществляется с помощью разрешения `CONNECT SQL`, которое предоставляется автоматически при создании нового имени входа.)</span><span class="sxs-lookup"><span data-stu-id="908d0-110">(Access is controlled by using the `CONNECT SQL` permission which is automatically granted when new logins are created.)</span></span>  
  
### <a name="for-more-information"></a><span data-ttu-id="908d0-111">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="908d0-111">For more information</span></span>  
 [<span data-ttu-id="908d0-112">Обеспечение безопасности SQL Server</span><span class="sxs-lookup"><span data-stu-id="908d0-112">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
  
