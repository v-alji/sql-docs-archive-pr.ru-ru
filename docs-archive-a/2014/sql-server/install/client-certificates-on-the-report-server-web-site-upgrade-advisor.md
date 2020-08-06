---
title: Клиентские сертификаты на веб-сайте сервера отчетов (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 5ecce26b-99df-4109-8e51-d150d369dff7
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 563a64e695ef552a712a5678f56d38fdfbff619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659221"
---
# <a name="client-certificates-on-the-report-server-web-site-upgrade-advisor"></a><span data-ttu-id="70d88-102">Сертификаты клиента на веб-сайте сервера отчетов (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="70d88-102">Client certificates on the report server web site (Upgrade Advisor)</span></span>
  <span data-ttu-id="70d88-103">Помощник по обновлению обнаружил один или несколько клиентских сертификатов на сайте IIS, где расположены виртуальные каталоги сервера отчетов или диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="70d88-103">Upgrade Advisor detected one or more client certificates on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span>  
  
||  
|-|  
|<span data-ttu-id="70d88-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим.</span><span class="sxs-lookup"><span data-stu-id="70d88-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="70d88-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="70d88-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="70d88-106">Описание</span><span class="sxs-lookup"><span data-stu-id="70d88-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="70d88-107">не [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] поддерживает использование сертификатов клиента для проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="70d88-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not support the use of client certificates to authenticate users.</span></span> <span data-ttu-id="70d88-108">Обновление может быть продолжено, но обновленный сервер отчетов не будет использовать клиентские сертификаты.</span><span class="sxs-lookup"><span data-stu-id="70d88-108">Upgrade can continue, but client certificates will not be used by the upgraded report server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="70d88-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="70d88-109">Corrective Action</span></span>  
 <span data-ttu-id="70d88-110">Если требуется проверка подлинности с помощью клиентских сертификатов, ее нужно реализовать в виде отдельного решения, например с помощью ISA Server.</span><span class="sxs-lookup"><span data-stu-id="70d88-110">You will have to use a separate solution such as ISA Server to ensure any client certificate authentication requirements are addressed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d88-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="70d88-111">See Also</span></span>  
 [<span data-ttu-id="70d88-112">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="70d88-112">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
