---
title: Диалоговое окно «Свойства таблицы» (службы SSAS — табличные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.ssmsimbi.TableProperties.f1
ms.assetid: 77571ccd-bdba-4e07-af55-465509dc6a33
author: minewiskan
ms.author: owend
ms.openlocfilehash: e3ca6d787616821532b30af0fe3591f79d6dbea6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658431"
---
# <a name="table-properties-dialog-box-ssas---tabular"></a><span data-ttu-id="ef120-102">Диалоговое окно «Свойства таблицы» (службы SSAS — табличные модели)</span><span class="sxs-lookup"><span data-stu-id="ef120-102">Table Properties Dialog Box (SSAS - Tabular)</span></span>
  <span data-ttu-id="ef120-103">Используйте диалоговое окно **Свойства таблицы** в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для просмотра свойств таблицы в базе данных с табличной моделью.</span><span class="sxs-lookup"><span data-stu-id="ef120-103">Use the **Table Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to view the properties of a table in a tabular model database.</span></span> <span data-ttu-id="ef120-104">Все свойства доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ef120-104">All properties are read-only.</span></span>  
  
 <span data-ttu-id="ef120-105">Чтобы открыть диалоговое окно **Свойства таблицы** , необходимо щелкнуть правой кнопкой мыши таблицу в обозревателе объектов и выбрать пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ef120-105">You can display the **Table Properties** dialog box by right-clicking a table in Object Explorer and selecting **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ef120-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="ef120-106">Options</span></span>  
  
|<span data-ttu-id="ef120-107">Термин</span><span class="sxs-lookup"><span data-stu-id="ef120-107">Term</span></span>|<span data-ttu-id="ef120-108">Определение</span><span class="sxs-lookup"><span data-stu-id="ef120-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="ef120-109">**имя**;</span><span class="sxs-lookup"><span data-stu-id="ef120-109">**Name**</span></span>|<span data-ttu-id="ef120-110">Отображает имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef120-110">Displays the name of the table.</span></span>|  
|<span data-ttu-id="ef120-111">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="ef120-111">**ID**</span></span>|<span data-ttu-id="ef120-112">Отображает идентификатор таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef120-112">Displays the identifier of the table.</span></span>|  
|<span data-ttu-id="ef120-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ef120-113">**Description**</span></span>|<span data-ttu-id="ef120-114">Показывает описание таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef120-114">Displays the description of the table.</span></span>|  
|<span data-ttu-id="ef120-115">**Отметка времени создания**</span><span class="sxs-lookup"><span data-stu-id="ef120-115">**Create Timestamp**</span></span>|<span data-ttu-id="ef120-116">Отображает дату и время создания таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef120-116">Displays the date and time the table was created.</span></span>|  
|<span data-ttu-id="ef120-117">**Последнее обновление схемы**</span><span class="sxs-lookup"><span data-stu-id="ef120-117">**Last Schema Update**</span></span>|<span data-ttu-id="ef120-118">Отображает дату и время последнего обновления метаданных таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef120-118">Displays the date and time the metadata for the table was last updated.</span></span>|  
|<span data-ttu-id="ef120-119">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="ef120-119">**State**</span></span>|<span data-ttu-id="ef120-120">Отображает состояние обработки таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef120-120">Displays the processing state of the table.</span></span> <span data-ttu-id="ef120-121">Дополнительные сведения о значениях этого свойства см. в разделе <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef120-121">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span></span>|  
|<span data-ttu-id="ef120-122">**Последняя обработка**</span><span class="sxs-lookup"><span data-stu-id="ef120-122">**Last Processed**</span></span>|<span data-ttu-id="ef120-123">Отображает дату и время последней обработки таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef120-123">Displays the date and time the table was last processed.</span></span>|  
|<span data-ttu-id="ef120-124">**Текущий режим хранения**</span><span class="sxs-lookup"><span data-stu-id="ef120-124">**Current Storage Mode**</span></span>|<span data-ttu-id="ef120-125">Отображает текущий режим хранения для таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef120-125">Displays the current storage mode for the table.</span></span> <span data-ttu-id="ef120-126">Режим хранения устанавливается на уровне базы данных и наследуется всеми таблицами.</span><span class="sxs-lookup"><span data-stu-id="ef120-126">Storage mode is set at the database level and inherited by all tables.</span></span> <span data-ttu-id="ef120-127">Нельзя использовать различные режимы хранения на уровне таблицы.</span><span class="sxs-lookup"><span data-stu-id="ef120-127">You cannot use different storage modes at the table level.</span></span> <span data-ttu-id="ef120-128">Допустимые значения: InMemory (по умолчанию), InMemoryWithDirectQuery, DirectQuery, DirectQueryWithinMemory.</span><span class="sxs-lookup"><span data-stu-id="ef120-128">Valid values are InMemory (default), InMemoryWithDirectQuery, DirectQuery, DirectQueryWithinMemory.</span></span>|  
  
  
