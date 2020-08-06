---
title: Диалоговое окно "Просмотр данных" (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.previewdata.f1
ms.assetid: 423ac26a-ba02-4fdf-88b4-07995fe4a97e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 17debc001d8ba7826fe845c006e944e5a3dc87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666146"
---
# <a name="preview-data-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="cec6e-102">Диалоговое окно «Просмотр данных» (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cec6e-102">Preview Data Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="cec6e-103">Используйте диалоговое окно **Просмотр данных** , чтобы просмотреть запрос, который [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Мастер импорта и экспорта будет отправлять в источник данных.</span><span class="sxs-lookup"><span data-stu-id="cec6e-103">Use the **Preview Data** dialog box to see the query that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard will send to the data source.</span></span> <span data-ttu-id="cec6e-104">Это диалоговое окно можно также использовать для просмотра до 200 строк образца данных.</span><span class="sxs-lookup"><span data-stu-id="cec6e-104">You can also use this dialog box to preview up to 200 rows of sample data.</span></span>  
  
 <span data-ttu-id="cec6e-105">Дополнительные сведения о [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] мастере импорта и экспорта см. в разделе [SQL Server мастер импорта и экспорта](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="cec6e-105">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="cec6e-106">Дополнительные сведения о параметрах запуска мастера и о разрешениях, необходимых для успешного запуска мастера, см. [в разделе Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="cec6e-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="cec6e-107">Мастера импорта и экспорта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предназначен для копирования данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="cec6e-107">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="cec6e-108">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="cec6e-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="cec6e-109">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="cec6e-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="cec6e-110">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="cec6e-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
 <span data-ttu-id="cec6e-111">**Открытие диалогового окна «Просмотр данных»**</span><span class="sxs-lookup"><span data-stu-id="cec6e-111">**To open the Preview Data dialog box**</span></span>  
  
-   <span data-ttu-id="cec6e-112">На странице **Выбор исходных таблиц и представлений** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] мастера импорта и экспорта нажмите кнопку **Предварительный просмотр**.</span><span class="sxs-lookup"><span data-stu-id="cec6e-112">On the **Select Source Tables and Views** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, click **Preview**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cec6e-113">Варианты</span><span class="sxs-lookup"><span data-stu-id="cec6e-113">Options</span></span>  
 <span data-ttu-id="cec6e-114">**Source**</span><span class="sxs-lookup"><span data-stu-id="cec6e-114">**Source**</span></span>  
 <span data-ttu-id="cec6e-115">Отображает запрос, посылаемый мастером источнику данных.</span><span class="sxs-lookup"><span data-stu-id="cec6e-115">Displays the query that the wizard will send to the data source.</span></span>  
  
 <span data-ttu-id="cec6e-116">**Сетка образца данных**</span><span class="sxs-lookup"><span data-stu-id="cec6e-116">**Sample data grid**</span></span>  
 <span data-ttu-id="cec6e-117">Отображает до 200 строк образца данных, возвращаемых запросом.</span><span class="sxs-lookup"><span data-stu-id="cec6e-117">Displays up to 200 rows of sample data that the query returned.</span></span>  
  
  
