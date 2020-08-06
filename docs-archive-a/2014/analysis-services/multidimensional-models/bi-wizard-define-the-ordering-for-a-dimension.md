---
title: Определение порядка для измерения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OrderBy property
- dimensions [Analysis Services], ordering
- Business Intelligence enhancements [Analysis Services], ordering
- dimensions [Analysis Services], Business Intelligence enhancements
- ordering dimensions [Analysis Services]
- OrderByAttributeID property
ms.assetid: c42fbd58-244d-4e0a-b715-6f919cbc3ad9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8cd5ea148e374c18c530ba0a15c80dbb23983020
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657377"
---
# <a name="define-the-ordering-for-a-dimension"></a><span data-ttu-id="4cdef-102">Определение упорядочивания для измерения</span><span class="sxs-lookup"><span data-stu-id="4cdef-102">Define the Ordering for a Dimension</span></span>
  <span data-ttu-id="4cdef-103">Добавьте расширение упорядочивания атрибутов к кубу или измерению, чтобы указать, как упорядочиваются элементы атрибута.</span><span class="sxs-lookup"><span data-stu-id="4cdef-103">Add the attribute ordering enhancement to a cube or dimension to specify how the members of an attribute are ordered.</span></span> <span data-ttu-id="4cdef-104">Элементы можно упорядочивать по имени или ключу атрибута, либо по имени или ключу другого атрибута (основанному на связи атрибута).</span><span class="sxs-lookup"><span data-stu-id="4cdef-104">Members can be ordered by the name or the key of the attribute, or by the name or the key of another attribute (based on an attribute relationship).</span></span> <span data-ttu-id="4cdef-105">По умолчанию элементы упорядочиваются по имени.</span><span class="sxs-lookup"><span data-stu-id="4cdef-105">By default, members are ordered by the name.</span></span> <span data-ttu-id="4cdef-106">Это расширение изменяет настройки свойств `OrderBy` и `OrderByAttributeID` для атрибутов в измерении.</span><span class="sxs-lookup"><span data-stu-id="4cdef-106">This enhancement changes the `OrderBy` and `OrderByAttributeID` property settings for attributes in a dimension.</span></span>  
  
 <span data-ttu-id="4cdef-107">Чтобы добавить упорядочивание атрибутов, используйте мастер бизнес-аналитики и выберите параметр **Задать сортировку атрибута** на странице **Выбор расширения** .</span><span class="sxs-lookup"><span data-stu-id="4cdef-107">To add attribute ordering, you use the Business Intelligence Wizard, and select the **Specify attribute ordering** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="4cdef-108">После этого мастер отобразит шаги, позволяющие выбрать измерение, к которому необходимо применить упорядочивание атрибутов, и указать способ упорядочивания атрибутов для выбранного измерения.</span><span class="sxs-lookup"><span data-stu-id="4cdef-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply attribute ordering and specifying how to order the attributes for the selected dimension.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="4cdef-109">Выбор измерения</span><span class="sxs-lookup"><span data-stu-id="4cdef-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="4cdef-110">На первой странице **Определение порядка атрибутов** мастера указывается измерение, к которому необходимо применить упорядочивание атрибутов.</span><span class="sxs-lookup"><span data-stu-id="4cdef-110">On the first **Specify Attribute Ordering** page of the wizard, you specify the dimension to which you want to apply attribute ordering.</span></span> <span data-ttu-id="4cdef-111">Добавление расширения упорядочивания атрибутов к этому выбранному измерению приведет к изменению измерения.</span><span class="sxs-lookup"><span data-stu-id="4cdef-111">The attribute ordering enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="4cdef-112">Эти изменения будут наследоваться всеми кубами, включающими выбранное измерение.</span><span class="sxs-lookup"><span data-stu-id="4cdef-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="specifying-ordering"></a><span data-ttu-id="4cdef-113">Указание упорядочивания</span><span class="sxs-lookup"><span data-stu-id="4cdef-113">Specifying Ordering</span></span>  
 <span data-ttu-id="4cdef-114">На второй странице **Определение порядка атрибутов** мастера указывается, как будут упорядочиваться все атрибуты в измерении.</span><span class="sxs-lookup"><span data-stu-id="4cdef-114">On the second **Specify Attribute Ordering** page of the wizard, you specify how all the attributes in the dimension will be ordered.</span></span>  
  
 <span data-ttu-id="4cdef-115">В столбце **Атрибут сортировки** можно изменить атрибут, используемый для выполнения упорядочивания.</span><span class="sxs-lookup"><span data-stu-id="4cdef-115">In the **Ordering Attribute** column, you can change the attribute used to do the ordering.</span></span> <span data-ttu-id="4cdef-116">Если атрибут, который нужно использовать для упорядочивания элементов, отсутствует в списке, прокрутите список вниз, а затем выберите, **\<New attribute...>** чтобы открыть диалоговое окно **Выбор столбца** , в котором можно выбрать столбец в таблице измерения.</span><span class="sxs-lookup"><span data-stu-id="4cdef-116">If the attribute that you want to use to order members is not in the list, scroll down the list, and then select **\<New attribute...>** to open the **Select a Column** dialog box, where you can select a column in a dimension table.</span></span> <span data-ttu-id="4cdef-117">При выборе столбца с использованием диалогового окна **Выбор столбца** создается дополнительный атрибут, с помощью которого необходимо упорядочивать элементы атрибута.</span><span class="sxs-lookup"><span data-stu-id="4cdef-117">Selecting a column by using the **Select a Column** dialog box creates an additional attribute with which to order members of an attribute.</span></span>  
  
 <span data-ttu-id="4cdef-118">В столбце **Критерии** после этого можно выбрать, необходимо ли упорядочивать элементы атрибута по **Key** или **Name**.</span><span class="sxs-lookup"><span data-stu-id="4cdef-118">In the **Criteria** column, you can then select whether to order the members of the attribute by either **Key** or **Name**.</span></span>  
  
  
