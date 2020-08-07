---
title: Элемент DatabaseToConnect (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DatabaseToConnect element
ms.assetid: 65153a66-3aee-4429-99b7-0816ac23c285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c21b36319e4007264677d499b84964c7cb5ea7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727649"
---
# <a name="databasetoconnect-element-dta"></a><span data-ttu-id="58c2a-102">Элемент DatabaseToConnect (DTA)</span><span class="sxs-lookup"><span data-stu-id="58c2a-102">DatabaseToConnect Element (DTA)</span></span>
  <span data-ttu-id="58c2a-103">Позволяет задать первую базу данных, к которой подключается помощник по настройке ядра СУБД при настройке рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="58c2a-103">Specifies the first database to which Database Engine Tuning Advisor connects when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58c2a-104">Syntax</span></span>  
  
```  
  
    <TuningOptions>  
...code removed here...  
      <DatabaseToConnect>...</DatabaseToConnect>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="58c2a-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="58c2a-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="58c2a-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="58c2a-106">Characteristic</span></span>|<span data-ttu-id="58c2a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="58c2a-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="58c2a-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="58c2a-108">**Data type and length**</span></span>|<span data-ttu-id="58c2a-109">`string`, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="58c2a-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="58c2a-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="58c2a-110">**Default value**</span></span>|<span data-ttu-id="58c2a-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="58c2a-111">None.</span></span>|  
|<span data-ttu-id="58c2a-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="58c2a-112">**Occurrence**</span></span>|<span data-ttu-id="58c2a-113">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="58c2a-113">Optional.</span></span> <span data-ttu-id="58c2a-114">Может использоваться один раз для каждого элемента `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="58c2a-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="58c2a-115">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="58c2a-115">Element Relationships</span></span>  
  
|<span data-ttu-id="58c2a-116">Связь</span><span class="sxs-lookup"><span data-stu-id="58c2a-116">Relationship</span></span>|<span data-ttu-id="58c2a-117">Элементы</span><span class="sxs-lookup"><span data-stu-id="58c2a-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="58c2a-118">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="58c2a-118">**Parent element**</span></span>|[<span data-ttu-id="58c2a-119">Элемент TuningOptions (DTA)</span><span class="sxs-lookup"><span data-stu-id="58c2a-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="58c2a-120">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="58c2a-120">**Child elements**</span></span>|<span data-ttu-id="58c2a-121">None</span><span class="sxs-lookup"><span data-stu-id="58c2a-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58c2a-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="58c2a-122">Remarks</span></span>  
 <span data-ttu-id="58c2a-123">Используйте `DatabaseToConnect` для указания имени первой базы данных, к которой должен подключиться помощник по настройке ядра СУБД при запуске сеанса настройки.</span><span class="sxs-lookup"><span data-stu-id="58c2a-123">Use `DatabaseToConnect` to specify the name of the first database to which you want Database Engine Tuning Advisor to connect when it starts the tuning session.</span></span> <span data-ttu-id="58c2a-124">Этот элемент позволяет задать только одну базу данных.</span><span class="sxs-lookup"><span data-stu-id="58c2a-124">You can specify only one database with this element.</span></span> <span data-ttu-id="58c2a-125">Если задано несколько имен баз данных, помощник по настройке ядра СУБД вернет ошибку.</span><span class="sxs-lookup"><span data-stu-id="58c2a-125">If multiple database names are specified, Database Engine Tuning Advisor returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58c2a-126">Пример</span><span class="sxs-lookup"><span data-stu-id="58c2a-126">Example</span></span>  
 <span data-ttu-id="58c2a-127">Пример использования см. в разделе [Образец входного XML-файла с описанием встроенной рабочей нагрузки (DTA)](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="58c2a-127">For a usage example, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c2a-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="58c2a-128">See Also</span></span>  
 [<span data-ttu-id="58c2a-129">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="58c2a-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
