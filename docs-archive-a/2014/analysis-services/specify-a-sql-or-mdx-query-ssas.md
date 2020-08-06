---
title: Указание запроса SQL или многомерных выражений (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.specsqlmdxquery.f1
ms.assetid: e4128221-3b46-48be-b0f1-d82477ce6782
author: minewiskan
ms.author: owend
ms.openlocfilehash: bce5e92aaed7a62311e989d6963e4fa5764028ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736851"
---
# <a name="specify-a-sql-or-mdx-query-ssas"></a><span data-ttu-id="453a0-102">Указание SQL-запроса или запроса многомерных выражений (службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="453a0-102">Specify a SQL or MDX Query (SSAS)</span></span>
  <span data-ttu-id="453a0-103">На этой странице **мастера импорта таблиц** можно импортировать данные с помощью SQL-запроса или запроса многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="453a0-103">This page of the **Table Import Wizard** enables you to import data by using a SQL or MDX query.</span></span> <span data-ttu-id="453a0-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="453a0-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="453a0-105">С помощью запроса можно обрабатывать импортируемые данные.</span><span class="sxs-lookup"><span data-stu-id="453a0-105">The query can manipulate the data that is imported.</span></span> <span data-ttu-id="453a0-106">Например, можно объединить данные из различных таблиц или выбрать только строки, отвечающие определенным критериям.</span><span class="sxs-lookup"><span data-stu-id="453a0-106">For example, you could join data from different tables or select only rows that meet certain criteria.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="453a0-107">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="453a0-107">UI element list</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="453a0-108">Термин</span><span class="sxs-lookup"><span data-stu-id="453a0-108">Term</span></span>|<span data-ttu-id="453a0-109">Определение</span><span class="sxs-lookup"><span data-stu-id="453a0-109">Definition</span></span>|  
|<span data-ttu-id="453a0-110">**Понятное имя запроса**</span><span class="sxs-lookup"><span data-stu-id="453a0-110">**Friendly Query Name**</span></span>|<span data-ttu-id="453a0-111">Введите уникальное имя для запроса.</span><span class="sxs-lookup"><span data-stu-id="453a0-111">Type a unique name for the query.</span></span> <span data-ttu-id="453a0-112">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="453a0-112">This is a required field.</span></span>|  
|<span data-ttu-id="453a0-113">**Инструкция SQL**</span><span class="sxs-lookup"><span data-stu-id="453a0-113">**SQL Statement**</span></span>|<span data-ttu-id="453a0-114">Введите или вставьте инструкцию SQL.</span><span class="sxs-lookup"><span data-stu-id="453a0-114">Type or paste a SQL statement.</span></span>|  
|<span data-ttu-id="453a0-115">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="453a0-115">**Validate**</span></span>|<span data-ttu-id="453a0-116">Проверяет допустимость инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="453a0-116">Determine if the SQL statement is valid.</span></span>|  
|<span data-ttu-id="453a0-117">**Оформление**</span><span class="sxs-lookup"><span data-stu-id="453a0-117">**Design**</span></span>|<span data-ttu-id="453a0-118">Создайте инструкцию SQL с помощью диалогового окна конструктора запросов.</span><span class="sxs-lookup"><span data-stu-id="453a0-118">Design a SQL statement by using the query designer dialog box.</span></span> <span data-ttu-id="453a0-119">Дополнительные сведения см. в разделе [Конструктор реляционных запросов (SSAS)](relational-query-designer-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="453a0-119">For more information, see [Relational Query Designer &#40;SSAS&#41;](relational-query-designer-ssas.md).</span></span>|  
  
  
