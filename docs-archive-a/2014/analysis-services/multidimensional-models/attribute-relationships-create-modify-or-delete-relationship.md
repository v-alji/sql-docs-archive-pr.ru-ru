---
title: Создание, изменение или удаление связи атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Analysis Services], member properties
- member properties [Analysis Services], creating
ms.assetid: 137b2f40-5dfb-4141-9110-70f961f259cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0e25140a75feda708850a2328498fb13df28a0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655424"
---
# <a name="create-modify-or-delete-an-attribute-relationship"></a><span data-ttu-id="e0d91-102">Создание, изменение или удаление связи атрибутов</span><span class="sxs-lookup"><span data-stu-id="e0d91-102">Create, Modify, or Delete an Attribute Relationship</span></span>
  <span data-ttu-id="e0d91-103">Связи атрибутов можно создавать, изменять и удалять с помощью вкладки **Связи атрибутов** конструктора измерений в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0d91-103">You can create, modify, or delete an attribute relationship between attributes in a dimension by using the **Attribute Relationships** tab of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-an-attribute-relationship"></a><span data-ttu-id="e0d91-104">Создание связи атрибутов</span><span class="sxs-lookup"><span data-stu-id="e0d91-104">To create an Attribute Relationship</span></span>  
  
1.  <span data-ttu-id="e0d91-105">В конструкторе измерений откройте измерение с атрибутами, между которыми нужно создать связь.</span><span class="sxs-lookup"><span data-stu-id="e0d91-105">In Dimension Designer, open the dimension that contains the attributes that you want to create an attribute relationship between.</span></span>  
  
2.  <span data-ttu-id="e0d91-106">На вкладке **Связи атрибутов** правой кнопкой мыши щелкните атрибут в диаграмме или на панели **Атрибуты** , а затем выберите **Создать связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="e0d91-106">On the **Attribute Relationships** tab, right-click an attribute in the diagram or in the **Attributes** pane, and then select **New Attribute Relationship**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0d91-107">Чтобы отобразить панель **Атрибуты** , нажмите кнопку **Показать списки** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="e0d91-107">To display the **Attributes** pane, click **Show List Views** on the toolbar.</span></span>  
  
3.  <span data-ttu-id="e0d91-108">В диалоговом окне **Создать связь атрибутов** выберите исходный атрибут и связанный с ним атрибут.</span><span class="sxs-lookup"><span data-stu-id="e0d91-108">In the **Create Attribute Relationship** dialog box, select a source attribute and a related attribute.</span></span>  
  
4.  <span data-ttu-id="e0d91-109">В списке **Тип связи** выберите тип связи и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e0d91-109">In the **Relationship type** list, select a relationship type, and then click **OK**.</span></span>  
  
### <a name="to-modify-an-attribute-relationship"></a><span data-ttu-id="e0d91-110">Изменение связи атрибутов</span><span class="sxs-lookup"><span data-stu-id="e0d91-110">To modify an Attribute Relationship</span></span>  
  
1.  <span data-ttu-id="e0d91-111">В конструкторе измерений откройте измерение со связью атрибутов, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="e0d91-111">In Dimension Designer, open the dimension that contains the attribute relationship that you want to modify.</span></span>  
  
2.  <span data-ttu-id="e0d91-112">Перейдите на вкладку **Связи атрибутов** .</span><span class="sxs-lookup"><span data-stu-id="e0d91-112">Click the **Attribute Relationships** tab.</span></span>  
  
3.  <span data-ttu-id="e0d91-113">Щелкните связь атрибутов правой кнопкой мыши на диаграмме или на панели **Связи атрибутов** и выберите **Изменить связь атрибутов**.</span><span class="sxs-lookup"><span data-stu-id="e0d91-113">Right-click the attribute relationship in the diagram or in the **Attribute Relationships** pane, and select **Edit Attribute Relationship**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0d91-114">Чтобы отобразить область **Связи атрибутов** , нажмите кнопку **Показать списки** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="e0d91-114">To display the **Attribute Relationships** pane, click **Show List Views** on the toolbar.</span></span>  
  
4.  <span data-ttu-id="e0d91-115">В диалоговом окне **Изменение связи атрибутов** выберите исходный атрибут и связанный с ним атрибут.</span><span class="sxs-lookup"><span data-stu-id="e0d91-115">In the **Edit Attribute Relationship** dialog box, select a source attribute and a related attribute.</span></span>  
  
5.  <span data-ttu-id="e0d91-116">В списке **Тип связи** выберите тип связи и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e0d91-116">In the **Relationship type** list, select a relationship type, and then click **OK**.</span></span>  
  
### <a name="to-delete-an-attribute-relationship"></a><span data-ttu-id="e0d91-117">Удаление связи атрибутов</span><span class="sxs-lookup"><span data-stu-id="e0d91-117">To delete an Attribute Relationship</span></span>  
  
1.  <span data-ttu-id="e0d91-118">В конструкторе измерений откройте измерение со связью атрибутов, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="e0d91-118">In Dimension Designer, open the dimension that contains the attribute relationship that you want to delete.</span></span>  
  
2.  <span data-ttu-id="e0d91-119">На вкладке **Связи атрибутов** щелкните связь атрибутов правой кнопкой мыши в диаграмме или на панели **Связи атрибутов** , а затем выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e0d91-119">On the **Attribute Relationships** tab, right-click the attribute relationship in the diagram or in the **Attribute Relationships** pane, and then select **Delete**.</span></span>  
  
3.  <span data-ttu-id="e0d91-120">В диалоговом окне **Удаление объектов** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e0d91-120">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d91-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0d91-121">See Also</span></span>  
 [<span data-ttu-id="e0d91-122">можно изменить расположение фигур на вкладке</span><span class="sxs-lookup"><span data-stu-id="e0d91-122">Attribute Relationships</span></span>](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md)  
  
  
