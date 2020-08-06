---
title: Выбор способа импорта данных (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.choosehowtoimpdata.f1
ms.assetid: 17dc6903-c239-46aa-a3b0-6e3156accacc
author: minewiskan
ms.author: owend
ms.openlocfilehash: fba1d5801f325400b228920fffa06512f4db8de2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657414"
---
# <a name="choose-how-to-import-the-data-ssas"></a><span data-ttu-id="58da9-102">Выбор способа импорта данных (SSAS)</span><span class="sxs-lookup"><span data-stu-id="58da9-102">Choose How to Import the Data (SSAS)</span></span>
  <span data-ttu-id="58da9-103">На этой странице **мастера импорта таблиц** можно выбрать порядок импорта данных из выбранного источника данных.</span><span class="sxs-lookup"><span data-stu-id="58da9-103">This page of the **Table Import Wizard** enables you to choose how to import data from the selected data source.</span></span> <span data-ttu-id="58da9-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="58da9-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="58da9-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="58da9-105">UI element list</span></span>  
 <span data-ttu-id="58da9-106">**Выбрать из списка таблиц и представлений данные для импорта**</span><span class="sxs-lookup"><span data-stu-id="58da9-106">**Select from a list of tables and views to choose the data to import**</span></span>  
 <span data-ttu-id="58da9-107">Выберите этот параметр, если необходимо импортировать данные посредством выбора из списка.</span><span class="sxs-lookup"><span data-stu-id="58da9-107">Select this option if you want to import data by selecting from a list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58da9-108">Этот параметр доступен, только если выбранный источник данных предоставляет сведения о схеме, поддерживаемые **мастером импорта таблиц** .</span><span class="sxs-lookup"><span data-stu-id="58da9-108">This option is available only when the selected data source exposes schema information that the **Table Import Wizard** supports.</span></span>  
  
 <span data-ttu-id="58da9-109">**Написать запрос, указывающий данные для импорта**</span><span class="sxs-lookup"><span data-stu-id="58da9-109">**Write a query to specify the data to import**</span></span>  
 <span data-ttu-id="58da9-110">Выберите этот параметр, если необходимо импортировать данные с помощью SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="58da9-110">Select this option if you want to import data by using a SQL query.</span></span> <span data-ttu-id="58da9-111">С помощью SQL-запроса можно управлять импортируемыми данными.</span><span class="sxs-lookup"><span data-stu-id="58da9-111">The SQL query can manipulate the data that is imported.</span></span> <span data-ttu-id="58da9-112">Например, можно объединить данные из различных таблиц или выбрать только строки, отвечающие определенным критериям.</span><span class="sxs-lookup"><span data-stu-id="58da9-112">For example, you could join data from different tables or select only rows that meet certain criteria.</span></span>  
  
  
