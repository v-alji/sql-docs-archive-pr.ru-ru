---
title: Предварительный просмотр выбранной таблицы (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.previewselecttable.f1
ms.assetid: b6b34b5a-43b3-4a75-9f3b-b2ad1084b1b6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25eb4d4424223449052ab1f65b41cf270da81fb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750275"
---
# <a name="preview-selected-table-ssas"></a><span data-ttu-id="031d3-102">Предварительный просмотр выбранной таблицы (SSAS)</span><span class="sxs-lookup"><span data-stu-id="031d3-102">Preview Selected Table (SSAS)</span></span>
  <span data-ttu-id="031d3-103">Эта страница **мастера импорта таблиц** позволяет просмотреть данные в выбранной таблице, выбрать столбцы для включения в импорт данных и отфильтровать данные в выбранных столбцах.</span><span class="sxs-lookup"><span data-stu-id="031d3-103">This page of the **Table Import Wizard** enables you to preview the data in the selected table, to select the columns to include in the data import, and to filter data in the selected columns.</span></span> <span data-ttu-id="031d3-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="031d3-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="031d3-105">В таблице отображаются не все строки.</span><span class="sxs-lookup"><span data-stu-id="031d3-105">Not all the rows in the table are displayed.</span></span> <span data-ttu-id="031d3-106">Однако можно настроить фильтры так, чтобы они применялись ко всем данным в таблице во время импорта.</span><span class="sxs-lookup"><span data-stu-id="031d3-106">However, the filters that you set will be applied to all of the data in the table during import.</span></span>  
  
 <span data-ttu-id="031d3-107">Для источников данных, в которых используется проверка подлинности Windows, учетные данные текущего пользователя используются для выборки данных, отображаемых в диалоговом окне «Просмотр и фильтрация».</span><span class="sxs-lookup"><span data-stu-id="031d3-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the data displayed in the Preview and Filter dialog.</span></span> <span data-ttu-id="031d3-108">Для других источников данных для выборки данных используются учетные данные, указанные в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="031d3-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
 <span data-ttu-id="031d3-109">Внешний вид данных на этой странице не гарантирует, что импорт будет выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="031d3-109">The appearance of data on this page does not guarantee import will succeed.</span></span> <span data-ttu-id="031d3-110">Импорт завершится ошибкой, если имя пользователя, указанное на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="031d3-110">If the user name specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="031d3-111">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="031d3-111">UI element list</span></span>  
 <span data-ttu-id="031d3-112">**Флажок в заголовке столбца**</span><span class="sxs-lookup"><span data-stu-id="031d3-112">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="031d3-113">Установите флажок, чтобы включить столбец в импорт данных.</span><span class="sxs-lookup"><span data-stu-id="031d3-113">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="031d3-114">Снимите флажок, чтобы не импортировать столбец.</span><span class="sxs-lookup"><span data-stu-id="031d3-114">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="031d3-115">**Стрелка вниз в заголовке столбца**</span><span class="sxs-lookup"><span data-stu-id="031d3-115">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="031d3-116">Фильтровать данные в столбце.</span><span class="sxs-lookup"><span data-stu-id="031d3-116">Filter data in the column.</span></span>  
  
 <span data-ttu-id="031d3-117">**Очистить фильтры строк**</span><span class="sxs-lookup"><span data-stu-id="031d3-117">**Clear Row Filters**</span></span>  
 <span data-ttu-id="031d3-118">Удалить все фильтры, примененные к данным в столбцах.</span><span class="sxs-lookup"><span data-stu-id="031d3-118">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
