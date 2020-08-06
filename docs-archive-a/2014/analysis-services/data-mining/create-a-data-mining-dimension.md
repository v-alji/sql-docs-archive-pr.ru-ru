---
title: Создание измерения интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], dimensions
ms.assetid: 9f0c39e5-3516-43ab-b203-f3f6dbcff89a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 265cf671bbc825258f0b2bd6627690e8c52f252b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727474"
---
# <a name="create-a-data-mining-dimension"></a><span data-ttu-id="9fa6e-102">создать измерение интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9fa6e-102">Create a Data Mining Dimension</span></span>
  <span data-ttu-id="9fa6e-103">Если структура интеллектуального анализа данных основана на кубе OLAP, то можно создать измерение, которое содержит содержимое модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-103">If your mining structure is based on an OLAP cube, you can create a dimension that contains the content of the mining model.</span></span> <span data-ttu-id="9fa6e-104">После этого можно встроить это измерение обратно в исходный куб.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-104">You can then incorporate the dimension back into the source cube.</span></span>  
  
 <span data-ttu-id="9fa6e-105">Также можно просмотреть измерение, использовать его для исследования результатов модели или выполнить запрос к измерению с помощью многомерного выражения.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-105">You can also browse the dimension, use it to explore the model results, or query the dimension using MDX.</span></span>  
  
### <a name="to-create-a-data-mining-dimension"></a><span data-ttu-id="9fa6e-106">Создание измерения интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9fa6e-106">To create a data mining dimension</span></span>  
  
1.  <span data-ttu-id="9fa6e-107">В конструкторе интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]перейдите либо на вкладку **Структура интеллектуального анализа данных** , либо на вкладку **Модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="9fa6e-107">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], select either the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="9fa6e-108">В меню **Модель интеллектуального анализа данных** выберите пункт **Создать измерение интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-108">From the **Mining Model** menu, select **Create a Data Mining Dimension**.</span></span>  
  
     <span data-ttu-id="9fa6e-109">Откроется диалоговое окно **Создание измерения интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="9fa6e-109">The **Create Data Mining Dimension** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="9fa6e-110">В списке **Имя модели** диалогового окна **Создание измерения интеллектуального анализа данных** выберите OLAP-модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-110">In the **Model name** list of the **Create Data Mining Dimension** dialog box, select an OLAP mining model.</span></span>  
  
4.  <span data-ttu-id="9fa6e-111">В поле **Название измерения** введите имя для нового измерения интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-111">In the **Dimension name** box, enter a name for the new data mining dimension.</span></span>  
  
5.  <span data-ttu-id="9fa6e-112">При необходимости создания куба, включающего новое измерение интеллектуального анализа данных, выберите пункт **Создать куб**.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-112">If you want to create a cube that includes the new data mining dimension, select **Create cube**.</span></span> <span data-ttu-id="9fa6e-113">После выбора пункта **Создать куб**можно ввести новое имя для куба.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-113">After you select **Create cube**, you can enter a new name for the cube.</span></span>  
  
6.  <span data-ttu-id="9fa6e-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-114">Click **OK**.</span></span>  
  
     <span data-ttu-id="9fa6e-115">Измерение интеллектуального анализа данных создается и добавляется в папку **Измерения** в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="9fa6e-115">The data mining dimension is created and is added to the **Dimensions** folder in Solution Explorer.</span></span> <span data-ttu-id="9fa6e-116">Если выбран пункт **Создать куб**, то также создается новый куб и добавляется в папку **Кубы** .</span><span class="sxs-lookup"><span data-stu-id="9fa6e-116">If you selected **Create cube**, a new cube is also created and is added to the **Cubes** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa6e-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="9fa6e-117">See Also</span></span>  
 [<span data-ttu-id="9fa6e-118">Задачи и инструкции по структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9fa6e-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
