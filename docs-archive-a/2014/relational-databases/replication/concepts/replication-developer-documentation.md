---
title: Пошаговое руководством для разработчиков&#39;(репликация) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- developer's guide [SQL Server replication]
- programming [SQL Server replication]
- replication [SQL Server], development
ms.assetid: 7ee134ae-1cab-4a35-8017-8ac6d8fc64b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d9651aec1f02d19ea3494abf242f75049a4f33f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736242"
---
# <a name="developer39s-guide-replication"></a><span data-ttu-id="95aa6-102">Руководством разработчика&#39;(репликация)</span><span class="sxs-lookup"><span data-stu-id="95aa6-102">Developer&#39;s Guide (Replication)</span></span>
  <span data-ttu-id="95aa6-103">Возможность настраивать, сопровождать и осуществлять программным путем наблюдение за топологией репликации позволяет упростить повторное выполнение задачи репликации и повысить удобство работы пользователей с приложениями на основе репликации.</span><span class="sxs-lookup"><span data-stu-id="95aa6-103">The ability to programmatically configure, maintain, and monitor a replication topology enables you to both simplify repeated replication tasks and improve the user experience for your replication-based applications.</span></span> <span data-ttu-id="95aa6-104">Благодаря программной реализации средств репликации конечные пользователи получают возможность применять настраиваемые функциональные средства репликации, не будучи вынужденными изучать хранимые процедуры репликации и знакомиться с исполняемыми файлами агентов репликации или прибегать к использованию пользовательского интерфейса репликации, реализованного в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95aa6-104">By programming replication, your end-users can be provided with customized replication functionalities without having to be familiar with replication stored procedures and replication agent executables or having to using the replication user interface implemented by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="95aa6-105">Ниже описаны ситуации, в которых можно было бы усовершенствовать приложения путем предоставления программного доступа к службам репликации.</span><span class="sxs-lookup"><span data-stu-id="95aa6-105">The following are scenarios in which your applications might benefit from programmatic access to replication services:</span></span>  
  
-   <span data-ttu-id="95aa6-106">Добавление к существующему приложению конечного пользователя таких функциональных средств репликации, как синхронизация подписки по запросу, осуществляемая после нажатия кнопки пользователем.</span><span class="sxs-lookup"><span data-stu-id="95aa6-106">Adding replication functionalities to an existing end-user application, such as synchronizing a pull subscription when the user clicks a button.</span></span>   
-   <span data-ttu-id="95aa6-107">Создание пользовательского веб-интерфейса для дистанционного управления репликацией.</span><span class="sxs-lookup"><span data-stu-id="95aa6-107">Creating a Web-based user interface for remotely administering replication.</span></span>    
-   <span data-ttu-id="95aa6-108">Создание настраиваемого пользовательского интерфейса, который предоставляет доступ только к определенному подмножеству функциональных средств администрирования и может использоваться для дистанционного управления несколькими топологиями репликации из одного места или сочетает в себе функциональные возможности администрирования и синхронизации.</span><span class="sxs-lookup"><span data-stu-id="95aa6-108">Creating a custom user interface that exposes only a subset of administration functionality, can be used to remotely administer multiple replication topologies from a single location, or that combine administration and synchronization functionalities.</span></span>    
-   <span data-ttu-id="95aa6-109">Усовершенствование одного из существующих инструментальных средств наблюдения путем добавления возможности наблюдения за состоянием публикации, подписки или распространителя.</span><span class="sxs-lookup"><span data-stu-id="95aa6-109">Improving an existing monitoring tool by adding the ability to monitor the status of a publication, subscription, or at the Distributor.</span></span>    
-   <span data-ttu-id="95aa6-110">Создание пользовательского приложения для управления или синхронизации подписок на издателе Oracle.</span><span class="sxs-lookup"><span data-stu-id="95aa6-110">Creating a custom application to administer or synchronize subscriptions to an Oracle publisher.</span></span>    
-   <span data-ttu-id="95aa6-111">Написание настраиваемых бизнес-правил, выполняемых при синхронизации подписки на публикацию слиянием.</span><span class="sxs-lookup"><span data-stu-id="95aa6-111">Writing customized business rules that are executed when a merge subscription is synchronized.</span></span>    
-   <span data-ttu-id="95aa6-112">Формирование скриптов [!INCLUDE[tsql](../../../includes/tsql-md.md)], которые могут выполняться повторно при настройке новых подписчиков.</span><span class="sxs-lookup"><span data-stu-id="95aa6-112">Generating [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts that can be run repeated when configuring new Subscribers.</span></span>  
  
 <span data-ttu-id="95aa6-113">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] предусмотрена возможность управлять программным путем агентами репликации, а также осуществлять программное управление и текущее наблюдение за топологией репликации.</span><span class="sxs-lookup"><span data-stu-id="95aa6-113">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] enables you to programmatically control replication agents and to programmatically administer and monitor a replication topology.</span></span> <span data-ttu-id="95aa6-114">Дополнительные сведения о программировании репликации см. в статье [Основные понятия программирования репликации](replication-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="95aa6-114">To learn more about programming replication, see [Replication Programming Concepts](replication-programming-concepts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95aa6-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="95aa6-115">In This Section</span></span>  
 [<span data-ttu-id="95aa6-116">Основные понятия программирования репликации</span><span class="sxs-lookup"><span data-stu-id="95aa6-116">Replication Programming Concepts</span></span>](replication-programming-concepts.md)  
 <span data-ttu-id="95aa6-117">Описывает шаги планирования, связанные с разработкой приложения, в котором используется репликация.</span><span class="sxs-lookup"><span data-stu-id="95aa6-117">Describes the planning steps to develop an application that uses replication.</span></span>  
  
 [<span data-ttu-id="95aa6-118">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="95aa6-118">Replication System Stored Procedures Concepts</span></span>](replication-system-stored-procedures-concepts.md)  
 <span data-ttu-id="95aa6-119">Описывает способы использования системных хранимых процедур для предоставления программного доступа в топологии репликации.</span><span class="sxs-lookup"><span data-stu-id="95aa6-119">Describes how system stored procedures can be used to proivide programmatic access in a replication topology.</span></span>  
  
 [<span data-ttu-id="95aa6-120">Основные понятия объектов RMO</span><span class="sxs-lookup"><span data-stu-id="95aa6-120">Replication Management Objects Concepts</span></span>](replication-management-objects-concepts.md)  
 <span data-ttu-id="95aa6-121">Содержит основные понятия, связанные с использованием объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="95aa6-121">Explains the concepts for using Replication Management Objects (RMO).</span></span> <span data-ttu-id="95aa6-122">Это — сборка управляемого кода, которая инкапсулирует функциональные возможности репликации для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95aa6-122">This is a managed code assembly that encapsulates replication functionalities for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="95aa6-123">Replication Agent Executables Concepts</span><span class="sxs-lookup"><span data-stu-id="95aa6-123">Replication Agent Executables Concepts</span></span>](replication-agent-executables-concepts.md)  
 <span data-ttu-id="95aa6-124">Описывает использование исполняемых файлов агента репликации.</span><span class="sxs-lookup"><span data-stu-id="95aa6-124">Describes the use of Replication Agent Executable files.</span></span>  

  
  
