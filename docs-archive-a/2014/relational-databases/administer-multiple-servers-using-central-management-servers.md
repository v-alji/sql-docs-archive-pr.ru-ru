---
title: Администрирование нескольких серверов с использованием центральных серверов управления | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- central management server
- multiserver administration [SQL Server]
- master servers [SQL Server], central management servers
- target configuration [SQL Server]
- server configuration [SQL Server]
ms.assetid: 427911a7-57d4-4542-8846-47c3267a5d9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3906165b595f6faa15812f70377a3bc0f550e52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731766"
---
# <a name="administer-multiple-servers-using-central-management-servers"></a><span data-ttu-id="2809b-102">Администрирование нескольких серверов с использованием центральных серверов управления</span><span class="sxs-lookup"><span data-stu-id="2809b-102">Administer Multiple Servers Using Central Management Servers</span></span>
  <span data-ttu-id="2809b-103">Можно администрировать сразу несколько серверов, назначив центральные серверы управления и создав группы серверов.</span><span class="sxs-lookup"><span data-stu-id="2809b-103">You can administer multiple servers by designating Central Management Servers and creating server groups.</span></span>  
  
## <a name="benefits-of-central-management-servers-and-server-groups"></a><span data-ttu-id="2809b-104">Преимущества центральных серверов управления и групп серверов</span><span class="sxs-lookup"><span data-stu-id="2809b-104">Benefits of Central Management Servers and Server Groups</span></span>  
 <span data-ttu-id="2809b-105">Экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], предназначенный для работы в качестве сервера центрального управления, обслуживает группы серверов, в которых содержатся сведения о соединении для одного или нескольких экземпляров [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2809b-105">An instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is designated as a Central Management Server maintains server groups that contain the connection information for one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2809b-106">Инструкции [!INCLUDE[tsql](../includes/tsql-md.md)] и политики управления на основе политик могут одновременно выполняться для всех групп серверов.</span><span class="sxs-lookup"><span data-stu-id="2809b-106">[!INCLUDE[tsql](../includes/tsql-md.md)] statements and Policy-Based Management policies can be executed at the same time against server groups.</span></span> <span data-ttu-id="2809b-107">Можно также просмотреть файлы журналов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] на экземплярах, управляемых через сервер централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="2809b-107">You can also view the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] log files on instances that are managed through a Central Management Server.</span></span> <span data-ttu-id="2809b-108">Версии [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ранее [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] нельзя назначить в качестве сервера централизованного управления.</span><span class="sxs-lookup"><span data-stu-id="2809b-108">Versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] cannot be designated as a Central Management Server.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="2809b-109">также можно выполнить для локальных групп серверов в окне «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="2809b-109">statements can also be executed against local server groups in Registered Servers.</span></span>  
  
### <a name="related-tasks"></a><span data-ttu-id="2809b-110">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2809b-110">Related Tasks</span></span>  
 <span data-ttu-id="2809b-111">Для создания сервера централизованного управления и групп серверов воспользуйтесь окном **Зарегистрированные серверы** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2809b-111">To create a Central Management Server and server groups, use the **Registered Servers** window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2809b-112">Обратите внимание, что сервер центрального управления не может быть членом группы, которую он обслуживает.</span><span class="sxs-lookup"><span data-stu-id="2809b-112">Note that the Central Management Server cannot be a member of a group that it maintains.</span></span> <span data-ttu-id="2809b-113">Дополнительные сведения о создании центральных серверов управления и групп серверов см. в разделе [Создание центрального сервера управления и группы серверов (среда SQL Server Management Studio)](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="2809b-113">For more information about how to create Central Management Servers and server groups, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2809b-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="2809b-114">See Also</span></span>  
 [<span data-ttu-id="2809b-115">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="2809b-115">Administer Servers by Using Policy-Based Management</span></span>](policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
