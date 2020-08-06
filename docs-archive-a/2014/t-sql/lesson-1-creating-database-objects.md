---
title: Урок 1. Создание объектов базы данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
ms.assetid: 9fb8656b-0e4e-4ada-b404-4db4d3eea995
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 172fdbcaedc10f9c359befd48ed09ec825aea9bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735765"
---
# <a name="lesson-1-creating-database-objects"></a><span data-ttu-id="83f44-102">Урок 1. Создание объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="83f44-102">Lesson 1: Creating Database Objects</span></span>
  <span data-ttu-id="83f44-103">На этом занятии вы узнаете, как создать базу данных, создать таблицу в базе данных и получить доступ к данным таблицы и изменить их.</span><span class="sxs-lookup"><span data-stu-id="83f44-103">This lesson shows you how to create a database, create a table in the database, and then access and change the data in the table.</span></span> <span data-ttu-id="83f44-104">Поскольку это занятие является введением к использованию языка [!INCLUDE[tsql](../includes/tsql-md.md)], в нем не используются и не описываются многие параметры, доступные для этих инструкций.</span><span class="sxs-lookup"><span data-stu-id="83f44-104">Because this lesson is an introduction to using [!INCLUDE[tsql](../includes/tsql-md.md)], it does not use or describe the many options that are available for these statements.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="83f44-105">могут быть написаны и пересланы компоненту [!INCLUDE[ssDE](../includes/ssde-md.md)] следующими способами:</span><span class="sxs-lookup"><span data-stu-id="83f44-105">statements can be written and submitted to the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="83f44-106">При помощи среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83f44-106">By using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="83f44-107">Предполагается, что вы используете среду [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], но можно также использовать среду [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, которая может быть загружена бесплатно с веб-узла [центра загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=14630).</span><span class="sxs-lookup"><span data-stu-id="83f44-107">This tutorial assumes that you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], but you can also use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Express, which is available as a free download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=14630).</span></span>  
  
-   <span data-ttu-id="83f44-108">Посредством программы [sqlcmd](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="83f44-108">By using the [sqlcmd utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="83f44-109">Соединившись из создаваемого приложения.</span><span class="sxs-lookup"><span data-stu-id="83f44-109">By connecting from an application that you create.</span></span>  
  
 <span data-ttu-id="83f44-110">Исходный код исполняется в компоненте [!INCLUDE[ssDE](../includes/ssde-md.md)] таким же образом и с теми же разрешениями, независимо от того, как был передан исходный код инструкций.</span><span class="sxs-lookup"><span data-stu-id="83f44-110">The code executes on the [!INCLUDE[ssDE](../includes/ssde-md.md)] in the same way and with the same permissions, regardless of how you submit the code statements.</span></span>  
  
 <span data-ttu-id="83f44-111">Чтобы выполнить инструкцию языка [!INCLUDE[tsql](../includes/tsql-md.md)] в среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], откройте среду [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] и соединитесь с экземпляром компонента [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83f44-111">To run [!INCLUDE[tsql](../includes/tsql-md.md)] statements in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], open [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="83f44-112">Это занятие содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="83f44-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="83f44-113">Создание базы данных (учебник)</span><span class="sxs-lookup"><span data-stu-id="83f44-113">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
-   [<span data-ttu-id="83f44-114">Создание таблицы (учебник)</span><span class="sxs-lookup"><span data-stu-id="83f44-114">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
-   [<span data-ttu-id="83f44-115">Вставка данных в таблицу и их обновление (учебник)</span><span class="sxs-lookup"><span data-stu-id="83f44-115">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
-   [<span data-ttu-id="83f44-116">Чтение данных из таблицы (учебник)</span><span class="sxs-lookup"><span data-stu-id="83f44-116">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
-   [<span data-ttu-id="83f44-117">Сводка. Создание объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="83f44-117">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="83f44-118">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="83f44-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="83f44-119">Создание базы данных (учебник)</span><span class="sxs-lookup"><span data-stu-id="83f44-119">Creating a Database &#40;Tutorial&#41;</span></span>](lesson-1-1-creating-a-database.md)  
  
  
