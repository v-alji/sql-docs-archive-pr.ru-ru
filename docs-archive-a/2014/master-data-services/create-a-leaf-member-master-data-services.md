---
title: Создание конечного элемента (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services], creating
- creating leaf members [Master Data Services]
- members [Master Data Services], creating leaf members
ms.assetid: 0499d3b3-d508-4d43-a740-19cf53ade9f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe0245dd30019e1cb9112754bd8b8eeafed93aa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654392"
---
# <a name="create-a-leaf-member-master-data-services"></a><span data-ttu-id="7db32-102">Создание конечного элемента (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7db32-102">Create a Leaf Member (Master Data Services)</span></span>
  <span data-ttu-id="7db32-103">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] среде конечный элемент создается, если требуется добавить основные данные в систему и не используются промежуточные таблицы или [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="7db32-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a leaf member when you want to add master data to your system and are not using staging tables or the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] to import data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7db32-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7db32-104">Prerequisites</span></span>  
 <span data-ttu-id="7db32-105">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="7db32-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="7db32-106">Необходимо иметь разрешение на доступ к функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="7db32-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="7db32-107">Для сущности, в которую добавляется элемент, необходимо иметь разрешение на **Обновление** для объекта конечной модели.</span><span class="sxs-lookup"><span data-stu-id="7db32-107">You must have a minimum of **Update** permission to the leaf model object for the entity you are adding a member to.</span></span>  
  
### <a name="to-create-a-leaf-member"></a><span data-ttu-id="7db32-108">Создание конечного элемента</span><span class="sxs-lookup"><span data-stu-id="7db32-108">To create a leaf member</span></span>  
  
1.  <span data-ttu-id="7db32-109">На домашней странице [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] выберите модель в списке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="7db32-109">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="7db32-110">Если вы пользователь, выберите открытую версию из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="7db32-110">If you are a user, select an open version from the **Version** list.</span></span> <span data-ttu-id="7db32-111">Если вы являетесь администратором, выберите версию в открытом или блокированном состоянии из списка **Версия** .</span><span class="sxs-lookup"><span data-stu-id="7db32-111">If you are an administrator, select a version with open or locked status from the **Version** list.</span></span>  
  
3.  <span data-ttu-id="7db32-112">Нажмите кнопку **Браузер**.</span><span class="sxs-lookup"><span data-stu-id="7db32-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="7db32-113">В строке меню наведите указатель на пункт **Сущности** и щелкните имя сущности, к которой нужно добавить элемент.</span><span class="sxs-lookup"><span data-stu-id="7db32-113">From the menu bar, point to **Entities** and click the name of the entity you want to add a member to.</span></span>  
  
5.  <span data-ttu-id="7db32-114">Нажмите кнопку **Добавить элемент**.</span><span class="sxs-lookup"><span data-stu-id="7db32-114">Click **Add member**.</span></span>  
  
6.  <span data-ttu-id="7db32-115">Заполните поля в области **Сведения** .</span><span class="sxs-lookup"><span data-stu-id="7db32-115">In the **Details** pane, complete the fields.</span></span>  
  
7.  <span data-ttu-id="7db32-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7db32-116">Optional.</span></span> <span data-ttu-id="7db32-117">В поле **Заметки** введите комментарий о том, для чего добавлен элемент.</span><span class="sxs-lookup"><span data-stu-id="7db32-117">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="7db32-118">Заметку могут просматривать все пользователи, которые имеют доступ к элементу.</span><span class="sxs-lookup"><span data-stu-id="7db32-118">All users who have access to the member can view the annotation.</span></span>  
  
8.  <span data-ttu-id="7db32-119">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7db32-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db32-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="7db32-120">See Also</span></span>  
 <span data-ttu-id="7db32-121">[Загрузка или обновление элементов в Master Data Services с помощью промежуточного процесса](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7db32-121">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="7db32-122">[Создание &#40;объединенного элемента Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7db32-122">[Create a Consolidated Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span></span>  
 [<span data-ttu-id="7db32-123">Элементы (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7db32-123">Members &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/members-master-data-services.md)  
  
  
