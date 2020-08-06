---
title: Редактор преобразования "кэш" (страница "сопоставления") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetransmap.f1
ms.assetid: ffd53f18-9646-458a-a84a-f2467d601ea5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bb31e479ea98133da34dcbf257d59e70f4ffe8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667370"
---
# <a name="cache-transformation-editor-mappings-page"></a><span data-ttu-id="9a2cc-102">Редактор преобразования «Кэш» (страница «Сопоставления»)</span><span class="sxs-lookup"><span data-stu-id="9a2cc-102">Cache Transformation Editor (Mappings Page)</span></span>
  <span data-ttu-id="9a2cc-103">Используйте страницу **Сопоставления\*\*\*\*Редактора преобразования «Кэш»** , чтобы сопоставить входные столбцы в преобразовании «Преобразование кэша» с целевыми столбцами в диспетчере соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-103">Use the **Mappings** page of the **Cache Transformation Editor** to map the input columns in the Cache Transform transformation to destination columns in the Cache connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a2cc-104">Каждый входной столбец должен быть сопоставлен с целевым, имеющим тот же тип данных.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-104">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="9a2cc-105">В противном случае конструктор служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] отобразит сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-105">Otherwise, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
 <span data-ttu-id="9a2cc-106">Дополнительные сведения о преобразовании «Преобразование кэша» см. в разделе [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="9a2cc-106">To learn more about the Cache Transform, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
 <span data-ttu-id="9a2cc-107">Дополнительные сведения о диспетчере соединений с кэшем см. в разделе [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9a2cc-107">To learn more about the Cache connection manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9a2cc-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a2cc-108">Options</span></span>  
 <span data-ttu-id="9a2cc-109">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="9a2cc-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="9a2cc-110">Просмотрите список доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-110">View the list of available input columns.</span></span> <span data-ttu-id="9a2cc-111">Чтобы сопоставить доступные входные столбцы с целевыми столбцами, воспользуйтесь операцией перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-111">Use a drag-and-drop operation to map available input columns to destination columns.</span></span>  
  
 <span data-ttu-id="9a2cc-112">Также можно сопоставить входные и целевые столбцы с помощью клавиатуры, выделив цветом столбец в таблице **Доступные входные столбцы** , нажав клавишу меню и выбрав пункт **Сопоставлять элементы по совпадению имен**.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-112">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="9a2cc-113">**Доступные целевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="9a2cc-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="9a2cc-114">Просмотрите список доступных целевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-114">View the list of available destination columns.</span></span> <span data-ttu-id="9a2cc-115">Чтобы сопоставить доступные входные столбцы с целевыми столбцами, воспользуйтесь операцией перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-115">Use a drag-and-drop operation to map available destination columns to input columns.</span></span>  
  
 <span data-ttu-id="9a2cc-116">Также можно сопоставить входные и целевые столбцы с помощью клавиатуры, выделив цветом столбец в таблице **Доступные целевые столбцы** , нажав клавишу меню и выбрав пункт **Сопоставлять элементы по совпадению имен**.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-116">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Destination Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="9a2cc-117">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="9a2cc-117">**Input Column**</span></span>  
 <span data-ttu-id="9a2cc-118">Просмотрите входные столбцы, выбранные ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-118">View input columns selected earlier in this topic.</span></span> <span data-ttu-id="9a2cc-119">Сопоставления можно изменить с помощью списка **Доступные входные столбцы**.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-119">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="9a2cc-120">**Целевой столбец**</span><span class="sxs-lookup"><span data-stu-id="9a2cc-120">**Destination Column**</span></span>  
 <span data-ttu-id="9a2cc-121">Просмотр каждого доступного целевого столбца.</span><span class="sxs-lookup"><span data-stu-id="9a2cc-121">View each available destination column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a2cc-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a2cc-122">See Also</span></span>  
 [<span data-ttu-id="9a2cc-123">Редактор преобразования "Кэш" (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="9a2cc-123">Cache Transformation Editor &#40;Connection Manager Page&#41;</span></span>](../../2014/integration-services/cache-transformation-editor-connection-manager-page.md)  
  
  
