---
title: Элемент DTAXML (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAXML element
ms.assetid: 3d9942ed-8a27-40db-a7c9-808984d914a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9f428cf996bb819ece74c13226fcd5116a19142b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734802"
---
# <a name="dtaxml-element-dta"></a><span data-ttu-id="0fd6a-102">Элемент DTAXML (DTA)</span><span class="sxs-lookup"><span data-stu-id="0fd6a-102">DTAXML Element (DTA)</span></span>
  <span data-ttu-id="0fd6a-103">**DTAXML** — корневой элемент входного или выходного файла XML-данных помощника по настройке ядра СУБД — содержит все элементы, определяющие вход и выход настройки, создаваемой помощником по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-103">The root element of a Database Engine Tuning Advisor XML input or output file, **DTAXML** contains all elements that describe tuning input and the tuning output that Database Engine Tuning Advisor generates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fd6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fd6a-104">Syntax</span></span>  
  
```  
  
<DTAXML   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
    xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">  
    ...code removed here...  
</DTAXML>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="0fd6a-105">Атрибуты элемента</span><span class="sxs-lookup"><span data-stu-id="0fd6a-105">Element Attributes</span></span>  
  
|<span data-ttu-id="0fd6a-106">attribute</span><span class="sxs-lookup"><span data-stu-id="0fd6a-106">Attribute</span></span>|<span data-ttu-id="0fd6a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd6a-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns:xsi`|<span data-ttu-id="0fd6a-108">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-108">Required.</span></span> <span data-ttu-id="0fd6a-109">Определяет пространство имен экземпляра XML-схемы.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-109">Identifies the XML Schema Instance namespace.</span></span> <span data-ttu-id="0fd6a-110">Атрибуты этого пространства имен используются для обращения к схеме, применяемой для проверки XML-файла помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-110">Attributes from this namespace are used to reference the schema that is used to validate the Database Engine Tuning Advisor XML file.</span></span><br /><br /> <span data-ttu-id="0fd6a-111">Обязательное значение: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span><span class="sxs-lookup"><span data-stu-id="0fd6a-111">Required value: [http://www.w3.org/2001/XMLSchema-instance](http://www.w3.org/2001/XMLSchema-instance)</span></span>|  
|`xmlns`|<span data-ttu-id="0fd6a-112">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-112">Required.</span></span> <span data-ttu-id="0fd6a-113">Определяет пространство имен помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-113">Identifies the Database Engine Tuning Advisor namespace.</span></span><br /><br /> <span data-ttu-id="0fd6a-114">При редактировании XML-файла помощника по настройке ядра СУБД в редакторе XML из [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]это значение используется в справке F1, а также в динамической справке для поиска подходящих разделов электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0fd6a-114">If you edit the Database Engine Tuning Advisor XML file using the XML editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this value is used by F1 Help and Dynamic Help to locate possible reference topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span><br /><br /> <span data-ttu-id="0fd6a-115">Обязательное значение:</span><span class="sxs-lookup"><span data-stu-id="0fd6a-115">Required value:</span></span><br /><br /> <span data-ttu-id="0fd6a-116">[XML-схема помощника по настройке компонента Database Engine](https://go.microsoft.com/fwlink/?LinkId=43100) Пространство имен</span><span class="sxs-lookup"><span data-stu-id="0fd6a-116">[Database Engine Tuning Advisor XML Schema](https://go.microsoft.com/fwlink/?LinkId=43100) Namespace</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="0fd6a-117">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="0fd6a-117">Element Characteristics</span></span>  
  
|<span data-ttu-id="0fd6a-118">Характеристика</span><span class="sxs-lookup"><span data-stu-id="0fd6a-118">Characteristic</span></span>|<span data-ttu-id="0fd6a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd6a-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0fd6a-120">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-120">**Data type and length**</span></span>|<span data-ttu-id="0fd6a-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-121">None.</span></span>|  
|<span data-ttu-id="0fd6a-122">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-122">**Default value**</span></span>|<span data-ttu-id="0fd6a-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-123">None.</span></span>|  
|<span data-ttu-id="0fd6a-124">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-124">**Occurrence**</span></span>|<span data-ttu-id="0fd6a-125">Требуется один раз для каждого файла DTA XML.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-125">Required once per DTA XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="0fd6a-126">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="0fd6a-126">Element Relationships</span></span>  
  
|<span data-ttu-id="0fd6a-127">Связь</span><span class="sxs-lookup"><span data-stu-id="0fd6a-127">Relationship</span></span>|<span data-ttu-id="0fd6a-128">Элементы</span><span class="sxs-lookup"><span data-stu-id="0fd6a-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="0fd6a-129">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-129">**Parent element**</span></span>|<span data-ttu-id="0fd6a-130">None</span><span class="sxs-lookup"><span data-stu-id="0fd6a-130">None</span></span>|  
|<span data-ttu-id="0fd6a-131">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="0fd6a-131">**Child elements**</span></span>|[<span data-ttu-id="0fd6a-132">Элемент DTAInput (DTA)</span><span class="sxs-lookup"><span data-stu-id="0fd6a-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)<br /><br /> <span data-ttu-id="0fd6a-133">`DTAOutput`Элемент (сведения см. в разделе [Помощник по настройке ядра СУБД XML Schema](https://schemas.microsoft.com/sqlserver/) )</span><span class="sxs-lookup"><span data-stu-id="0fd6a-133">`DTAOutput` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fd6a-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="0fd6a-134">Remarks</span></span>  
 <span data-ttu-id="0fd6a-135">Дополнительные сведения о пространствах имен XML см. в статье [Пространства имен в XML-документе](https://go.microsoft.com/fwlink/?LinkId=7341) в библиотеке [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-135">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fd6a-136">Пример</span><span class="sxs-lookup"><span data-stu-id="0fd6a-136">Example</span></span>  
 <span data-ttu-id="0fd6a-137">Примеры типичных элементов **DTAXML** см. в разделе [Образцы входных XML-файлов (DTA)](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="0fd6a-137">For examples of typical **DTAXML** elements, see [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd6a-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="0fd6a-138">See Also</span></span>  
 <span data-ttu-id="0fd6a-139">[Справочник по входным XML-файлам (помощник по настройке ядра СУБД)](xml-input-file-reference-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0fd6a-139">[XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="0fd6a-140">Запуск и использование помощника по настройке ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="0fd6a-140">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)  
  
  
