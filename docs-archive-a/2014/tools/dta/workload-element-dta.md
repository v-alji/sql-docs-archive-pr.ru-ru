---
title: Элемент рабочей нагрузки (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Workload element
ms.assetid: 68ffd473-6546-4015-98d0-3763165de65c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20184760c3fcb5eed6c02b8f8fd9b63f5586c9af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658598"
---
# <a name="workload-element-dta"></a><span data-ttu-id="e8769-102">Элемент Workload (DTA)</span><span class="sxs-lookup"><span data-stu-id="e8769-102">Workload Element (DTA)</span></span>
  <span data-ttu-id="e8769-103">Позволяет задать рабочую нагрузку для использования в сеансе настройки.</span><span class="sxs-lookup"><span data-stu-id="e8769-103">Specifies the workload to be used for a tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8769-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8769-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="e8769-105">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="e8769-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="e8769-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="e8769-106">Characteristic</span></span>|<span data-ttu-id="e8769-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e8769-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e8769-108">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="e8769-108">**Data type and length**</span></span>|<span data-ttu-id="e8769-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="e8769-109">None.</span></span>|  
|<span data-ttu-id="e8769-110">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="e8769-110">**Default value**</span></span>|<span data-ttu-id="e8769-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="e8769-111">None.</span></span>|  
|<span data-ttu-id="e8769-112">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="e8769-112">**Occurrence**</span></span>|<span data-ttu-id="e8769-113">Требуется один раз для каждого элемента `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="e8769-113">Required once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="e8769-114">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="e8769-114">Element Relationships</span></span>  
  
|<span data-ttu-id="e8769-115">Связь</span><span class="sxs-lookup"><span data-stu-id="e8769-115">Relationship</span></span>|<span data-ttu-id="e8769-116">Элементы</span><span class="sxs-lookup"><span data-stu-id="e8769-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="e8769-117">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="e8769-117">**Parent element**</span></span>|[<span data-ttu-id="e8769-118">Запуск и использование помощника по настройке ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="e8769-118">Start and Use the Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)|  
|<span data-ttu-id="e8769-119">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="e8769-119">**Child elements**</span></span>|[<span data-ttu-id="e8769-120">Элемент File (DTA)</span><span class="sxs-lookup"><span data-stu-id="e8769-120">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)<br /><br /> [<span data-ttu-id="e8769-121">Элемент Database для рабочей нагрузки (DTA)</span><span class="sxs-lookup"><span data-stu-id="e8769-121">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)<br /><br /> [<span data-ttu-id="e8769-122">Элемент EventString (DTA)</span><span class="sxs-lookup"><span data-stu-id="e8769-122">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="e8769-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="e8769-123">Remarks</span></span>  
 <span data-ttu-id="e8769-124">Рабочая нагрузка представляет собой набор инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемый в одной или нескольких базах данных, которые необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="e8769-124">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="e8769-125">Помощник по настройке ядра СУБД может использовать в качестве рабочей нагрузки скрипты [!INCLUDE[tsql](../../includes/tsql-md.md)] , файлы трассировки и таблицы трассировки.</span><span class="sxs-lookup"><span data-stu-id="e8769-125">The Database Engine Tuning Advisor can use [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, trace files, and trace tables as workloads.</span></span>  
  
 <span data-ttu-id="e8769-126">Если заданы две рабочие нагрузки (одна во входном файле XML-данных, другая в командной строке с помощью средства **dta** ), для настройки будет использоваться последняя.</span><span class="sxs-lookup"><span data-stu-id="e8769-126">If you specify a workload in an XML input file and a workload on the command line with the **dta** tool, the workload specified on the command line will be used for tuning.</span></span> <span data-ttu-id="e8769-127">Параметры настройки, заданные в командной строке, имеют приоритет над параметрами, заданными во входном XML-файле.</span><span class="sxs-lookup"><span data-stu-id="e8769-127">All tuning options specified on the command line override those that are specified in an XML input file.</span></span> <span data-ttu-id="e8769-128">Единственное исключение имеет место в том случае, когда пользовательская конфигурация вводится во входном XML-файле в режиме оценки.</span><span class="sxs-lookup"><span data-stu-id="e8769-128">The only exception is if a user-specified configuration is entered in the evaluate mode in the XML input file.</span></span> <span data-ttu-id="e8769-129">Например, если конфигурация вводится посредством элемента `Configuration` входного XML-файла и, кроме того, в качестве одного из параметров настройки задан элемент `EvaluateConfiguration`, параметры настройки из входного XML-файла получат приоритет над любыми параметрами настройки, введенными в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e8769-129">For example, if a configuration is entered in the `Configuration` element of the XML input file and the `EvaluateConfiguration` element is also specified as one of the tuning options, the tuning options specified in the XML input file will override any tuning options entered at the command line.</span></span>  
  
 <span data-ttu-id="e8769-130">Для каждого сеанса настройки должна быть указана одна рабочая нагрузка.</span><span class="sxs-lookup"><span data-stu-id="e8769-130">One workload must be specified for each tuning session.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8769-131">Пример</span><span class="sxs-lookup"><span data-stu-id="e8769-131">Example</span></span>  
 <span data-ttu-id="e8769-132">В следующем примере кода задается таблица трассировки **MyDatabase. MyDBOwner. TuningTable001** для `Workload` элемента.</span><span class="sxs-lookup"><span data-stu-id="e8769-132">The following code example specifies the **MyDatabase.MyDBOwner.TuningTable001** trace table for the `Workload` element.</span></span> <span data-ttu-id="e8769-133">Таблица **TuningTable001** создана с помощью шаблона настройки в SQL Server Profiler путем сохранения выходной трассировки в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="e8769-133">The **TuningTable001** was created by using the Tuning template with SQL Server Profiler and saving the trace output as a table.</span></span>  
  
```  
<DTAXML ...>  
  <DTAInput>  
    <Server>  
...code removed here...  
    </Server>  
    <Workload>  
      <Database>  
        <Name>MyDatabase</Name>  
        <Schema>  
          <Name>MyDBOwner</Name>  
            <Table>  
              <Name>TuningTable001</Name>  
            </Table>  
        </Schema>  
      </Database>  
    </Workload>  
...code removed here...  
  </DTAInput>  
</DTAXML>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8769-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8769-134">See Also</span></span>  
 [<span data-ttu-id="e8769-135">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="e8769-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
