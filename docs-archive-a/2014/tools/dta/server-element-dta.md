---
title: Элемент Server (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: 9fe0bfb4-3aa6-4eb2-a83e-c0d0e7d4e9f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab67e0303c2b629c3774886441474f5ef5b10a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666312"
---
# <a name="server-element-dta"></a><span data-ttu-id="49614-102">Элемент Server (DTA)</span><span class="sxs-lookup"><span data-stu-id="49614-102">Server Element (DTA)</span></span>
  <span data-ttu-id="49614-103">Содержит сведения идентификации сервера, на котором находятся настраиваемые базы данных.</span><span class="sxs-lookup"><span data-stu-id="49614-103">Contains the identifying information for the server on which the databases reside that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49614-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49614-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
    ...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="49614-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="49614-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="49614-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="49614-106">Characteristic</span></span>|<span data-ttu-id="49614-107">Описание</span><span class="sxs-lookup"><span data-stu-id="49614-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="49614-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="49614-108">**Data type and length**</span></span>|<span data-ttu-id="49614-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="49614-109">None.</span></span>|  
|<span data-ttu-id="49614-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="49614-110">**Default value**</span></span>|<span data-ttu-id="49614-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="49614-111">None.</span></span>|  
|<span data-ttu-id="49614-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="49614-112">**Occurrence**</span></span>|<span data-ttu-id="49614-113">Требуется один раз на каждый элемент `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="49614-113">Required once per `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="49614-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="49614-114">Element Relationships</span></span>  
  
|<span data-ttu-id="49614-115">Связь</span><span class="sxs-lookup"><span data-stu-id="49614-115">Relationship</span></span>|<span data-ttu-id="49614-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="49614-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="49614-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="49614-117">**Parent element**</span></span>|[<span data-ttu-id="49614-118">Элемент DTAInput (DTA)</span><span class="sxs-lookup"><span data-stu-id="49614-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="49614-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="49614-119">**Child elements**</span></span>|[<span data-ttu-id="49614-120">Элемент Name описания сервера (DTA)</span><span class="sxs-lookup"><span data-stu-id="49614-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="49614-121">Элемент Database описания сервера (DTA)</span><span class="sxs-lookup"><span data-stu-id="49614-121">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="49614-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="49614-122">Remarks</span></span>  
 <span data-ttu-id="49614-123">Для элемента можно указать только один `Server` элемент `DTAInput` .</span><span class="sxs-lookup"><span data-stu-id="49614-123">You can specify only one `Server` element for the `DTAInput` element.</span></span> <span data-ttu-id="49614-124">Этот элемент с именем **ServerDetailsTypecomplexType** определен в схеме XML DTA.</span><span class="sxs-lookup"><span data-stu-id="49614-124">This element is of the **ServerDetailsTypecomplexType** name in the DTA XML schema.</span></span> <span data-ttu-id="49614-125">Не следует путать данный элемент `Server` с дочерним элементом элемента `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="49614-125">Do not confuse this `Server` element with the one that is the child of the `Configuration` element.</span></span> <span data-ttu-id="49614-126">Дополнительные сведения см. в разделе [Элемент Server описания конфигурации (DTA)](server-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="49614-126">For more information, see [Server Element for Configuration &#40;DTA&#41;](server-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49614-127">Пример</span><span class="sxs-lookup"><span data-stu-id="49614-127">Example</span></span>  
 <span data-ttu-id="49614-128">Следующий пример иллюстрирует, как указать таблицу **Sales.SalesPerson** в базе данных **AdventureWorks** на сервере SERVER001:</span><span class="sxs-lookup"><span data-stu-id="49614-128">The following example shows how to specify the **Sales.SalesPerson** table in the **AdventureWorks** database on SERVER001:</span></span>  
  
```xml  
<Server>  
  <Name>SERVER001</Name>  
  <Database>  
    <Name>AdventureWorks</Name>  
    <Schema>  
      <Name>Sales</Name>  
      <Table>  
        <Name>SalesPerson</Name>  
      </Table>  
    </Schema>  
  </Database>  
</Server  
```  
  
## <a name="see-also"></a><span data-ttu-id="49614-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="49614-129">See Also</span></span>  
 [<span data-ttu-id="49614-130">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="49614-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
