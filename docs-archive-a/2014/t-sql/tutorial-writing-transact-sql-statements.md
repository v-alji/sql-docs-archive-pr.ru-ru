---
title: Учебник. Составление инструкций Transact-SQL | Документы Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL statements, tutorials
- Transact-SQL tutorials
- tutorials [Transact-SQL]
ms.assetid: 2addc9be-67d0-423d-a457-192fe9d7d058
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ac190d6099bca1a38ca2f286e6ce048fe5322e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750400"
---
# <a name="tutorial-writing-transact-sql-statements"></a><span data-ttu-id="0ecd3-102">Учебник. Составление инструкций Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0ecd3-102">Tutorial: Writing Transact-SQL Statements</span></span>
  <span data-ttu-id="0ecd3-103">Учебник «Составление инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] ».</span><span class="sxs-lookup"><span data-stu-id="0ecd3-103">Welcome to the Writing [!INCLUDE[tsql](../includes/tsql-md.md)] Statements tutorial.</span></span> <span data-ttu-id="0ecd3-104">Этот учебник предназначен для пользователей, не умеющих составлять инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-104">This tutorial is intended for users who are new to writing SQL statements.</span></span> <span data-ttu-id="0ecd3-105">Он поможет новым пользователям начать обучение с просмотра некоторых простых инструкций по созданию таблиц и вставке данных.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-105">It will help new users get started by reviewing some basic statements for creating tables and inserting data.</span></span> <span data-ttu-id="0ecd3-106">Этот учебник использует язык [!INCLUDE[tsql](../includes/tsql-md.md)], [!INCLUDE[msCoName](../includes/msconame-md.md)] -реализацию стандарта SQL.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-106">This tutorial uses [!INCLUDE[tsql](../includes/tsql-md.md)], the [!INCLUDE[msCoName](../includes/msconame-md.md)] implementation of the SQL standard.</span></span> <span data-ttu-id="0ecd3-107">Он представляет собой краткое введение в язык [!INCLUDE[tsql](../includes/tsql-md.md)] и не заменяет обучение языку [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ecd3-107">This tutorial is intended as a brief introduction to the [!INCLUDE[tsql](../includes/tsql-md.md)] language and not as a replacement for a [!INCLUDE[tsql](../includes/tsql-md.md)] class.</span></span> <span data-ttu-id="0ecd3-108">Инструкции в учебнике намеренно простые и не представляют всей сложности типичной производственной базы данных.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-108">The statements in this tutorial are intentionally simple, and are not meant to represent the complexity found in a typical production database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ecd3-109">Новые пользователи баз данных чаще всего считают, что с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] легче работать с помощью среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] вместо инструкций [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ecd3-109">Novice users of databases will usually find it easier to work with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], instead of writing [!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span>  
  
## <a name="finding-more-information"></a><span data-ttu-id="0ecd3-110">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0ecd3-110">Finding More Information</span></span>  
 <span data-ttu-id="0ecd3-111">Дополнительные сведения об отдельных инструкциях см. в электронной документации по SQL Server либо по имени инструкции, либо используя вкладку "Содержание" для просмотра 1800 языковых элементов, перечисленных в алфавитном порядке в разделе [Справочник по Transact-SQL (компонент Database Engine)](/sql/t-sql/language-reference).</span><span class="sxs-lookup"><span data-stu-id="0ecd3-111">To find more information about any specific statement, either search for the statement by name in SQL Server Books Online, or use the Contents to browse the 1,800 language elements listed alphabetically under [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference).</span></span> <span data-ttu-id="0ecd3-112">Еще одной хорошей стратегией нахождения информации является ее поиск по ключевым словам, относящимся к интересующей вас тематике.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-112">Another good strategy for finding information is to search for key words that are related to the subject matter you are interested in.</span></span> <span data-ttu-id="0ecd3-113">Например, чтобы узнать, как возвратить часть даты (например, месяц), выполните поиск в индексе по **датам [SQL Server]** , а затем используйте **функции извлечения частей даты**.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-113">For example, if you want to know how to return a part of a date (such as the month), search the index for **dates [SQL Server]**, and then select **dateparts**.</span></span> <span data-ttu-id="0ecd3-114">Это приведет к разделу [DATEPART (Transact-SQL)](/sql/t-sql/functions/datepart-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0ecd3-114">This takes you to the topic [DATEPART &#40;Transact-SQL&#41;](/sql/t-sql/functions/datepart-transact-sql).</span></span> <span data-ttu-id="0ecd3-115">В качестве другого примера, чтобы выяснить, как работать со строками, ищите **строковые функции**.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-115">As another example, to find out how to work with strings, search for **string functions**.</span></span> <span data-ttu-id="0ecd3-116">Это приведет к разделу [Строковые функции (Transact-SQL)](/sql/t-sql/functions/string-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0ecd3-116">This takes you to the topic [String Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/string-functions-transact-sql).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="0ecd3-117">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="0ecd3-117">What You Will Learn</span></span>  
 <span data-ttu-id="0ecd3-118">В этом учебнике показано, как создать базу данных и таблицу в ней, вставить данные в таблицу, обновить их, прочитать и удалить данные, удалить таблицу.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-118">This tutorial shows you how to create a database, create a table in the database, insert data into the table, update the data, read the data, delete the data, and then delete the table.</span></span> <span data-ttu-id="0ecd3-119">Будут созданы представления и хранимые процедуры, а для базы данных и данных будет настроен пользователь.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-119">You will create views and stored procedures and configure a user to the database and the data.</span></span>  
  
 <span data-ttu-id="0ecd3-120">Учебник разделен на три занятия.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-120">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="0ecd3-121">Урок 1. Создание объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="0ecd3-121">Lesson 1: Creating Database Objects</span></span>](lesson-1-creating-database-objects.md)  
 <span data-ttu-id="0ecd3-122">В этом занятии будет создана база данных, таблица в ней, вставлены данные в таблицу, затем данные будут обновлены и прочитаны.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-122">In this lesson, you create a database, create a table in the database, insert data into the table, update the data, and read the data.</span></span>  
  
 [<span data-ttu-id="0ecd3-123">Урок 2. Настройка разрешений для объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="0ecd3-123">Lesson 2: Configuring Permissions on Database Objects</span></span>](lesson-2-configuring-permissions-on-database-objects.md)  
 <span data-ttu-id="0ecd3-124">В этом занятии будут созданы имя входа и пользователь.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-124">In this lesson, you create a login and user.</span></span> <span data-ttu-id="0ecd3-125">Также будут созданы представление и хранимая процедура, и пользователю будет предоставлено разрешение на нее.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-125">You will also create a view and a stored procedure, and then grant the user permission to the stored procedure.</span></span>  
  
 [<span data-ttu-id="0ecd3-126">Урок 3. Удаление объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="0ecd3-126">Lesson 3: Deleting Database Objects</span></span>](lesson-3-1-deleting-database-objects.md)  
 <span data-ttu-id="0ecd3-127">В этом занятии доступ к данным будет запрещен, данные из таблицы удалены, сама таблица тоже удалена вместе с базой данных.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-127">In this lesson, you remove access to data, delete data from a table, delete the table, and then delete the database.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ecd3-128">Требования</span><span class="sxs-lookup"><span data-stu-id="0ecd3-128">Requirements</span></span>  
 <span data-ttu-id="0ecd3-129">Чтобы завершить этот учебник, не нужно обладать знаниями языка SQL, но нужно иметь основные понятия о базах данных, таких как таблицы.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-129">To complete this tutorial, you do not have to know the SQL language, but you should understand basic database concepts such as tables.</span></span> <span data-ttu-id="0ecd3-130">С помощью этого учебника будут созданы база данных и пользователь Windows.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-130">During this tutorial, you will create a database and create a Windows user.</span></span> <span data-ttu-id="0ecd3-131">Эти задачи требуют высокого уровня разрешений, так что следует войти в систему в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-131">These tasks require a high level of permissions; therefore, you should log in to the computer as an administrator.</span></span>  
  
 <span data-ttu-id="0ecd3-132">В системе должно быть установлено следующее.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-132">Your system must have the following installed:</span></span>  
  
-   <span data-ttu-id="0ecd3-133">Любой выпуск [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ecd3-133">Any edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="0ecd3-134">Среда [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] или Management Studio Express.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-134">Either [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or Management Studio Express.</span></span>  
  
-   <span data-ttu-id="0ecd3-135">Internet Explorer 6 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-135">Internet Explorer 6 or later.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ecd3-136">При просмотре учебников рекомендуется добавить кнопки **Далее** и **назад** на панель инструментов средства просмотра документов.</span><span class="sxs-lookup"><span data-stu-id="0ecd3-136">When you review the tutorials, we recommend that you add the **Next** and **Previous** buttons to the document viewer toolbar.</span></span>  
  
  
