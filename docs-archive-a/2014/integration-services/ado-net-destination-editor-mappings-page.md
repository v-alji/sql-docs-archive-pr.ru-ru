---
title: Редактор назначения «ADO.NET» (страница «сопоставления») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.mappings.f1
ms.assetid: 842d075f-8b7a-457c-a1a1-a7acbe10e9b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7e7a2397e4e2d16e6eeca93d41f5127dfde4c35e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654463"
---
# <a name="ado-net-destination-editor-mappings-page"></a><span data-ttu-id="b67f1-102">Редактор назначения «ADO.NET» (страница «Сопоставления»)</span><span class="sxs-lookup"><span data-stu-id="b67f1-102">ADO NET Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="b67f1-103">Страница **Сопоставления** диалогового окна **Редактор назначения «ADO.NET»** используется для сопоставления входных столбцов с целевыми.</span><span class="sxs-lookup"><span data-stu-id="b67f1-103">Use the **Mappings** page of the **ADO NET Destination Editor** dialog box to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="b67f1-104">Дополнительные сведения о назначении «ADO.NET» см. в разделе [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="b67f1-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="b67f1-105">**Открытие страницы «Сопоставления»**</span><span class="sxs-lookup"><span data-stu-id="b67f1-105">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="b67f1-106">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий назначение «ADO.NET».</span><span class="sxs-lookup"><span data-stu-id="b67f1-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="b67f1-107">На вкладке **Поток данных** дважды щелкните назначение "ADO.NET".</span><span class="sxs-lookup"><span data-stu-id="b67f1-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="b67f1-108">В окне **Редактор назначения «ADO.NET»** нажмите кнопку **Сопоставления**.</span><span class="sxs-lookup"><span data-stu-id="b67f1-108">In the **ADO NET Destination Editor**, click **Mappings**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b67f1-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="b67f1-109">Options</span></span>  
 <span data-ttu-id="b67f1-110">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="b67f1-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="b67f1-111">Просмотрите список доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="b67f1-111">View the list of available input columns.</span></span> <span data-ttu-id="b67f1-112">Для сопоставления доступных входных столбцов с целевыми столбцами используется операция перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="b67f1-112">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="b67f1-113">**Доступные целевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="b67f1-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="b67f1-114">Просмотрите список доступных целевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="b67f1-114">View the list of available destination columns.</span></span> <span data-ttu-id="b67f1-115">Чтобы сопоставить доступные целевые столбцы с входными столбцами, воспользуйтесь операцией перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="b67f1-115">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="b67f1-116">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="b67f1-116">**Input Column**</span></span>  
 <span data-ttu-id="b67f1-117">Позволяет просматривать выбранные входные столбцы.</span><span class="sxs-lookup"><span data-stu-id="b67f1-117">View the input columns that you selected.</span></span> <span data-ttu-id="b67f1-118">Сопоставления можно удалить, выбрав вариант **\<ignore>** , чтобы исключить столбцы из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b67f1-118">You can remove mappings by selecting **\<ignore>** to exclude columns from the output.</span></span>  
  
 <span data-ttu-id="b67f1-119">**Целевой столбец**</span><span class="sxs-lookup"><span data-stu-id="b67f1-119">**Destination Column**</span></span>  
 <span data-ttu-id="b67f1-120">Позволяет просмотреть каждый из доступных целевых столбцов без учета наличия или отсутствия сопоставления.</span><span class="sxs-lookup"><span data-stu-id="b67f1-120">View each available destination column, regardless of whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67f1-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="b67f1-121">See Also</span></span>  
 <span data-ttu-id="b67f1-122">[Редактор назначения «ADO NET» &#40;«диспетчер соединений»&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="b67f1-122">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="b67f1-123">Редактор назначения ADO.NET (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="b67f1-123">ADO NET Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-error-output-page.md)  
  
  
