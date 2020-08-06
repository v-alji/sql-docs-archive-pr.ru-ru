---
title: Добавление таблиц в экземпляр CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- addTabs
ms.assetid: ad260e19-c021-4035-9311-c02fc96ceaea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: edcd84db9e3c464334d407987cb3567f78edd44e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728645"
---
# <a name="add-tables-to-a-cdc-instance"></a><span data-ttu-id="3f5fd-102">Добавление таблиц в экземпляр CDC</span><span class="sxs-lookup"><span data-stu-id="3f5fd-102">Add Tables to a CDC Instance</span></span>
  <span data-ttu-id="3f5fd-103">Диалоговое окно «Выбор таблицы» используется для добавления дополнительных таблиц из источника Oracle в экземпляр CDC.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-103">Use the Table Selection dialog box to add additional tables from the Oracle source to the CDC instance.</span></span> <span data-ttu-id="3f5fd-104">Выбранные таблицы добавляются в список на вкладке **Таблицы** редактора свойств.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-104">The tables selected are added to the list in the **Tables** tab of the Properties editor.</span></span>  
  
 <span data-ttu-id="3f5fd-105">По умолчанию список таблиц в этом диалоговом окне пуст.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-105">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="3f5fd-106">Вы можете установить флажок **(Выделить все)** или выполнить поиск определенных таблиц.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-106">You can select the **(Select All)** check box or search for specific tables.</span></span>  
  
 <span data-ttu-id="3f5fd-107">**Поиск определенных таблиц**</span><span class="sxs-lookup"><span data-stu-id="3f5fd-107">**To search for specific tables**</span></span>  
 <span data-ttu-id="3f5fd-108">Введите критерии поиска, как показано далее, и нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-108">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="3f5fd-109">**Схема**. Выберите схему базы данных в списке.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-109">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="3f5fd-110">В список будут включены только те таблицы, которые имеют эту схему.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-110">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="3f5fd-111">**Шаблон имени таблицы**. Введите любую строку символов.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-111">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="3f5fd-112">Отображены будут только те таблицы, в которых есть введенная строка символов.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-112">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f5fd-113">Критерии можно ввести в одном из полей либо в обоих полях.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-113">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="3f5fd-114">**Отображение первых 1000 совпадающих таблиц**. По умолчанию этот флажок установлен.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-114">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="3f5fd-115">Этот параметр ограничивает число отображаемых таблиц, соответствующих заданным критериям, до первой тысячи.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-115">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="3f5fd-116">Если снять этот флажок, то будут отображены все таблицы, которые соответствуют заданным критериям.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-116">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="3f5fd-117">Если таблиц очень много, то для их отображения может потребоваться длительное время.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-117">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="3f5fd-118">**Выбор таблиц для включения в экземпляр CDC**</span><span class="sxs-lookup"><span data-stu-id="3f5fd-118">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="3f5fd-119">Установите флажок около любой таблицы, которую требуется включить в экземпляр, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-119">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="3f5fd-120">Выбранные таблицы добавляются в список на странице **Выбор таблиц и столбцов** мастера создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-120">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="3f5fd-121">Нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно без добавления каких-либо таблиц.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-121">Click **Close** to close the dialog box without adding any tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f5fd-122">Если была выбрана таблица, в которой содержатся данные неподдерживаемого типа, то на экране появится сообщение об ошибке, а таблица не будет включена в экземпляр.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-122">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f5fd-123">Список таблиц можно просматривать в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-123">You can view the list of tables in the viewer.</span></span> <span data-ttu-id="3f5fd-124">При использовании средства просмотра отображаемые в нем данные доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-124">When using the viewer the information is read only.</span></span> <span data-ttu-id="3f5fd-125">В средстве просмотра отображается также список отслеживаемых столбцов из таблицы.</span><span class="sxs-lookup"><span data-stu-id="3f5fd-125">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="3f5fd-126">Дополнительные сведения о доступе к средству просмотра см. в разделе [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="3f5fd-126">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f5fd-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f5fd-127">See Also</span></span>  
 <span data-ttu-id="3f5fd-128">[Как изменить свойства экземпляра CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="3f5fd-128">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 <span data-ttu-id="3f5fd-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="3f5fd-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="3f5fd-130">Выбор таблиц Oracle для отслеживания изменений</span><span class="sxs-lookup"><span data-stu-id="3f5fd-130">Select Oracle Tables for Capturing Changes</span></span>](select-oracle-tables-for-capturing-changes.md)  
  
  
