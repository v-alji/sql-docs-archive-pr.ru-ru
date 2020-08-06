---
title: Занятие 1. Создание и применение политики, отключенной по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: d31367db-b7db-44c4-8df2-f1240474cf78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a76df1a72b93d09c5c1c199cb0246dbb51c9cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655680"
---
# <a name="lesson-1-create-and-apply-an-off-by-default-policy"></a><span data-ttu-id="3f073-102">Урок 1. Создание и применение политики, отключенной по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3f073-102">Lesson 1: Create and Apply an Off By Default Policy</span></span>
  <span data-ttu-id="3f073-103">С помощью политик управления на основе политик можно администрировать один или несколько экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], один или несколько объектов экземпляра, экземпляров сервера, баз данных, а также один или несколько объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="3f073-103">Using Policy-Based Management policies, you can administer one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], one or more instance objects, server instances, one or more databases, or one or more database objects.</span></span> <span data-ttu-id="3f073-104">Администратор базы данных должен убедиться, что определенные серверы компонента Database Mail отключены.</span><span class="sxs-lookup"><span data-stu-id="3f073-104">As the database administrator, you want to ensure that certain servers do not have Database Mail enabled.</span></span> <span data-ttu-id="3f073-105">На этом занятии создаются условие и политика, задающие этот параметр сервера.</span><span class="sxs-lookup"><span data-stu-id="3f073-105">In this lesson, you will create a condition and a policy that sets that server option.</span></span> <span data-ttu-id="3f073-106">Выполняется проверка сервера на предмет соответствия политике.</span><span class="sxs-lookup"><span data-stu-id="3f073-106">You will test the server to see whether it complies with the policy.</span></span> <span data-ttu-id="3f073-107">Затем используется политика для изменения настройки сервера с целью приведения его в соответствие.</span><span class="sxs-lookup"><span data-stu-id="3f073-107">Then, you will use the policy to reconfigure the server to bring the server into compliance.</span></span>  
  
 <span data-ttu-id="3f073-108">Это занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="3f073-108">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="3f073-109">Создание политики, отключенной по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3f073-109">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
-   [<span data-ttu-id="3f073-110">Настройка сервера для выполнения политики «Отключено по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="3f073-110">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3f073-111">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="3f073-111">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3f073-112">Создание политики, отключенной по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3f073-112">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="3f073-113">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="3f073-113">Next Lesson</span></span>  
 [<span data-ttu-id="3f073-114">Урок 2. Создание и применение политики стандартов именования</span><span class="sxs-lookup"><span data-stu-id="3f073-114">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
