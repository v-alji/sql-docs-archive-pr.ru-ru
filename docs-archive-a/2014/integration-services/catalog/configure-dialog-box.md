---
title: Диалоговое окно "Настройка" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.SSIS.SSMS.ISPROJECTPROP.PARAMETERS.F1
- SQL12.SSIS.SSMS.ISPROJECTPROP.REFERENCES.F1
- sql12.dts.designer.configure.f1
ms.assetid: 10183c8d-b1be-420f-972a-96ea97d4f4d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857baf3421f2744144e10b0df0b770538f533192
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665508"
---
# <a name="configure-dialog-box"></a><span data-ttu-id="212fb-102">Диалоговое окно «Настройка»</span><span class="sxs-lookup"><span data-stu-id="212fb-102">Configure Dialog Box</span></span>
  <span data-ttu-id="212fb-103">Диалоговое окно **Настройка** используется для настройки параметров, диспетчеров соединений и ссылок на среды для пакетов и проектов.</span><span class="sxs-lookup"><span data-stu-id="212fb-103">Use the **Configure** dialog box to configure parameters, connection managers, and references to environments, for packages and projects.</span></span>  
  
 <span data-ttu-id="212fb-104">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="212fb-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="212fb-105">Откройте диалоговое окно «Настройка».</span><span class="sxs-lookup"><span data-stu-id="212fb-105">Open the Configure Dialog Box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="212fb-106">Задание параметров на странице «Параметры»</span><span class="sxs-lookup"><span data-stu-id="212fb-106">Set the options on the Parameters page</span></span>](#parameter)  
  
-   [<span data-ttu-id="212fb-107">Задание параметров на странице «Ссылки»</span><span class="sxs-lookup"><span data-stu-id="212fb-107">Set the options on the References page</span></span>](#references)  
  
##  <a name="open-the-configure-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="212fb-108">Откройте диалоговое окно «Настройка».</span><span class="sxs-lookup"><span data-stu-id="212fb-108">Open the Configure Dialog Box</span></span>  
  
1.  <span data-ttu-id="212fb-109">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]установите соединение с сервером служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="212fb-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="212fb-110">Устанавливается соединение с экземпляром [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], в котором размещена база данных SSISDB.</span><span class="sxs-lookup"><span data-stu-id="212fb-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="212fb-111">В обозревателе объектов разверните дерево для отображения узла **Каталоги служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="212fb-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="212fb-112">Разверните узел **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="212fb-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="212fb-113">Разверните папку, содержащую проект или пакет, который требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="212fb-113">Expand the folder that contains the package or project that you want to configure.</span></span>  
  
5.  <span data-ttu-id="212fb-114">Щелкните правой кнопкой мыши пакет или проект и выберите пункт **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="212fb-114">Right-click the package or project, and then click **Configure**.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-page"></a><a name="parameter"></a> <span data-ttu-id="212fb-115">Задание параметров на странице «Параметры»</span><span class="sxs-lookup"><span data-stu-id="212fb-115">Set the options on the Parameters page</span></span>  
 <span data-ttu-id="212fb-116">Использование страницы **Параметры** для просмотра имен и значений параметров и для изменения значений.</span><span class="sxs-lookup"><span data-stu-id="212fb-116">Use the **Parameters** page to view parameter names and values, and to modify the values.</span></span>  
  
 <span data-ttu-id="212fb-117">Выберите область параметров, отображаемых на вкладках **Параметры** и **Диспетчеры соединений** в раскрывающемся списке **Область** .</span><span class="sxs-lookup"><span data-stu-id="212fb-117">Select the scope of the parameters displayed in the **Parameters** and **Connection Managers** tabs, in the **Scope** drop-down list.</span></span>  
  
 <span data-ttu-id="212fb-118">Ниже приведен список параметров на вкладке **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="212fb-118">The following is a list of the options in the **Parameters** tab.</span></span>  
  
 <span data-ttu-id="212fb-119">**Контейнер**</span><span class="sxs-lookup"><span data-stu-id="212fb-119">**Container**</span></span>  
 <span data-ttu-id="212fb-120">Выводит список объектов, содержащих параметр.</span><span class="sxs-lookup"><span data-stu-id="212fb-120">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="212fb-121">**имя**;</span><span class="sxs-lookup"><span data-stu-id="212fb-121">**Name**</span></span>  
 <span data-ttu-id="212fb-122">Выводит список имен параметра.</span><span class="sxs-lookup"><span data-stu-id="212fb-122">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="212fb-123">**Значение**</span><span class="sxs-lookup"><span data-stu-id="212fb-123">**Value**</span></span>  
 <span data-ttu-id="212fb-124">Выводит список значений параметра.</span><span class="sxs-lookup"><span data-stu-id="212fb-124">Lists the parameter value.</span></span> <span data-ttu-id="212fb-125">Нажмите кнопку с многоточием, чтобы изменить значение в диалоговом окне **Задание значения параметра** .</span><span class="sxs-lookup"><span data-stu-id="212fb-125">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span>  
  
 <span data-ttu-id="212fb-126">В следующем списке приведены параметры на вкладке **Диспетчеры соединений** . Используйте эту вкладку для изменения значений свойств диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="212fb-126">The following is a list of the options in the **Connection Managers** tab. You use this tab to change values for connection manager properties.</span></span> <span data-ttu-id="212fb-127">Для свойств автоматически создаются параметры на сервере служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="212fb-127">Parameters are automatically generated on the SSIS server for the properties.</span></span>  
  
 <span data-ttu-id="212fb-128">**Контейнер**</span><span class="sxs-lookup"><span data-stu-id="212fb-128">**Container**</span></span>  
 <span data-ttu-id="212fb-129">Выводит список объектов, содержащих диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="212fb-129">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="212fb-130">**имя**;</span><span class="sxs-lookup"><span data-stu-id="212fb-130">**Name**</span></span>  
 <span data-ttu-id="212fb-131">Выводит список имен диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="212fb-131">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="212fb-132">**Имя свойства**</span><span class="sxs-lookup"><span data-stu-id="212fb-132">**Property name**</span></span>  
 <span data-ttu-id="212fb-133">Выводит список названий свойств диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="212fb-133">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="212fb-134">**Значение**</span><span class="sxs-lookup"><span data-stu-id="212fb-134">**Value**</span></span>  
 <span data-ttu-id="212fb-135">Выводит список значений, присвоенных свойствам диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="212fb-135">Lists the value assigned to the connection manager property.</span></span> <span data-ttu-id="212fb-136">Нажмите кнопку с многоточием, чтобы изменить значение в диалоговом окне **Задание значения параметра** .</span><span class="sxs-lookup"><span data-stu-id="212fb-136">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span> <span data-ttu-id="212fb-137">Можно ввести литеральное значение, сопоставить переменную среды, содержащую необходимое значение, или использовать значение по умолчанию из пакета.</span><span class="sxs-lookup"><span data-stu-id="212fb-137">You can enter a literal value, map an environment variable that contains the value you want to use, or use the default value from the package.</span></span>  
  
##  <a name="set-the-options-on-the-references-page"></a><a name="references"></a> <span data-ttu-id="212fb-138">Задание параметров на странице «Ссылки»</span><span class="sxs-lookup"><span data-stu-id="212fb-138">Set the options on the References page</span></span>  
 <span data-ttu-id="212fb-139">Используйте страницу **Ссылки** , чтобы добавлять и удалять ссылки на среды, а также для доступа к свойствам среды.</span><span class="sxs-lookup"><span data-stu-id="212fb-139">Use the **References** page to add and remove references to environments, and to access environment properties.</span></span>  
  
 <span data-ttu-id="212fb-140">Среда указывает значения времени выполнения для пакетов, содержащихся в проектах, которые развернуты на сервере служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="212fb-140">An environment specifies runtime values for packages contained in the projects you've deployed to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="212fb-141">**Среда**</span><span class="sxs-lookup"><span data-stu-id="212fb-141">**Environment**</span></span>  
 <span data-ttu-id="212fb-142">Перечисляет среду.</span><span class="sxs-lookup"><span data-stu-id="212fb-142">Lists the environment.</span></span>  
  
 <span data-ttu-id="212fb-143">**Папка среды**</span><span class="sxs-lookup"><span data-stu-id="212fb-143">**Environment Folder**</span></span>  
 <span data-ttu-id="212fb-144">Выводит имя папки, которая содержит среду.</span><span class="sxs-lookup"><span data-stu-id="212fb-144">Lists the folder that contains the environment.</span></span>  
  
 <span data-ttu-id="212fb-145">**Открыть**</span><span class="sxs-lookup"><span data-stu-id="212fb-145">**Open**</span></span>  
 <span data-ttu-id="212fb-146">Нажмите, чтобы открыть диалоговое окно **Свойства среды** .</span><span class="sxs-lookup"><span data-stu-id="212fb-146">Click to open the **Environment Properties** dialog box.</span></span>  
  
 <span data-ttu-id="212fb-147">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="212fb-147">**Add**</span></span>  
 <span data-ttu-id="212fb-148">Нажмите, чтобы добавить ссылку к среде.</span><span class="sxs-lookup"><span data-stu-id="212fb-148">Click to add a reference to an environment.</span></span> <span data-ttu-id="212fb-149">В диалоговом окне **Выбор среды** выберите среду и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="212fb-149">In the **Browse Environments** dialog box click an environment and then click **OK**.</span></span>  
  
 <span data-ttu-id="212fb-150">Вы можете выбрать среду, содержащуюся в любой папке проекта, под узлом **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="212fb-150">You can select an environment contained in any project folder under the **SSISDB** node.</span></span>  
  
 <span data-ttu-id="212fb-151">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="212fb-151">**Remove**</span></span>  
 <span data-ttu-id="212fb-152">Выберите среду, перечисленную в области **Ссылки** , а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="212fb-152">Click an environment listed in the **References** area, and then click **Remove**.</span></span>  
  
  
