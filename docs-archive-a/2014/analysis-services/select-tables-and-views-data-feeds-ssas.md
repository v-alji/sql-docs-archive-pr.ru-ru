---
title: Выбор таблиц и представлений (веб-каналов данных) (службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviewsdf.f1
ms.assetid: 6c4fafe0-e02e-47d1-b8bc-e70e872690af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 46c317ecf2a87adcde264e8d6d7e822eb833b8b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658434"
---
# <a name="select-tables-and-views-data-feeds-ssas"></a><span data-ttu-id="40c21-102">Выбор таблиц и представлений (веб-каналов данных) (SSAS)</span><span class="sxs-lookup"><span data-stu-id="40c21-102">Select Tables and Views (Data Feeds) (SSAS)</span></span>
  <span data-ttu-id="40c21-103">На этой странице **мастера импорта таблиц** выбираются таблицы и представления, из которых импортируются данные.</span><span class="sxs-lookup"><span data-stu-id="40c21-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="40c21-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="40c21-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="40c21-105">Внешний вид таблиц и представлений на этой странице не гарантирует, что импорт будет выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="40c21-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="40c21-106">Импорт завершится ошибкой, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="40c21-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="40c21-107">Для источников данных, в которых используется проверка подлинности Windows, учетные данные текущего пользователя используются для выборки таблиц и представлений в диалоговом окне «Выбор таблиц и представлений».</span><span class="sxs-lookup"><span data-stu-id="40c21-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="40c21-108">Для других источников данных для выборки данных используются учетные данные, указанные в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="40c21-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="40c21-109">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="40c21-109">UI element list</span></span>  
 <span data-ttu-id="40c21-110">**URL-адрес канала данных**</span><span class="sxs-lookup"><span data-stu-id="40c21-110">**Data feed URL**</span></span>  
 <span data-ttu-id="40c21-111">Отображает URL-адрес для выбранного потока данных.</span><span class="sxs-lookup"><span data-stu-id="40c21-111">Displays the URL for the data feed that you selected.</span></span>  
  
 <span data-ttu-id="40c21-112">**Таблицы и представления**</span><span class="sxs-lookup"><span data-stu-id="40c21-112">**Tables and views**</span></span>  
 <span data-ttu-id="40c21-113">Содержит таблицы и представления в канале данных.</span><span class="sxs-lookup"><span data-stu-id="40c21-113">Lists the tables and views in the data feed.</span></span> <span data-ttu-id="40c21-114">Установите флажок напротив каждой таблицы и представления, которые необходимо импортировать.</span><span class="sxs-lookup"><span data-stu-id="40c21-114">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="40c21-115">**Исходная таблица**</span><span class="sxs-lookup"><span data-stu-id="40c21-115">**Source Table**</span></span>  
 <span data-ttu-id="40c21-116">Указывает имя исходной таблицы в зависимости от типа источника данных.</span><span class="sxs-lookup"><span data-stu-id="40c21-116">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="40c21-117">**Понятное имя**</span><span class="sxs-lookup"><span data-stu-id="40c21-117">**Friendly Name**</span></span>  
 <span data-ttu-id="40c21-118">Указывает понятное имя исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="40c21-118">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="40c21-119">По умолчанию в столбце выводится имя исходной таблицы, которое отображается в столбце **Исходная таблица** .</span><span class="sxs-lookup"><span data-stu-id="40c21-119">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span>  
  
 <span data-ttu-id="40c21-120">**Сведения о фильтре**</span><span class="sxs-lookup"><span data-stu-id="40c21-120">**Filter Details**</span></span>  
 <span data-ttu-id="40c21-121">Отображает фильтр импорта данных в диалоговом окне **Сведения о фильтре**, если к импортируемым данным был применен фильтр.</span><span class="sxs-lookup"><span data-stu-id="40c21-121">Displays the data import filter in the **Filter Details** dialog box, when a filter has been applied to the data that is being imported.</span></span> <span data-ttu-id="40c21-122">Дополнительные сведения см. в разделе [Сведения о фильтре (SSAS)](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="40c21-122">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="40c21-123">**Просмотр и фильтрация**</span><span class="sxs-lookup"><span data-stu-id="40c21-123">**Preview and Filter**</span></span>  
 <span data-ttu-id="40c21-124">Выводит диалоговое окно **Предварительный просмотр выбранной таблицы**, которое используется для применения фильтра к импортируемым данным.</span><span class="sxs-lookup"><span data-stu-id="40c21-124">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="40c21-125">Дополнительные сведения см. в статье [Предварительный просмотр выбранной таблицы (SSAS)](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="40c21-125">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="40c21-126">**Выбор связанных таблиц**</span><span class="sxs-lookup"><span data-stu-id="40c21-126">**Select Related Tables**</span></span>  
 <span data-ttu-id="40c21-127">Выберите таблицы, связанные с выбранными таблицами и представлениями.</span><span class="sxs-lookup"><span data-stu-id="40c21-127">Select tables that are related to the tables and views that you have selected.</span></span>  
  
  
