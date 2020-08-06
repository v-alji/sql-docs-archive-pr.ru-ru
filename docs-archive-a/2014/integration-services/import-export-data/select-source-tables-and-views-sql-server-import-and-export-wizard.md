---
title: Выбор исходных таблиц и представлений (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.selectsourcetablesandviews.f1
ms.assetid: f60e1a19-2ea6-403c-89ab-3e60ac533ea0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e18f9f34db7965033d4e1e62964060a26404a45e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666137"
---
# <a name="select-source-tables-and-views-sql-server-import-and-export-wizard"></a><span data-ttu-id="7bbd8-102">Выбор исходных таблиц и представлений (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7bbd8-102">Select Source Tables and Views (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="7bbd8-103">Страница **Выбор исходных таблиц и представлений** используется для указания таблиц и представлений, которые должны быть скопированы из источника данных в назначение.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-103">Use the **Select Source Tables and Views** page to specify the tables and views to be copied from the data source to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bbd8-104">Если выбирается параметр «Копирование таблицы», необязательно копировать все столбцы таблицы.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="7bbd8-105">Выбрав целевую таблицу, нажмите кнопку изменить сопоставления, чтобы открыть диалоговое окно **сопоставления столбцов** .</span><span class="sxs-lookup"><span data-stu-id="7bbd8-105">After selecting a destination table, click Edit Mappings to display the **Column Mappings** dialog box.</span></span> <span data-ttu-id="7bbd8-106">Выберите **\<ignore>** в столбце **назначение** диалогового окна **сопоставления столбцов** для столбцов, которые необходимо пропустить.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-106">Select **\<ignore>** in the **Destination** column of the **Column Mappings** dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="7bbd8-107">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd8-107">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="7bbd8-108">Дополнительные сведения о параметрах запуска мастера и о разрешениях, необходимых для успешного запуска мастера, см. [в разделе Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd8-108">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="7bbd8-109">Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-109">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="7bbd8-110">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-110">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="7bbd8-111">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-111">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="7bbd8-112">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd8-112">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7bbd8-113">Варианты</span><span class="sxs-lookup"><span data-stu-id="7bbd8-113">Options</span></span>  
  
### <a name="tables-and-views-list"></a><span data-ttu-id="7bbd8-114">Список «Таблицы и представления»</span><span class="sxs-lookup"><span data-stu-id="7bbd8-114">Tables and views List</span></span>  
 <span data-ttu-id="7bbd8-115">**Source**</span><span class="sxs-lookup"><span data-stu-id="7bbd8-115">**Source**</span></span>  
 <span data-ttu-id="7bbd8-116">С помощью флажков выберите из списка таблицы и представления для копирования в место назначения.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-116">Using the check boxes, select from the list of available tables and views to copy to the destination.</span></span> <span data-ttu-id="7bbd8-117">Если выбрана исходная таблица или представление и никакие другие действия не выполняются, схема и данные из источника копируются без изменения.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-117">If you select a source table or view and perform no other action, the schema and data from the source are copied without changes.</span></span>  
  
 <span data-ttu-id="7bbd8-118">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="7bbd8-118">**Destination**</span></span>  
 <span data-ttu-id="7bbd8-119">Выберите целевую таблицу из списка для каждой исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-119">Select a destination table from the list for each source table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bbd8-120">Если в этой точке работы мастера создается целевая таблица в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] или другого средства, новая таблица не сразу отображается в списке доступных целевых таблиц.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-120">If you pause at this point in the wizard to create a destination table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or another tool, the new table is not immediately visible in the list of available destination tables.</span></span> <span data-ttu-id="7bbd8-121">Чтобы обновить список целевых таблиц, выполните шаг назад на две страницы на странице **Выбор назначения** , повторно выберите целевую базу данных, а затем снова выполните шаг вперед к **исходным таблицам и представлениям выбор исходных таблиц**.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-121">To refresh the list of destination tables, step back two pages to the **Choose a Destination** page, re-select the destination database, then step forward again to the **Select Source Tables and Views**.</span></span>  
  
### <a name="other-options"></a><span data-ttu-id="7bbd8-122">Другие параметры</span><span class="sxs-lookup"><span data-stu-id="7bbd8-122">Other Options</span></span>  
 <span data-ttu-id="7bbd8-123">**Изменить сопоставления**</span><span class="sxs-lookup"><span data-stu-id="7bbd8-123">**Edit mappings**</span></span>  
 <span data-ttu-id="7bbd8-124">Используйте диалоговое окно **сопоставления столбцов** , чтобы указать целевые столбцы для получения исходных данных.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-124">Use the **Column Mappings** dialog box to specify destination columns to receive the source data.</span></span> <span data-ttu-id="7bbd8-125">Можно скопировать только подмножество столбцов, выбрав \<ignore> в столбце **назначение** диалогового окна **сопоставления столбцов** для столбцов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-125">You can copy only a subset of columns by selecting \<ignore> in the **Destination** column of the **Column Mappings** dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="7bbd8-126">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="7bbd8-126">**Preview**</span></span>  
 <span data-ttu-id="7bbd8-127">Предварительный просмотр исходных данных в диалоговом окне **Просмотр данных** для проверки перед выполнением импорта или экспорта.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-127">Preview source data in the **Preview Data** dialog box to verify it before performing the import or export.</span></span> <span data-ttu-id="7bbd8-128">В диалоговом окне **Предварительный просмотр данных** отображается до 200 строк данных.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-128">The **Preview Data** dialog box displays up to 200 rows of data.</span></span>  
  
 <span data-ttu-id="7bbd8-129">После просмотра данных может понадобиться изменить выбранные параметры для источника данных и назначения.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-129">After previewing the data, you might want to change the options that you have selected for the data source and destination.</span></span> <span data-ttu-id="7bbd8-130">Для этого на странице **Выбор исходных таблиц и представлений** нажмите кнопку **Назад** , чтобы вернуться к предыдущим страницам, где можно изменить выбранные параметры.</span><span class="sxs-lookup"><span data-stu-id="7bbd8-130">To make these changes, on the **Select Source Tables and Views** page, click **Back** to return to previous pages where you can change your selections.</span></span>  
  
  
