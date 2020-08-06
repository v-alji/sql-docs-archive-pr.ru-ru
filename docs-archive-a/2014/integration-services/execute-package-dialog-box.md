---
title: Диалоговое окно «Выполнение пакета» | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageexecute.f1
- sql12.ssis.ssms.executepackage.f1
ms.assetid: 4f7a806d-4867-4d1f-bc65-b00c1caee7b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b60381054c781cd59f0a9d434710663b72d616c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665017"
---
# <a name="execute-package-dialog-box"></a><span data-ttu-id="1501b-102">Execute Package Dialog Box</span><span class="sxs-lookup"><span data-stu-id="1501b-102">Execute Package Dialog Box</span></span>
  <span data-ttu-id="1501b-103">Используйте диалоговое окно **Выполнение пакета** , чтобы запустить пакет, хранящийся на сервере служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1501b-103">Use the **Execute Package** dialog box to run a package that is stored on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="1501b-104">Пакет служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] может содержать параметры, значения которых хранятся в переменных среды.</span><span class="sxs-lookup"><span data-stu-id="1501b-104">An [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package may contain parameters that values stored in environment variables.</span></span> <span data-ttu-id="1501b-105">Перед выполнением такого пакета необходимо указать, какая среда будет применяться для задания значений переменных среды.</span><span class="sxs-lookup"><span data-stu-id="1501b-105">Before executing such a package, you must specify which environment will be used to provide the environment variable values.</span></span> <span data-ttu-id="1501b-106">Проект может содержать несколько сред, но для привязки значений переменных среды во время выполнения может использоваться только одна среда.</span><span class="sxs-lookup"><span data-stu-id="1501b-106">A project may contain multiple environments, but only one environment can be used for binding environment variable values at the time of execution.</span></span> <span data-ttu-id="1501b-107">Если в пакете не используются переменные среды, среда не требуется.</span><span class="sxs-lookup"><span data-stu-id="1501b-107">If no environment variables are used in the package, an environment is not required.</span></span>  
  
 <span data-ttu-id="1501b-108">Выбор действия</span><span class="sxs-lookup"><span data-stu-id="1501b-108">What do you want to do?</span></span>  
  
-   [<span data-ttu-id="1501b-109">Открытие диалогового окна «Выполнение пакета»</span><span class="sxs-lookup"><span data-stu-id="1501b-109">Open the Execute Package dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="1501b-110">Задание параметров на странице «Общие»</span><span class="sxs-lookup"><span data-stu-id="1501b-110">Set the Options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="1501b-111">Задание параметров на вкладке «Параметры»</span><span class="sxs-lookup"><span data-stu-id="1501b-111">Set the Options on the Parameters tab</span></span>](#parameters)  
  
-   [<span data-ttu-id="1501b-112">Задание параметров на вкладке «Диспетчеры соединений»</span><span class="sxs-lookup"><span data-stu-id="1501b-112">Set the Options on the Connection Managers tab</span></span>](#connection)  
  
-   [<span data-ttu-id="1501b-113">Задание параметров на вкладке «Дополнительно»</span><span class="sxs-lookup"><span data-stu-id="1501b-113">Set the Options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="1501b-114">Создание скриптов параметров в диалоговом окне выполнения пакета</span><span class="sxs-lookup"><span data-stu-id="1501b-114">Scripting the Options in the Execute Package Dialog Box</span></span>](#script)  
  
##  <a name="open-the-execute-package-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="1501b-115">Открытие диалогового окна «Выполнение пакета»</span><span class="sxs-lookup"><span data-stu-id="1501b-115">Open the Execute Package dialog box</span></span>  
  
1.  <span data-ttu-id="1501b-116">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]установите соединение с сервером служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1501b-116">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="1501b-117">Устанавливается соединение с экземпляром [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)], в котором размещена база данных SSISDB.</span><span class="sxs-lookup"><span data-stu-id="1501b-117">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="1501b-118">В обозревателе объектов разверните дерево для отображения узла **Каталоги служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="1501b-118">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="1501b-119">Разверните узел **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="1501b-119">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="1501b-120">Разверните папку, содержащую пакет, который необходимо запустить.</span><span class="sxs-lookup"><span data-stu-id="1501b-120">Expand the folder that contains the package you want to run.</span></span>  
  
5.  <span data-ttu-id="1501b-121">Щелкните правой кнопкой мыши пакет и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1501b-121">Right-click the package, and then click **Execute**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="1501b-122">Задание параметров на странице «Общие»</span><span class="sxs-lookup"><span data-stu-id="1501b-122">Set the Options on the General page</span></span>  
 <span data-ttu-id="1501b-123">Выберите **Среда** для указания среды, которая будет применена с запуском пакета.</span><span class="sxs-lookup"><span data-stu-id="1501b-123">Select **Environment** to specify the environment that is applied with the package is run.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-tab"></a><a name="parameters"></a> <span data-ttu-id="1501b-124">Задание параметров на вкладке «Параметры»</span><span class="sxs-lookup"><span data-stu-id="1501b-124">Set the Options on the Parameters tab</span></span>  
 <span data-ttu-id="1501b-125">На вкладке **Параметры** измените значения параметров, которые используются при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="1501b-125">Use the **Parameters** tab to modify the parameter values that are used when the package runs.</span></span>  
  
##  <a name="set-the-options-on-the-connection-managers-tab"></a><a name="connection"></a> <span data-ttu-id="1501b-126">Задание параметров на вкладке «Диспетчеры соединений»</span><span class="sxs-lookup"><span data-stu-id="1501b-126">Set the Options on the Connection Managers tab</span></span>  
 <span data-ttu-id="1501b-127">На вкладке «Диспетчеры соединений» задайте свойства диспетчеров соединений пакета.</span><span class="sxs-lookup"><span data-stu-id="1501b-127">Use the Connection Managers tab to set the properties of the package connection manager(s).</span></span>  
  
##  <a name="set-the-options-on-the-advanced-tab"></a><a name="advanced"></a> <span data-ttu-id="1501b-128">Задание параметров на вкладке «Дополнительно»</span><span class="sxs-lookup"><span data-stu-id="1501b-128">Set the Options on the Advanced tab</span></span>  
 <span data-ttu-id="1501b-129">На вкладке «Дополнительно» выполняется управление свойствами и другими параметрами пакета.</span><span class="sxs-lookup"><span data-stu-id="1501b-129">Use the Advanced tab to manage properties and other package settings.</span></span>  
  
 <span data-ttu-id="1501b-130">**Добавить**, **Изменить**, **Удалить**</span><span class="sxs-lookup"><span data-stu-id="1501b-130">**Add**, **Edit**, **Remove**</span></span>  
 <span data-ttu-id="1501b-131">Используйте эти кнопки для добавления, изменения или удаления свойства.</span><span class="sxs-lookup"><span data-stu-id="1501b-131">Click to add, edit, or remove a property.</span></span>  
  
 <span data-ttu-id="1501b-132">**Уровень ведения журнала**</span><span class="sxs-lookup"><span data-stu-id="1501b-132">**Logging level**</span></span>  
 <span data-ttu-id="1501b-133">Выберите уровень ведения журнала для выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="1501b-133">Select the logging level for the package execution.</span></span> <span data-ttu-id="1501b-134">Дополнительные сведения см. в разделе [catalog.set_execution_parameter_value (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="1501b-134">For more information, see [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span></span>  
  
 <span data-ttu-id="1501b-135">**Дамп при ошибках**</span><span class="sxs-lookup"><span data-stu-id="1501b-135">**Dump on errors**</span></span>  
 <span data-ttu-id="1501b-136">Укажите, будет ли при возникновении ошибок создаваться файл дампа во время выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="1501b-136">Specify whether a dump file is created when errors occur during the package execution.</span></span> <span data-ttu-id="1501b-137">Дополнительные сведения см. в статье [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="1501b-137">For more information, see [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span></span>  
  
 <span data-ttu-id="1501b-138">**32-разрядная среда выполнения**</span><span class="sxs-lookup"><span data-stu-id="1501b-138">**32-bit runtime**</span></span>  
 <span data-ttu-id="1501b-139">Укажите, что пакет будет выполняться в 32-разрядной системе.</span><span class="sxs-lookup"><span data-stu-id="1501b-139">Specify that the package will execute on a 32-bit system.</span></span>  
  
##  <a name="scripting-the-options-in-the-execute-package-dialog-box"></a><a name="script"></a> <span data-ttu-id="1501b-140">Создание скриптов параметров в диалоговом окне выполнения пакета</span><span class="sxs-lookup"><span data-stu-id="1501b-140">Scripting the Options in the Execute Package Dialog Box</span></span>  
 <span data-ttu-id="1501b-141">Кроме того, в диалоговом окне **Выполнение пакета** вы можете использовать кнопку **Скрипт** на панели инструментов для записи кода [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1501b-141">While you are in the **Execute Package** dialog box, you can also use the **Script** button on the toolbar to write [!INCLUDE[tsql](../includes/tsql-md.md)] code for you.</span></span> <span data-ttu-id="1501b-142">Созданный скрипт вызывает хранимые процедуры [catalog.start_execution (база данных SSISDB)](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) с теми же параметрами, которые были выбраны в диалоговом окне **Выполнение пакета**.</span><span class="sxs-lookup"><span data-stu-id="1501b-142">The generated script calls the stored procedures [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) with the same options that you have selected in the **Execute Package** dialog box.</span></span> <span data-ttu-id="1501b-143">Скрипт отображается в новом окне скрипта в среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1501b-143">The script appears in a new script window in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
  
