---
title: Элемент Issue (ssbdiagnose) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- issue element
- XML output file format [ssbdiagnose], issue element
- ssbdiagnose
ms.assetid: 2246a886-686b-44ca-9771-b155cedad8be
author: stevestein
ms.author: sstein
ms.openlocfilehash: a178c1323c1c20f84e67d4d7699fc313090a4c71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727530"
---
# <a name="issue-element-ssbdiagnose"></a><span data-ttu-id="4969b-102">Элемент Issue (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="4969b-102">Issue Element (ssbdiagnose)</span></span>
  <span data-ttu-id="4969b-103">Сообщает о проблеме, обнаруженной программой **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="4969b-103">Reports an issue that was found by the **ssbdiagnose** utility.</span></span> <span data-ttu-id="4969b-104">В выходном XML-файле программы **ssbdiagnose** для каждой из обнаруженных проблем присутствует один элемент Issue.</span><span class="sxs-lookup"><span data-stu-id="4969b-104">The **ssbdiagnose** XML output file has one Issue element per issue reported.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4969b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4969b-105">Syntax</span></span>  
  
```  
  
<Issue  
    type="..."   
    code="..."   
    server="..."   
    database="..."   
    object="...">   
    ...   
</Issue>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="4969b-106">Атрибуты элемента</span><span class="sxs-lookup"><span data-stu-id="4969b-106">Element Attributes</span></span>  
  
|<span data-ttu-id="4969b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="4969b-107">Attribute</span></span>|<span data-ttu-id="4969b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4969b-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="4969b-109">Определяет категорию проблемы, о которой сообщает элемент Issue:</span><span class="sxs-lookup"><span data-stu-id="4969b-109">Identifies which category of problem the Issue element is reporting:</span></span><br /><br /> <span data-ttu-id="4969b-110">**"Diagnosis"** . Сообщает о проблеме, обнаруженной во время анализа конфигурации компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4969b-110">**"Diagnosis"** Reports a configuration issue found when you analyze a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span><br /><br /> <span data-ttu-id="4969b-111">**Problem** . Сообщает о проблеме, в результате которой программе **ssbdiagnose** не удалось завершить анализ.</span><span class="sxs-lookup"><span data-stu-id="4969b-111">**"Problem"** Reports an issue that has prevented **ssbdiagnose** from completing its analysis.</span></span> <span data-ttu-id="4969b-112">Устраните проблему и снова запустите программу **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="4969b-112">Correct the problem and rerun **ssbdiagnose**.</span></span><br /><br /> <span data-ttu-id="4969b-113">**Event** . Сообщает о событии приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , обнаруженном во время выполнения проверки **-RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="4969b-113">**"Event"** Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event found when you run a **-RUNTIME** check.</span></span> <span data-ttu-id="4969b-114">События включаются в отчет, только если указан параметр **-SHOWEVENTS** .</span><span class="sxs-lookup"><span data-stu-id="4969b-114">Events are only reported if **-SHOWEVENTS** is specified.</span></span>|  
|`code`|<span data-ttu-id="4969b-115">Определяет номер ошибки для сообщения.</span><span class="sxs-lookup"><span data-stu-id="4969b-115">Identifies the error number for the message.</span></span>|  
|`server`|<span data-ttu-id="4969b-116">Определяет экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , в котором обнаружена проблема.</span><span class="sxs-lookup"><span data-stu-id="4969b-116">Identifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the problem was found.</span></span> <span data-ttu-id="4969b-117">Если проблема произошла в экземпляре по умолчанию, то в атрибуте server будет указано только имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="4969b-117">If the problem was in a default instance, the server attribute only has the computer name.</span></span> <span data-ttu-id="4969b-118">Если проблема произошла в именованном экземпляре, то атрибут server будет иметь значение в формате «ИмяКомпьютера\ИмяЭкземпляра».</span><span class="sxs-lookup"><span data-stu-id="4969b-118">If the problem was in a named instance, the server attribute is in the form ComputerName\InstanceName.</span></span>|  
|`database`|<span data-ttu-id="4969b-119">Определяет имя базы данных, в которой обнаружена проблема.</span><span class="sxs-lookup"><span data-stu-id="4969b-119">Identifies the name of the database in which the problem was found.</span></span>|  
|`object`|<span data-ttu-id="4969b-120">Определяет имя объекта, в котором обнаружена проблема.</span><span class="sxs-lookup"><span data-stu-id="4969b-120">Identifies the name of the object in which the problem was found.</span></span> <span data-ttu-id="4969b-121">Если неполадка произошла на уровне экземпляра или базы данных, то в атрибуте object повторяется имя экземпляра или базы данных.</span><span class="sxs-lookup"><span data-stu-id="4969b-121">If the problem was an instance or database level issue, the object attribute repeats the instance or database name.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="4969b-122">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="4969b-122">Element Characteristics</span></span>  
  
|<span data-ttu-id="4969b-123">Характеристика</span><span class="sxs-lookup"><span data-stu-id="4969b-123">Characteristic</span></span>|<span data-ttu-id="4969b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="4969b-124">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4969b-125">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="4969b-125">**Data type and length**</span></span>|<span data-ttu-id="4969b-126">`string`, неограниченная длина</span><span class="sxs-lookup"><span data-stu-id="4969b-126">`string`, length is unlimited.</span></span>|  
|<span data-ttu-id="4969b-127">**Значение**</span><span class="sxs-lookup"><span data-stu-id="4969b-127">**Value**</span></span>|<span data-ttu-id="4969b-128">Возвращает текст сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4969b-128">Returns the text of the error message.</span></span>|  
|<span data-ttu-id="4969b-129">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="4969b-129">**Occurrence**</span></span>|<span data-ttu-id="4969b-130">Один раз для каждой ошибки.</span><span class="sxs-lookup"><span data-stu-id="4969b-130">Once per reported error.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="4969b-131">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="4969b-131">Element Relationships</span></span>  
  
|<span data-ttu-id="4969b-132">Связь</span><span class="sxs-lookup"><span data-stu-id="4969b-132">Relationship</span></span>|<span data-ttu-id="4969b-133">Элементы</span><span class="sxs-lookup"><span data-stu-id="4969b-133">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="4969b-134">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="4969b-134">**Parent element**</span></span>|[<span data-ttu-id="4969b-135">Элемент DiagnosticInformation (программа ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="4969b-135">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="4969b-136">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="4969b-136">**Child elements**</span></span>|<span data-ttu-id="4969b-137">None</span><span class="sxs-lookup"><span data-stu-id="4969b-137">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4969b-138">Пример</span><span class="sxs-lookup"><span data-stu-id="4969b-138">Example</span></span>  
 <span data-ttu-id="4969b-139">Следующий элемент сообщает об ошибке с номером 1102 для базы данных, в которой отсутствует главный ключ. Ошибка была обнаружена во время анализа конфигурации компонента [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4969b-139">This element reports an 1102 error for a database that does not have a master key, where the error was found when you analyzed a [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration.</span></span>  
  
```  
<Issue type="Diagnosis" code="1102" server="TestComputer" database="TargetDB" object="TargetDB">The master key was not found</diagnostic>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4969b-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="4969b-140">See Also</span></span>  
 [<span data-ttu-id="4969b-141">Программа ssbdiagnose (компонент Service Broker)</span><span class="sxs-lookup"><span data-stu-id="4969b-141">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
