---
title: Руководство. Администрирование серверов с помощью управления на основе политик | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: 7de96e7b-9fb8-4cc8-8d85-61345d68a1e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b707a5ecd362c6b3b54e853f89d79e25a9e1428
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657708"
---
# <a name="tutorial-administering-servers-by-using-policy-based-management"></a><span data-ttu-id="1703f-102">Руководство по Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="1703f-102">Tutorial: Administering Servers by Using Policy-Based Management</span></span>
  <span data-ttu-id="1703f-103">Добро пожаловать в учебник по администрированию серверов с помощью политик управления на основе политик.</span><span class="sxs-lookup"><span data-stu-id="1703f-103">Welcome to the Administering Servers by Using Policy-Based Management Policies tutorial.</span></span> <span data-ttu-id="1703f-104">Этот учебник предназначен для пользователей, знакомых с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , но новичков в управлении на основе политик.</span><span class="sxs-lookup"><span data-stu-id="1703f-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but new to the Policy-Based Management.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="1703f-105">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="1703f-105">What You Will Learn</span></span>  
 <span data-ttu-id="1703f-106">Данный учебник создает политику администрирования сервера, а также политику, применяемую к одиночной базе данных.</span><span class="sxs-lookup"><span data-stu-id="1703f-106">This tutorial creates a policy to administer your server and a policy that applies to a single database.</span></span> <span data-ttu-id="1703f-107">Одна политика запускается по запросу для проверки на соответствие.</span><span class="sxs-lookup"><span data-stu-id="1703f-107">One policy is run on demand to test for compliance.</span></span> <span data-ttu-id="1703f-108">Другая политика обеспечивает будущее соответствие.</span><span class="sxs-lookup"><span data-stu-id="1703f-108">The other policy enforces future compliance.</span></span>  
  
 <span data-ttu-id="1703f-109">Учебник разделен на два занятия.</span><span class="sxs-lookup"><span data-stu-id="1703f-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="1703f-110">Урок 1. Создание и применение политики, отключенной по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1703f-110">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
 <span data-ttu-id="1703f-111">На данном занятии создается политика, указывающая, что компонент Database Mail не включен на сервере.</span><span class="sxs-lookup"><span data-stu-id="1703f-111">This lesson creates a policy that specifies that Database Mail is not enabled on the server.</span></span> <span data-ttu-id="1703f-112">Затем выполняется проверка сервера на соответствие политике и его настройка путем отключения компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="1703f-112">Then, it checks to see whether your server complies with the policy, and configures the server by disabling Database Mail.</span></span>  
  
 [<span data-ttu-id="1703f-113">Урок 2. Создание и применение политики стандартов именования</span><span class="sxs-lookup"><span data-stu-id="1703f-113">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
 <span data-ttu-id="1703f-114">Данное занятие создает политику, определяющую и обеспечивающую стандарт именования таблиц.</span><span class="sxs-lookup"><span data-stu-id="1703f-114">This lesson creates a policy that defines and enforces a naming standard for tables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1703f-115">Требования</span><span class="sxs-lookup"><span data-stu-id="1703f-115">Requirements</span></span>  
 <span data-ttu-id="1703f-116">Для выполнения этого занятия требуются основные знания о базах данных и основные сведения о [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1703f-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1703f-117">Для работы с этим учебником необходима установка среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1703f-117">To use this tutorial, your system must have [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="1703f-118">Приступить к изучению</span><span class="sxs-lookup"><span data-stu-id="1703f-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="1703f-119">Урок 1. Создание и применение политики, отключенной по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1703f-119">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="1703f-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="1703f-120">See Also</span></span>  
 [<span data-ttu-id="1703f-121">Администрирование серверов с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="1703f-121">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
