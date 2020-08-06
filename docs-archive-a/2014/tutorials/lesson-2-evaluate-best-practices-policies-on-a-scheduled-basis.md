---
title: Занятие 2. Оценка рекомендаций для политик по расписанию | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 37ffad63-d6db-4609-8deb-786200659554
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a454e38ec2f07bf9867183a3894ac4ea001a942e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657437"
---
# <a name="lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis"></a><span data-ttu-id="2490f-102">Урок 2. Выполнение политик рекомендаций по расписанию</span><span class="sxs-lookup"><span data-stu-id="2490f-102">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>
  <span data-ttu-id="2490f-103">Можно настроить запланированные оценки рекомендованных политик на одном или нескольких экземплярах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2490f-103">You can configure scheduled evaluations of best practices policies on one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2490f-104">Чтобы настроить рекомендованные политики на выполнение в соответствии с расписанием, необходимо импортировать эти политики в целевой экземпляр.</span><span class="sxs-lookup"><span data-stu-id="2490f-104">To configure best practices policies to run on a scheduled basis, you must import the policies into the target instance.</span></span>  
  
 <span data-ttu-id="2490f-105">Чтобы развернуть запланированные политики на нескольких серверах, можно импортировать политики на одном экземпляре, настроить расписания для каждой из них, экспортировать запланированные политики в одну из папок, а затем развертывать эти запланированные политики на целевых экземплярах с помощью зарегистрированных серверов.</span><span class="sxs-lookup"><span data-stu-id="2490f-105">To deploy scheduled policies to multiple servers, you can import the policies to one instance, configure the schedules for each policy, export the scheduled policies to a folder, and then deploy the scheduled policies to target instances through Registered Servers.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2490f-106">На целевом экземпляре должен быть запущен [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] или более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="2490f-106">The target instances must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="2490f-107">Автоматизация требует локального сохранения политик на экземпляре, что не поддерживается версиями [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ранее [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2490f-107">Automation requires the policies to be stored locally on the instance, which is not supported by versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="2490f-108">На этом занятии будут выполнены следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2490f-108">In this lesson, you will do the following:</span></span>  
  
-   <span data-ttu-id="2490f-109">Импорт рекомендованных политик в экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2490f-109">Import the best practices policies into an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="2490f-110">Настройка политик на запуск по расписанию.</span><span class="sxs-lookup"><span data-stu-id="2490f-110">Configure the policies to run on a schedule.</span></span>  
  
-   <span data-ttu-id="2490f-111">Развертывание запланированных рекомендованных политик на нескольких экземплярах, управляемых через окно «Зарегистрированные серверы».</span><span class="sxs-lookup"><span data-stu-id="2490f-111">Deploy the scheduled best practices policies to multiple instances through Registered Servers.</span></span>  
  
 <span data-ttu-id="2490f-112">Это занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="2490f-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="2490f-113">Импорт политик в один экземпляр</span><span class="sxs-lookup"><span data-stu-id="2490f-113">Import the Policies to a Single Instance</span></span>](../../2014/tutorials/import-the-policies-to-a-single-instance.md)  
  
-   [<span data-ttu-id="2490f-114">Планирование политик</span><span class="sxs-lookup"><span data-stu-id="2490f-114">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
-   [<span data-ttu-id="2490f-115">Развертывание запланированных политик на нескольких экзмплярах</span><span class="sxs-lookup"><span data-stu-id="2490f-115">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
## <a name="see-also"></a><span data-ttu-id="2490f-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="2490f-116">See Also</span></span>  
 [<span data-ttu-id="2490f-117">Администрирование нескольких серверов с помощью центральных серверов управления</span><span class="sxs-lookup"><span data-stu-id="2490f-117">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
