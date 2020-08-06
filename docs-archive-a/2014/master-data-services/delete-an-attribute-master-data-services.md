---
title: Удаление атрибута (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], deleting
- deleting attributes [Master Data Services]
ms.assetid: ec3e66f7-0e35-43d7-a80d-64899948ebfe
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 96db56dac9356b1131e722fc7f6b779c93305bb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728418"
---
# <a name="delete-an-attribute-master-data-services"></a><span data-ttu-id="16a82-102">Удаление атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="16a82-102">Delete an Attribute (Master Data Services)</span></span>
  <span data-ttu-id="16a82-103">Операция удаления атрибута в службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]без возможности восстановления удаляет атрибут и все связанные с ним значения.</span><span class="sxs-lookup"><span data-stu-id="16a82-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute when you want to permanently delete the attribute and all associated attribute values.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="16a82-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="16a82-104">Prerequisites</span></span>  
 <span data-ttu-id="16a82-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="16a82-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="16a82-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="16a82-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="16a82-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="16a82-107">You must be a model administrator.</span></span> <span data-ttu-id="16a82-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="16a82-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute"></a><span data-ttu-id="16a82-109">Удаление атрибута</span><span class="sxs-lookup"><span data-stu-id="16a82-109">To delete an attribute</span></span>  
  
1.  <span data-ttu-id="16a82-110">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="16a82-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="16a82-111">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="16a82-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="16a82-112">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="16a82-112">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="16a82-113">Выберите строку сущности, содержащую атрибут, который необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="16a82-113">Select the row for the entity that contains the attribute you want to delete.</span></span>  
  
5.  <span data-ttu-id="16a82-114">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="16a82-114">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="16a82-115">На странице **Изменение сущности** щелкните атрибут, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="16a82-115">On the **Edit Entity** page, click the attribute you want to delete.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16a82-116">Удалить атрибуты «Имя» и «Код» нельзя.</span><span class="sxs-lookup"><span data-stu-id="16a82-116">You cannot delete the Name or Code attributes.</span></span>  
  
7.  <span data-ttu-id="16a82-117">Щелкните **Удалить выбранный атрибут**.</span><span class="sxs-lookup"><span data-stu-id="16a82-117">Click **Delete selected attribute**.</span></span>  
  
8.  <span data-ttu-id="16a82-118">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="16a82-118">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="16a82-119">В дополнительном диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="16a82-119">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a82-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="16a82-120">See Also</span></span>  
 <span data-ttu-id="16a82-121">[Master Data Services &#40;атрибутов&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="16a82-121">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="16a82-122">[Атрибуты на основе домена &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="16a82-122">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="16a82-123">[Создание текстового атрибута &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="16a82-123">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="16a82-124">Создание атрибута на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="16a82-124">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
