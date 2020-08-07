---
title: Занятие 2. Создание инструкций на языке Transact-SQL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 439cfab5-c049-43a8-8617-59eaa8d24873
author: stevestein
ms.author: sstein
ms.openlocfilehash: 927594c2af09ad3c45a518e7ffb5dc50589a7fe8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731293"
---
# <a name="lesson-2-writing-transact-sql"></a><span data-ttu-id="4d890-102">Занятие 2. Создание инструкций на языке Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d890-102">Lesson 2: Writing Transact-SQL</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="4d890-103">— это интегрированная среда разработки, предназначенная для создания запросов многомерных выражений, запросов расширений интеллектуального анализа данных, запросов на языках [!INCLUDE[tsql](../../includes/tsql-md.md)]и XML, а также команд SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="4d890-103">is an integrated development environment for writing [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX, and XML queries, and SQLCMD commands.</span></span> <span data-ttu-id="4d890-104">Учебник демонстрирует использование редактора запросов компонента ядра СУБД для создания скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d890-104">The tutorial illustrates using the Database Engine Query Editor to write a [!INCLUDE[tsql](../../includes/tsql-md.md)] script.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d890-105">На данном занятии основное внимание уделяется возможностям этого средства.</span><span class="sxs-lookup"><span data-stu-id="4d890-105">This lesson focuses on the features of the tool.</span></span> <span data-ttu-id="4d890-106">Руководство по написанию инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] см. в разделе [Учебник. Составление инструкций Transact-SQL](../../t-sql/tutorial-writing-transact-sql-statements.md).</span><span class="sxs-lookup"><span data-stu-id="4d890-106">For a tutorial on writing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, see [Tutorial: Writing Transact-SQL Statements](../../t-sql/tutorial-writing-transact-sql-statements.md).</span></span>  
  
 <span data-ttu-id="4d890-107">Это занятие содержит следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="4d890-107">This lesson covers the following topics:</span></span>  
  
-   <span data-ttu-id="4d890-108">Соединение с редактором запросов</span><span class="sxs-lookup"><span data-stu-id="4d890-108">Connecting with Query Editor</span></span>  
  
-   <span data-ttu-id="4d890-109">Добавление отступов</span><span class="sxs-lookup"><span data-stu-id="4d890-109">Adding Indentation</span></span>  
  
-   <span data-ttu-id="4d890-110">Развертывание окна редактора запросов</span><span class="sxs-lookup"><span data-stu-id="4d890-110">Maximizing the Query Editor</span></span>  
  
-   <span data-ttu-id="4d890-111">Использование комментариев</span><span class="sxs-lookup"><span data-stu-id="4d890-111">Using Comments</span></span>  
  
-   <span data-ttu-id="4d890-112">Другие способы просмотра окна кода</span><span class="sxs-lookup"><span data-stu-id="4d890-112">Other Ways of Viewing the Code Window</span></span>  
  
-   <span data-ttu-id="4d890-113">Создание сценариев для таблиц</span><span class="sxs-lookup"><span data-stu-id="4d890-113">Scripting a Table</span></span>  
  
-   <span data-ttu-id="4d890-114">Сводка</span><span class="sxs-lookup"><span data-stu-id="4d890-114">Summary</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4d890-115">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="4d890-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4d890-116">Соединение с редактором запросов</span><span class="sxs-lookup"><span data-stu-id="4d890-116">Connecting with Query Editor</span></span>](lesson-2-1-connecting-with-query-editor.md)  
  
  
