---
title: Доступ к службе Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- viewing packages while running
- displaying packacges while running
- security [Integration Services], running packages
- packages [Integration Services], security
- current packages running
- Integration Services packages, security
- SQL Server Integration Services packages, security
ms.assetid: 1088aafc-14c5-4e7d-9930-606a24c3049b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7dd6fbed4bedc285069306ab4c400f0f67f9f293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656537"
---
# <a name="access-to-the-integration-services-service"></a><span data-ttu-id="48b90-102">Доступ к службам Integration Services</span><span class="sxs-lookup"><span data-stu-id="48b90-102">Access to the Integration Services Service</span></span>
  <span data-ttu-id="48b90-103">Уровни защиты пакетов могут ограничивать круг пользователей, которым разрешается изменять и выполнять пакет.</span><span class="sxs-lookup"><span data-stu-id="48b90-103">Package protection levels can limit who is allowed to edit and execute a package.</span></span> <span data-ttu-id="48b90-104">Дополнительная защита требуется для ограничения круга пользователей, которым разрешается просматривать список пакетов, выполняющихся в данный момент на сервере, и останавливать выполнение пакетов в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48b90-104">Additional protection is needed to limit who can view the list of packages currently running on a server and who can stop currently executing packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="48b90-105">использует службы [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48b90-105">uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service to list running packages.</span></span> <span data-ttu-id="48b90-106">Члены группы «Администраторы» Windows могут просматривать и останавливать все выполняемые в текущее время пакеты.</span><span class="sxs-lookup"><span data-stu-id="48b90-106">Members of the Windows Administrators group can view and stop all currently running packages.</span></span> <span data-ttu-id="48b90-107">Пользователи, не являющиеся членами группы «Администраторы», могут просматривать и останавливать только пакеты, запущенные ими самими.</span><span class="sxs-lookup"><span data-stu-id="48b90-107">Users who are not members of the Administrators group can view and stop only packages that they started.</span></span>  
  
 <span data-ttu-id="48b90-108">Важно ограничить доступ к компьютерам, на которых запущены службы [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , особенно службы [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , которые могут перечислить удаленные папки.</span><span class="sxs-lookup"><span data-stu-id="48b90-108">It is important to restrict access to computers that run an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service, especially an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service that can enumerate remote folders.</span></span> <span data-ttu-id="48b90-109">Любой пользователь, прошедший проверку подлинности, может запрашивать перечисление пакетов.</span><span class="sxs-lookup"><span data-stu-id="48b90-109">Any authenticated user can request the enumeration of packages.</span></span> <span data-ttu-id="48b90-110">Даже если служба не находит службу, служба перечисляет папки.</span><span class="sxs-lookup"><span data-stu-id="48b90-110">Even if the service doesn not find the service, the service enumerates folders.</span></span> <span data-ttu-id="48b90-111">Имена папок могут оказаться полезными сведениями для злоумышленника.</span><span class="sxs-lookup"><span data-stu-id="48b90-111">These folder names may be useful to a malicious user.</span></span> <span data-ttu-id="48b90-112">Если администратор настроил службу для перечисления папок на удаленном компьютере, пользователи также смогут увидеть имена, которые они в действительности не должны были видеть.</span><span class="sxs-lookup"><span data-stu-id="48b90-112">If an administrator has configured the service to enumerate folders on a remote machine, users may also be able to see folder names that they would normally not be able to see.</span></span>  
  
  
