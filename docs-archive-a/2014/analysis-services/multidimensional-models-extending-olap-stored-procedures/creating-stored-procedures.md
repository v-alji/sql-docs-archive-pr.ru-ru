---
title: Создание хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- registering assemblies
- database assemblies [Analysis Services]
- server assemblies [Analysis Services]
- stored procedures [Analysis Services], creating
- assemblies [Analysis Services]
ms.assetid: a12ff02f-6d0b-4488-9846-3609fc0d0554
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9a997244a2d54cca8732196107dd21927b5f9e2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732166"
---
# <a name="creating-stored-procedures"></a><span data-ttu-id="6231e-102">Создание хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="6231e-102">Creating Stored Procedures</span></span>
  <span data-ttu-id="6231e-103">Для использования любой хранимой процедуры необходимо, чтобы она была связана с классом среды CLR или модели COM.</span><span class="sxs-lookup"><span data-stu-id="6231e-103">All stored procedures must be associated with a common language runtime (CLR) or Component Object Model (COM) class in order to be used.</span></span> <span data-ttu-id="6231e-104">Класс должен быть установлен на сервере — обычно в виде [!INCLUDE[msCoName](../../includes/msconame-md.md)] библиотеки динамической компоновки ActiveX® (DLL) и регистрируется как сборка на сервере или в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="6231e-104">The class must be installed on the server - usually in the form of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® dynamic link library (DLL) - and registered as an assembly on the server or in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="6231e-105">Хранимые процедуры регистрируются на сервере или в базе данных.</span><span class="sxs-lookup"><span data-stu-id="6231e-105">Stored procedures are registered on a server or on a database.</span></span> <span data-ttu-id="6231e-106">Серверные хранимые процедуры могут вызываться из контекста любого запроса.</span><span class="sxs-lookup"><span data-stu-id="6231e-106">Server stored procedures can be called from any query context.</span></span> <span data-ttu-id="6231e-107">Доступ к хранимым процедурам базы данных имеется, только если контекст базы данных представляет собой базу данных, в которой определена хранимая процедура.</span><span class="sxs-lookup"><span data-stu-id="6231e-107">Database stored procedures can only be accessed if the database context is the database under which the stored procedure is defined.</span></span> <span data-ttu-id="6231e-108">Если функции из одной сборки вызывают функции из другой сборки, то необходимо зарегистрировать обе сборки в одном и том же контексте (сервера или базы данных).</span><span class="sxs-lookup"><span data-stu-id="6231e-108">If functions in one assembly call functions in a different assembly, you must register both assemblies in the same context (server or database).</span></span> <span data-ttu-id="6231e-109">Для сервера или развернутой [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных на сервере можно использовать [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для регистрации сборки.</span><span class="sxs-lookup"><span data-stu-id="6231e-109">For a server or a deployed [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database on a server, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to register an assembly.</span></span> <span data-ttu-id="6231e-110">Для проекта служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] можно использовать конструктор служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для регистрации сборки в проекте.</span><span class="sxs-lookup"><span data-stu-id="6231e-110">For an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you can use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Designer to register an assembly in the project.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6231e-111">Использование сборок COM может представлять угрозу безопасности.</span><span class="sxs-lookup"><span data-stu-id="6231e-111">COM assemblies might pose a security risk.</span></span> <span data-ttu-id="6231e-112">По этой причине, а также по ряду других сборки COM в службах [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)]являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="6231e-112">Due to this risk and other considerations, COM assemblies were deprecated in [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)].</span></span> <span data-ttu-id="6231e-113">Поддержка сборок COM в последующих версиях может быть прекращена.</span><span class="sxs-lookup"><span data-stu-id="6231e-113">COM assemblies might not be supported in future releases.</span></span>  
  
## <a name="registering-a-server-assembly"></a><span data-ttu-id="6231e-114">Регистрация серверной сборки</span><span class="sxs-lookup"><span data-stu-id="6231e-114">Registering a Server Assembly</span></span>  
 <span data-ttu-id="6231e-115">В обозревателе объектов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] список серверных сборок приведен в папке «Сборки» под экземпляром служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6231e-115">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], server assemblies are listed in the Assemblies folder under an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="6231e-116">Серверные сборки могут содержать как сборки .NET (среды CLR), так и библиотеки COM.</span><span class="sxs-lookup"><span data-stu-id="6231e-116">Server assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-server-assembly"></a><span data-ttu-id="6231e-117">Создание серверной сборки</span><span class="sxs-lookup"><span data-stu-id="6231e-117">To create a server assembly</span></span>  
  
1.  <span data-ttu-id="6231e-118">Разверните экземпляр [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в обозревателе объектов, щелкните правой кнопкой мыши папку **сборки** и выберите пункт **создать сборку**.</span><span class="sxs-lookup"><span data-stu-id="6231e-118">Expand the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="6231e-119">Откроется диалоговое окно **Регистрация сборки сервера** .</span><span class="sxs-lookup"><span data-stu-id="6231e-119">This displays the **Register Server Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="6231e-120">В поле **тип** укажите тип сборки:</span><span class="sxs-lookup"><span data-stu-id="6231e-120">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="6231e-121">Для DLL-библиотеки управляемого кода (среда CLR) задайте сборку .NET.</span><span class="sxs-lookup"><span data-stu-id="6231e-121">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="6231e-122">Для DLL-библиотеки собственного кода (COM) укажите COM DLL.</span><span class="sxs-lookup"><span data-stu-id="6231e-122">For a native code (COM) DLL, specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="6231e-123">В поле **имя файла**укажите библиотеку DLL, содержащую хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="6231e-123">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="6231e-124">В поле **имя сборки**укажите имя сборки.</span><span class="sxs-lookup"><span data-stu-id="6231e-124">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="6231e-125">Если это отладочная сборка библиотеки, которую вы собираетесь использовать для отладки хранимых процедур, установите флажок **включить отладочную информацию** .</span><span class="sxs-lookup"><span data-stu-id="6231e-125">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="6231e-126">Дополнительные сведения об отладке хранимых процедур см. в разделе [Отладка хранимых процедур](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6231e-126">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="6231e-127">Можно нажать кнопку **ОК** для немедленной регистрации сборки или на панели инструментов диалогового окна, **чтобы создать скрипт** действия регистрации в окне запроса, в файле или в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="6231e-127">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="6231e-128">После регистрации серверной сборки ее можно настроить, щелкнув правой кнопкой мыши сборку в обозревателе объектов и выбрав пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6231e-128">After you register a server assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-on-the-server"></a><span data-ttu-id="6231e-129">Регистрация сборки базы данных на сервере</span><span class="sxs-lookup"><span data-stu-id="6231e-129">Registering a Database Assembly on the Server</span></span>  
 <span data-ttu-id="6231e-130">В обозревателе объектов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] список сборок базы данных приведен в папке «Сборки» под базой данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6231e-130">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="6231e-131">Сборки баз данных могут содержать как сборки .NET (среда CLR), так и библиотеки COM.</span><span class="sxs-lookup"><span data-stu-id="6231e-131">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-on-a-server"></a><span data-ttu-id="6231e-132">Создание сборки базы данных на сервере</span><span class="sxs-lookup"><span data-stu-id="6231e-132">To create a database assembly on a server</span></span>  
  
1.  <span data-ttu-id="6231e-133">Разверните экземпляр [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных в обозревателе объектов, щелкните правой кнопкой мыши папку **сборки** и выберите пункт **создать сборку**.</span><span class="sxs-lookup"><span data-stu-id="6231e-133">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="6231e-134">Откроется диалоговое окно **Регистрация сборки базы данных** .</span><span class="sxs-lookup"><span data-stu-id="6231e-134">This displays the **Register Database Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="6231e-135">В поле **тип** укажите тип сборки:</span><span class="sxs-lookup"><span data-stu-id="6231e-135">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="6231e-136">Для DLL-библиотеки управляемого кода (среда CLR) задайте сборку .NET.</span><span class="sxs-lookup"><span data-stu-id="6231e-136">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="6231e-137">Для DLL-библиотеки собственного кода (COM) укажите COM DLL.</span><span class="sxs-lookup"><span data-stu-id="6231e-137">For a native code (COM) DLL), specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="6231e-138">В поле **имя файла**укажите библиотеку DLL, содержащую хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="6231e-138">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="6231e-139">В поле **имя сборки**укажите имя сборки.</span><span class="sxs-lookup"><span data-stu-id="6231e-139">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="6231e-140">Если это отладочная сборка библиотеки, которую вы собираетесь использовать для отладки хранимых процедур, установите флажок **включить отладочную информацию** .</span><span class="sxs-lookup"><span data-stu-id="6231e-140">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="6231e-141">Дополнительные сведения об отладке хранимых процедур см. в разделе [Отладка хранимых процедур](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6231e-141">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="6231e-142">Можно нажать кнопку **ОК** для немедленной регистрации сборки или на панели инструментов диалогового окна, **чтобы создать скрипт** действия регистрации в окне запроса, в файле или в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="6231e-142">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="6231e-143">После регистрации сборки базы данных ее можно настроить, щелкнув правой кнопкой мыши сборку в обозревателе объектов и выбрав пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6231e-143">After you register a database assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-in-a-project"></a><span data-ttu-id="6231e-144">Регистрация сборки базы данных в проекте</span><span class="sxs-lookup"><span data-stu-id="6231e-144">Registering a Database Assembly in a Project</span></span>  
 <span data-ttu-id="6231e-145">В обозревателе объектов в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] список сборок базы данных приведен в папке «Сборки» под проектом служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6231e-145">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="6231e-146">Сборки баз данных могут содержать как сборки .NET (среда CLR), так и библиотеки COM.</span><span class="sxs-lookup"><span data-stu-id="6231e-146">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-in-an-analysis-service-project"></a><span data-ttu-id="6231e-147">Создание сборки базы данных в проекте служб Analysis Service</span><span class="sxs-lookup"><span data-stu-id="6231e-147">To create a database assembly in an Analysis Service project</span></span>  
  
1.  <span data-ttu-id="6231e-148">Разверните экземпляр [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных в обозревателе объектов, щелкните правой кнопкой мыши папку **сборки** и выберите пункт **создать ссылку на сборку**.</span><span class="sxs-lookup"><span data-stu-id="6231e-148">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly Reference**.</span></span> <span data-ttu-id="6231e-149">Откроется диалоговое окно **Добавление ссылки** .</span><span class="sxs-lookup"><span data-stu-id="6231e-149">This displays the **Add Reference** dialog box.</span></span> <span data-ttu-id="6231e-150">На вкладке **.NET** диалогового окна **Добавление ссылки** перечислены существующие сборки .NET (среда CLR), а на вкладке **проекты** перечислены проекты.</span><span class="sxs-lookup"><span data-stu-id="6231e-150">The **.NET** tab of the **Add Reference** dialog box lists existing .NET (CLR) assemblies, while the **Projects** tab lists projects.</span></span>  
  
2.  <span data-ttu-id="6231e-151">Можно щелкнуть существующий компонент или проект и нажать кнопку **Добавить** , чтобы добавить его в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проект.</span><span class="sxs-lookup"><span data-stu-id="6231e-151">You can click an existing component or project and then click **Add** to add it to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="6231e-152">Чтобы добавить ссылку на DLL-библиотеку COM, щелкните вкладку **Обзор** , чтобы найти файл.</span><span class="sxs-lookup"><span data-stu-id="6231e-152">To add a reference to a COM DLL, click the **Browse** tab to find the file.</span></span> <span data-ttu-id="6231e-153">В списке **Выбранные проекты и компоненты** отображаются имя, тип, версия и расположение для каждого компонента, добавляемого в проект.</span><span class="sxs-lookup"><span data-stu-id="6231e-153">The **Selected projects and components** list shows the name, type, version, and location for each component that you are adding to the project.</span></span>  
  
3.  <span data-ttu-id="6231e-154">Завершив выбор компонентов для добавления, нажмите кнопку **ОК** , чтобы добавить их в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проект.</span><span class="sxs-lookup"><span data-stu-id="6231e-154">When you are finished selecting components to add, click **OK** to add them to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
## <a name="script-format-for-an-assembly"></a><span data-ttu-id="6231e-155">Формат скрипта для сборки</span><span class="sxs-lookup"><span data-stu-id="6231e-155">Script Format For an Assembly</span></span>  
 <span data-ttu-id="6231e-156">Регистрация сборки .NET довольно проста.</span><span class="sxs-lookup"><span data-stu-id="6231e-156">Registering a .NET assembly is fairly simple.</span></span> <span data-ttu-id="6231e-157">Сборка .NET добавляется к базе данных в бинарном виде с использованием следующего формата:</span><span class="sxs-lookup"><span data-stu-id="6231e-157">A .NET assembly is added to a database in binary format using the following format:</span></span>  
  
```  
<Create>  
   <ObjectDefinition>  
      <Assembly>  
         <Files>  
            <File>  
               <Name>filename</Name>  
               <Type>filetype</Type>  
               <Data>  
                  <Block>binarydatablock</Block>  
                  <Block>binarydatablock</Block>  
                  ...  
               </Data>  
            </File>  
         </Files>  
         <PermissionSet>PermissionSet</PermissionSet>  
      </Assembly>  
   <ObjectDefinition>  
</Create>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6231e-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="6231e-158">See Also</span></span>  
 <span data-ttu-id="6231e-159">[Управление сборками многомерной модели](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="6231e-159">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="6231e-160">Определение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="6231e-160">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
