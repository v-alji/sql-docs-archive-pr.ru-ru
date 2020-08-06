---
title: Проверка целостности базы данных с потенциально поврежденными страницами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3b1ec9fe-f6c5-46f7-aa63-6e671be1572d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cc1f87917c78f34ec7722fa21a1a67fda40a8c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728221"
---
# <a name="check-integrity-of-database-with-suspect-pages"></a><span data-ttu-id="35a4f-102">Проверка целостности базы данных с потенциально поврежденными страницами</span><span class="sxs-lookup"><span data-stu-id="35a4f-102">Check Integrity of Database with Suspect Pages</span></span>
  <span data-ttu-id="35a4f-103">Это правило проверяет, находится ли пользовательские базы данных в подозрительном состоянии.</span><span class="sxs-lookup"><span data-stu-id="35a4f-103">This rule checks for user databases that have the database status set to suspect.</span></span> <span data-ttu-id="35a4f-104">Когда компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] считывает страницу базы данных, содержащую ошибку 824, страница помечается как потенциально поврежденная, ее идентификатор записывается в таблицу suspect_pages в msdb, а база данных, содержащая эту страницу, также помечается как подозрительная.</span><span class="sxs-lookup"><span data-stu-id="35a4f-104">When the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] reads a database page that contains an 824 error, the page is considered suspect, its page ID is recorded in the suspect_pages table in msdb, and the database that contains the page is set to suspect.</span></span>  
  
 <span data-ttu-id="35a4f-105">Ошибка 824 означает, что в ходе операции считывания была обнаружена ошибка логической согласованности данных.</span><span class="sxs-lookup"><span data-stu-id="35a4f-105">Error 824 indicates that a logical consistency error was detected during a read operation.</span></span> <span data-ttu-id="35a4f-106">Часто эта ошибка свидетельствует о повреждении данных, вызванном сбоями компонента подсистемы ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="35a4f-106">This error frequently indicates data corruption caused by a faulty I/O subsystem component.</span></span> <span data-ttu-id="35a4f-107">Это серьезная ошибка, которая угрожает целостности базы данных, поэтому она должна быть немедленно исправлена.</span><span class="sxs-lookup"><span data-stu-id="35a4f-107">This is a severe error condition that threatens database integrity and must be corrected immediately.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="35a4f-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="35a4f-108">Best Practices Recommendations</span></span>  
  
-   <span data-ttu-id="35a4f-109">Проверьте в журнале ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] наличие сведений об ошибке 824 для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="35a4f-109">Review the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the details of the 824 error for this database.</span></span>  
  
-   <span data-ttu-id="35a4f-110">Выполните полную проверку согласованности базы данных ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="35a4f-110">Complete a full database consistency check ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span></span>  
  
-   <span data-ttu-id="35a4f-111">Выполните действия, описанные в разделе [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span><span class="sxs-lookup"><span data-stu-id="35a4f-111">Implement the user actions that are defined in [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="35a4f-112">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="35a4f-112">For More Information</span></span>  
 [<span data-ttu-id="35a4f-113">Управление таблицей suspect_pages (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="35a4f-113">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
