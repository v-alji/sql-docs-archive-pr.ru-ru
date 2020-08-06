---
title: Урок 2. Настройка разрешений для объектов базы данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
helpviewer_keywords:
- database permissions
ms.assetid: f964b66a-ec32-44c2-a185-6a0f173bfa22
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: fcc6ee3ddf9be072b51bd568fd3e72eb6c871785
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749551"
---
# <a name="lesson-2-configuring-permissions-on-database-objects"></a><span data-ttu-id="822b0-102">Занятие 2. Настройка разрешений на объекты базы данных</span><span class="sxs-lookup"><span data-stu-id="822b0-102">Lesson 2: Configuring Permissions on Database Objects</span></span>
  <span data-ttu-id="822b0-103">Предоставление пользователю доступа к базе данных включает три шага.</span><span class="sxs-lookup"><span data-stu-id="822b0-103">Granting a user access to a database involves three steps.</span></span> <span data-ttu-id="822b0-104">Вначале создается имя входа.</span><span class="sxs-lookup"><span data-stu-id="822b0-104">First, you create a login.</span></span> <span data-ttu-id="822b0-105">Имя входа дает пользователю возможность подключиться к компоненту [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="822b0-105">The login lets the user connect to the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="822b0-106">Затем имя входа настраивается как пользователь в заданной базе данных.</span><span class="sxs-lookup"><span data-stu-id="822b0-106">Then you configure the login as a user in the specified database.</span></span> <span data-ttu-id="822b0-107">Наконец, предоставляются пользовательские разрешения на объекты базы данных.</span><span class="sxs-lookup"><span data-stu-id="822b0-107">And finally, you grant that user permission to database objects.</span></span> <span data-ttu-id="822b0-108">В этом занятии показаны все три шага, а также создание представления и хранимой процедуры в виде объекта.</span><span class="sxs-lookup"><span data-stu-id="822b0-108">This lesson shows you these three steps, and shows you how to create a view and a stored procedure as the object.</span></span>  
  
 <span data-ttu-id="822b0-109">Это занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="822b0-109">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="822b0-110">Создание имени входа</span><span class="sxs-lookup"><span data-stu-id="822b0-110">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
-   [<span data-ttu-id="822b0-111">Предоставление доступа к базе данных</span><span class="sxs-lookup"><span data-stu-id="822b0-111">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
-   [<span data-ttu-id="822b0-112">Создание представлений и хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="822b0-112">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
-   [<span data-ttu-id="822b0-113">Предоставление доступа к объекту базы данных</span><span class="sxs-lookup"><span data-stu-id="822b0-113">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
-   [<span data-ttu-id="822b0-114">Сводка. Настройка разрешений на объекты базы данных</span><span class="sxs-lookup"><span data-stu-id="822b0-114">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="822b0-115">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="822b0-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="822b0-116">Создание имени входа</span><span class="sxs-lookup"><span data-stu-id="822b0-116">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
  
