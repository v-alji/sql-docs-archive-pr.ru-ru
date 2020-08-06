---
title: Элемент Database для рабочей нагрузки (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: 112fca2a-37e5-4162-b2e7-b56eb8ab0c6f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2774bc7ed981c84c966a394c95347208cbc6d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727657"
---
# <a name="database-element-for-workload-dta"></a><span data-ttu-id="715ff-102">Элемент Database описания рабочей нагрузки (DTA)</span><span class="sxs-lookup"><span data-stu-id="715ff-102">Database Element for Workload (DTA)</span></span>
  <span data-ttu-id="715ff-103">Указывает базу данных, в которой находится таблица трассировки рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="715ff-103">Specifies the database where the workload trace table is located.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="715ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="715ff-104">Syntax</span></span>  
  
```  
  
<Workload>  
  <Database>  
   ...code removed here...  
  </Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="715ff-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="715ff-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="715ff-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="715ff-106">Characteristic</span></span>|<span data-ttu-id="715ff-107">Описание</span><span class="sxs-lookup"><span data-stu-id="715ff-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="715ff-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="715ff-108">**Data type and length**</span></span>|<span data-ttu-id="715ff-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="715ff-109">None.</span></span>|  
|<span data-ttu-id="715ff-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="715ff-110">**Default value**</span></span>|<span data-ttu-id="715ff-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="715ff-111">None.</span></span>|  
|<span data-ttu-id="715ff-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="715ff-112">**Occurrence**</span></span>|<span data-ttu-id="715ff-113">Необходимо наличие одного такого элемента, если не задан никакой другой тип рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="715ff-113">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="715ff-114">Для родительского элемента `EventString` необходимо задать дочерний элемент `File`, `Database` или `Workload`, однако одновременно может использоваться только один из них.</span><span class="sxs-lookup"><span data-stu-id="715ff-114">You must specify an `EventString`, a `File`, or a `Database` child element for the `Workload` parent, but only one type can be used.</span></span> <span data-ttu-id="715ff-115">Например, если рабочая нагрузка определена посредством элемента `Database`, в том же входном XML-файле нельзя указывать рабочую нагрузку также с помощью элемента `File`.</span><span class="sxs-lookup"><span data-stu-id="715ff-115">For example, if you specify a workload with the `Database` element, you cannot also specify a workload with the `File` element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="715ff-116">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="715ff-116">Element Relationships</span></span>  
  
|<span data-ttu-id="715ff-117">Связь</span><span class="sxs-lookup"><span data-stu-id="715ff-117">Relationship</span></span>|<span data-ttu-id="715ff-118">Элементы</span><span class="sxs-lookup"><span data-stu-id="715ff-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="715ff-119">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="715ff-119">**Parent element**</span></span>|[<span data-ttu-id="715ff-120">Элемент Workload (DTA)</span><span class="sxs-lookup"><span data-stu-id="715ff-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="715ff-121">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="715ff-121">**Child elements**</span></span>|[<span data-ttu-id="715ff-122">Элемент Name для базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="715ff-122">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="715ff-123">Элемент Schema описания базы данных (DTA)</span><span class="sxs-lookup"><span data-stu-id="715ff-123">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="715ff-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="715ff-124">Remarks</span></span>  
 <span data-ttu-id="715ff-125">Этот элемент с именем **DatabaseDetailsTypecomplexType** определен в схеме XML помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="715ff-125">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="715ff-126">Не путайте этот элемент `Database` с элементом, корневым родительским элементом которого является `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="715ff-126">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="715ff-127">(См. раздел [Элемент Database описания конфигурации (DTA)](database-element-for-configuration-dta.md).)</span><span class="sxs-lookup"><span data-stu-id="715ff-127">(See [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).)</span></span>  
  
## <a name="example"></a><span data-ttu-id="715ff-128">Пример</span><span class="sxs-lookup"><span data-stu-id="715ff-128">Example</span></span>  
 <span data-ttu-id="715ff-129">Пример использования этого `Database` элемента см. в примере кода в [элементе рабочей нагрузки &#40;dta&#41;](workload-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="715ff-129">For a usage example of this `Database` element, see the code example in [Workload Element &#40;DTA&#41;](workload-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="715ff-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="715ff-130">See Also</span></span>  
 [<span data-ttu-id="715ff-131">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="715ff-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
