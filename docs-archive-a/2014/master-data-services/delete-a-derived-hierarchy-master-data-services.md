---
title: Удаление производной иерархии (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting derived hierarchies [Master Data Services]
- derived hierarchies, deleting
ms.assetid: f46d660e-47f2-47ca-9372-1b5931540beb
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a49922c0d719415436d28eb48657a7fc93c547fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664974"
---
# <a name="delete-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="0c59e-102">Удаление производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0c59e-102">Delete a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="0c59e-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]можно удалить производную иерархию, если она больше не нужна.</span><span class="sxs-lookup"><span data-stu-id="0c59e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a derived hierarchy when you are sure you no longer need it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c59e-104">Удаление производной иерархии не влияет на связи атрибутов, на которых основана иерархия.</span><span class="sxs-lookup"><span data-stu-id="0c59e-104">Deleting a derived hierarchy has no effect on the attribute relationships that the hierarchy is based on.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0c59e-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0c59e-105">Prerequisites</span></span>  
 <span data-ttu-id="0c59e-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="0c59e-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0c59e-107">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="0c59e-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="0c59e-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="0c59e-108">You must be a model administrator.</span></span> <span data-ttu-id="0c59e-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0c59e-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-derived-hierarchy"></a><span data-ttu-id="0c59e-110">Удаление производной иерархии</span><span class="sxs-lookup"><span data-stu-id="0c59e-110">To delete a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="0c59e-111">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="0c59e-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="0c59e-112">На странице **представление модели** в строке меню наведите указатель мыши на пункт **Управление** и щелкните **производные иерархии**.</span><span class="sxs-lookup"><span data-stu-id="0c59e-112">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="0c59e-113">На странице **Обслуживание производной иерархии** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="0c59e-113">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="0c59e-114">Выберите строку для производной иерархии, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="0c59e-114">Select the row for the derived hierarchy that you want to delete.</span></span>  
  
5.  <span data-ttu-id="0c59e-115">Нажмите кнопку **Удалить выбранную иерархию**.</span><span class="sxs-lookup"><span data-stu-id="0c59e-115">Click **Delete selected hierarchy**.</span></span>  
  
6.  <span data-ttu-id="0c59e-116">В диалоговом окне подтверждения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0c59e-116">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c59e-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="0c59e-117">See Also</span></span>  
 <span data-ttu-id="0c59e-118">[Создание производной иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0c59e-118">[Create a Derived Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="0c59e-119">Производные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0c59e-119">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
