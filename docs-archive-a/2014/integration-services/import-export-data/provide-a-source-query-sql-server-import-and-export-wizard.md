---
title: Определение исходного запроса (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.providesourcequery.f1
ms.assetid: c8cbd07e-b9c3-422f-94b8-d6fc8cf31cf5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b21100f51c279e9ba764c8f82565af9d6e391ef3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666143"
---
# <a name="provide-a-source-query-sql-server-import-and-export-wizard"></a><span data-ttu-id="c0ed9-102">Определение исходного запроса (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c0ed9-102">Provide a Source Query (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="c0ed9-103">Используйте страницу **Указание исходного запроса** , чтобы ввести инструкцию SQL, которая будет формировать данные для копирования из источника данных в место назначения.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-103">Use the **Provide a Source Query** page to type the SQL statement that will generate the data to copy from the data source to the destination.</span></span>  
  
 <span data-ttu-id="c0ed9-104">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c0ed9-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="c0ed9-105">Дополнительные сведения о параметрах запуска мастера, а также о разрешениях, необходимых для успешного запуска мастера, см. в разделе [Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c0ed9-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="c0ed9-106">Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="c0ed9-107">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="c0ed9-108">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="c0ed9-109">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c0ed9-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0ed9-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="c0ed9-110">Options</span></span>  
 <span data-ttu-id="c0ed9-111">**Инструкция SQL**</span><span class="sxs-lookup"><span data-stu-id="c0ed9-111">**SQL statement**</span></span>  
 <span data-ttu-id="c0ed9-112">Инструкция запроса для извлечения нужных строк данных из базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-112">Type a query statement to retrieve selected rows of data from the source database.</span></span> <span data-ttu-id="c0ed9-113">Например: следующая инструкция запроса извлекает столбцы **SalesPersonID**, **SalesQuota**и **SalesYTD** из базы данных AdventureWorks для менеджеров по продажам, получающих более 1,5 процентов комиссионных от продаж.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-113">For example, the following query statement retrieves the **SalesPersonID**, **SalesQuota**, and **SalesYTD** from the AdventureWorks database for sales persons whose commission percentage is more than 1.5 percent.</span></span>  
  
```  
SELECT SalesPersonID, SalesQuota, SalesYTD  
FROM Sales.SalesPerson  
WHERE CommissionPct > 0.015  
```  
  
 <span data-ttu-id="c0ed9-114">**Анализ**</span><span class="sxs-lookup"><span data-stu-id="c0ed9-114">**Parse**</span></span>  
 <span data-ttu-id="c0ed9-115">Проверка синтаксиса инструкции SQL, введенной в текстовое поле **Инструкция SQL**.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-115">Checks the syntax of the SQL statement in the **SQL statement** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0ed9-116">Если время, затрачиваемое на проверку синтаксиса инструкции, превышает 30 секунд, синтаксический анализ прерывается и формируется ошибка.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-116">If the time that is required to check the syntax of the statement exceeds the time-out value of 30 seconds, parsing stops and generates an error.</span></span> <span data-ttu-id="c0ed9-117">Перейти на следующую страницу мастера невозможно, пока не будет успешно выполнен синтаксический анализ.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-117">You will not be able to move past this page of the wizard until parsing succeeds.</span></span> <span data-ttu-id="c0ed9-118">Одно из возможных решений заключается в создании представления базы данных на основе данного запроса и выполнения запросов из мастера к этому представлению вместо явного ввода текста запроса.</span><span class="sxs-lookup"><span data-stu-id="c0ed9-118">One solution is to create a database view based on the query, and to query the view from the wizard, instead of entering the query text directly.</span></span>  
  
 <span data-ttu-id="c0ed9-119">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="c0ed9-119">**Browse**</span></span>  
 <span data-ttu-id="c0ed9-120">Выберите файл, содержащий инструкцию SQL, с помощью диалогового окна **Открыть** .</span><span class="sxs-lookup"><span data-stu-id="c0ed9-120">Select a file containing a SQL statement by using the **Open** dialog box.</span></span> <span data-ttu-id="c0ed9-121">При выборе файла текст копируется из файла в текстовое поле **Инструкция запроса** .</span><span class="sxs-lookup"><span data-stu-id="c0ed9-121">Selecting a file copies the text from the file into the **Query statement** text box.</span></span>  
  
  
