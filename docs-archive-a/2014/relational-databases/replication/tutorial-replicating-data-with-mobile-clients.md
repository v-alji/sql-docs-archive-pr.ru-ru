---
title: Руководство. Репликация данных с мобильными клиентами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: af673514-30c7-403a-9d18-d01e1a095115
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdf8be7cb0da11f0aa1022ba656d50c10826ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668746"
---
# <a name="tutorial-replicating-data-with-mobile-clients"></a><span data-ttu-id="1782e-102">Учебник. Репликация данных с мобильными клиентами</span><span class="sxs-lookup"><span data-stu-id="1782e-102">Tutorial: Replicating Data with Mobile Clients</span></span>
  <span data-ttu-id="1782e-103">Репликация является хорошим решением проблемы перемещения данных между центральным сервером и мобильными клиентами, не имеющими постоянного подключения.</span><span class="sxs-lookup"><span data-stu-id="1782e-103">Replication is a good solution to the problem of moving data between a central server and mobile clients that are only occasionally connected.</span></span> <span data-ttu-id="1782e-104">С помощью мастеров репликации можно легко настроить и администрировать топологию репликации.</span><span class="sxs-lookup"><span data-stu-id="1782e-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="1782e-105">В этом учебнике демонстрируется, как настроить топологию репликации для мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="1782e-105">This tutorial shows you how to configure a replication topology for mobile clients.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="1782e-106">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="1782e-106">What You Will Learn</span></span>  
 <span data-ttu-id="1782e-107">В этом учебнике используется репликация слиянием, чтобы опубликовать данные из центральной базы данных для одного или более мобильных пользователей так, что каждый пользователь получит уникальным образом фильтрованное подмножество данных.</span><span class="sxs-lookup"><span data-stu-id="1782e-107">In this tutorial you will use merge replication to publish data from a central database to one or more mobile users so that each user gets a uniquely filtered subset of the data.</span></span> <span data-ttu-id="1782e-108">На первом занятии рассматривается, как создать публикацию при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1782e-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="1782e-109">На последующих занятиях рассматривается, как создать и синхронизировать подписку.</span><span class="sxs-lookup"><span data-stu-id="1782e-109">Later lessons show how to create and synchronize a subscription.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1782e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1782e-110">Requirements</span></span>  
 <span data-ttu-id="1782e-111">Этот учебник предназначен для пользователей, знакомых с основными операциями с базами данных, но имеющих ограниченный опыт работы с репликацией.</span><span class="sxs-lookup"><span data-stu-id="1782e-111">This tutorial is intended for users familiar with fundamental database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="1782e-112">Перед тем как приступить к работе с этим учебником, необходимо освоить [Учебник. Подготовка сервера к репликации](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="1782e-112">Before you start this tutorial, you must complete [Tutorial: Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="1782e-113">Для работы с этим учебником в системе должны быть установлены следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="1782e-113">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   <span data-ttu-id="1782e-114">На сервере-издателе (источник):</span><span class="sxs-lookup"><span data-stu-id="1782e-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="1782e-115">Любой выпуск [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], за исключением Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) или [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1782e-115">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="1782e-116">Эти выпуски не могут быть издателями репликации.</span><span class="sxs-lookup"><span data-stu-id="1782e-116">These editions cannot be a replication Publisher.</span></span>  
  
    -   <span data-ttu-id="1782e-117">Образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1782e-117">The [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="1782e-118">В целях повышения безопасности образцы баз данных по умолчанию не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="1782e-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="1782e-119">На сервере-подписчике (целевом):</span><span class="sxs-lookup"><span data-stu-id="1782e-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="1782e-120">Любой выпуск [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], за исключением [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1782e-120">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="1782e-121">не поддерживается публикацией, созданной в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="1782e-121">is not supported by the publication created in this tutorial.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1782e-122">По умолчанию на [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]репликация не устанавливается.</span><span class="sxs-lookup"><span data-stu-id="1782e-122">Replication is not installed by default on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1782e-123">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]необходимо подключиться к издателю и подписчику с помощью имени входа, которое является членом предопределенной роли сервера sysadmin.</span><span class="sxs-lookup"><span data-stu-id="1782e-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the sysadmin fixed server role.</span></span>  
  
 <span data-ttu-id="1782e-124">**Предполагаемое время выполнения этого учебника: 30 минут.**</span><span class="sxs-lookup"><span data-stu-id="1782e-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="1782e-125">Занятия этого учебника</span><span class="sxs-lookup"><span data-stu-id="1782e-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="1782e-126">Занятие 1. Публикация данных с помощью репликации слиянием</span><span class="sxs-lookup"><span data-stu-id="1782e-126">Lesson 1: Publishing Data Using Merge Replication</span></span>](lesson-1-publishing-data-using-merge-replication.md)  
  
-   [<span data-ttu-id="1782e-127">Занятие 2. Создание подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="1782e-127">Lesson 2: Creating a Subscription to the Merge Publication</span></span>](lesson-2-creating-a-subscription-to-the-merge-publication.md)  
  
 [<span data-ttu-id="1782e-128">Запуск учебника</span><span class="sxs-lookup"><span data-stu-id="1782e-128">Start the Tutorial</span></span>](merge/merge-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="1782e-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="1782e-129">See Also</span></span>  
 [<span data-ttu-id="1782e-130">Основные понятия программирования репликации</span><span class="sxs-lookup"><span data-stu-id="1782e-130">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
