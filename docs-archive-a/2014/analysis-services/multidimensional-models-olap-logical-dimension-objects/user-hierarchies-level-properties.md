---
title: Свойства уровня | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- user hierarchies [Analysis Services]
- hierarchies [Analysis Services], user
ms.assetid: dabb7335-887b-442a-b67c-4901ba1242b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 553503b9d35142bcc998b4ec12ad2e29d4c66318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656019"
---
# <a name="level-properties"></a><span data-ttu-id="165f8-102">Свойства уровня</span><span class="sxs-lookup"><span data-stu-id="165f8-102">Level Properties</span></span> 
  <span data-ttu-id="165f8-103">В следующей таблице приведен список и описание свойств уровня в пользовательской иерархии.</span><span class="sxs-lookup"><span data-stu-id="165f8-103">The following table lists and describes the properties of a level in a user-defined hierarchy.</span></span>  
  
|<span data-ttu-id="165f8-104">Свойство</span><span class="sxs-lookup"><span data-stu-id="165f8-104">Property</span></span>|<span data-ttu-id="165f8-105">Описание</span><span class="sxs-lookup"><span data-stu-id="165f8-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="165f8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="165f8-106">Description</span></span>|<span data-ttu-id="165f8-107">Содержит описание уровня.</span><span class="sxs-lookup"><span data-stu-id="165f8-107">Contains the description of the level.</span></span>|  
|<span data-ttu-id="165f8-108">HideMemberIf</span><span class="sxs-lookup"><span data-stu-id="165f8-108">HideMemberIf</span></span>|<span data-ttu-id="165f8-109">Указывает, необходимо ли и когда необходимо скрывать элемент уровня от клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="165f8-109">Indicates whether and when a member in a level should be hidden from client applications.</span></span> <span data-ttu-id="165f8-110">Это свойство может иметь следующие значения:</span><span class="sxs-lookup"><span data-stu-id="165f8-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="165f8-111">Никогда</span><span class="sxs-lookup"><span data-stu-id="165f8-111">Never</span></span><br /> <span data-ttu-id="165f8-112">Элементы никогда не скрываются.</span><span class="sxs-lookup"><span data-stu-id="165f8-112">Members are never hidden.</span></span> <span data-ttu-id="165f8-113">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="165f8-113">This is the default value.</span></span><br /><br /> <span data-ttu-id="165f8-114">OnlyChildWithNoName</span><span class="sxs-lookup"><span data-stu-id="165f8-114">OnlyChildWithNoName</span></span><br /> <span data-ttu-id="165f8-115">Элемент скрывается, когда он является единственным дочерним элементом своего родительского элемента и его имя пусто.</span><span class="sxs-lookup"><span data-stu-id="165f8-115">A member is hidden when the member is the only child of its parent and the member's name is empty.</span></span><br /><br /> <span data-ttu-id="165f8-116">OnlyChildWithParentName</span><span class="sxs-lookup"><span data-stu-id="165f8-116">OnlyChildWithParentName</span></span><br /> <span data-ttu-id="165f8-117">Элемент скрывается, когда он является единственным дочерним элементом своего родительского элемента и его имя идентично имени родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="165f8-117">A member is hidden when the member is the only child of its parent and the member's name is identical to that of its parent.</span></span><br /><br /> <span data-ttu-id="165f8-118">NoName</span><span class="sxs-lookup"><span data-stu-id="165f8-118">NoName</span></span><br /> <span data-ttu-id="165f8-119">Элемент скрывается, когда его имя пусто.</span><span class="sxs-lookup"><span data-stu-id="165f8-119">A member is hidden when the member's name is empty.</span></span><br /><br /> <span data-ttu-id="165f8-120">ParentName</span><span class="sxs-lookup"><span data-stu-id="165f8-120">ParentName</span></span><br /> <span data-ttu-id="165f8-121">Элемент скрывается, когда его имя идентично имени родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="165f8-121">A member is hidden when the member's name is identical to that of its parent.</span></span>|  
|<span data-ttu-id="165f8-122">ID</span><span class="sxs-lookup"><span data-stu-id="165f8-122">ID</span></span>|<span data-ttu-id="165f8-123">Содержит уникальный идентификатор уровня.</span><span class="sxs-lookup"><span data-stu-id="165f8-123">Contains the unique identifier (ID) of the level.</span></span>|  
|<span data-ttu-id="165f8-124">Имя</span><span class="sxs-lookup"><span data-stu-id="165f8-124">Name</span></span>|<span data-ttu-id="165f8-125">Содержит понятное имя уровня.</span><span class="sxs-lookup"><span data-stu-id="165f8-125">Contains the friendly name of the level.</span></span> <span data-ttu-id="165f8-126">По умолчанию имя уровня совпадает с именем исходного атрибута.</span><span class="sxs-lookup"><span data-stu-id="165f8-126">By default, the name of a level is the same as the name of the source attribute.</span></span>|  
|<span data-ttu-id="165f8-127">SourceAttribute</span><span class="sxs-lookup"><span data-stu-id="165f8-127">SourceAttribute</span></span>|<span data-ttu-id="165f8-128">Содержит имя исходного атрибута, на котором основан уровень.</span><span class="sxs-lookup"><span data-stu-id="165f8-128">Contains the name of the source attribute on which the level is based.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="165f8-129">См. также</span><span class="sxs-lookup"><span data-stu-id="165f8-129">See Also</span></span>  
 [<span data-ttu-id="165f8-130">Свойства пользовательской иерархии</span><span class="sxs-lookup"><span data-stu-id="165f8-130">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
