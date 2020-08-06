---
title: Компонент SQL Server Database Engine | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server]
- SQL Server Database Engine
ms.assetid: 65e2f424-1386-45a6-8912-bd053f434073
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a6c243115e940f7af085c0068d2ca5c277aa5162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655326"
---
# <a name="sql-server-database-engine"></a><span data-ttu-id="6abae-102">Компонент SQL Server Database Engine</span><span class="sxs-lookup"><span data-stu-id="6abae-102">SQL Server Database Engine</span></span>
  <span data-ttu-id="6abae-103">[!INCLUDE[ssDE](../includes/ssde-md.md)] — основная служба для хранения, обработки и защиты данных.</span><span class="sxs-lookup"><span data-stu-id="6abae-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="6abae-104">Компонент [!INCLUDE[ssDE](../includes/ssde-md.md)] обеспечивает управляемый доступ и быструю обработку транзакций, достаточную даже для самых требовательных к предоставляемым данным приложений.</span><span class="sxs-lookup"><span data-stu-id="6abae-104">The [!INCLUDE[ssDE](../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications within your enterprise.</span></span>

 <span data-ttu-id="6abae-105">Компонент [!INCLUDE[ssDE](../includes/ssde-md.md)] используется для создания реляционных баз данных для обработки транзакций в сети или интерактивной аналитической обработки.</span><span class="sxs-lookup"><span data-stu-id="6abae-105">Use the [!INCLUDE[ssDE](../includes/ssde-md.md)] to create relational databases for online transaction processing or online analytical processing data.</span></span> <span data-ttu-id="6abae-106">Сюда входит создание таблиц для хранения данных и объектов баз данных, таких как индексы, представления и хранимые процедуры для просмотра и защиты данных и для управления ими.</span><span class="sxs-lookup"><span data-stu-id="6abae-106">This includes creating tables for storing data, and database objects such as indexes, views, and stored procedures for viewing, managing, and securing data.</span></span> <span data-ttu-id="6abae-107">Для управления объектами баз данных можно использовать среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , для захвата событий сервера — приложение [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6abae-107">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to manage the database objects, and [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to capture server events.</span></span>

 <span data-ttu-id="6abae-108">**Обзор содержимого по области** ![маленький значок папки с файлами](../../2014/integration-services/media/filefolder-small.gif "Маленький значок папки") новые возможности [(ядро СУБД)](whats-new-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="6abae-108">**Browse Content by Area** ![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [What's New (Database Engine)](whats-new-in-sql-server-2016.md)</span></span>

 <span data-ttu-id="6abae-109">![Маленький значок папки с файлами](../../2014/integration-services/media/filefolder-small.gif "Маленький значок папки") [SQL Server ядро СУБД обратной совместимости](sql-server-database-engine-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="6abae-109">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Database Engine Backward Compatibility](sql-server-database-engine-backward-compatibility.md)</span></span>

 <span data-ttu-id="6abae-110">![Маленький значок папки с файлами](../../2014/integration-services/media/filefolder-small.gif "Маленький значок папки") [средства управления SQL Server обратной совместимости](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="6abae-110">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Management Tools Backward Compatibility](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span></span>

 <span data-ttu-id="6abae-111">![Маленький значок папки](../../2014/integration-services/media/filefolder-small.gif "Маленький значок папки") [функции и задачи базы данных](../../2014/database-engine/database-engine-features-and-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="6abae-111">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Database Features and Tasks](../../2014/database-engine/database-engine-features-and-tasks.md)</span></span>

 <span data-ttu-id="6abae-112">![Маленький значок папки с файлами](../../2014/integration-services/media/filefolder-small.gif "Маленький значок папки") [Технический справочник](../../2014/database-engine/technical-reference-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="6abae-112">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Technical Reference](../../2014/database-engine/technical-reference-database-engine.md)</span></span>

 <span data-ttu-id="6abae-113">![Маленький значок папки](../../2014/integration-services/media/filefolder-small.gif "Маленький значок папки") [Справочник по Transact-SQL](/sql/t-sql/language-reference)</span><span class="sxs-lookup"><span data-stu-id="6abae-113">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Transact-SQL Reference](/sql/t-sql/language-reference)</span></span>

 <span data-ttu-id="6abae-114">![Маленький значок папки с файлом](../../2014/integration-services/media/filefolder-small.gif "Маленький значок папки") [справочника XQuery](/sql/xquery/xquery-language-reference-sql-server)</span><span class="sxs-lookup"><span data-stu-id="6abae-114">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [XQuery Reference](/sql/xquery/xquery-language-reference-sql-server)</span></span>

## <a name="see-also"></a><span data-ttu-id="6abae-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="6abae-115">See Also</span></span>
 [<span data-ttu-id="6abae-116">Центр ресурсов SQL Server</span><span class="sxs-lookup"><span data-stu-id="6abae-116">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=219676)


