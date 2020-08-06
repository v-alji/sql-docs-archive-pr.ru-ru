---
title: Предоставление доступа к базе данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database access
ms.assetid: 686edfe2-3650-48a6-a2da-9d46fa211ad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45b6d6c8dcd9c04d18489807271802aafee785b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667998"
---
# <a name="granting-access-to-a-database"></a><span data-ttu-id="8d9b2-102">Предоставление доступа к базе данных</span><span class="sxs-lookup"><span data-stu-id="8d9b2-102">Granting Access to a Database</span></span>
  <span data-ttu-id="8d9b2-103">Теперь Mary имеет доступ к данному экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], но не имеет разрешения на доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="8d9b2-103">Mary now has access to this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but does not have permission to access the databases.</span></span> <span data-ttu-id="8d9b2-104">У нее даже нет доступа к своей базе данных по умолчанию **TestData** , пока вы не авторизируете ее в качестве пользователя базы данных.</span><span class="sxs-lookup"><span data-stu-id="8d9b2-104">She does not even have access to her default database **TestData** until you authorize her as a database user.</span></span>  
  
 <span data-ttu-id="8d9b2-105">Чтобы предоставить Mary доступ, переключитесь на базу данных **TestData** и при помощи инструкции CREATE USER сопоставьте ее имя входа с именем пользователя «Mary».</span><span class="sxs-lookup"><span data-stu-id="8d9b2-105">To grant Mary access, switch to the **TestData** database, and then use the CREATE USER statement to map her login to a user named Mary.</span></span>  
  
### <a name="to-create-a-user-in-a-database"></a><span data-ttu-id="8d9b2-106">Создание пользователя в базе данных</span><span class="sxs-lookup"><span data-stu-id="8d9b2-106">To create a user in a database</span></span>  
  
1.  <span data-ttu-id="8d9b2-107">Введите и выполните следующие инструкции (заменяя `computer_name` на имя компьютера), чтобы предоставить пользователю `Mary` доступ к базе данных `TestData` .</span><span class="sxs-lookup"><span data-stu-id="8d9b2-107">Type and execute the following statements (replacing `computer_name` with the name of your computer) to grant `Mary` access to the `TestData` database.</span></span>  
  
    ```  
    USE [TestData];  
    GO  
  
    CREATE USER [Mary] FOR LOGIN [computer_name\Mary];  
    GO  
  
    ```  
  
     <span data-ttu-id="8d9b2-108">Теперь пользователь Mary имеет доступ к [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и к базе данных `TestData` .</span><span class="sxs-lookup"><span data-stu-id="8d9b2-108">Now, Mary has access to both [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and the `TestData` database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8d9b2-109">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="8d9b2-109">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8d9b2-110">Создание представлений и хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="8d9b2-110">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
  
