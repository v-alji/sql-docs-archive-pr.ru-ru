---
title: Выбор таблиц Oracle для отслеживания изменений | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selOraTabDia
ms.assetid: 2e295dc8-999d-4c4d-96cc-1519674b47a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e9064789dce83ff7d3917ed026c861743142e048
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735510"
---
# <a name="select-oracle-tables-for-capturing-changes"></a><span data-ttu-id="130ef-102">Выбор таблиц Oracle для отслеживания изменений</span><span class="sxs-lookup"><span data-stu-id="130ef-102">Select Oracle Tables for Capturing Changes</span></span>
  <span data-ttu-id="130ef-103">В этом диалоговом окне можно выбрать таблицы, включенные в экземпляр CDC.</span><span class="sxs-lookup"><span data-stu-id="130ef-103">Use this dialog box to select the tables that are included in the CDC instance.</span></span> <span data-ttu-id="130ef-104">Выбранные таблицы добавляются в список на странице **Выбор таблиц и столбцов** мастера создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="130ef-104">The tables selected are added to the list in the **Select Tables and Columns** page of the New Instance wizard.</span></span> <span data-ttu-id="130ef-105">Это диалоговое окно предназначено для следующих целей.</span><span class="sxs-lookup"><span data-stu-id="130ef-105">You can do the following in this dialog box.</span></span>  
  
 <span data-ttu-id="130ef-106">По умолчанию список таблиц в этом диалоговом окне пуст.</span><span class="sxs-lookup"><span data-stu-id="130ef-106">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="130ef-107">Можно установить флажок в верхней части столбца с флажками, чтобы выбрать все таблицы, а также выполнить поиск определенных таблиц.</span><span class="sxs-lookup"><span data-stu-id="130ef-107">You can select the check box at the top of the check box column to select all of the tables or search for specific tables.</span></span>  
  
 <span data-ttu-id="130ef-108">**Поиск определенных таблиц**</span><span class="sxs-lookup"><span data-stu-id="130ef-108">**To search for specific tables**</span></span>  
 <span data-ttu-id="130ef-109">Введите критерии поиска, как показано далее, и нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="130ef-109">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="130ef-110">**Схема**. Выберите схему базы данных в списке.</span><span class="sxs-lookup"><span data-stu-id="130ef-110">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="130ef-111">В список будут включены только те таблицы, которые имеют эту схему.</span><span class="sxs-lookup"><span data-stu-id="130ef-111">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="130ef-112">**Шаблон имени таблицы**. Введите любую строку символов.</span><span class="sxs-lookup"><span data-stu-id="130ef-112">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="130ef-113">Отображены будут только те таблицы, в которых есть введенная строка символов.</span><span class="sxs-lookup"><span data-stu-id="130ef-113">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="130ef-114">Критерии можно ввести в одном из полей либо в обоих полях.</span><span class="sxs-lookup"><span data-stu-id="130ef-114">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="130ef-115">**Отображение первых 1000 совпадающих таблиц**. По умолчанию этот флажок установлен.</span><span class="sxs-lookup"><span data-stu-id="130ef-115">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="130ef-116">Этот параметр ограничивает число отображаемых таблиц, соответствующих заданным критериям, до первой тысячи.</span><span class="sxs-lookup"><span data-stu-id="130ef-116">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="130ef-117">Если снять этот флажок, то будут отображены все таблицы, которые соответствуют заданным критериям.</span><span class="sxs-lookup"><span data-stu-id="130ef-117">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="130ef-118">Если таблиц очень много, то для их отображения может потребоваться длительное время.</span><span class="sxs-lookup"><span data-stu-id="130ef-118">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="130ef-119">**Выбор таблиц для включения в экземпляр CDC**</span><span class="sxs-lookup"><span data-stu-id="130ef-119">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="130ef-120">Установите флажок около любой таблицы, которую требуется включить в экземпляр, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="130ef-120">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="130ef-121">Выбранные таблицы добавляются в список на странице **Выбор таблиц и столбцов** мастера создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="130ef-121">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="130ef-122">Нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно без добавления каких-либо дополнительных таблиц.</span><span class="sxs-lookup"><span data-stu-id="130ef-122">Click **Close** to close the dialog box without adding any additional tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="130ef-123">Если была выбрана таблица, в которой содержатся данные неподдерживаемого типа, то на экране появится сообщение об ошибке, а таблица не будет включена в экземпляр.</span><span class="sxs-lookup"><span data-stu-id="130ef-123">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="130ef-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="130ef-124">See Also</span></span>  
 <span data-ttu-id="130ef-125">[Как создать экземпляр изменения базы данных SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="130ef-125">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="130ef-126">Выбор таблиц и столбцов Oracle</span><span class="sxs-lookup"><span data-stu-id="130ef-126">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
