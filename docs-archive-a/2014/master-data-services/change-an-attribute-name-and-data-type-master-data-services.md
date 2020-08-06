---
title: Изменение имени атрибута (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], changing name
ms.assetid: d348f238-f59d-41c7-ad20-3ccd55bfd9e5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: abbe5f666daed42b25b46f02e954343b57446145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734226"
---
# <a name="change-an-attribute-name-master-data-services"></a><span data-ttu-id="47be4-102">Изменение имени атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="47be4-102">Change an Attribute Name (Master Data Services)</span></span>
  <span data-ttu-id="47be4-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно изменять имя атрибутов.</span><span class="sxs-lookup"><span data-stu-id="47be4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can change the name of an attribute.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="47be4-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="47be4-104">Prerequisites</span></span>  
 <span data-ttu-id="47be4-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="47be4-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="47be4-106">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="47be4-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="47be4-107">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="47be4-107">You must be a model administrator.</span></span> <span data-ttu-id="47be4-108">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="47be4-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-change-an-attribute-name"></a><span data-ttu-id="47be4-109">Изменение имени атрибута</span><span class="sxs-lookup"><span data-stu-id="47be4-109">To change an attribute name</span></span>  
  
1.  <span data-ttu-id="47be4-110">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="47be4-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="47be4-111">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="47be4-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="47be4-112">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="47be4-112">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="47be4-113">Щелкните строку сущности, содержащую атрибут, имя которого необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="47be4-113">Click the row for the entity that contains the attribute with the name you want to change.</span></span>  
  
5.  <span data-ttu-id="47be4-114">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="47be4-114">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="47be4-115">На странице **Изменение сущности** щелкните атрибут с именем, которое необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="47be4-115">On the **Edit Entity** page, click the attribute with the name you want to change.</span></span>  
  
7.  <span data-ttu-id="47be4-116">Щелкните **изменить выбранный атрибут**.</span><span class="sxs-lookup"><span data-stu-id="47be4-116">Click **Edit selected attribute**.</span></span>  
  
8.  <span data-ttu-id="47be4-117">Введите новое имя атрибута в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="47be4-117">In the **Name** box, type the updated name of the attribute.</span></span> <span data-ttu-id="47be4-118">Список слов, которые не должны использоваться в качестве имен атрибутов, см. в разделе [зарезервированные слова &#40;Master Data Services&#41;](reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="47be4-118">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="47be4-119">Нажмите кнопку **Сохранить атрибут**.</span><span class="sxs-lookup"><span data-stu-id="47be4-119">Click **Save attribute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47be4-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="47be4-120">See Also</span></span>  
 <span data-ttu-id="47be4-121">[Создание текстового атрибута &#40;Master Data Services&#41;](create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="47be4-121">[Create a Text Attribute &#40;Master Data Services&#41;](create-a-text-attribute-master-data-services.md) </span></span>  
 <span data-ttu-id="47be4-122">[Удаление атрибута &#40;Master Data Services&#41;](delete-an-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="47be4-122">[Delete an Attribute &#40;Master Data Services&#41;](delete-an-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="47be4-123">Атрибуты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="47be4-123">Attributes &#40;Master Data Services&#41;</span></span>](attributes-master-data-services.md)  
  
  
