---
title: Редактор задачи «веб-служба» (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.general.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 4d7df283-430d-4f0f-9dd4-5909554cd5eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dbacf2a2a867ab01039678ff4f43eebac839c11a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667787"
---
# <a name="web-service-task-editor-general-page"></a><span data-ttu-id="fc6bf-102">Редактор задачи «Веб-служба» (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="fc6bf-102">Web Service Task Editor (General Page)</span></span>
  <span data-ttu-id="fc6bf-103">Страница **Общие** в диалоговом окне **Редактор задачи "Веб-служба"** применяется для указания диспетчера HTTP-соединений, расположения файла WSDL, используемого задачей веб-службы, описания задачи веб-службы и загрузки файла WSDL.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-103">Use the **General** page of the **Web Services Task Editor** dialog box to specify an HTTP connection manager, specify the location of the Web Services Description Language (WSDL) file the Web Service task uses, describe the Web Services task, and download the WSDL file.</span></span>  
  
 <span data-ttu-id="fc6bf-104">Дополнительные сведения об этой задаче см. в разделе [Задача "Веб-служба"](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="fc6bf-104">For more information about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fc6bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc6bf-105">Options</span></span>  
 <span data-ttu-id="fc6bf-106">**HTTPConnection**</span><span class="sxs-lookup"><span data-stu-id="fc6bf-106">**HTTPConnection**</span></span>  
 <span data-ttu-id="fc6bf-107">Выберите из списка диспетчер подключений или нажмите кнопку \<**New connection...**> для создания нового диспетчера подключений.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-107">Select a connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fc6bf-108">Диспетчер HTTP-соединений поддерживает только анонимную проверку подлинности и обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-108">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="fc6bf-109">Проверка подлинности Windows не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-109">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="fc6bf-110">**См. также:**  подробные сведения о [диспетчере HTTP-подключений](connection-manager/http-connection-manager.md) и о [редакторе диспетчера HTTP-подключений &#40;страница "Сервер"&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md).</span><span class="sxs-lookup"><span data-stu-id="fc6bf-110">**Related Topics:**  [HTTP Connection Manager](connection-manager/http-connection-manager.md), [HTTP Connection Manager Editor &#40;Server Page&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span></span>  
  
 <span data-ttu-id="fc6bf-111">**WSDLFile**</span><span class="sxs-lookup"><span data-stu-id="fc6bf-111">**WSDLFile**</span></span>  
 <span data-ttu-id="fc6bf-112">Введите полный путь к локальному WSDL-файлу на компьютере или нажмите кнопку обзора **(...)** и выберите файл.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-112">Type the fully qualified path of a WSDL file that is local to the computer, or click the browse button **(...)** and locate this file.</span></span>  
  
 <span data-ttu-id="fc6bf-113">Если WSDL-файл был загружен на компьютер вручную, выберите этот файл.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-113">If you have already manually downloaded the WSDL file to the computer, select this file.</span></span> <span data-ttu-id="fc6bf-114">Однако, если WSDL-файл еще не был загружен, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-114">However, if the WSDL file has not yet been downloaded, follow these steps:</span></span>  
  
-   <span data-ttu-id="fc6bf-115">Создайте пустой файл с расширением WSDL.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-115">Create an empty file that has the ".wsdl" file name extension.</span></span>  
  
-   <span data-ttu-id="fc6bf-116">Выберите этот пустой файл для параметра **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="fc6bf-116">Select this empty file for the **WSDLFile** option.</span></span>  
  
-   <span data-ttu-id="fc6bf-117">Присвойте параметру **свойство overwritewsdlfile** значение, `True` чтобы разрешить перезапись пустого файла с фактическим WSDL-файлом.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-117">Set the value of **OverwriteWSDLFile** to `True` to enable the empty file to be overwritten with the actual WSDL file.</span></span>  
  
-   <span data-ttu-id="fc6bf-118">Нажмите кнопку **Загрузить язык WSDL** , чтобы загрузить фактический WSDL-файл и перезаписать пустой файл.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-118">Click **Download WSDL** to download the actual WSDL file and overwrite the empty file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fc6bf-119">Кнопка **Загрузить язык WSDL** недоступна, пока не указано имя существующего локального файла в поле **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="fc6bf-119">The **Download WSDL** option is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
 <span data-ttu-id="fc6bf-120">**OverwriteWSDLFile**</span><span class="sxs-lookup"><span data-stu-id="fc6bf-120">**OverwriteWSDLFile**</span></span>  
 <span data-ttu-id="fc6bf-121">Укажите, можно ли перезаписать WSDL-файл для задачи веб-службы.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-121">Indicate whether the WSDL file for the Web Service task can be overwritten.</span></span>  
  
 <span data-ttu-id="fc6bf-122">Если вы собираетесь загрузить WSDL-файл с помощью кнопки **скачать WSDL** , задайте для этого параметра значение `True` .</span><span class="sxs-lookup"><span data-stu-id="fc6bf-122">If you intend to download the WSDL file by using the **Download WSDL** button, set this value to `True`.</span></span>  
  
 <span data-ttu-id="fc6bf-123">**имя**;</span><span class="sxs-lookup"><span data-stu-id="fc6bf-123">**Name**</span></span>  
 <span data-ttu-id="fc6bf-124">Введите уникальное имя задачи веб-службы.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-124">Provide a unique name for the Web Service task.</span></span> <span data-ttu-id="fc6bf-125">Это имя используется в качестве метки для значка задачи.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-125">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc6bf-126">Имена задач в пределах пакета должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-126">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="fc6bf-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fc6bf-127">**Description**</span></span>  
 <span data-ttu-id="fc6bf-128">Введите описание задачи веб-службы.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-128">Type a description of the Web Service task.</span></span>  
  
 <span data-ttu-id="fc6bf-129">**Загрузить язык WSDL**</span><span class="sxs-lookup"><span data-stu-id="fc6bf-129">**Download WSDL**</span></span>  
 <span data-ttu-id="fc6bf-130">Загрузите файл WSDL.</span><span class="sxs-lookup"><span data-stu-id="fc6bf-130">Download the WSDL file.</span></span>  
  
 <span data-ttu-id="fc6bf-131">Эта кнопка недоступна, пока не указано имя существующего локального файла в поле **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="fc6bf-131">This button is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6bf-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc6bf-132">See Also</span></span>  
 <span data-ttu-id="fc6bf-133">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fc6bf-133">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fc6bf-134">[Редактор задачи "веб-служба" &#40;"входная страница"&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="fc6bf-134">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 <span data-ttu-id="fc6bf-135">[Редактор задачи "веб-служба" &#40;страница "выходные данные"&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="fc6bf-135">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="fc6bf-136">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="fc6bf-136">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
