---
title: Учебник. Оценка рекомендаций с помощью управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- best practices analyzer
- Policy-Based Management, best practices policies
- Best Practices [Database Engine]
- Policy-Based Management, evaluating policies
- BPA
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: c7867f9b-7acc-4fae-bde1-63808c403ebc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 42e6b505c71abecce7b56b5cb2544b4e9f4e8f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733338"
---
# <a name="tutorial-evaluating-best-practices-by-using-policy-based-management"></a><span data-ttu-id="a20f1-102">Руководство по Выполнение политик рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="a20f1-102">Tutorial: Evaluating Best Practices by Using Policy-Based Management</span></span>
  <span data-ttu-id="a20f1-103">Добро пожаловать в учебник по выполнению рекомендаций с помощью управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="a20f1-103">Welcome to the Evaluating Best Practices by Using Policy-Based Management tutorial.</span></span> <span data-ttu-id="a20f1-104">Этот учебник предназначен для пользователей, имеющих представление о [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], но незнакомых с управлением на основе политик.</span><span class="sxs-lookup"><span data-stu-id="a20f1-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but new to Policy-Based Management.</span></span> <span data-ttu-id="a20f1-105">Управление на основе политик — это система определения политик, которые можно использовать для обеспечения принудительного выполнения стандартов администрирования.</span><span class="sxs-lookup"><span data-stu-id="a20f1-105">Policy-Based Management is a system for defining policies that can be used enforce site administration standards.</span></span> <span data-ttu-id="a20f1-106">Управление на основе политик подразумевает использование набора рекомендуемых политик, которые могут быть использованы для анализа экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и дают возможность определить, соответствует ли он советам и рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="a20f1-106">Policy-Based Management includes a set of best practices policies that you can use to analyze an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to determine whether the instance meets best practices guidelines and recommendations.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="a20f1-107">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="a20f1-107">What You Will Learn</span></span>  
 <span data-ttu-id="a20f1-108">В этом учебнике будет показано, как выполнять рекомендованные политики для компонента [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] на основе метода оценки политики по требованию (называемого также нерегламентированным) или по расписанию.</span><span class="sxs-lookup"><span data-stu-id="a20f1-108">In this tutorial, you will learn how to evaluate best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on an on-demand (or "ad hoc") basis, or on a scheduled basis.</span></span>  
  
 <span data-ttu-id="a20f1-109">Учебник разделен на два занятия.</span><span class="sxs-lookup"><span data-stu-id="a20f1-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="a20f1-110">Урок 1. Выполнение политик рекомендаций по запросу</span><span class="sxs-lookup"><span data-stu-id="a20f1-110">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
 <span data-ttu-id="a20f1-111">На этом занятии будет выполнено выполнение по запросу рекомендованных политик на одном или нескольких экземплярах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a20f1-111">In this lesson, you perform an on-demand evaluation of the policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a20f1-112">Урок 2. Выполнение политик рекомендаций по расписанию</span><span class="sxs-lookup"><span data-stu-id="a20f1-112">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
 <span data-ttu-id="a20f1-113">На этом занятии будет выполнена настройка рекомендованных политик для запуска по расписанию.</span><span class="sxs-lookup"><span data-stu-id="a20f1-113">In this lesson, you configure best practices policies to run on a scheduled basis.</span></span> <span data-ttu-id="a20f1-114">Занятие показывает, как произвести настройку запланированных политик на единственном экземпляре и развернуть запланированные политики из центрального местоположения на нескольких экземплярах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a20f1-114">The lesson shows how to configure scheduled policies on a single instance, and how to deploy scheduled policies from a central location to multiple instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a20f1-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a20f1-115">Requirements</span></span>  
 <span data-ttu-id="a20f1-116">Для выполнения этого занятия требуются основные знания о базах данных и основные сведения о [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a20f1-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a20f1-117">Для работы с этим учебником на сервере должна быть установлена среда [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a20f1-117">To use this tutorial, the server must have [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="a20f1-118">Приступить к изучению</span><span class="sxs-lookup"><span data-stu-id="a20f1-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="a20f1-119">Урок 1. Выполнение политик рекомендаций по запросу</span><span class="sxs-lookup"><span data-stu-id="a20f1-119">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="a20f1-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="a20f1-120">See Also</span></span>  
 [<span data-ttu-id="a20f1-121">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="a20f1-121">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
