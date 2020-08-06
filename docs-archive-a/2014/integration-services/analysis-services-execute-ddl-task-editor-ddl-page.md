---
title: Редактор задачи «Выполнение инструкции DDL Analysis Services» (страница «DDL») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.ddl.f1
helpviewer_keywords:
- Analysis Services Execute DDL Task Editor
ms.assetid: f21bf8d0-ec5f-4c18-9de0-8875addb927b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d207afe666e582c44f1014a6c80f4f4984fd5410
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657236"
---
# <a name="analysis-services-execute-ddl-task-editor-ddl-page"></a><span data-ttu-id="7f33d-102">Редактор задачи «Выполнение инструкции DDL служб Analysis Services» (страница DDL)</span><span class="sxs-lookup"><span data-stu-id="7f33d-102">Analysis Services Execute DDL Task Editor (DDL Page)</span></span>
  <span data-ttu-id="7f33d-103">Используйте страницу **DDL** диалогового окна **Редактор задачи "Выполнение инструкции DDL служб аналитики"** , чтобы настроить соединение с проектом [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или базой данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , а также предоставить сведения об источнике инструкций языка определения данных (DDL).</span><span class="sxs-lookup"><span data-stu-id="7f33d-103">Use the **DDL** page of the **Analysis Services Execute DDL Task Editor** dialog box to specify a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database and to provide information about the source of data definition language (DDL) statements.</span></span>  
  
 <span data-ttu-id="7f33d-104">Дополнительные сведения об этой задаче см. в разделе [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span><span class="sxs-lookup"><span data-stu-id="7f33d-104">To learn about this task, see [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="7f33d-105">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="7f33d-105">Static Options</span></span>  
 <span data-ttu-id="7f33d-106">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="7f33d-106">**Connection**</span></span>  
 <span data-ttu-id="7f33d-107">Выберите проект [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или диспетчер подключений [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] в списке или щелкните \<**New connection...**> и создайте подключение с помощью диалогового окна **Добавление диспетчера соединений со службами Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="7f33d-107">Select an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager in the list, or click \<**New connection...**> and use the **Add Analysis Services Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="7f33d-108">**См. также:** [Диалоговое окно "Добавление диспетчера соединений со службами Analysis Services" в справочнике по пользовательскому интерфейсу](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Диспетчер соединений служб Analysis Services](connection-manager/analysis-services-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="7f33d-108">**Related Topics:** [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md)</span></span>  
  
 <span data-ttu-id="7f33d-109">**Тип источника**</span><span class="sxs-lookup"><span data-stu-id="7f33d-109">**SourceType**</span></span>  
 <span data-ttu-id="7f33d-110">Указать тип источника инструкции DDL.</span><span class="sxs-lookup"><span data-stu-id="7f33d-110">Specify the source type of the DDL statements.</span></span> <span data-ttu-id="7f33d-111">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7f33d-111">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="7f33d-112">Значение</span><span class="sxs-lookup"><span data-stu-id="7f33d-112">Value</span></span>|<span data-ttu-id="7f33d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7f33d-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7f33d-114">**Прямой ввод**</span><span class="sxs-lookup"><span data-stu-id="7f33d-114">**Direct Input**</span></span>|<span data-ttu-id="7f33d-115">Установите в качестве источника инструкцию DDL, содержащуюся в текстовом поле **SourceDirect** .</span><span class="sxs-lookup"><span data-stu-id="7f33d-115">Set the source to the DDL statement stored in the **SourceDirect** text box.</span></span> <span data-ttu-id="7f33d-116">При выборе этого значения в следующем подразделе отображаются динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="7f33d-116">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="7f33d-117">**Соединение с файлом**</span><span class="sxs-lookup"><span data-stu-id="7f33d-117">**File Connection**</span></span>|<span data-ttu-id="7f33d-118">В качестве источника указывается файл, содержащий инструкцию DDL.</span><span class="sxs-lookup"><span data-stu-id="7f33d-118">Set the source to a file that contains the DDL statement.</span></span> <span data-ttu-id="7f33d-119">При выборе этого значения в следующем подразделе отображаются динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="7f33d-119">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="7f33d-120">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="7f33d-120">**Variable**</span></span>|<span data-ttu-id="7f33d-121">Установите в качестве источника переменную.</span><span class="sxs-lookup"><span data-stu-id="7f33d-121">Set the source to a variable.</span></span> <span data-ttu-id="7f33d-122">При выборе этого значения в следующем подразделе отображаются динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="7f33d-122">Selecting this value displays the dynamic options in the following section.</span></span>|  
  
## <a name="dynamic-options"></a><span data-ttu-id="7f33d-123">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="7f33d-123">Dynamic Options</span></span>  
  
### <a name="sourcetype--direct-input"></a><span data-ttu-id="7f33d-124">SourceType = Прямой ввод</span><span class="sxs-lookup"><span data-stu-id="7f33d-124">SourceType = Direct Input</span></span>  
 <span data-ttu-id="7f33d-125">**Source**</span><span class="sxs-lookup"><span data-stu-id="7f33d-125">**Source**</span></span>  
 <span data-ttu-id="7f33d-126">Введите инструкции DDL или нажмите кнопку с многоточием **(…)** и после этого введите инструкции в диалоговом окне **Инструкции DDL**.</span><span class="sxs-lookup"><span data-stu-id="7f33d-126">Type the DDL statements or click the ellipsis **(...)** and then type the statements in the **DDL Statements** dialog box.</span></span>  
  
### <a name="sourcetype--file-connection"></a><span data-ttu-id="7f33d-127">SourceType = Подключение файла</span><span class="sxs-lookup"><span data-stu-id="7f33d-127">SourceType = File Connection</span></span>  
 <span data-ttu-id="7f33d-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="7f33d-128">**Source**</span></span>  
 <span data-ttu-id="7f33d-129">Выберите "Соединение с файлом" в списке или щелкните \<**New connection...**> и создайте подключение с помощью диалогового окна **Диспетчер соединения файлов**.</span><span class="sxs-lookup"><span data-stu-id="7f33d-129">Select a File connection in the list, or click \<**New connection...**> and use the **File Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="7f33d-130">**См. также:** [Диспетчер соединения файлов](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="7f33d-130">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
### <a name="sourcetype--variable"></a><span data-ttu-id="7f33d-131">SourceType = Переменная</span><span class="sxs-lookup"><span data-stu-id="7f33d-131">SourceType = Variable</span></span>  
 <span data-ttu-id="7f33d-132">**Source**</span><span class="sxs-lookup"><span data-stu-id="7f33d-132">**Source**</span></span>  
 <span data-ttu-id="7f33d-133">Выберите переменную в списке или щелкните \<**New variable...**> и создайте переменную с помощью диалогового окна **Добавление переменной**.</span><span class="sxs-lookup"><span data-stu-id="7f33d-133">Select a variable in the list, or click \<**New variable...**> and use the **Add Variable** dialog box to create a new variable.</span></span>  
  
 <span data-ttu-id="7f33d-134">**См. также:** [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="7f33d-134">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f33d-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f33d-135">See Also</span></span>  
 <span data-ttu-id="7f33d-136">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7f33d-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="7f33d-137">[Редактор задачи "Analysis Services выполнение инструкции DDL" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="7f33d-137">[Analysis Services Execute DDL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="7f33d-138">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="7f33d-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="7f33d-139">[Поток управления](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="7f33d-139">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="7f33d-140">[Справочник по языку сценариев Analysis Services &#40;языка ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span><span class="sxs-lookup"><span data-stu-id="7f33d-140">[Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span></span>  
 [<span data-ttu-id="7f33d-141">Справочник по XML для аналитики (XMLA)</span><span class="sxs-lookup"><span data-stu-id="7f33d-141">XML for Analysis  &#40;XMLA&#41; Reference</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference)  
  
  
