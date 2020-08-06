---
title: Задание нестандартных формул элементов для атрибутов в измерении | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Business Intelligence enhancements [Analysis Services], custom member formulas
- member formulas [Analysis Services]
- dimensions [Analysis Services], Business Intelligence enhancements
- custom member formulas [Analysis Services]
- CustomRollupColumn property
ms.assetid: c4467b08-ce59-4de7-a2d9-c22e246bdd52
author: minewiskan
ms.author: owend
ms.openlocfilehash: 112f8944bd20b2b6a464b0d84fb8ac1a0e89d976
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657375"
---
# <a name="set-custom-member-formulas-for-attributes-in-a-dimension"></a><span data-ttu-id="90625-102">Настройка нестандартных формул элементов для атрибутов в измерении</span><span class="sxs-lookup"><span data-stu-id="90625-102">Set Custom Member Formulas for Attributes in a Dimension</span></span>
  <span data-ttu-id="90625-103">Добавьте расширение нестандартных формул элементов к кубу или измерению, чтобы заменить статистическое вычисление по умолчанию, связанное с элементом измерения, результатами многомерного выражения.</span><span class="sxs-lookup"><span data-stu-id="90625-103">Add a custom member formula enhancement to a cube or dimension to replace the default aggregation that is associated with a dimension member with the results of a Multidimensional Expressions (MDX) expression.</span></span> <span data-ttu-id="90625-104">(Это расширение устанавливает свойство `CustomRollupColumn` для указанного атрибута в измерении.)</span><span class="sxs-lookup"><span data-stu-id="90625-104">(This enhancement sets the `CustomRollupColumn` property on a specified attribute in a dimension.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90625-105">Нестандартная формула элемента доступна только для измерений, основанных на существующих источниках данных.</span><span class="sxs-lookup"><span data-stu-id="90625-105">A custom member formula is available only for dimensions that are based on existing data sources.</span></span> <span data-ttu-id="90625-106">Для измерений, созданных без использования источника данных, необходимо запустить мастер формирования схем, чтобы создать представление источника данных перед тем, как добавить нестандартную формулу элемента.</span><span class="sxs-lookup"><span data-stu-id="90625-106">For dimensions that were created without using a data source, you must run the Schema Generation Wizard to create a data source view before adding a custom member formula.</span></span>  
  
 <span data-ttu-id="90625-107">Чтобы добавить нестандартную формулу элемента, используйте мастер бизнес-аналитики и выберите параметр **Создать нестандартную формулу элемента** на странице **Выбор расширения** .</span><span class="sxs-lookup"><span data-stu-id="90625-107">To add a custom member formula, you use the Business Intelligence Wizard, and select the **Create a custom member formula** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="90625-108">После этого мастер отобразит шаги, позволяющие выбрать измерение, к которому необходимо применить нестандартную формулу элемента, и включить нестандартную формулу элемента.</span><span class="sxs-lookup"><span data-stu-id="90625-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply a custom member formula and enabling the custom member formula.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="90625-109">Выбор измерения</span><span class="sxs-lookup"><span data-stu-id="90625-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="90625-110">На первой странице **Создание нестандартной формулы элемента** мастера указывается измерение, к которому необходимо применить нестандартную формулу элемента.</span><span class="sxs-lookup"><span data-stu-id="90625-110">On the first **Create a Custom Member Formula** page of the wizard, you specify the dimension to which you want to apply a custom member formula.</span></span> <span data-ttu-id="90625-111">Добавление расширения нестандартной формулы элемента к этому выбранному измерению приведет к изменению измерения.</span><span class="sxs-lookup"><span data-stu-id="90625-111">The custom member formula enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="90625-112">Эти изменения будут наследоваться всеми кубами, включающими выбранное измерение.</span><span class="sxs-lookup"><span data-stu-id="90625-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="enabling-a-custom-member-formula"></a><span data-ttu-id="90625-113">Включение нестандартной формулы элемента</span><span class="sxs-lookup"><span data-stu-id="90625-113">Enabling a Custom Member Formula</span></span>  
 <span data-ttu-id="90625-114">На второй странице **Создание нестандартной формулы элемента** связывается исходный столбец, содержащий нестандартную формулу элемента, с одним или несколькими атрибутами в измерении.</span><span class="sxs-lookup"><span data-stu-id="90625-114">On the second **Create a Custom Member Formula** page, you associate the source column that contains the custom member formula with one or more attributes in the dimension.</span></span> <span data-ttu-id="90625-115">В столбце **Атрибут** установите флажок рядом с атрибутом, который необходимо связать со столбцом нестандартной формулы элемента.</span><span class="sxs-lookup"><span data-stu-id="90625-115">In the **Attribute** column, select the check box next to the attribute that you want to associate with the custom member formula column.</span></span> <span data-ttu-id="90625-116">После выбора каждого атрибута мастер отображает диалоговое окно **Выбор столбца** .</span><span class="sxs-lookup"><span data-stu-id="90625-116">After you select each attribute, the wizard displays the **Select a Column** dialog box.</span></span> <span data-ttu-id="90625-117">В этом диалоговом окне щелкните столбец таблицы измерения, который содержит формулу.</span><span class="sxs-lookup"><span data-stu-id="90625-117">In this dialog box, click the column in the dimension table that contains the formula.</span></span> <span data-ttu-id="90625-118">При необходимости изменения выбора после закрытия диалогового окна **Выбор столбца** щелкните ячейку **Исходный столбец** , которую необходимо изменить, а затем нажмите кнопку с многоточием (**...**), чтобы вновь открыть диалоговое окно **Выбор столбца** .</span><span class="sxs-lookup"><span data-stu-id="90625-118">If you want to change a selection after you close the **Select a Column** dialog box, click the **Source Column** cell that you want to change, and then click the ellipsis (**...**) to open the **Select a Column** dialog box again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90625-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="90625-119">See Also</span></span>  
 [<span data-ttu-id="90625-120">Использование мастера бизнес-аналитики для улучшения измерений</span><span class="sxs-lookup"><span data-stu-id="90625-120">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
  
  
