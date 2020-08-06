---
title: Отладка хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- debugging stored procedures [Analysis Services]
- stored procedures [Analysis Services], debugging
ms.assetid: 34f51b85-02b3-40dd-bf93-375a9e522385
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4f5971fe611f06a413ca48b2bc91237a8c87ee8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732162"
---
# <a name="debugging-stored-procedures"></a><span data-ttu-id="513ee-102">Отладка хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="513ee-102">Debugging Stored Procedures</span></span>
  <span data-ttu-id="513ee-103">Хранимые процедуры служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в реальности представляют собой библиотеки CLR или COM (обычно DLL), написанные на языке C# (или на любом другом языке CLR или COM).</span><span class="sxs-lookup"><span data-stu-id="513ee-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures are actually CLR or COM libraries (normally DLLs) that are written in C# (or any other CLR or COM language).</span></span> <span data-ttu-id="513ee-104">Таким образом, отладка хранимой процедуры практически аналогична отладке любого другого приложения в среде отладки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="513ee-104">Therefore, debugging a stored procedure is much like debugging any other application in the Visual Studio debugging environment.</span></span> <span data-ttu-id="513ee-105">Отладка хранимых процедур в среде разработки Visual Studio производится с использованием интегрированных функций отладки.</span><span class="sxs-lookup"><span data-stu-id="513ee-105">You debug stored procedures in the Visual Studio development environment using the integrated debugging functions.</span></span> <span data-ttu-id="513ee-106">Они позволяют осуществлять остановку процедуры в определенных местах, контролировать значения в памяти и регистрах, изменять переменные, следить за трафиком сообщений и подробно анализировать работу кода.</span><span class="sxs-lookup"><span data-stu-id="513ee-106">These allow you to stop at procedure locations, inspect memory and register values, change variables, observe message traffic and get a close look at how your code works.</span></span>  
  
### <a name="to-debug-a-stored-procedure"></a><span data-ttu-id="513ee-107">Отладка хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="513ee-107">To debug a stored procedure</span></span>  
  
1.  <span data-ttu-id="513ee-108">Откройте проект, используемый для создания библиотеки DLL, в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="513ee-108">Open the project used to create the DLL in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="513ee-109">Создайте точки прерывания в методе или функции, соответствующей процедуре, которую необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="513ee-109">Create breakpoints in the method or function corresponding to the procedure you want to debug.</span></span>  
  
3.  <span data-ttu-id="513ee-110">Используйте среду Visual Studio для создания отладочной сборки библиотеки DLL хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="513ee-110">Use Visual Studio to create a debug build of a stored procedure DLL.</span></span>  
  
4.  <span data-ttu-id="513ee-111">Разверните эту библиотеку DLL на сервере.</span><span class="sxs-lookup"><span data-stu-id="513ee-111">Deploy the DLL to the server.</span></span> <span data-ttu-id="513ee-112">Дополнительные сведения о развертывании библиотеки DLL на сервере см. в разделе [Создание хранимых процедур](creating-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="513ee-112">For more information about deploying the DLL to the server, see [Creating Stored Procedures](creating-stored-procedures.md).</span></span>  
  
5.  <span data-ttu-id="513ee-113">Необходимо приложение, вызывающее хранимую процедуру, подлежащую тестированию.</span><span class="sxs-lookup"><span data-stu-id="513ee-113">You need an application that calls the stored procedure that you want to test.</span></span> <span data-ttu-id="513ee-114">При его отсутствии можно использовать редактор запросов многомерных выражений в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для создания запроса многомерных выражений, вызывающего хранимую процедуру, которую необходимо протестировать.</span><span class="sxs-lookup"><span data-stu-id="513ee-114">If you do not have one ready, you can use the MDX Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create an MDX query that calls the stored procedure that you want to test.</span></span>  
  
6.  <span data-ttu-id="513ee-115">В среде Visual Studio подключитесь к процессу служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (Msmdsrv.exe).</span><span class="sxs-lookup"><span data-stu-id="513ee-115">In Visual Studio, attach to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process (Msmdsrv.exe).</span></span>  
  
    1.  <span data-ttu-id="513ee-116">В меню **Отладка** выберите **аттатч топроцесс**.</span><span class="sxs-lookup"><span data-stu-id="513ee-116">From the **Debug** menu, choose **Attatch toProcess**.</span></span>  
  
    2.  <span data-ttu-id="513ee-117">В диалоговом окне **Аттатч топроцесс** выберите пункт **Показывать процессы всех пользователей**.</span><span class="sxs-lookup"><span data-stu-id="513ee-117">In the **Attatch toProcess** dialog box, select **Show processes from all users**.</span></span>  
  
    3.  <span data-ttu-id="513ee-118">В списке **Доступные процессы** в столбце **процесс** щелкните **Msmdsrv.exe**.</span><span class="sxs-lookup"><span data-stu-id="513ee-118">In the **Available Processes** list, in the **Process** column, click **Msmdsrv.exe**.</span></span> <span data-ttu-id="513ee-119">Если на сервере несколько экземпляров служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], то определить необходимый процесс можно по идентификатору экземпляра.</span><span class="sxs-lookup"><span data-stu-id="513ee-119">If there is more than one instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] running on the server, you need to identify the process by the ID of the instance you want to use.</span></span>  
  
    4.  <span data-ttu-id="513ee-120">Убедитесь, что в текстовом поле **присоединить к** выбран нужный тип программы.</span><span class="sxs-lookup"><span data-stu-id="513ee-120">In the **Attach to** text box, make sure that the appropriate program type is selected.</span></span> <span data-ttu-id="513ee-121">Для DLL-библиотеки CLR нажмите кнопку **выбрать**, выберите **Отладка этих типов кода**, затем выберите **управляемый**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="513ee-121">For a CLR DLL, click **Select**, then click **Debug these code types**, then click **Managed**, then click **OK**.</span></span> <span data-ttu-id="513ee-122">Для DLL-библиотеки COM нажмите кнопку **выбрать**, выберите **Отладка этих типов кода**, затем выберите **собственный**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="513ee-122">For a COM DLL, click **Select**, then click **Debug these code types**, then click **Native**, then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="513ee-123">Нажмите кнопку **Присоединить**.</span><span class="sxs-lookup"><span data-stu-id="513ee-123">Click **Attach**.</span></span>  
  
7.  <span data-ttu-id="513ee-124">В службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] запустите программу или скрипт многомерных выражений, вызывающий хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="513ee-124">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], invoke the program or MDX script that calls the stored procedure.</span></span> <span data-ttu-id="513ee-125">Отладчик останавливается, когда достигает строку, содержащую точку прерывания.</span><span class="sxs-lookup"><span data-stu-id="513ee-125">The debugger breaks when it reaches a line containing a breakpoint.</span></span> <span data-ttu-id="513ee-126">Можно оценить переменные в окне наблюдения, просмотреть локальные значения и проверить шаги кода.</span><span class="sxs-lookup"><span data-stu-id="513ee-126">You can evaluate variables in the watch window, view locals, and step through the code.</span></span>  
  
 <span data-ttu-id="513ee-127">При возникновении проблем с отладкой библиотеки убедитесь, что соответствующий файл базы данных программ (PDB-файл) скопирован в место развертывания на сервере.</span><span class="sxs-lookup"><span data-stu-id="513ee-127">If you have problems debugging a library, make sure that the corresponding program database (PDB) file was copied to the deployment location on the server.</span></span> <span data-ttu-id="513ee-128">Если этот файл не был скопирован во время регистрации или развертывания, то его необходимо скопировать вручную в то же место, где находится библиотека DLL.</span><span class="sxs-lookup"><span data-stu-id="513ee-128">If this file was not copied during registration or deployment, you must copy it manually to the same location as the DLL.</span></span> <span data-ttu-id="513ee-129">Для собственного кода (COM DLL) PDB-файл находится в подкаталоге \debug.</span><span class="sxs-lookup"><span data-stu-id="513ee-129">For native code (COM DLL), the PDB file resides in the \debug subdirectory.</span></span> <span data-ttu-id="513ee-130">Для управляемого (CLR DLL) — он находится в подкаталоге \WINDEBUG.</span><span class="sxs-lookup"><span data-stu-id="513ee-130">For managed code (CLR DLL), it resides in the \WINDEBUG subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="513ee-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="513ee-131">See Also</span></span>  
 <span data-ttu-id="513ee-132">[Управление сборками многомерной модели](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="513ee-132">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="513ee-133">Определение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="513ee-133">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
