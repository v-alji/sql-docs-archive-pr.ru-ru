---
title: Определение логических первичных ключей в представлении источника данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- removing logical primary keys
- logical primary keys [SQL Server]
- deleting logical primary keys
- data source views [Analysis Services], logical primary keys
ms.assetid: 172bc267-c637-4caa-bf55-0ba198d30b1e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25092e5d754381c572dcdbfc03e5ee0f29c1df24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664606"
---
# <a name="define-logical-primary-keys-in-a-data-source-view-analysis-services"></a><span data-ttu-id="31b43-102">Определение логических первичных ключей в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="31b43-102">Define Logical Primary Keys in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="31b43-103">Мастер представлений источника данных и конструктор представлений источника данных автоматически определяют первичный ключ для таблицы, добавляемой в представление источника данных на основе базовой таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="31b43-103">The Data Source View Wizard and Data Source View Designer automatically define a primary key for a table that is added to a data source view based on underlying database table.</span></span>  
  
 <span data-ttu-id="31b43-104">Иногда может потребоваться вручную определить первичный ключ в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="31b43-104">Occasionally, you may need to manually define a primary key in the data source view.</span></span> <span data-ttu-id="31b43-105">Например, по соображениям производительности или архитектурным соображениям таблицы в источнике данных могут не иметь явно определенных первичных ключевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="31b43-105">For example, for performance or design reasons, tables in a data source may not have explicitly defined primary key columns.</span></span> <span data-ttu-id="31b43-106">В именованных запросах и представлениях первичный ключевой столбец для таблицы также может опускаться.</span><span class="sxs-lookup"><span data-stu-id="31b43-106">Named queries and views may also omit the primary key column for a table.</span></span> <span data-ttu-id="31b43-107">Если таблица, представление или именованный запрос не имеют заданного физического первичного ключа, можно вручную задать логический первичный ключ для таблицы или именованного запроса в конструкторе представлений источника данных.</span><span class="sxs-lookup"><span data-stu-id="31b43-107">If a table, view, or named query does not have a physical primary key defined, you can manually define a logical primary key on the table, view or named query in Data Source View Designer.</span></span>  
  
## <a name="set-a-logical-primary-key"></a><span data-ttu-id="31b43-108">Установка логического первичного ключа</span><span class="sxs-lookup"><span data-stu-id="31b43-108">Set a Logical Primary Key</span></span>  
 <span data-ttu-id="31b43-109">Первичные ключи требуются в службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для уникальной идентификации записей в таблице, идентификации ключевых столбцов в таблицах измерений и для поддержки связей между таблицами, представлениями и именованными запросами.</span><span class="sxs-lookup"><span data-stu-id="31b43-109">Primary keys are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to uniquely identify records in a table, identify key columns in dimension tables and to support relationships between tables, views and named queries.</span></span> <span data-ttu-id="31b43-110">Эти связи используются при построении запросов для получения данных и метаданных из базовых источников данных и для использования преимуществ расширенных функций бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="31b43-110">These relationships are used to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="31b43-111">В качестве логического первичного ключа можно использовать любой столбец, включая именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="31b43-111">Any column can be used for the logical primary key, including a named calculation.</span></span> <span data-ttu-id="31b43-112">При создании логического первичного ключа в представлении источника данных создается ограничение уникальности, которое помечается как ограничение первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="31b43-112">When you create a logical primary key, a unique constraint is created in the data source view and marked as a primary key constraint.</span></span> <span data-ttu-id="31b43-113">Любой другой существующий в выбранной таблице логический первичный ключ удаляется.</span><span class="sxs-lookup"><span data-stu-id="31b43-113">Any other existing logical primary key specified in the selected table is deleted.</span></span>  
  
1.  <span data-ttu-id="31b43-114">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект или подключитесь к базе данных, содержащей представление источника данных, в котором необходимо установить логический первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="31b43-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to set a logical primary key.</span></span>  
  
2.  <span data-ttu-id="31b43-115">В обозревателе решений откройте папку **Представления источников данных** и дважды щелкните представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="31b43-115">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>  
  
     <span data-ttu-id="31b43-116">Чтобы найти таблицу или представление, можно использовать параметр **Найти таблицу** , либо щелкнув меню **представление источника данных** , либо щелкнув правой кнопкой мыши в открытой области панелей **таблицы** или **диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="31b43-116">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View**  menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
3.  <span data-ttu-id="31b43-117">В соответствующей таблице на панели **Таблицы** или **Диаграмма** щелкните правой кнопкой мыши столбец или столбцы, которые необходимо использовать для определения логического первичного ключа, а затем выберите **Задать логический первичный ключ**.</span><span class="sxs-lookup"><span data-stu-id="31b43-117">In either the **Tables** or the **Diagram** pane, right-click the column or columns that you want to use to define a logical primary key, and then click **Set Logical Primary Key**.</span></span>  
  
     <span data-ttu-id="31b43-118">Параметр задания логического первичного ключа доступен только для таблиц без первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="31b43-118">The option to set a logical primary key is available only for tables that do not have a primary key.</span></span>  
  
     <span data-ttu-id="31b43-119">Обратите внимание, что после задания ключа первичные ключевые столбцы теперь отмечены значком ключа.</span><span class="sxs-lookup"><span data-stu-id="31b43-119">Notice that after you set the key, a key icon now identifies the primary key columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b43-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="31b43-120">See Also</span></span>  
 <span data-ttu-id="31b43-121">[Представления источников данных в многомерных моделях](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="31b43-121">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="31b43-122">Определение именованных вычислений в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="31b43-122">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
