---
title: Редактор задачи "выполнение пакета" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executepackagetask.parameter.F1
- sql12.dts.designer.executepackagetask.package.f1
- sql12.dts.designer.executepackagetask.general.f1
ms.assetid: c2c96b4f-eb10-4d8b-be34-88edfd0785fb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9b2e18516e1f5c1b7af56bd1e84ef875557fd49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665012"
---
# <a name="execute-package-task-editor"></a><span data-ttu-id="bd0bc-102">редактор задачи «Выполнение пакета»</span><span class="sxs-lookup"><span data-stu-id="bd0bc-102">Execute Package Task Editor</span></span>
  <span data-ttu-id="bd0bc-103">Для настройки задачи «Выполнение пакета» используйте редактор задачи «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="bd0bc-103">Use the Execute Package Task Editor to configure the Execute Package Task.</span></span> <span data-ttu-id="bd0bc-104">Задача «Выполнение пакета» расширяет возможности служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в рамках организации, позволяя одним пакетам выполнять другие пакеты как часть рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-104">The Execute Package task extends the enterprise capabilities of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by letting packages run other packages as part of a workflow.</span></span>  
  
 <span data-ttu-id="bd0bc-105">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="bd0bc-106">Открытие редактора задачи «Выполнение пакета»</span><span class="sxs-lookup"><span data-stu-id="bd0bc-106">Open the Execute Package Task Editor</span></span>](#open)  
  
-   [<span data-ttu-id="bd0bc-107">Задание параметров на странице «Общие»</span><span class="sxs-lookup"><span data-stu-id="bd0bc-107">Set the Options on the General Page</span></span>](#general)  
  
-   [<span data-ttu-id="bd0bc-108">Задание параметров на странице «Пакет»</span><span class="sxs-lookup"><span data-stu-id="bd0bc-108">Set the Options on the Package Page</span></span>](#package)  
  
-   [<span data-ttu-id="bd0bc-109">Задание параметров на странице «Привязки параметров»</span><span class="sxs-lookup"><span data-stu-id="bd0bc-109">Set the Options on the Parameter Bindings Page</span></span>](#parameter)  
  
##  <a name="open-the-execute-package-task-editor"></a><a name="open"></a> <span data-ttu-id="bd0bc-110">Открытие редактора задачи «Выполнение пакета»</span><span class="sxs-lookup"><span data-stu-id="bd0bc-110">Open the Execute Package Task Editor</span></span>  
  
1.  <span data-ttu-id="bd0bc-111">Откройте в среде [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] проект служб [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , содержащий задачу «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="bd0bc-111">Open an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] that contains an Execute Package task.</span></span>  
  
2.  <span data-ttu-id="bd0bc-112">Щелкните правой кнопкой задание в конструкторе служб SSIS и выберите пункт **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-112">Right-click the task in the SSIS Designer, and then click **Edit**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="bd0bc-113">Задание параметров на странице «Общие»</span><span class="sxs-lookup"><span data-stu-id="bd0bc-113">Set the Options on the General Page</span></span>  
 <span data-ttu-id="bd0bc-114">**имя**;</span><span class="sxs-lookup"><span data-stu-id="bd0bc-114">**Name**</span></span>  
 <span data-ttu-id="bd0bc-115">Укажите уникальное имя для задачи «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="bd0bc-115">Provide a unique name for the Execute Package task.</span></span> <span data-ttu-id="bd0bc-116">Это имя используется в качестве метки для значка задачи.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd0bc-117">Имена задач в пределах пакета должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="bd0bc-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-118">**Description**</span></span>  
 <span data-ttu-id="bd0bc-119">Введите описание для задачи «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="bd0bc-119">Type a description of the Execute Package task.</span></span>  
  
##  <a name="set-the-options-on-the-package-page"></a><a name="package"></a> <span data-ttu-id="bd0bc-120">Задание параметров на странице «Пакет»</span><span class="sxs-lookup"><span data-stu-id="bd0bc-120">Set the Options on the Package Page</span></span>  
 <span data-ttu-id="bd0bc-121">**Тип ссылки**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-121">**ReferenceType**</span></span>  
 <span data-ttu-id="bd0bc-122">Выберите пункт меню **Ссылка на проект** для дочерних пакетов, содержащихся в проекте.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-122">Select **Project Reference** for child packages that are in the project.</span></span> <span data-ttu-id="bd0bc-123">Выберите пункт меню **Внешняя ссылка** для дочерних пакетов, расположенных вне проекта.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-123">Select **External Reference** for child packages that are located outside the package</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd0bc-124">Если проект, в котором содержится пакет, не был преобразован в модель развертывания проекта, то параметр **Тип ссылки** доступен только для чтения и принимает значение **Внешняя ссылка** .</span><span class="sxs-lookup"><span data-stu-id="bd0bc-124">The **ReferenceType** option is ready-only and set to **External Reference** if the project that contains the package has not been converted to the project deployment model.</span></span> <span data-ttu-id="bd0bc-125">Дополнительные сведения о преобразовании см. в разделе [Развертывание проектов на сервере служб Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd0bc-125">For more information about conversion, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="bd0bc-126">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-126">**Password**</span></span>  
 <span data-ttu-id="bd0bc-127">Если дочерний пакет защищен паролем, введите пароль для него или нажмите кнопку с многоточием (...) и создайте новый пароль для данного дочернего пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-127">If the child package is password protected, provide the password for the child package, or click the ellipsis button (...) and create a new password for the child package.</span></span>  
  
 `ExecuteOutOfProcess`  
 <span data-ttu-id="bd0bc-128">Укажите, должен дочерний пакет выполняться в процессе родительского пакета или в отдельном процессе.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-128">Specify whether the child package runs in the process of the parent package or in a separate process.</span></span> <span data-ttu-id="bd0bc-129">По умолчанию свойство параметр ExecuteOutOfProcess задачи «Выполнение пакета» имеет значение `False` , а дочерний пакет выполняется в том же процессе, что и родительский пакет.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-129">By default, the ExecuteOutOfProcess property of the Execute Package task is set to `False`, and the child package runs in the same process as the parent package.</span></span> <span data-ttu-id="bd0bc-130">Если установить свойство в значение `true`, дочерний пакет запускается в отдельном процессе.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-130">If you set this property to `true`, the child package runs in a separate process.</span></span> <span data-ttu-id="bd0bc-131">Это может замедлить запуск дочернего пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-131">This may slow down the launching of the child package.</span></span> <span data-ttu-id="bd0bc-132">Кроме того, если свойству задано значение `true`, то выполнять отладку пакета только при установке средств нельзя. Для этого необходимо установить продукт службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd0bc-132">In addition, if set the property to `true`, you cannot debug the package in a tools-only install; you must install the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] product.</span></span> <span data-ttu-id="bd0bc-133">Дополнительные сведения см. в статье [Установка служб Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="bd0bc-133">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
### <a name="referencetype-dynamic-options"></a><span data-ttu-id="bd0bc-134">Динамические параметры ReferenceType</span><span class="sxs-lookup"><span data-stu-id="bd0bc-134">ReferenceType Dynamic Options</span></span>  
  
#### <a name="referencetype--external-reference"></a><span data-ttu-id="bd0bc-135">ReferenceType = внешняя ссылка</span><span class="sxs-lookup"><span data-stu-id="bd0bc-135">ReferenceType = External Reference</span></span>  
 <span data-ttu-id="bd0bc-136">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-136">**Location**</span></span>  
 <span data-ttu-id="bd0bc-137">Выберите местоположение дочернего пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-137">Select the location of the child package.</span></span> <span data-ttu-id="bd0bc-138">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-138">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="bd0bc-139">Значение</span><span class="sxs-lookup"><span data-stu-id="bd0bc-139">Value</span></span>|<span data-ttu-id="bd0bc-140">Описание</span><span class="sxs-lookup"><span data-stu-id="bd0bc-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd0bc-141">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-141">**SQL Server**</span></span>|<span data-ttu-id="bd0bc-142">Установите местонахождение экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd0bc-142">Set the location to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="bd0bc-143">**Файловая система**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-143">**File system**</span></span>|<span data-ttu-id="bd0bc-144">Указывает, что местоположение находится в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-144">Set the location to the file system.</span></span>|  
  
 <span data-ttu-id="bd0bc-145">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-145">**Connection**</span></span>  
 <span data-ttu-id="bd0bc-146">Выберите тип места хранения дочернего пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-146">Select the type of storage location for the child package.</span></span>  
  
 <span data-ttu-id="bd0bc-147">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-147">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="bd0bc-148">Отображает имя пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-148">Displays the package name.</span></span>  
  
#### <a name="referencetype--project-reference"></a><span data-ttu-id="bd0bc-149">ReferenceType = ссылка на проект</span><span class="sxs-lookup"><span data-stu-id="bd0bc-149">ReferenceType = Project Reference</span></span>  
 <span data-ttu-id="bd0bc-150">**PackageNameFromProjectReference**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-150">**PackageNameFromProjectReference**</span></span>  
 <span data-ttu-id="bd0bc-151">Выберите пакет, содержащийся в проекте, который станет дочерним пакетом.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-151">Select a package contained in the project, to be the child package.</span></span>  
  
### <a name="location-dynamic-options"></a><span data-ttu-id="bd0bc-152">Динамические параметры местоположения</span><span class="sxs-lookup"><span data-stu-id="bd0bc-152">Location Dynamic Options</span></span>  
  
#### <a name="location--sql-server"></a><span data-ttu-id="bd0bc-153">Местонахождение = SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd0bc-153">Location = SQL Server</span></span>  
 <span data-ttu-id="bd0bc-154">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-154">**Connection**</span></span>  
 <span data-ttu-id="bd0bc-155">Выберите в списке диспетчер подключений OLE DB или щелкните \<**New connection...**>, чтобы создать диспетчер подключений.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-155">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="bd0bc-156">**См. также:** [Диспетчер подключений OLE DB](connection-manager/ole-db-connection-manager.md), [Настройка диспетчера подключений OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="bd0bc-156">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="bd0bc-157">**PackageName**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-157">**PackageName**</span></span>  
 <span data-ttu-id="bd0bc-158">Введите имя дочернего пакета или нажмите кнопку с многоточием (...) и определите местоположение пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-158">Type the name of the child package, or click the ellipsis (...) and then locate the package.</span></span>  
  
#### <a name="location--file-system"></a><span data-ttu-id="bd0bc-159">Местоположение = файловая система</span><span class="sxs-lookup"><span data-stu-id="bd0bc-159">Location = File system</span></span>  
 <span data-ttu-id="bd0bc-160">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-160">**Connection**</span></span>  
 <span data-ttu-id="bd0bc-161">Выберите в списке диспетчер подключений файлов или щелкните \<**New connection...**>, чтобы создать диспетчер подключений.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-161">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="bd0bc-162">**См. также:** подробные сведения о [диспетчере файловых подключений](connection-manager/file-connection-manager.md) и о [редакторе диспетчера файловых подключений](../../2014/integration-services/file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="bd0bc-162">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="bd0bc-163">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-163">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="bd0bc-164">Отображает имя пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-164">Displays the package name.</span></span>  
  
##  <a name="set-the-options-on-the-parameter-bindings-page"></a><a name="parameter"></a> <span data-ttu-id="bd0bc-165">Задание параметров на странице «Привязки параметров»</span><span class="sxs-lookup"><span data-stu-id="bd0bc-165">Set the Options on the Parameter Bindings Page</span></span>  
 <span data-ttu-id="bd0bc-166">Из родительского пакета или проекта можно передавать значения в дочерний пакет.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-166">You can pass values from the parent package or the project, to the child package.</span></span> <span data-ttu-id="bd0bc-167">Проект должен использовать модель развертывания проекта, а дочерний пакет должен содержаться в одном проекте с родительским пакетом.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-167">The project must use the project deployment model and the child package must be contained in the same project that contains the parent package.</span></span>  
  
 <span data-ttu-id="bd0bc-168">Сведения о преобразовании проектов в модели развертывания проектов см. в разделе [Развертывание проектов на сервере служб Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="bd0bc-168">For information about converting projects to the project deployment model, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="bd0bc-169">**Параметр дочернего проекта**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-169">**Child package parameter**</span></span>  
 <span data-ttu-id="bd0bc-170">Введите или выберите имя параметра дочернего пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-170">Enter or select a name for the child package parameter.</span></span>  
  
 <span data-ttu-id="bd0bc-171">**Параметр привязки или переменная**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-171">**Binding parameter or variable**</span></span>  
 <span data-ttu-id="bd0bc-172">Выберите параметр или переменную, содержащие значение, которое необходимо передать в дочерний пакет.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-172">Select the parameter or variable that contains the value that you want to pass to the child package.</span></span>  
  
 <span data-ttu-id="bd0bc-173">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-173">**Add**</span></span>  
 <span data-ttu-id="bd0bc-174">Нажмите, чтобы сопоставить параметр или переменную с параметром дочернего пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-174">Click to map a parameter or variable to a child package parameter.</span></span>  
  
 <span data-ttu-id="bd0bc-175">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="bd0bc-175">**Remove**</span></span>  
 <span data-ttu-id="bd0bc-176">Нажмите, чтобы удалить сопоставление параметра или переменной с параметром дочернего пакета.</span><span class="sxs-lookup"><span data-stu-id="bd0bc-176">Click to remove a mapping between a parameter or variable and a child package parameter.</span></span>  
  
  
