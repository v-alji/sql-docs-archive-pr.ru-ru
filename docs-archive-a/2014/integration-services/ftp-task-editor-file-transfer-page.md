---
title: Редактор задачи «FTP» (страница «Перемещение файлов») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.filetransfer.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 37e52220-feb2-474c-ad88-fa1b1059acd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8094051e93c4165be6ae186bde394f9271d60669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657160"
---
# <a name="ftp-task-editor-file-transfer-page"></a><span data-ttu-id="a17fe-102">Редактор задачи «FTP» (страница «Передача файлов»)</span><span class="sxs-lookup"><span data-stu-id="a17fe-102">FTP Task Editor (File Transfer Page)</span></span>
  <span data-ttu-id="a17fe-103">Страница **Передача файлов** диалогового окна **Редактор задачи «FTP»** используется для настройки операции FTP, выполняемой задачей.</span><span class="sxs-lookup"><span data-stu-id="a17fe-103">Use the **File Transfer** page of the **FTP Task Editor** dialog box to configure the FTP operation that the task performs.</span></span>  
  
 <span data-ttu-id="a17fe-104">Дополнительные сведения об этой задаче см. в разделе [Задача FTP](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="a17fe-104">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a17fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a17fe-105">Options</span></span>  
 <span data-ttu-id="a17fe-106">**IsRemotePathVariable**</span><span class="sxs-lookup"><span data-stu-id="a17fe-106">**IsRemotePathVariable**</span></span>  
 <span data-ttu-id="a17fe-107">Укажите, хранится ли удаленный путь в переменной.</span><span class="sxs-lookup"><span data-stu-id="a17fe-107">Indicate whether the remote path is stored in a variable.</span></span> <span data-ttu-id="a17fe-108">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a17fe-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="a17fe-109">Значение</span><span class="sxs-lookup"><span data-stu-id="a17fe-109">Value</span></span>|<span data-ttu-id="a17fe-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a17fe-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a17fe-111">**True**</span><span class="sxs-lookup"><span data-stu-id="a17fe-111">**True**</span></span>|<span data-ttu-id="a17fe-112">Целевой путь хранится в переменной.</span><span class="sxs-lookup"><span data-stu-id="a17fe-112">The destination path is stored in a variable.</span></span> <span data-ttu-id="a17fe-113">Выбор этого значения отображает динамический параметр **RemoteVariable**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-113">Selecting the value displays the dynamic option, **RemoteVariable**.</span></span>|  
|<span data-ttu-id="a17fe-114">**False**</span><span class="sxs-lookup"><span data-stu-id="a17fe-114">**False**</span></span>|<span data-ttu-id="a17fe-115">Целевой путь задается в диспетчере подключения файлов.</span><span class="sxs-lookup"><span data-stu-id="a17fe-115">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="a17fe-116">Выбор этого значения отображает динамический параметр **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-116">Selecting the value displays the dynamic option, **RemotePath**.</span></span>|  
  
 <span data-ttu-id="a17fe-117">**OverwriteFileAtDestination**</span><span class="sxs-lookup"><span data-stu-id="a17fe-117">**OverwriteFileAtDestination**</span></span>  
 <span data-ttu-id="a17fe-118">Задайте, можно ли заменять файл в месте назначения.</span><span class="sxs-lookup"><span data-stu-id="a17fe-118">Specify whether a file at the destination can be overwritten.</span></span>  
  
 <span data-ttu-id="a17fe-119">**IsLocalPathVariable**</span><span class="sxs-lookup"><span data-stu-id="a17fe-119">**IsLocalPathVariable**</span></span>  
 <span data-ttu-id="a17fe-120">Укажите, хранится ли локальный путь в переменной.</span><span class="sxs-lookup"><span data-stu-id="a17fe-120">Indicate whether the local path is stored in a variable.</span></span> <span data-ttu-id="a17fe-121">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a17fe-121">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="a17fe-122">Значение</span><span class="sxs-lookup"><span data-stu-id="a17fe-122">Value</span></span>|<span data-ttu-id="a17fe-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a17fe-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a17fe-124">**True**</span><span class="sxs-lookup"><span data-stu-id="a17fe-124">**True**</span></span>|<span data-ttu-id="a17fe-125">Целевой путь хранится в переменной.</span><span class="sxs-lookup"><span data-stu-id="a17fe-125">The destination path is stored in a variable.</span></span> <span data-ttu-id="a17fe-126">Выбор этого значения отображает динамический параметр **LocalVariable**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-126">Selecting the value displays the dynamic option, **LocalVariable**.</span></span>|  
|<span data-ttu-id="a17fe-127">**False**</span><span class="sxs-lookup"><span data-stu-id="a17fe-127">**False**</span></span>|<span data-ttu-id="a17fe-128">Целевой путь задается в диспетчере подключения файлов.</span><span class="sxs-lookup"><span data-stu-id="a17fe-128">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="a17fe-129">Выбор этого значения отображает динамический параметр **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-129">Selecting the value displays the dynamic option, **LocalPath**.</span></span>|  
  
 <span data-ttu-id="a17fe-130">**Операция**</span><span class="sxs-lookup"><span data-stu-id="a17fe-130">**Operation**</span></span>  
 <span data-ttu-id="a17fe-131">Выберите операцию протокола FTP для выполнения.</span><span class="sxs-lookup"><span data-stu-id="a17fe-131">Select the FTP operation to perform.</span></span> <span data-ttu-id="a17fe-132">Это свойство имеет параметры, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a17fe-132">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="a17fe-133">Значение</span><span class="sxs-lookup"><span data-stu-id="a17fe-133">Value</span></span>|<span data-ttu-id="a17fe-134">Описание</span><span class="sxs-lookup"><span data-stu-id="a17fe-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a17fe-135">**Отправить файлы**</span><span class="sxs-lookup"><span data-stu-id="a17fe-135">**Send files**</span></span>|<span data-ttu-id="a17fe-136">Отправляет файлы.</span><span class="sxs-lookup"><span data-stu-id="a17fe-136">Send files.</span></span> <span data-ttu-id="a17fe-137">При выборе этого значения выводятся динамические параметры **LocalVariable**, **LocalPathRemoteVariable** и **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-137">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="a17fe-138">**Получить файлы**</span><span class="sxs-lookup"><span data-stu-id="a17fe-138">**Receive files**</span></span>|<span data-ttu-id="a17fe-139">Получает файлы.</span><span class="sxs-lookup"><span data-stu-id="a17fe-139">Receive files.</span></span> <span data-ttu-id="a17fe-140">При выборе этого значения выводятся динамические параметры **LocalVariable**, **LocalPathRemoteVariable** и **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-140">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="a17fe-141">**Создать локальный каталог**</span><span class="sxs-lookup"><span data-stu-id="a17fe-141">**Create local directory**</span></span>|<span data-ttu-id="a17fe-142">Создает локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="a17fe-142">Create a local directory.</span></span> <span data-ttu-id="a17fe-143">При выборе этого значения выводятся динамические параметры **LocalVariable** и **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-143">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="a17fe-144">**Создать удаленный каталог**</span><span class="sxs-lookup"><span data-stu-id="a17fe-144">**Create remote directory**</span></span>|<span data-ttu-id="a17fe-145">Создает удаленный каталог.</span><span class="sxs-lookup"><span data-stu-id="a17fe-145">Create a remote directory.</span></span> <span data-ttu-id="a17fe-146">При выборе этого значения выводятся динамические параметры **RemoteVariable** и **RemoteIPath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-146">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotelPath**.</span></span>|  
|<span data-ttu-id="a17fe-147">**Удалить локальный каталог**</span><span class="sxs-lookup"><span data-stu-id="a17fe-147">**Remove local directory**</span></span>|<span data-ttu-id="a17fe-148">Удаляет локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="a17fe-148">Removes a local directory.</span></span> <span data-ttu-id="a17fe-149">При выборе этого значения выводятся динамические параметры **LocalVariable** и **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-149">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="a17fe-150">**Удалить удаленный каталог**</span><span class="sxs-lookup"><span data-stu-id="a17fe-150">**Remove remote directory**</span></span>|<span data-ttu-id="a17fe-151">Удаляет удаленный каталог.</span><span class="sxs-lookup"><span data-stu-id="a17fe-151">Remove a remote directory.</span></span> <span data-ttu-id="a17fe-152">При выборе этого значения выводятся динамические параметры **RemoteVariable** и **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-152">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="a17fe-153">**Удалить локальные файлы**</span><span class="sxs-lookup"><span data-stu-id="a17fe-153">**Delete local files**</span></span>|<span data-ttu-id="a17fe-154">Удаляет локальные файлы.</span><span class="sxs-lookup"><span data-stu-id="a17fe-154">Delete local files.</span></span> <span data-ttu-id="a17fe-155">При выборе этого значения выводятся динамические параметры **LocalVariable** и **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-155">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="a17fe-156">**Удалить удаленные файлы**</span><span class="sxs-lookup"><span data-stu-id="a17fe-156">**Delete remote files**</span></span>|<span data-ttu-id="a17fe-157">Удаляет удаленные файлы.</span><span class="sxs-lookup"><span data-stu-id="a17fe-157">Delete remote files.</span></span> <span data-ttu-id="a17fe-158">При выборе этого значения выводятся динамические параметры **RemoteVariable** и **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="a17fe-158">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
  
 <span data-ttu-id="a17fe-159">**IsTransferASCII**</span><span class="sxs-lookup"><span data-stu-id="a17fe-159">**IsTransferASCII**</span></span>  
 <span data-ttu-id="a17fe-160">Укажите, должны ли файлы, передаваемые на и с удаленного FTP-сервера, передаваться в режиме ASCII.</span><span class="sxs-lookup"><span data-stu-id="a17fe-160">Indicate whether files transferred to and from the remote FTP server should be transferred in ASCII mode.</span></span>  
  
## <a name="isremotepathvariable-dynamic-options"></a><span data-ttu-id="a17fe-161">Динамические параметры IsRemotePathVariable</span><span class="sxs-lookup"><span data-stu-id="a17fe-161">IsRemotePathVariable Dynamic Options</span></span>  
  
### <a name="isremotepathvariable--true"></a><span data-ttu-id="a17fe-162">IsRemotePathVariable = True</span><span class="sxs-lookup"><span data-stu-id="a17fe-162">IsRemotePathVariable = True</span></span>  
 <span data-ttu-id="a17fe-163">**RemoteVariable**</span><span class="sxs-lookup"><span data-stu-id="a17fe-163">**RemoteVariable**</span></span>  
 <span data-ttu-id="a17fe-164">Выберите существующую переменную, определяемую пользователем, или выберите пункт \<**New variable...**> для ее создания.</span><span class="sxs-lookup"><span data-stu-id="a17fe-164">Select an existing user-defined variable, or click \<**New variable...**> to create a user-defined variable.</span></span>  
  
 <span data-ttu-id="a17fe-165">**См. также:** [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), "Добавление переменной"</span><span class="sxs-lookup"><span data-stu-id="a17fe-165">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="isremotepathvariable--false"></a><span data-ttu-id="a17fe-166">IsRemotePathVariable = False</span><span class="sxs-lookup"><span data-stu-id="a17fe-166">IsRemotePathVariable = False</span></span>  
 <span data-ttu-id="a17fe-167">**RemotePath**</span><span class="sxs-lookup"><span data-stu-id="a17fe-167">**RemotePath**</span></span>  
 <span data-ttu-id="a17fe-168">Выберите существующий диспетчер подключений FTP или создайте его, щелкнув пункт \<**New connection...**>.</span><span class="sxs-lookup"><span data-stu-id="a17fe-168">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="a17fe-169">**См. также:** [Диспетчер FTP-сеансов](connection-manager/ftp-connection-manager.md), [Редактор диспетчера FTP-сеансов](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="a17fe-169">**Related Topics:** [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
## <a name="islocalpathvariable-dynamic-options"></a><span data-ttu-id="a17fe-170">Динамические параметры IsLocalPathVariable</span><span class="sxs-lookup"><span data-stu-id="a17fe-170">IsLocalPathVariable Dynamic Options</span></span>  
  
### <a name="islocalpathvariable--true"></a><span data-ttu-id="a17fe-171">IsLocalPathVariable = True</span><span class="sxs-lookup"><span data-stu-id="a17fe-171">IsLocalPathVariable = True</span></span>  
 <span data-ttu-id="a17fe-172">**LocalVariable**</span><span class="sxs-lookup"><span data-stu-id="a17fe-172">**LocalVariable**</span></span>  
 <span data-ttu-id="a17fe-173">Выберите существующую переменную, определяемую пользователем, или выберите пункт \<**New variable...**> для создания переменной.</span><span class="sxs-lookup"><span data-stu-id="a17fe-173">Select an existing user-defined variable, or click \<**New variable...**> to create a variable.</span></span>  
  
 <span data-ttu-id="a17fe-174">**См. также:** [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md), "Добавление переменной"</span><span class="sxs-lookup"><span data-stu-id="a17fe-174">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="islocalpathvariable--false"></a><span data-ttu-id="a17fe-175">IsLocalPathVariable = False</span><span class="sxs-lookup"><span data-stu-id="a17fe-175">IsLocalPathVariable = False</span></span>  
 <span data-ttu-id="a17fe-176">**LocalPath**</span><span class="sxs-lookup"><span data-stu-id="a17fe-176">**LocalPath**</span></span>  
 <span data-ttu-id="a17fe-177">Выберите существующий диспетчер подключений файлов или создайте его, щелкнув пункт \<**New connection...**>.</span><span class="sxs-lookup"><span data-stu-id="a17fe-177">Select an existing File connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="a17fe-178">**См. также**: [Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="a17fe-178">**Related Topics**: [Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a17fe-179">См. также:</span><span class="sxs-lookup"><span data-stu-id="a17fe-179">See Also</span></span>  
 <span data-ttu-id="a17fe-180">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a17fe-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a17fe-181">[Редактор задачи "FTP" &#40;страница "Общие"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a17fe-181">[FTP Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="a17fe-182">Страница «Выражения»</span><span class="sxs-lookup"><span data-stu-id="a17fe-182">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
