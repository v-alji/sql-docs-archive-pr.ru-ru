---
title: Автоматическое формирование значений атрибута Code (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 19b354ee-2906-4cc7-ba2f-32b4543bddcf
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6c442f37ffe322985ba55b29b2c4cd539b8a3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667266"
---
# <a name="automatically-generate-code-attribute-values-master-data-services"></a><span data-ttu-id="745b2-102">Автоматическое формирование значений атрибута Code (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="745b2-102">Automatically Generate Code Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="745b2-103">Если необходимо автоматически задавать целое число для значения Code при создании нового элемента, то в [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] значения для атрибута Code сущности могут формироваться автоматически.</span><span class="sxs-lookup"><span data-stu-id="745b2-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's Code attribute when you want an integer to be automatically assigned to the Code value each time a new member is created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="745b2-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="745b2-104">Prerequisites</span></span>  
 <span data-ttu-id="745b2-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="745b2-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="745b2-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="745b2-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="745b2-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="745b2-107">You must be a model administrator.</span></span> <span data-ttu-id="745b2-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="745b2-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="745b2-109">Сущность должна существовать.</span><span class="sxs-lookup"><span data-stu-id="745b2-109">The entity must exist.</span></span> <span data-ttu-id="745b2-110">Дополнительные сведения см. в разделе [Создание сущности (службы Master Data Services)](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="745b2-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-code-values"></a><span data-ttu-id="745b2-111">Автоматическое формирование значений Code</span><span class="sxs-lookup"><span data-stu-id="745b2-111">To automatically generate Code values</span></span>  
  
1.  <span data-ttu-id="745b2-112">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="745b2-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="745b2-113">На странице **Обозреватель моделей** в строке меню наведите указатель мыши на пункт **Управление** и щелкните **сущности**.</span><span class="sxs-lookup"><span data-stu-id="745b2-113">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="745b2-114">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="745b2-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="745b2-115">Выберите строку сущности, для которой необходимо сформировать коды.</span><span class="sxs-lookup"><span data-stu-id="745b2-115">Select the row for the entity that you want to generate codes for.</span></span>  
  
5.  <span data-ttu-id="745b2-116">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="745b2-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="745b2-117">Установите флажок в поле **Автоматически создавать значения кода** .</span><span class="sxs-lookup"><span data-stu-id="745b2-117">Select the **Create Code values automatically** check box.</span></span>  
  
7.  <span data-ttu-id="745b2-118">В поле **Начать с** введите начальное значение, с которого начнется приращение.</span><span class="sxs-lookup"><span data-stu-id="745b2-118">In the **Start with** box, type a number to begin incrementing.</span></span> <span data-ttu-id="745b2-119">Если элементы уже существуют, то значение Code будет установлено, исходя из наибольшего существующего значения.</span><span class="sxs-lookup"><span data-stu-id="745b2-119">If members already exist, the Code will be set based on the highest existing value.</span></span> <span data-ttu-id="745b2-120">Например, если наибольшее существующее значение Code равно 299, то следующее значение Code элемента будет равно 300.</span><span class="sxs-lookup"><span data-stu-id="745b2-120">For example, if the highest existing Code value is 299, the next member's Code value will be set to 300.</span></span>  
  
8.  <span data-ttu-id="745b2-121">Нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="745b2-121">Click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="745b2-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="745b2-122">See Also</span></span>  
 <span data-ttu-id="745b2-123">[Автоматическое создание кода &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="745b2-123">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 [<span data-ttu-id="745b2-124">Автоматическое формирование значений атрибута, отличного от Code (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="745b2-124">Automatically Generate Attribute Values Other Than Code &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/automatically-generate-attribute-values-other-than-code-master-data-services.md)  
  
  
