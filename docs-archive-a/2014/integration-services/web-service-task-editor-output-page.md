---
title: Редактор задачи «веб-служба» (страница «выходные данные») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.output.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 73c83969-7b0e-479d-a436-0a46b2068d01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ad034ae78a096ebe5998ac2c3d2573fe7c3bfd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667782"
---
# <a name="web-service-task-editor-output-page"></a><span data-ttu-id="c4f10-102">Редактор задачи «Веб-служба» (страница «Вывод»)</span><span class="sxs-lookup"><span data-stu-id="c4f10-102">Web Service Task Editor (Output Page)</span></span>
  <span data-ttu-id="c4f10-103">Используйте страницу **Вывод** диалогового окна **Редактор задачи «Веб-служба»** , чтобы указать, где следует хранить результаты, возвращенные веб-методом.</span><span class="sxs-lookup"><span data-stu-id="c4f10-103">Use the **Output** page of the **Web Service Task Editor** dialog box to specify where to store the result returned by the Web method.</span></span>  
  
 <span data-ttu-id="c4f10-104">Дополнительные сведения об этой задаче см. в разделе [Задача "Веб-служба"](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="c4f10-104">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="c4f10-105">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="c4f10-105">Static Options</span></span>  
 <span data-ttu-id="c4f10-106">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="c4f10-106">**OutputType**</span></span>  
 <span data-ttu-id="c4f10-107">Выберите тип хранения, используемый для хранения результатов.</span><span class="sxs-lookup"><span data-stu-id="c4f10-107">Select the storage type to use when storing the results.</span></span> <span data-ttu-id="c4f10-108">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c4f10-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="c4f10-109">Значение</span><span class="sxs-lookup"><span data-stu-id="c4f10-109">Value</span></span>|<span data-ttu-id="c4f10-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c4f10-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4f10-111">**Соединение с файлом**</span><span class="sxs-lookup"><span data-stu-id="c4f10-111">**File Connection**</span></span>|<span data-ttu-id="c4f10-112">Хранить результаты в файле.</span><span class="sxs-lookup"><span data-stu-id="c4f10-112">Store the results in a file.</span></span> <span data-ttu-id="c4f10-113">При выборе этого значения отображается динамический параметр **Файл**.</span><span class="sxs-lookup"><span data-stu-id="c4f10-113">Selecting this value displays the dynamic option, **File**.</span></span>|  
|<span data-ttu-id="c4f10-114">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="c4f10-114">**Variable**</span></span>|<span data-ttu-id="c4f10-115">Хранить результаты в переменной.</span><span class="sxs-lookup"><span data-stu-id="c4f10-115">Store the results in a variable.</span></span> <span data-ttu-id="c4f10-116">При выборе этого значения отображается динамический параметр **Переменная**.</span><span class="sxs-lookup"><span data-stu-id="c4f10-116">Selecting this value displays the dynamic option, **Variable**.</span></span>|  
  
## <a name="outputtype-dynamic-options"></a><span data-ttu-id="c4f10-117">Динамические параметры OutputType</span><span class="sxs-lookup"><span data-stu-id="c4f10-117">OutputType Dynamic Options</span></span>  
  
### <a name="outputtype--file-connection"></a><span data-ttu-id="c4f10-118">OutputType = Соединение с файлом</span><span class="sxs-lookup"><span data-stu-id="c4f10-118">OutputType = File Connection</span></span>  
 <span data-ttu-id="c4f10-119">**Файл**</span><span class="sxs-lookup"><span data-stu-id="c4f10-119">**File**</span></span>  
 <span data-ttu-id="c4f10-120">Выберите в списке диспетчер подключений файлов или щелкните \<**New Connection...**>, чтобы создать диспетчер подключений.</span><span class="sxs-lookup"><span data-stu-id="c4f10-120">Select a File connection manager in the list or click \<**New Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="c4f10-121">**См. также:** подробные сведения о [диспетчере файловых подключений](connection-manager/file-connection-manager.md) и о [редакторе диспетчера файловых подключений](../../2014/integration-services/file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="c4f10-121">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="outputtype--variable"></a><span data-ttu-id="c4f10-122">OutputType = Переменная</span><span class="sxs-lookup"><span data-stu-id="c4f10-122">OutputType = Variable</span></span>  
 <span data-ttu-id="c4f10-123">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="c4f10-123">**Variable**</span></span>  
 <span data-ttu-id="c4f10-124">Выберите переменную в списке или щелкните \<**New Variable...**> для создания переменной.</span><span class="sxs-lookup"><span data-stu-id="c4f10-124">Select a variable in the list or click \<**New Variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="c4f10-125">**См. также:**  подробные сведения о [переменных в службах Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md) и о [добавлении переменной](../../2014/integration-services/add-variable.md).</span><span class="sxs-lookup"><span data-stu-id="c4f10-125">**Related Topics:**  [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f10-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4f10-126">See Also</span></span>  
 <span data-ttu-id="c4f10-127">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c4f10-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c4f10-128">[Редактор задачи "веб-служба" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="c4f10-128">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="c4f10-129">[Редактор задачи "веб-служба" &#40;"входная страница"&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="c4f10-129">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 [<span data-ttu-id="c4f10-130">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="c4f10-130">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
