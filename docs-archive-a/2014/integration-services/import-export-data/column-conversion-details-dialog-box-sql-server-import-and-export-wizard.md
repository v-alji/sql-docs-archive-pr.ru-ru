---
title: Диалоговое окно "Сведения о преобразовании столбца" (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.issuedetails.f1
ms.assetid: e2d00a39-dfbd-4821-a4d8-a5bd1164ed4d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9207e76191060c56acad37db734827579a83aae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666163"
---
# <a name="column-conversion-details-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="8af89-102">Диалоговое окно «Сведения о преобразовании столбца» (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8af89-102">Column Conversion Details Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="8af89-103">Используйте диалоговое окно **сведения о преобразовании столбца** для просмотра подробных сведений о преобразовании отдельного столбца.</span><span class="sxs-lookup"><span data-stu-id="8af89-103">Use the **Column Conversion Details** dialog box to review detailed conversion information about an individual column.</span></span> <span data-ttu-id="8af89-104">Эти сведения содержат тип данных столбца в источнике и назначении, а также преобразование, которое будет выполнено мастером.</span><span class="sxs-lookup"><span data-stu-id="8af89-104">This conversion information contains the column's data type at the source and the destination, and the conversion that the wizard will perform.</span></span> <span data-ttu-id="8af89-105">На этой странице также перечисляются файлы сопоставления типов данных, используемые мастером для определения требуемых преобразований.</span><span class="sxs-lookup"><span data-stu-id="8af89-105">This page also lists the data type mapping files that the wizard uses to determine the data type conversions that are required.</span></span> <span data-ttu-id="8af89-106">Эти файлы устанавливаются в процессе установки служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8af89-106">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs these data type mapping files during setup.</span></span>  
  
 <span data-ttu-id="8af89-107">**Открытие диалогового окна «Сведения о преобразовании столбца»**</span><span class="sxs-lookup"><span data-stu-id="8af89-107">**To open the Column Conversion Details dialog box**</span></span>  
  
1.  <span data-ttu-id="8af89-108">На странице **Просмотр проблем с типами данных** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] мастера импорта и экспорта в списке **Таблица** выберите таблицу.</span><span class="sxs-lookup"><span data-stu-id="8af89-108">On the **Review Data Type Issues** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, in the **Table** list, select a table.</span></span>  
  
2.  <span data-ttu-id="8af89-109">В списке **Сопоставление типов данных** дважды щелкните строку, содержащую столбец, сведения о преобразовании которого необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="8af89-109">In the **Data type mapping** list, double-click the row that contains the column for which you want to view conversion details.</span></span>  
  
 <span data-ttu-id="8af89-110">Дополнительные сведения о [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] мастере импорта и экспорта см. в разделе [SQL Server мастер импорта и экспорта](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8af89-110">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="8af89-111">Дополнительные сведения о параметрах запуска мастера и о разрешениях, необходимых для успешного запуска мастера, см. [в разделе Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8af89-111">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="8af89-112">Мастера импорта и экспорта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предназначен для копирования данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="8af89-112">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="8af89-113">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="8af89-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="8af89-114">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="8af89-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="8af89-115">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8af89-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
  
