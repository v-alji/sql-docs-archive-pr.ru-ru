---
title: Фильтрация исходного куба для структуры интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slice cubes [Analysis Services]
- mining structures [Analysis Services], filtering source cube
- cubes [Analysis Services], slicing
- filtering data [Analysis Services]
ms.assetid: 05dce7e1-2fe5-4500-bacf-c1a8a76e1424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61409b4803f43d3ff2634daaba65a92bc343db36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656700"
---
# <a name="filter-the-source-cube-for-a-mining-structure"></a><span data-ttu-id="f2d41-102">отфильтровать исходный куб для структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f2d41-102">Filter the Source Cube for a Mining Structure</span></span>
  <span data-ttu-id="f2d41-103">При создании структуры интеллектуального анализа, основанной на данных в многомерной модели (кубе OLAP), можно выполнить *срез* Куба, на котором основана структура интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f2d41-103">When you create a mining structure that is based on data in a multidimensional model (an OLAP cube), you can *slice* the cube that the mining structure is based on.</span></span> <span data-ttu-id="f2d41-104">Создание сечения позволяет выделить подмножество данных, аналогично фильтрации данных, используемой для обучения модели интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="f2d41-104">Slicing lets you create subsets of data, as a kind of filter on the data that is used to train the mining model.</span></span>  
  
### <a name="to-slice-a-cube"></a><span data-ttu-id="f2d41-105">Выполнение среза куба</span><span class="sxs-lookup"><span data-stu-id="f2d41-105">To slice a cube</span></span>  
  
1.  <span data-ttu-id="f2d41-106">В конструкторе интеллектуального анализа данных в [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] выберите вкладку **Структура интеллектуального анализа** или **модели интеллектуального анализа** данных.</span><span class="sxs-lookup"><span data-stu-id="f2d41-106">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], select the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="f2d41-107">В меню **модель интеллектуального анализа данных** выберите пункт **определить срез куба структуры интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="f2d41-107">On the **Mining Model** menu, select **Define Mining Structure Cube Slice**.</span></span>  
  
     <span data-ttu-id="f2d41-108">Откроется диалоговое окно **срез куба** .</span><span class="sxs-lookup"><span data-stu-id="f2d41-108">The **Slice Cube** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="f2d41-109">В столбце **измерение** диалогового окна **срез куба** выберите измерение, которое необходимо отфильтровать.</span><span class="sxs-lookup"><span data-stu-id="f2d41-109">In the **Dimension** column of the **Slice Cube** dialog box, select the dimension that you want to filter.</span></span>  
  
4.  <span data-ttu-id="f2d41-110">Выберите уровень иерархии с помощью списка в столбце **Иерархия** .</span><span class="sxs-lookup"><span data-stu-id="f2d41-110">Select a level of a hierarchy, using the list in the **Hierarchy** column.</span></span>  
  
5.  <span data-ttu-id="f2d41-111">Выберите оператор из списка в столбце **оператор** , чтобы использовать его при построении условия фильтра.</span><span class="sxs-lookup"><span data-stu-id="f2d41-111">Select an operator from the list in the **Operator** column, to use in building the filter condition.</span></span>  
  
6.  <span data-ttu-id="f2d41-112">Щелкните поле в столбце **Фильтр** .</span><span class="sxs-lookup"><span data-stu-id="f2d41-112">Click the box in the **Filter** column.</span></span>  
  
     <span data-ttu-id="f2d41-113">Откроется диалоговое окно со всеми элементами на выбранном уровне иерархии.</span><span class="sxs-lookup"><span data-stu-id="f2d41-113">A dialog box opens that contains all the members at the specified level of the hierarchy.</span></span>  
  
7.  <span data-ttu-id="f2d41-114">Выберите элементы, по которым нужно выполнить фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="f2d41-114">Select the member or members on which you want to filter.</span></span>  
  
8.  <span data-ttu-id="f2d41-115">Нажмите кнопку **ОК** в диалоговом окне член.</span><span class="sxs-lookup"><span data-stu-id="f2d41-115">Click **OK** in the member dialog box.</span></span>  
  
9. <span data-ttu-id="f2d41-116">Нажмите кнопку **ОК** в диалоговом окне **срез куба** .</span><span class="sxs-lookup"><span data-stu-id="f2d41-116">Click **OK** in the **Slice Cube** dialog box.</span></span>  
  
     <span data-ttu-id="f2d41-117">Теперь исходный куб отфильтрован в соответствии с заданным срезом.</span><span class="sxs-lookup"><span data-stu-id="f2d41-117">The source cube is now filtered as defined by the cube slice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d41-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2d41-118">See Also</span></span>  
 <span data-ttu-id="f2d41-119">[Задачи и инструкции по структуре интеллектуального анализа данных](data-mining/mining-structure-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="f2d41-119">[Mining Structure Tasks and How-tos](data-mining/mining-structure-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="f2d41-120">создать новую структуру интеллектуального анализа OLAP</span><span class="sxs-lookup"><span data-stu-id="f2d41-120">Create a New OLAP Mining Structure</span></span>](data-mining/create-a-new-olap-mining-structure.md)  
  
  
