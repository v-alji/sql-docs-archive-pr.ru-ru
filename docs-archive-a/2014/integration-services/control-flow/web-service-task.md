---
title: Задача "Веб-служба" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicetask.f1
helpviewer_keywords:
- Web Service task [Integration Services]
ms.assetid: 5c7206f1-7d6a-4923-8dff-3c4912da4157
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a2f719a6fb0076a3bb286865199a9cf6a008d32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656512"
---
# <a name="web-service-task"></a><span data-ttu-id="7bfdc-102">Задача «Веб-служба»</span><span class="sxs-lookup"><span data-stu-id="7bfdc-102">Web Service Task</span></span>
  <span data-ttu-id="7bfdc-103">Задача «Веб-служба» выполняет метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-103">The Web Service task executes a Web service method.</span></span> <span data-ttu-id="7bfdc-104">Возможно использование задачи «Веб-служба» в следующих целях:</span><span class="sxs-lookup"><span data-stu-id="7bfdc-104">You can use the Web Service task for the following purposes:</span></span>  
  
-   <span data-ttu-id="7bfdc-105">Запись в переменную значений, возвращаемых методом веб-службы.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-105">Writing to a variable the values that a Web service method returns.</span></span> <span data-ttu-id="7bfdc-106">Например, можно получить самую высокую температуру дня из метода веб-службы с последующим использованием ее значения для обновления переменной, которая используется в выражении, задающем значение столбца.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-106">For example, you could obtain the highest temperature of the day from a Web service method, and then use that value to update a variable that is used in an expression that sets a column value.</span></span>  
  
-   <span data-ttu-id="7bfdc-107">Запись в файл значений, возвращаемых методом веб-службы.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-107">Writing to a file the values that a Web service method returns.</span></span> <span data-ttu-id="7bfdc-108">Например, список потенциальных покупателей может быть записан в файл, который затем используется в качестве источника данных в пакете, очищающем данные перед их занесением в базу данных.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-108">For example, a list of potential customers can be written to a file and the file then used as a data source in a package that cleans the data before it is written to a database.</span></span>  
  
## <a name="wsdl-file"></a><span data-ttu-id="7bfdc-109">WSDL-файл</span><span class="sxs-lookup"><span data-stu-id="7bfdc-109">WSDL File</span></span>  
 <span data-ttu-id="7bfdc-110">Для подключения к веб-службе задача «Веб-служба» использует диспетчер HTTP-соединений.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-110">The Web Service task uses an HTTP connection manager to connect to the Web service.</span></span> <span data-ttu-id="7bfdc-111">Редактор диспетчера HTTP-соединений сконфигурирован отдельно от задачи «Веб-служба», ссылка на него содержится в задаче.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-111">The HTTP connection manager is configured separately from the Web Service task, and is referenced in the task.</span></span> <span data-ttu-id="7bfdc-112">Диспетчер HTTP-соединений указывает настройки прокси-сервера, такие как URL-адрес сервера, учетные записи для доступа к веб-службе и длительность времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-112">The HTTP connection manager specifies the server proxy settings such as the server URL, credentials for accessing the Web services server, and time-out length.</span></span> <span data-ttu-id="7bfdc-113">Дополнительные сведения см. в статье [Диспетчер HTTP-соединений](../connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7bfdc-113">For more information, see [HTTP Connection Manager](../connection-manager/http-connection-manager.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7bfdc-114">Диспетчер HTTP-соединений поддерживает только анонимную проверку подлинности и обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-114">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="7bfdc-115">Проверка подлинности Windows не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-115">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="7bfdc-116">Диспетчер HTTP-соединений может указывать на веб-сайт или на файл языка описания веб-служб (язык WSDL).</span><span class="sxs-lookup"><span data-stu-id="7bfdc-116">The HTTP connection manager can point to a Web site or to a Web Service Description Language (WSDL) file.</span></span> <span data-ttu-id="7bfdc-117">URL-адрес диспетчера HTTP-подключений, указывающий на WSDL-файл, содержит параметр `?WSDL` , например `http://MyServer/MyWebService/MyPage.asmx?WSDL`.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-117">The URL of the HTTP connection manager that points to a WSDL file includes the `?WSDL` parameter: for example, `http://MyServer/MyWebService/MyPage.asmx?WSDL`.</span></span>  
  
 <span data-ttu-id="7bfdc-118">Чтобы настроить задачу «Веб-служба», используя диалоговое окно **Редактор задачи «Веб-служба»** , которое предоставляет конструктор [!INCLUDE[ssIS](../../includes/ssis-md.md)] , WSDL-файл должен быть доступен локально.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-118">The WSDL file must be available locally to configure the Web Service task using the **Web Service Task Editor** dialog box that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides.</span></span>  
  
-   <span data-ttu-id="7bfdc-119">Если диспетчер HTTP-соединений указывает на веб-сайт, то WSDL-файл должен быть скопирован на локальный компьютер вручную.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-119">If the HTTP connection manager points to a Web site, the WSDL file must be copied manually to a local computer.</span></span>  
  
-   <span data-ttu-id="7bfdc-120">Если диспетчер HTTP-соединений указывает на WSDL-файл, то файл можно сделать локальным, загрузив его с веб-сайта при помощи задачи «Веб-служба».</span><span class="sxs-lookup"><span data-stu-id="7bfdc-120">If the HTTP connection manager points to a WSDL file, the file can be downloaded from the Web site to a local file by the Web Service task.</span></span>  
  
 <span data-ttu-id="7bfdc-121">WSDL-файл перечисляет методы, предлагаемые веб-службой; входные параметры, запрашиваемые методами; ответы, возвращаемые методами; а также метод обмена данными с веб-службой.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-121">The WSDL file lists the methods that the Web service offers, the input parameters that the methods require, the responses that the methods return, and how to communicate with the Web service.</span></span>  
  
 <span data-ttu-id="7bfdc-122">Если метод использует входные параметры, то задача «Веб-служба» запрашивает значения параметров.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-122">If the method uses input parameters, the Web Service task requires parameter values.</span></span> <span data-ttu-id="7bfdc-123">Например, метод веб-службы рекомендует длину приобретаемых лыж, основываясь на росте покупателя, поэтому требует, чтобы рост был записан во входном параметре.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-123">For example, a Web service method that recommends the length of skis you should purchase based on your height requires that your height be submitted in an input parameter.</span></span> <span data-ttu-id="7bfdc-124">Значения параметра можно задать строками, определенными в задаче, или переменными, определенными в области видимости задачи или родительского контейнера.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-124">The parameter values can be provided either by strings that are defined in the task, or by variables defined in the scope of the task or a parent container.</span></span> <span data-ttu-id="7bfdc-125">Преимущество использования переменных в том, что они позволяют динамически обновлять значения параметров с помощью конфигураций пакетов или скриптов.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-125">The advantage of using variables is that they let you dynamically update the parameter values by using package configurations or scripts.</span></span> <span data-ttu-id="7bfdc-126">Дополнительные сведения см. в разделах [Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md) и [Конфигурации пакета](../package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="7bfdc-126">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Package Configurations](../package-configurations.md).</span></span>  
  
 <span data-ttu-id="7bfdc-127">Многие методы веб-службы не используют входные параметры.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-127">Many Web service methods do not use input parameters.</span></span> <span data-ttu-id="7bfdc-128">Например, метод веб-службы, выдающий имена сотрудников, рожденных в текущем месяце, не запрашивает входного параметра, потому что веб-служба может определить текущий месяц локально.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-128">For example, a Web service method that gets the names of presidents who were born in the current month would not require an input parameter because the Web service can determine the current month locally.</span></span>  
  
 <span data-ttu-id="7bfdc-129">Результаты метода веб-службы могут быть записаны в переменную или в файл.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-129">The results of the Web service method can be written to a variable or to a file.</span></span> <span data-ttu-id="7bfdc-130">Используйте диспетчер подключений файла для указания файла или для указания имени переменной, в которую записывается результат.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-130">You use the File connection manager either to specify the file or to provide the name of the variable to write the results to.</span></span> <span data-ttu-id="7bfdc-131">Дополнительные сведения см. в разделах [Диспетчер соединения файлов](../connection-manager/file-connection-manager.md) и [Переменные в службах Integration Services (SSIS)](../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="7bfdc-131">For more information, see [File Connection Manager](../connection-manager/file-connection-manager.md) and [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md).</span></span>  
  
## <a name="custom-logging-messages-available-on-the-web-service-task"></a><span data-ttu-id="7bfdc-132">Пользовательские сообщения для ведения журнала, доступные в задаче «Веб-служба»</span><span class="sxs-lookup"><span data-stu-id="7bfdc-132">Custom Logging Messages Available on the Web Service Task</span></span>  
 <span data-ttu-id="7bfdc-133">В следующей таблице перечислены пользовательские записи в журнале для задачи «Веб-служба».</span><span class="sxs-lookup"><span data-stu-id="7bfdc-133">The following table lists the custom log entries that you can enable for the Web Service task.</span></span> <span data-ttu-id="7bfdc-134">Дополнительные сведения см. в разделах [Ведение журналов в службах Integration Services (SSIS)](../performance/integration-services-ssis-logging.md) и [Пользовательские сообщения для ведения журнала](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="7bfdc-134">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="7bfdc-135">Запись журнала</span><span class="sxs-lookup"><span data-stu-id="7bfdc-135">Log entry</span></span>|<span data-ttu-id="7bfdc-136">Описание</span><span class="sxs-lookup"><span data-stu-id="7bfdc-136">Description</span></span>|  
|---------------|-----------------|  
|`WSTaskBegin`|<span data-ttu-id="7bfdc-137">Задача получила доступ к веб-службе.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-137">The task began to access a Web service.</span></span>|  
|`WSTaskEnd`|<span data-ttu-id="7bfdc-138">Задача завершила метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-138">The task completed a Web service method.</span></span>|  
|`WSTaskInfo`|<span data-ttu-id="7bfdc-139">Описательные сведения об этой задаче.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-139">Descriptive information about the task.</span></span>|  
  
## <a name="configuration-of-the-web-service-task"></a><span data-ttu-id="7bfdc-140">Настройка задачи «Веб-служба»</span><span class="sxs-lookup"><span data-stu-id="7bfdc-140">Configuration of the Web Service Task</span></span>  
 <span data-ttu-id="7bfdc-141">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-141">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7bfdc-142">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7bfdc-142">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7bfdc-143">Редактор задачи "Веб-служба" (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="7bfdc-143">Web Service Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="7bfdc-144">Редактор задачи "Веб-служба" (страница "Ввод")</span><span class="sxs-lookup"><span data-stu-id="7bfdc-144">Web Service Task Editor &#40;Input Page&#41;</span></span>](../web-service-task-editor-input-page.md)  
  
-   [<span data-ttu-id="7bfdc-145">Редактор задачи "Веб-служба" (страница "Вывод")</span><span class="sxs-lookup"><span data-stu-id="7bfdc-145">Web Service Task Editor &#40;Output Page&#41;</span></span>](../web-service-task-editor-output-page.md)  
  
-   [<span data-ttu-id="7bfdc-146">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="7bfdc-146">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="7bfdc-147">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="7bfdc-147">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7bfdc-148">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="7bfdc-148">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-web-service-task"></a><span data-ttu-id="7bfdc-149">Программная настройка задачи «Веб-служба»</span><span class="sxs-lookup"><span data-stu-id="7bfdc-149">Programmatic Configuration of the Web Service Task</span></span>  
 <span data-ttu-id="7bfdc-150">Дополнительные сведения о программной настройке этих свойств см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7bfdc-150">For more information about programmatically setting these properties, click one of the following topics:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WebServiceTask.WebServiceTask>  
  
## <a name="related-content"></a><span data-ttu-id="7bfdc-151">См. также</span><span class="sxs-lookup"><span data-stu-id="7bfdc-151">Related Content</span></span>  
 <span data-ttu-id="7bfdc-152">Видео с руководством по [ вызвать веб-службу с помощью задачи "Веб-служба" (видеоматериал по SQL Server)](https://go.microsoft.com/fwlink/?LinkId=259642) на портале technet.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7bfdc-152">Video, [How to: Call a Web Service by Using the Web Service Task (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=259642), on technet.microsoft.com.</span></span>  
  
 <span data-ttu-id="7bfdc-153">Использование [веб-службы с помощью пакета служб SSIS](https://www.c-sharpcorner.com/article/how-to-consume-web-service-through-ssis-package/).</span><span class="sxs-lookup"><span data-stu-id="7bfdc-153">[How To Consume Web Service Through SSIS Package](https://www.c-sharpcorner.com/article/how-to-consume-web-service-through-ssis-package/).</span></span>  
  
  
