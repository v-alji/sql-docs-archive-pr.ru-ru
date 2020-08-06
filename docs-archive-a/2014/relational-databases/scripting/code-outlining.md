---
title: Структурирование кода
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], outlining code
- Query Editor [SQL Server Management Studio], hiding code
ms.assetid: 556c7dfe-7bc8-4cab-a36f-2b753a05d3f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 0a142ca8fbdcdfcfbfd1b71de06c0b0fd4c5339c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658170"
---
# <a name="code-outlining"></a><span data-ttu-id="a9149-102">Структурирование кода</span><span class="sxs-lookup"><span data-stu-id="a9149-102">Code Outlining</span></span>
  <span data-ttu-id="a9149-103">Функция структурирования в редакторах запросов среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] позволяет при редактировании запросов выборочно скрывать участки кода.</span><span class="sxs-lookup"><span data-stu-id="a9149-103">You can use the outlining feature in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] query editors to selectively hide code when you edit queries.</span></span> <span data-ttu-id="a9149-104">Это делает просмотр кода при редактировании более удобным, особенно когда файл запроса имеет большой размер.</span><span class="sxs-lookup"><span data-stu-id="a9149-104">This enables you to more easily view the code you are working on, especially in large query files.</span></span>

## <a name="outlining-overview"></a><span data-ttu-id="a9149-105">Общие сведения о функции структурирования</span><span class="sxs-lookup"><span data-stu-id="a9149-105">Outlining Overview</span></span>
 <span data-ttu-id="a9149-106">По умолчанию при открытии окна редактора запросов весь код является видимым.</span><span class="sxs-lookup"><span data-stu-id="a9149-106">By default, all code is visible when you open a query editor window.</span></span> <span data-ttu-id="a9149-107">Участки кода можно свернуть, чтобы скрыть их.</span><span class="sxs-lookup"><span data-stu-id="a9149-107">Regions of the code can be collapsed to hide it from view.</span></span> <span data-ttu-id="a9149-108">Квадрат со знаком «минус» (-) возле вертикальной линии, проходящей вдоль левого края окна редактора, обозначает начало каждого сворачиваемого участка кода.</span><span class="sxs-lookup"><span data-stu-id="a9149-108">A vertical line on the left edge of the editor window uses a square with a minus sign (-) to identify the start of each collapsible code region.</span></span> <span data-ttu-id="a9149-109">Если щелкнуть значок "минус", то текст участка кода будет заменен полем, содержащим три точки (...), а значок "минус" заменяется значком "плюс" (+).</span><span class="sxs-lookup"><span data-stu-id="a9149-109">When you click a minus sign, the text of the code region is replaced with a box that contains three periods (...), and the minus sign changes to a plus sign (+).</span></span> <span data-ttu-id="a9149-110">Если щелкнуть значок «плюс», то свернутый код будет отображен, а значок «плюс» заменен значком «минус».</span><span class="sxs-lookup"><span data-stu-id="a9149-110">When you click a plus sign, the collapsed code appears and the plus sign changes to a minus sign.</span></span> <span data-ttu-id="a9149-111">Если указатель находится над полем с тремя точками, то отображается всплывающая подсказка, содержащая код свернутого раздела.</span><span class="sxs-lookup"><span data-stu-id="a9149-111">When you move the pointer over a box that has three periods, a tooltip appears that shows the code in the collapsed section.</span></span>

## <a name="system-outline-regions"></a><span data-ttu-id="a9149-112">Системные структурные области</span><span class="sxs-lookup"><span data-stu-id="a9149-112">System Outline Regions</span></span>
 <span data-ttu-id="a9149-113">Каждый редактор в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] формирует набор структурных областей, по умолчанию определяемых системой.</span><span class="sxs-lookup"><span data-stu-id="a9149-113">Each [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] editor generates a set of default, system-defined outline regions.</span></span>

 <span data-ttu-id="a9149-114">Редакторы кода многомерных выражений и расширений интеллектуального анализа данных создают структурные области для каждой многострочной инструкции.</span><span class="sxs-lookup"><span data-stu-id="a9149-114">The MDX and DMX code editors create outline regions for each multiline statement.</span></span> <span data-ttu-id="a9149-115">Это единственный уровень структурирования, поддерживаемый этими редакторами.</span><span class="sxs-lookup"><span data-stu-id="a9149-115">This is the only level of outlining that these editors support.</span></span>

### <a name="analysis-services-xmla-query-editor-regions"></a><span data-ttu-id="a9149-116">Области редактора запросов XMLA служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a9149-116">Analysis Services XMLA Query Editor Regions</span></span>
 <span data-ttu-id="a9149-117">Редактор запросов XMLA служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] формирует структурную область для каждого многострочного XML-атрибута.</span><span class="sxs-lookup"><span data-stu-id="a9149-117">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query Editor generates an outline region for each multiline XML attribute.</span></span> <span data-ttu-id="a9149-118">Редактор создает вложенные структурные области для вложенных тегов.</span><span class="sxs-lookup"><span data-stu-id="a9149-118">The editor nests the outline regions for nested tags.</span></span> <span data-ttu-id="a9149-119">Например, редактор XMLA создает три структурные области в следующем документе.</span><span class="sxs-lookup"><span data-stu-id="a9149-119">For example, the XMLA Editor creates three outline regions for the following document.</span></span>

 <span data-ttu-id="a9149-120">![XML-код, демонстрирующий структурирование](../../database-engine/media/editoutlinexmlfull.gif "XML-код, демонстрирующий структурирование")</span><span class="sxs-lookup"><span data-stu-id="a9149-120">![XML code showing outlining](../../database-engine/media/editoutlinexmlfull.gif "XML code showing outlining")</span></span>

 <span data-ttu-id="a9149-121">Если щелкнуть знак «минус \<InnerTag> » в строке, то будет свернута только InnerTag, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a9149-121">When you click the minus sign on the \<InnerTag> line, just the InnerTag is collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="a9149-122">![XML-код со скрытым внутренним узлом](../../database-engine/media/editoutlinexmlinnercol.gif "XML-код со скрытым внутренним узлом")</span><span class="sxs-lookup"><span data-stu-id="a9149-122">![XML code with inner node hidden](../../database-engine/media/editoutlinexmlinnercol.gif "XML code with inner node hidden")</span></span>

 <span data-ttu-id="a9149-123">Когда указатель находится над полем с тремя точками (...), то код в свернутой области отображается во всплывающей подсказке, как показано на следующей иллюстрации.</span><span class="sxs-lookup"><span data-stu-id="a9149-123">When you move the pointer over the box that has the three periods (...), the code in the collapsed region appears in a tooltip, as shown in the following illustration.</span></span>

 <span data-ttu-id="a9149-124">![XML-код с подсказками, отображающими скрытый код](../../database-engine/media/editoutlinexmlmouse.gif "XML-код с подсказками, отображающими скрытый код")</span><span class="sxs-lookup"><span data-stu-id="a9149-124">![XML code with tooltip showing hidden code](../../database-engine/media/editoutlinexmlmouse.gif "XML code with tooltip showing hidden code")</span></span>

 <span data-ttu-id="a9149-125">Если щелкнуть знак "минус" в \<MiddleTag> строке, будут свернуты как MiddleTag, так и InnerTag, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a9149-125">When you click the minus sign on the \<MiddleTag> line, both the MiddleTag and InnerTag are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="a9149-126">![XML-код со скрытыми внутренними и средними тегами](../../database-engine/media/editoutlinexmlmiddlecol.gif "XML-код со скрытыми внутренними и средними тегами")</span><span class="sxs-lookup"><span data-stu-id="a9149-126">![XML code with inner and middle tags hidden](../../database-engine/media/editoutlinexmlmiddlecol.gif "XML code with inner and middle tags hidden")</span></span>

 <span data-ttu-id="a9149-127">Если щелкнуть знак "минус" в \<OuterTag> строке, будут свернуты все три строки, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a9149-127">When you click the minus sign on the \<OuterTag> line, all three lines are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="a9149-128">![XML-код, где скрыты все три тега](../../database-engine/media/editoutlinexmloutercol.gif "XML-код со скрытыми всеми тремя тегами")</span><span class="sxs-lookup"><span data-stu-id="a9149-128">![XML code showing all three tags hidden](../../database-engine/media/editoutlinexmloutercol.gif "XML code showing all three tags hidden")</span></span>

### <a name="database-engine-query-editor-regions"></a><span data-ttu-id="a9149-129">Области редактора запросов к ядру СУБД</span><span class="sxs-lookup"><span data-stu-id="a9149-129">Database Engine Query Editor Regions</span></span>
 <span data-ttu-id="a9149-130">Редактор запросов компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] формирует структурные области для каждого элемента в следующей иерархии.</span><span class="sxs-lookup"><span data-stu-id="a9149-130">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor generates outline regions for each element in the following hierarchy:</span></span>

1.  <span data-ttu-id="a9149-131">Пакеты.</span><span class="sxs-lookup"><span data-stu-id="a9149-131">Batches.</span></span> <span data-ttu-id="a9149-132">Первый пакет содержит код от начала файла до первой команды GO либо до конца файла, если он не содержит команд GO.</span><span class="sxs-lookup"><span data-stu-id="a9149-132">The first batch is the code from the start of the file to either the first GO command or the end of the file when there are no GO commands.</span></span> <span data-ttu-id="a9149-133">Каждый последующий пакет после первой команды GO охватывает код от соответствующей команды GO до следующей команды GO, либо до конца файла.</span><span class="sxs-lookup"><span data-stu-id="a9149-133">After the first GO, there is one batch from each GO command to either the next GO command or the end of the file.</span></span>

2.  <span data-ttu-id="a9149-134">Блоки, разделяемые следующими ключевыми словами:</span><span class="sxs-lookup"><span data-stu-id="a9149-134">Blocks delimited by the following keywords:</span></span>

    -   <span data-ttu-id="a9149-135">BEGIN — END</span><span class="sxs-lookup"><span data-stu-id="a9149-135">BEGIN - END</span></span>

    -   <span data-ttu-id="a9149-136">BEGIN TRY — END TRY</span><span class="sxs-lookup"><span data-stu-id="a9149-136">BEGIN TRY - END TRY</span></span>

    -   <span data-ttu-id="a9149-137">BEGIN CATCH — END CATCH</span><span class="sxs-lookup"><span data-stu-id="a9149-137">BEGIN CATCH - END CATCH</span></span>

3.  <span data-ttu-id="a9149-138">Многострочные инструкции.</span><span class="sxs-lookup"><span data-stu-id="a9149-138">Multiline statements.</span></span>

 <span data-ttu-id="a9149-139">Например, редактор запросов компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] создает три структурные области в следующем запросе.</span><span class="sxs-lookup"><span data-stu-id="a9149-139">For example, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor creates three outline regions for the following query:</span></span>

```
CREATE PROCEDURE Sales.SampleProc --Outline region 1
AS
BEGIN --Outline region 2 
  SELECT GETDATE() AS TimeOfQuery;
  SELECT * --Outline region 3
  FROM sys.transmission_queue;
  SELECT @@VERSION;
END;
GO
```

 <span data-ttu-id="a9149-140">Щелкнув значок «минус» в строке `SELECT *` , можно свернуть только инструкцию `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="a9149-140">You can click the minus sign on the `SELECT *` line to collapse just that `SELECT` statement.</span></span> <span data-ttu-id="a9149-141">Чтобы свернуть весь блок `BEGIN - END` , щелкните значок «минус» в строке `BEGIN` .</span><span class="sxs-lookup"><span data-stu-id="a9149-141">To collapse the whole `BEGIN - END` block, click the minus sign on the `BEGIN` line.</span></span> <span data-ttu-id="a9149-142">Чтобы свернуть весь блок `GO` , щелкните значок «минус» в строке `CREATE PROCEDURE` .</span><span class="sxs-lookup"><span data-stu-id="a9149-142">To collapse the whole batch to the `GO` command, click the minus sign on the `CREATE PROCEDURE` line.</span></span> <span data-ttu-id="a9149-143">Свернуть строки `SELECT GETDATE()` или `SELECT @@VERSION` по отдельности нельзя, поскольку они являются однострочными инструкциями и не выделяются в структурные области.</span><span class="sxs-lookup"><span data-stu-id="a9149-143">You cannot collapse the `SELECT GETDATE()` or `SELECT @@VERSION` lines individually because they are single line statements and do not get outlining regions.</span></span>


