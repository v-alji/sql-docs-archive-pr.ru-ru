---
title: Редактор задачи "Профилирование данных" (страница "Общие") | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataprofilingtask.general.f1
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: eec15906-d757-4079-b2f6-aca4e52b3b4c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cfcdf472f817d3dd688a5f867ac74d46835ab91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665483"
---
# <a name="data-profiling-task-editor-general-page"></a><span data-ttu-id="bdd01-102">Редактор задачи «Профилирование данных» (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="bdd01-102">Data Profiling Task Editor (General Page)</span></span>
  <span data-ttu-id="bdd01-103">На странице **Общие** окна **Редактор задачи «Профилирование данных»** можно настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="bdd01-103">Use the **General** page of the **Data Profiling Task Editor** to configure the following options:</span></span>  
  
-   <span data-ttu-id="bdd01-104">указать назначение выходных данных профиля;</span><span class="sxs-lookup"><span data-stu-id="bdd01-104">Specify the destination for the profile output.</span></span>  
  
-   <span data-ttu-id="bdd01-105">использовать настройки по умолчанию для упрощения задачи профилирования отдельной таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="bdd01-105">Use the default settings to simplify the task of profiling a single table or view.</span></span>  
  
 <span data-ttu-id="bdd01-106">Дополнительные сведения об использовании задачи "Профилирование данных" см. в разделе [Установка задачи "Профилирование данных"](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="bdd01-106">For more information about how to use the Data Profiling task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="bdd01-107">Дополнительные сведения об использовании средства просмотра профиля данных для анализа результатов задачи "Профилирование данных" см. в разделе [Средство просмотра профиля данных](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="bdd01-107">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
 <span data-ttu-id="bdd01-108">**Открытие страницы «Общие» окна «Редактор задачи "Профилирование данных"»**</span><span class="sxs-lookup"><span data-stu-id="bdd01-108">**To open the General page of the Data Profiling Task Editor**</span></span>  
  
1.  <span data-ttu-id="bdd01-109">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий задачу «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="bdd01-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that has the Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="bdd01-110">На вкладке **Поток управления** дважды щелкните задачу "Профилирование данных".</span><span class="sxs-lookup"><span data-stu-id="bdd01-110">On the **Control Flow** tab, double-click the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="bdd01-111">В окне **Редактор задачи «Профилирование данных»** нажмите кнопку **Общие**.</span><span class="sxs-lookup"><span data-stu-id="bdd01-111">In the **Data Profiling Task Editor**, click **General**.</span></span>  
  
## <a name="data-profiling-options"></a><span data-ttu-id="bdd01-112">Параметры задачи «Профилирование данных»</span><span class="sxs-lookup"><span data-stu-id="bdd01-112">Data Profiling Options</span></span>  
 <span data-ttu-id="bdd01-113">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="bdd01-113">**Timeout**</span></span>  
 <span data-ttu-id="bdd01-114">Время ожидания выполнения задачи «Профилирование данных» в секундах, по истечении которого выполнение этой задачи должно прекратиться.</span><span class="sxs-lookup"><span data-stu-id="bdd01-114">Specify the number of seconds after which the Data Profiling task should timeout and stop running.</span></span> <span data-ttu-id="bdd01-115">По умолчанию установлено значение 0, означающее неограниченное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="bdd01-115">The default value is 0, which indicates no timeout.</span></span>  
  
## <a name="destination-options"></a><span data-ttu-id="bdd01-116">Целевые параметры</span><span class="sxs-lookup"><span data-stu-id="bdd01-116">Destination Options</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bdd01-117">В выходном файле могут содержаться конфиденциальные данные о базе данных и о содержащихся в ней данных.</span><span class="sxs-lookup"><span data-stu-id="bdd01-117">The output file might contain sensitive data about your database and the data that database contains.</span></span> <span data-ttu-id="bdd01-118">Рекомендации по повышению защищенности этого файла см. в разделе [Доступ к файлам, используемым пакетами](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="bdd01-118">For suggestions about how to make this file more secure, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="bdd01-119">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="bdd01-119">**DestinationType**</span></span>  
 <span data-ttu-id="bdd01-120">Указывает, сохранять ли выходные данные профиля в файле или в переменной.</span><span class="sxs-lookup"><span data-stu-id="bdd01-120">Specify whether to save the data profile output to a file or a variable:</span></span>  
  
|<span data-ttu-id="bdd01-121">Значение</span><span class="sxs-lookup"><span data-stu-id="bdd01-121">Value</span></span>|<span data-ttu-id="bdd01-122">Description</span><span class="sxs-lookup"><span data-stu-id="bdd01-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdd01-123">**FileConnection**</span><span class="sxs-lookup"><span data-stu-id="bdd01-123">**FileConnection**</span></span>|<span data-ttu-id="bdd01-124">Сохранение выходных данных профиля в файле, расположение которого указано в диспетчере соединения файлов.</span><span class="sxs-lookup"><span data-stu-id="bdd01-124">Save the profile output to a file in the location that is specified in a File connection manager.</span></span><br /><br /> <span data-ttu-id="bdd01-125">Примечание. С помощью параметра **Назначение** можно указать, какой диспетчер подключений файлов следует использовать.</span><span class="sxs-lookup"><span data-stu-id="bdd01-125">Note: You specify which File connection manager to use in the **Destination** option.</span></span>|  
|<span data-ttu-id="bdd01-126">**Переменная**</span><span class="sxs-lookup"><span data-stu-id="bdd01-126">**Variable**</span></span>|<span data-ttu-id="bdd01-127">Сохранение выходных данных профиля в переменной пакета.</span><span class="sxs-lookup"><span data-stu-id="bdd01-127">Save the profile output to a package variable.</span></span><br /><br /> <span data-ttu-id="bdd01-128">Примечание. С помощью параметра **Назначение** можно указать, какую переменную пакета следует использовать.</span><span class="sxs-lookup"><span data-stu-id="bdd01-128">Note: You specify which package variable to use in the **Destination** option.</span></span>|  
  
 <span data-ttu-id="bdd01-129">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="bdd01-129">**Destination**</span></span>  
 <span data-ttu-id="bdd01-130">Указывает, какой диспетчер соединения файлов или какая переменная пакета содержит выходные данные профиля данных.</span><span class="sxs-lookup"><span data-stu-id="bdd01-130">Specify which File connection manager or package variable contains the data profile output:</span></span>  
  
-   <span data-ttu-id="bdd01-131">Если для параметра **DestinationType** установлено значение **FileConnection**, в параметре **Целевой объект** отображаются доступные диспетчеры соединения файлов.</span><span class="sxs-lookup"><span data-stu-id="bdd01-131">If the **DestinationType** option is set to **FileConnection**, the **Destination** option displays the available File connection managers.</span></span> <span data-ttu-id="bdd01-132">Выберите один из этих диспетчеров или элемент \<New File connection>, чтобы создать новый диспетчер подключений файлов.</span><span class="sxs-lookup"><span data-stu-id="bdd01-132">Select one of these connection managers, or select \<New File connection> to create a new File connection manager.</span></span>  
  
-   <span data-ttu-id="bdd01-133">Если для параметра **DestinationType** установлено значение **Переменные**, в параметре **Целевой объект** отображаются доступные в списке **Целевой объект** переменные пакета.</span><span class="sxs-lookup"><span data-stu-id="bdd01-133">If the **DestinationType** option is set to **Variable**, the **Destination** option displays the available package variables in the **Destination** list.</span></span> <span data-ttu-id="bdd01-134">Выберите одну из этих переменных или элемент\<New Variable>, чтобы создать новую переменную.</span><span class="sxs-lookup"><span data-stu-id="bdd01-134">Select one of these variables, or select \<New Variable> to create a new variable.</span></span>  
  
 <span data-ttu-id="bdd01-135">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="bdd01-135">**OverwriteDestination**</span></span>  
 <span data-ttu-id="bdd01-136">Указывает, следует ли перезаписать выходной файл, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="bdd01-136">Specify whether to overwrite the output file if it already exists.</span></span> <span data-ttu-id="bdd01-137">Значение по умолчанию равно **False**.</span><span class="sxs-lookup"><span data-stu-id="bdd01-137">The default value is **False**.</span></span> <span data-ttu-id="bdd01-138">Значение этого свойства используется только при условии, что для параметра DestinationType установлено значение FileConnection.</span><span class="sxs-lookup"><span data-stu-id="bdd01-138">The value of this property is used only when the DestinationType option is set to FileConnection.</span></span> <span data-ttu-id="bdd01-139">Если параметр DestinationType имеет значение Variable, то предыдущее значение переменной всегда перезаписывается.</span><span class="sxs-lookup"><span data-stu-id="bdd01-139">When the DestinationType option is set to Variable, the task always overwrites the previous value of the variable.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bdd01-140">Если попытаться выполнить задачу "Профилирование данных" более одного раза без изменения имени выходного файла или значения свойства **OverwriteDestination** на **True**, задача завершится с ошибкой и сообщением, что выходной файл уже существует.</span><span class="sxs-lookup"><span data-stu-id="bdd01-140">If you try to run the Data Profiling task more than once without changing the output file name or changing the value of the **OverwriteDestination** property to **True**, the task fails with the message that the output file already exists.</span></span>  
  
## <a name="other-options"></a><span data-ttu-id="bdd01-141">Другие параметры</span><span class="sxs-lookup"><span data-stu-id="bdd01-141">Other Options</span></span>  
 <span data-ttu-id="bdd01-142">**Быстрый профиль**</span><span class="sxs-lookup"><span data-stu-id="bdd01-142">**Quick Profile**</span></span>  
 <span data-ttu-id="bdd01-143">Отображает окно **Форма быстрого профиля одной таблицы**.</span><span class="sxs-lookup"><span data-stu-id="bdd01-143">Display the **Single Table Quick Profile Form**.</span></span> <span data-ttu-id="bdd01-144">Эта форма упрощает задачу профилирования отдельной таблицы или представления путем использования настроек по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bdd01-144">This form simplifies the task of profiling a single table or view by using default settings.</span></span> <span data-ttu-id="bdd01-145">Дополнительные сведения см. в разделе [Форма быстрого профиля одной таблицы (задача "Профилирование данных")](single-table-quick-profile-form-data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="bdd01-145">For more information, see [Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md).</span></span>  
  
 <span data-ttu-id="bdd01-146">**Открыть средство просмотра профиля**</span><span class="sxs-lookup"><span data-stu-id="bdd01-146">**Open Profile Viewer**</span></span>  
 <span data-ttu-id="bdd01-147">Открывает средство просмотра профиля данных.</span><span class="sxs-lookup"><span data-stu-id="bdd01-147">Opens the Data Profile Viewer.</span></span> <span data-ttu-id="bdd01-148">Изолированное средство просмотра профиля данных отображает выходной профиль данных из задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="bdd01-148">The stand-alone Data Profile Viewer displays data profile output from the Data Profiling task.</span></span> <span data-ttu-id="bdd01-149">Выходной профиль данных вы можете просмотреть после запуска задачи «Профилирование данных» внутри пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] и расчета профилей данных.</span><span class="sxs-lookup"><span data-stu-id="bdd01-149">You can view the data profile output after you have run the Data Profiling task inside the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package and computed the data profiles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bdd01-150">Вы можете также открыть средство просмотра профиля данных, запустив DataProfileViewer.exe в папке *\<drive>* :\Program Files (x86) | Program Files\Microsoft SQL Server\110\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="bdd01-150">You can also open the Data Profile Viewer by running the DataProfileViewer.exe in the folder, *\<drive>*:\Program Files (x86) | Program Files\Microsoft SQL Server\110\DTS\Binn.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd01-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="bdd01-151">See Also</span></span>  
 <span data-ttu-id="bdd01-152">[Форма быстрого профиля одной таблицы (задача "Профилирование данных")](single-table-quick-profile-form-data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="bdd01-152">[Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md) </span></span>  
 [<span data-ttu-id="bdd01-153">Редактор задачи "Профилирование данных" (страница "Запросы профиля")</span><span class="sxs-lookup"><span data-stu-id="bdd01-153">Data Profiling Task Editor &#40;Profile Requests Page&#41;</span></span>](data-profiling-task-editor-profile-requests-page.md)  
  
  
