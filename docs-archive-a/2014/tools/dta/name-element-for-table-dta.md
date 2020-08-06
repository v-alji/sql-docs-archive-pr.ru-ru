---
title: Элемент Name для Table (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: 422a755f-ee52-4863-b1aa-f4ef1b8fd0bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8fa8481cf8990fb63995abcb6300cd9a352c859a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666317"
---
# <a name="name-element-for-table-dta"></a><span data-ttu-id="59a48-102">Элемент Name описания таблицы (DTA)</span><span class="sxs-lookup"><span data-stu-id="59a48-102">Name Element for Table (DTA)</span></span>
  <span data-ttu-id="59a48-103">Позволяет задать имя настраиваемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="59a48-103">Specifies a table name for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59a48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59a48-104">Syntax</span></span>  
  
```  
  
<Schema>  
    <Table>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="59a48-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="59a48-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="59a48-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="59a48-106">Characteristic</span></span>|<span data-ttu-id="59a48-107">Описание</span><span class="sxs-lookup"><span data-stu-id="59a48-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="59a48-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="59a48-108">**Data type and length**</span></span>|<span data-ttu-id="59a48-109">`string`, от 1 до 255 символов</span><span class="sxs-lookup"><span data-stu-id="59a48-109">`string`, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="59a48-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="59a48-110">**Default value**</span></span>|<span data-ttu-id="59a48-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="59a48-111">None.</span></span>|  
|<span data-ttu-id="59a48-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="59a48-112">**Occurrence**</span></span>|<span data-ttu-id="59a48-113">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59a48-113">Required.</span></span> <span data-ttu-id="59a48-114">Один раз для каждого элемента `Table`.</span><span class="sxs-lookup"><span data-stu-id="59a48-114">Once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="59a48-115">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="59a48-115">Element Relationships</span></span>  
  
|<span data-ttu-id="59a48-116">Связь</span><span class="sxs-lookup"><span data-stu-id="59a48-116">Relationship</span></span>|<span data-ttu-id="59a48-117">Элементы</span><span class="sxs-lookup"><span data-stu-id="59a48-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="59a48-118">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="59a48-118">**Parent element**</span></span>|[<span data-ttu-id="59a48-119">Элемент Table для схемы (DTA)</span><span class="sxs-lookup"><span data-stu-id="59a48-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="59a48-120">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="59a48-120">**Child elements**</span></span>|<span data-ttu-id="59a48-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="59a48-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="59a48-122">Пример</span><span class="sxs-lookup"><span data-stu-id="59a48-122">Example</span></span>  
 <span data-ttu-id="59a48-123">Пример использования см. в разделе [Элемент Server (DTA)](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="59a48-123">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a48-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="59a48-124">See Also</span></span>  
 [<span data-ttu-id="59a48-125">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="59a48-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
