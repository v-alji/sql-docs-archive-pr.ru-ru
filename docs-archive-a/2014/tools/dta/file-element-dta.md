---
title: Элемент File (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- File element
ms.assetid: 73dce835-9a80-4aef-8e0f-9dcf07dd5b80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0eeb2bdcc9513ca6283447daca63c8bbc4fa1726
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735750"
---
# <a name="file-element-dta"></a><span data-ttu-id="841fb-102">Элемент File (DTA)</span><span class="sxs-lookup"><span data-stu-id="841fb-102">File Element (DTA)</span></span>
  <span data-ttu-id="841fb-103">Служит для указания файла рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="841fb-103">Specifies the workload file.</span></span> <span data-ttu-id="841fb-104">Рабочая нагрузка представляет собой набор инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемый в одной или нескольких базах данных, которые необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="841fb-104">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="841fb-105">Файлы рабочей нагрузки могут представлять собой скрипты [!INCLUDE[tsql](../../includes/tsql-md.md)] (SQL) или файлы трассировки (TRC).</span><span class="sxs-lookup"><span data-stu-id="841fb-105">Workload files can be [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts (.sql) or trace files (.trc).</span></span> <span data-ttu-id="841fb-106">Дополнительные сведения см. в разделе [Запуск и использование помощника по настройке ядра СУБД](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="841fb-106">For more information, see [Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="841fb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="841fb-107">Syntax</span></span>  
  
```  
  
<DTAInput>  
  <Server>...</Server>  
  <Workload>  
    <File>...</File>  
  </Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="841fb-108">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="841fb-108">Element Characteristics</span></span>  
  
|<span data-ttu-id="841fb-109">Характеристика</span><span class="sxs-lookup"><span data-stu-id="841fb-109">Characteristic</span></span>|<span data-ttu-id="841fb-110">Описание</span><span class="sxs-lookup"><span data-stu-id="841fb-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="841fb-111">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="841fb-111">**Data type and length**</span></span>|<span data-ttu-id="841fb-112">Для задания пути к каталогу, в котором находится файл рабочей загрузки, используется тип данных `string`.</span><span class="sxs-lookup"><span data-stu-id="841fb-112">Use the `string` data type to specify the directory path to your workload file.</span></span> <span data-ttu-id="841fb-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="841fb-113">For example:</span></span><br /><br /> `<File>C:\Tuning\tun.sql</File>`<br /><br /> <span data-ttu-id="841fb-114">Ограничение на длину устанавливается сервером.</span><span class="sxs-lookup"><span data-stu-id="841fb-114">Length limit is enforced by the server.</span></span>|  
|<span data-ttu-id="841fb-115">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="841fb-115">**Default value**</span></span>|<span data-ttu-id="841fb-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="841fb-116">None.</span></span>|  
|<span data-ttu-id="841fb-117">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="841fb-117">**Occurrence**</span></span>|<span data-ttu-id="841fb-118">Необходимо наличие одного такого элемента, если не задан никакой другой тип рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="841fb-118">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="841fb-119">Для родительского элемента **EventString**необходимо задать дочерний элемент **File**, **Database** или **Workload** , однако одновременно может использоваться только один из них.</span><span class="sxs-lookup"><span data-stu-id="841fb-119">You must specify an **EventString**, a **File**, or a **Database** child element for the **Workload** parent, but only one type can be used.</span></span> <span data-ttu-id="841fb-120">Например, если рабочая нагрузка задана элементом **File** , то в том же входном XML-файле уже нельзя задать рабочую нагрузку элементом **Database** .</span><span class="sxs-lookup"><span data-stu-id="841fb-120">For example, if you specify a workload with the **File** element, then you cannot also specify a workload with the **Database** element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="841fb-121">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="841fb-121">Element Relationships</span></span>  
  
|<span data-ttu-id="841fb-122">Связь</span><span class="sxs-lookup"><span data-stu-id="841fb-122">Relationship</span></span>|<span data-ttu-id="841fb-123">Элементы</span><span class="sxs-lookup"><span data-stu-id="841fb-123">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="841fb-124">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="841fb-124">**Parent element**</span></span>|[<span data-ttu-id="841fb-125">Элемент Workload (DTA)</span><span class="sxs-lookup"><span data-stu-id="841fb-125">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="841fb-126">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="841fb-126">**Child elements**</span></span>|<span data-ttu-id="841fb-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="841fb-127">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="841fb-128">Пример</span><span class="sxs-lookup"><span data-stu-id="841fb-128">Example</span></span>  
 <span data-ttu-id="841fb-129">Пример использования этого элемента см. в разделе [Образец простого входного файла XML (DTA)](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="841fb-129">For a usage example of this element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841fb-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="841fb-130">See Also</span></span>  
 [<span data-ttu-id="841fb-131">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="841fb-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
