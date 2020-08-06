---
title: Зарезервированные слова (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- reserved words [Master Data Services]
- Master Data Services, reserved words
ms.assetid: 88afd0d0-4362-4394-8357-4e65388fc0fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c54bb371cd8f797cfb36f015387e0e21339c0426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664971"
---
# <a name="reserved-words-master-data-services"></a><span data-ttu-id="ea7d0-102">Зарезервированные слова (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ea7d0-102">Reserved Words (Master Data Services)</span></span>
  <span data-ttu-id="ea7d0-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]при создании элементов и объектов модели нельзя использовать некоторые слова.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when you create model objects or members, some words cannot be used.</span></span> <span data-ttu-id="ea7d0-104">В противном случае могут возникнуть ошибки.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-104">Using these words may cause errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea7d0-105">Кроме того, следует ограничить использование специальных знаков (особых символов, знаков переноса и т. п.).</span><span class="sxs-lookup"><span data-stu-id="ea7d0-105">You should also limit your use of special characters (symbols, hyphenation, etc.).</span></span>  
  
-   [<span data-ttu-id="ea7d0-106">Модели</span><span class="sxs-lookup"><span data-stu-id="ea7d0-106">Models</span></span>](#models)  
  
-   [<span data-ttu-id="ea7d0-107">Сущности</span><span class="sxs-lookup"><span data-stu-id="ea7d0-107">Entities</span></span>](#entities)  
  
-   [<span data-ttu-id="ea7d0-108">Явные иерархии</span><span class="sxs-lookup"><span data-stu-id="ea7d0-108">Explicit Hierarchies</span></span>](#exhierarchies)  
  
-   [<span data-ttu-id="ea7d0-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea7d0-109">Attributes</span></span>](#attributes)  
  
-   [<span data-ttu-id="ea7d0-110">Члены</span><span class="sxs-lookup"><span data-stu-id="ea7d0-110">Members</span></span>](#members)  
  
##  <a name="models"></a><a name="models"></a><span data-ttu-id="ea7d0-111">Моделью</span><span class="sxs-lookup"><span data-stu-id="ea7d0-111">Models</span></span>  
 <span data-ttu-id="ea7d0-112">Если вы создаете модель с именем **Name, не**выбирайте параметр **создать сущность с тем же именем, что и модель** , поскольку **имя** не может использоваться для имени сущности.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-112">If you create a model with the name set to **Name**, do not select **Create entity with same name as model** because **Name** cannot be used for the name of an entity.</span></span>  
  
##  <a name="entities"></a><a name="entities"></a><span data-ttu-id="ea7d0-113">Объектах</span><span class="sxs-lookup"><span data-stu-id="ea7d0-113">Entities</span></span>  
 <span data-ttu-id="ea7d0-114">В качестве имен сущностей нельзя указывать **Name** и **Code**.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-114">For entity names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="explicit-hierarchies"></a><a name="exhierarchies"></a><span data-ttu-id="ea7d0-115">Явные иерархии</span><span class="sxs-lookup"><span data-stu-id="ea7d0-115">Explicit Hierarchies</span></span>  
 <span data-ttu-id="ea7d0-116">В качестве имен явных иерархий нельзя указывать **Name** и **Code**.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-116">For explicit hierarchy names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="attributes"></a><a name="attributes"></a><span data-ttu-id="ea7d0-117">Атрибута</span><span class="sxs-lookup"><span data-stu-id="ea7d0-117">Attributes</span></span>  
  
-   <span data-ttu-id="ea7d0-118">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-118">**ID**</span></span>  
  
-   <span data-ttu-id="ea7d0-119">**Код**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-119">**Code**</span></span>  
  
-   <span data-ttu-id="ea7d0-120">**имя**;</span><span class="sxs-lookup"><span data-stu-id="ea7d0-120">**Name**</span></span>  
  
-   <span data-ttu-id="ea7d0-121">**EnterDTM**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-121">**EnterDTM**</span></span>  
  
-   <span data-ttu-id="ea7d0-122">**EnterUserID**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-122">**EnterUserID**</span></span>  
  
-   <span data-ttu-id="ea7d0-123">**EnterUserName**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-123">**EnterUserName**</span></span>  
  
-   <span data-ttu-id="ea7d0-124">**LastChgDTM**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-124">**LastChgDTM**</span></span>  
  
-   <span data-ttu-id="ea7d0-125">**LastChgUserID**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-125">**LastChgUserID**</span></span>  
  
-   <span data-ttu-id="ea7d0-126">**Status_ID**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-126">**Status_ID**</span></span>  
  
-   <span data-ttu-id="ea7d0-127">**ValidationStatus_ID**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-127">**ValidationStatus_ID**</span></span>  
  
-   <span data-ttu-id="ea7d0-128">**Version_ID**</span><span class="sxs-lookup"><span data-stu-id="ea7d0-128">**Version_ID**</span></span>  
  
##  <a name="members"></a><a name="members"></a><span data-ttu-id="ea7d0-129">Участниками</span><span class="sxs-lookup"><span data-stu-id="ea7d0-129">Members</span></span>  
 <span data-ttu-id="ea7d0-130">Для элементов нельзя использовать **MDMMemberStatus** или **root** в качестве значения атрибута **Code** .</span><span class="sxs-lookup"><span data-stu-id="ea7d0-130">For members, you cannot use **MDMMemberStatus** or **ROOT** for the **Code** attribute value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea7d0-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea7d0-131">See Also</span></span>  
 [<span data-ttu-id="ea7d0-132">Обзор Master Data Services</span><span class="sxs-lookup"><span data-stu-id="ea7d0-132">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
  
