---
title: Руководство. Репликация данных между постоянно соединенными серверами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- tutorials [SQL Server replication]
- replication [SQL Server], tutorials
- wizards [SQL Server replication]
ms.assetid: 7b18a04a-2c3d-4efe-a0bc-c3f92be72fd0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 415cac62112c1c1d2aa6c42ec189c2614ec03923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668748"
---
# <a name="tutorial-replicating-data-between-continuously-connected-servers"></a><span data-ttu-id="48f40-102">Учебник. Репликация данных между постоянно соединенными серверами</span><span class="sxs-lookup"><span data-stu-id="48f40-102">Tutorial: Replicating Data Between Continuously Connected Servers</span></span>
  <span data-ttu-id="48f40-103">Репликация представляет собой хорошее решение проблемы перемещения данных между постоянно соединенными серверами.</span><span class="sxs-lookup"><span data-stu-id="48f40-103">Replication is a good solution to the problem of moving data between continuously connected servers.</span></span> <span data-ttu-id="48f40-104">С помощью мастеров репликации можно легко настроить и администрировать топологию репликации.</span><span class="sxs-lookup"><span data-stu-id="48f40-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="48f40-105">В этом учебники рассказывается о настройке топологии репликации для постоянно соединенных серверов.</span><span class="sxs-lookup"><span data-stu-id="48f40-105">This tutorial shows you how to configure a replication topology for continuously connected servers.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="48f40-106">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="48f40-106">What You Will Learn</span></span>  
 <span data-ttu-id="48f40-107">В этом учебнике рассказывается о публикации данных из одной базы данных в другую при помощи репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="48f40-107">This tutorial will show you how to publish data from one database to another using transactional replication.</span></span> <span data-ttu-id="48f40-108">На первом занятии рассматривается, как создать публикацию при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48f40-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="48f40-109">На дальнейших занятиях разбирается создание и проверка подписки, а также измерение задержки.</span><span class="sxs-lookup"><span data-stu-id="48f40-109">Later lessons show how to create and validate a subscription and how to measure latency.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f40-110">Требования</span><span class="sxs-lookup"><span data-stu-id="48f40-110">Requirements</span></span>  
 <span data-ttu-id="48f40-111">Этот учебник предназначен для пользователей, знакомых с основными операциями с базами данных, но имеющих ограниченный опыт в работе с репликацией.</span><span class="sxs-lookup"><span data-stu-id="48f40-111">This tutorial is intended for users who are familiar with basic database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="48f40-112">Для работы с этим учебником требуется завершить работу с предыдущим учебником, [Подготовка сервера для репликации](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="48f40-112">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="48f40-113">Для работы с этим учебником должны быть установлены следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="48f40-113">To use this tutorial, your system must have the following components:</span></span>  
  
-   <span data-ttu-id="48f40-114">На сервере-издателе (источник):</span><span class="sxs-lookup"><span data-stu-id="48f40-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="48f40-115">Любой выпуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], за исключением Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) или [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f40-115">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="48f40-116">Эти выпуски не могут быть издателями репликации.</span><span class="sxs-lookup"><span data-stu-id="48f40-116">These editions cannot be replication Publishers.</span></span>  
  
    -   [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] <span data-ttu-id="48f40-117">.</span><span class="sxs-lookup"><span data-stu-id="48f40-117">sample database.</span></span> <span data-ttu-id="48f40-118">В целях повышения безопасности образцы баз данных по умолчанию не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="48f40-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="48f40-119">На сервере-подписчике (целевом):</span><span class="sxs-lookup"><span data-stu-id="48f40-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="48f40-120">Любой выпуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], за исключением [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48f40-120">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="48f40-121">не может быть подписчиком в репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="48f40-121">cannot be a Subscriber in transactional replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="48f40-122">Репликация не устанавливается по умолчанию на [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48f40-122">Replication is not installed on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48f40-123">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] среде необходимо соединиться с издателем и подписчиком, используя имя входа, которое является членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="48f40-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="48f40-124">**Предполагаемое время выполнения этого учебника: 30 минут.**</span><span class="sxs-lookup"><span data-stu-id="48f40-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="48f40-125">Занятия этого учебника</span><span class="sxs-lookup"><span data-stu-id="48f40-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="48f40-126">Урок 1. Публикация данных с помощью репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="48f40-126">Lesson 1: Publishing Data Using Transactional Replication</span></span>](lesson-1-publishing-data-using-transactional-replication.md)  
  
-   [<span data-ttu-id="48f40-127">Занятие 2. Создание подписки на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="48f40-127">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>](lesson-2-creating-a-subscription-to-the-transactional-publication.md)  
  
-   [<span data-ttu-id="48f40-128">Занятие 3. Проверка подписки и измерение задержки</span><span class="sxs-lookup"><span data-stu-id="48f40-128">Lesson 3: Validating the Subscription and Measuring Latency</span></span>](lesson-3-validating-the-subscription-and-measuring-latency.md)  
  
 [<span data-ttu-id="48f40-129">Запуск учебника</span><span class="sxs-lookup"><span data-stu-id="48f40-129">Start the Tutorial</span></span>](transactional/transactional-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="48f40-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="48f40-130">See Also</span></span>  
 [<span data-ttu-id="48f40-131">Основные понятия программирования репликации</span><span class="sxs-lookup"><span data-stu-id="48f40-131">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
