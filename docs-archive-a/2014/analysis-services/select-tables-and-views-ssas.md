---
title: Выбор таблиц и представлений (службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviews.f1
ms.assetid: 5e8121cc-03f0-4168-98cf-63c5c032bb0b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 891da51478670122f5dbce8fdd7be55c98c898c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738888"
---
# <a name="select-tables-and-views-ssas"></a><span data-ttu-id="9e355-102">Выбор таблиц и представлений (SSAS)</span><span class="sxs-lookup"><span data-stu-id="9e355-102">Select Tables and Views (SSAS)</span></span>
  <span data-ttu-id="9e355-103">На этой странице **мастера импорта таблиц** выбираются таблицы и представления, из которых импортируются данные.</span><span class="sxs-lookup"><span data-stu-id="9e355-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="9e355-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="9e355-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="9e355-105">Внешний вид таблиц и представлений на этой странице не гарантирует, что импорт будет выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="9e355-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="9e355-106">Импорт завершится ошибкой, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="9e355-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="9e355-107">Для источников данных, в которых используется проверка подлинности Windows, учетные данные текущего пользователя используются для выборки таблиц и представлений в диалоговом окне «Выбор таблиц и представлений».</span><span class="sxs-lookup"><span data-stu-id="9e355-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="9e355-108">Для других источников данных для выборки данных используются учетные данные, указанные в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="9e355-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="9e355-109">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="9e355-109">UI element list</span></span>  
 <span data-ttu-id="9e355-110">**Server**</span><span class="sxs-lookup"><span data-stu-id="9e355-110">**Server**</span></span>  
 <span data-ttu-id="9e355-111">Отображает сервер, с которым установлено соединение.</span><span class="sxs-lookup"><span data-stu-id="9e355-111">Displays the server that you are connected to.</span></span>  
  
 <span data-ttu-id="9e355-112">**База данных**</span><span class="sxs-lookup"><span data-stu-id="9e355-112">**Database**</span></span>  
 <span data-ttu-id="9e355-113">Отображает выбранную базу данных.</span><span class="sxs-lookup"><span data-stu-id="9e355-113">Displays the database that you selected.</span></span>  
  
 <span data-ttu-id="9e355-114">**Таблицы и представления**</span><span class="sxs-lookup"><span data-stu-id="9e355-114">**Tables and Views**</span></span>  
 <span data-ttu-id="9e355-115">Содержит список таблиц и представлений в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9e355-115">Lists the tables and views in the database.</span></span> <span data-ttu-id="9e355-116">Установите флажок напротив каждой таблицы и представления, которые необходимо импортировать.</span><span class="sxs-lookup"><span data-stu-id="9e355-116">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="9e355-117">**Исходная таблица**</span><span class="sxs-lookup"><span data-stu-id="9e355-117">**Source Table**</span></span>  
 <span data-ttu-id="9e355-118">Указывает имя исходной таблицы в зависимости от типа источника данных.</span><span class="sxs-lookup"><span data-stu-id="9e355-118">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="9e355-119">**Схема**</span><span class="sxs-lookup"><span data-stu-id="9e355-119">**Schema**</span></span>  
 <span data-ttu-id="9e355-120">Задает схему, в которой содержится исходная таблица.</span><span class="sxs-lookup"><span data-stu-id="9e355-120">Specifies the schema in which the source table is contained.</span></span> <span data-ttu-id="9e355-121">В зависимости от типа базы данных, схема функционирует как контейнер для других объектов, таких как таблицы, и может также обозначать владение этими объектами.</span><span class="sxs-lookup"><span data-stu-id="9e355-121">Depending on the type of database, a schema functions as a container for other objects, such as tables, and can also indicate ownership of those objects.</span></span>  
  
 <span data-ttu-id="9e355-122">**Понятное имя**</span><span class="sxs-lookup"><span data-stu-id="9e355-122">**Friendly Name**</span></span>  
 <span data-ttu-id="9e355-123">Указывает понятное имя исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="9e355-123">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="9e355-124">По умолчанию в столбце выводится имя исходной таблицы, которое отображается в столбце **Исходная таблица** .</span><span class="sxs-lookup"><span data-stu-id="9e355-124">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span> <span data-ttu-id="9e355-125">Измените имя, если нужно использовать имя, отличное от имени, используемого в базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="9e355-125">Change the name if you want to use a different name than the name used in the source database.</span></span>  
  
 <span data-ttu-id="9e355-126">**Сведения о фильтре**</span><span class="sxs-lookup"><span data-stu-id="9e355-126">**Filter Details**</span></span>  
 <span data-ttu-id="9e355-127">Если фильтр был применен к импортируемым данным, отображает фильтр импорта данных в диалоговом окне **Сведения о фильтре**.</span><span class="sxs-lookup"><span data-stu-id="9e355-127">When a filter has been applied to the data that is being imported, displays the data import filter in the **Filter Details** dialog box.</span></span> <span data-ttu-id="9e355-128">Дополнительные сведения см. в разделе [Сведения о фильтре (SSAS)](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="9e355-128">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="9e355-129">**Просмотр и фильтрация**</span><span class="sxs-lookup"><span data-stu-id="9e355-129">**Preview and Filter**</span></span>  
 <span data-ttu-id="9e355-130">Выводит диалоговое окно **Предварительный просмотр выбранной таблицы**, которое используется для применения фильтра к импортируемым данным.</span><span class="sxs-lookup"><span data-stu-id="9e355-130">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="9e355-131">Дополнительные сведения см. в статье [Предварительный просмотр выбранной таблицы (SSAS)](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="9e355-131">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="9e355-132">**Выбор связанных таблиц**</span><span class="sxs-lookup"><span data-stu-id="9e355-132">**Select Related Tables**</span></span>  
 <span data-ttu-id="9e355-133">Выбирает для импорта те таблицы и представления, которые связаны с выбранными таблицами и представлениями.</span><span class="sxs-lookup"><span data-stu-id="9e355-133">Selects for import those tables and views that are related to the tables and views that you have already selected.</span></span>  
  
  
