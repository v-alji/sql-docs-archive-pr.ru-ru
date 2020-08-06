---
title: Редактор задачи «перемещение базы данных» (страница «базы данных») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.database.f1
helpviewer_keywords:
- Transfer Database Task Editor
ms.assetid: ccdb74d0-4bea-420c-a726-2e0eb8957e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df4452e28a32463a7825e9c64cfd053f98c53ee8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727282"
---
# <a name="transfer-database-task-editor-databases-page"></a><span data-ttu-id="84f8c-102">Редактор задачи «Передача базы данных» (страница «Базы данных»)</span><span class="sxs-lookup"><span data-stu-id="84f8c-102">Transfer Database Task Editor (Databases Page)</span></span>
  <span data-ttu-id="84f8c-103">Используйте страницу **Базы данных** в диалоговом окне **Редактор задачи «Передача базы данных»** , чтобы указать свойства для базы данных-источника и целевой базы данных, участвующих в задаче «Передача базы данных».</span><span class="sxs-lookup"><span data-stu-id="84f8c-103">Use the **Databases** page of the **Transfer Database Task Editor** dialog box to specify properties for the source and destination databases involved in the Transfer Database task.</span></span> <span data-ttu-id="84f8c-104">Задача «Передача базы данных» копирует или перемещает базу данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] между двумя экземплярами [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84f8c-104">The Transfer Database task copies or moves a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database between two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="84f8c-105">Эту задачу можно также использовать для копирования базы данных в пределах того же сервера.</span><span class="sxs-lookup"><span data-stu-id="84f8c-105">This task can also be used to copy a database within the same server.</span></span> <span data-ttu-id="84f8c-106">Дополнительные сведения об этой задаче см. в разделе [Задача "Передача базы данных"](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="84f8c-106">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="84f8c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="84f8c-107">Options</span></span>  
 <span data-ttu-id="84f8c-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="84f8c-108">**SourceConnection**</span></span>  
 <span data-ttu-id="84f8c-109">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к исходному серверу.</span><span class="sxs-lookup"><span data-stu-id="84f8c-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="84f8c-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="84f8c-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="84f8c-111">Выберите из списка диспетчер подключений SMO или нажмите кнопку **\<New connection...>** , чтобы создать новое подключение к целевому серверу.</span><span class="sxs-lookup"><span data-stu-id="84f8c-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="84f8c-112">**DestinationDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="84f8c-112">**DestinationDatabaseName**</span></span>  
 <span data-ttu-id="84f8c-113">Укажите имя базы данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="84f8c-113">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database on the destination server.</span></span>  
  
 <span data-ttu-id="84f8c-114">Чтобы автоматически заполнить это поле именем базы данных-источника, укажите сначала **SourceConnection** и **SourceDatabaseName** .</span><span class="sxs-lookup"><span data-stu-id="84f8c-114">To automatically populate this field with the source database name, specify the **SourceConnection** and **SourceDatabaseName** first.</span></span>  
  
 <span data-ttu-id="84f8c-115">Чтобы переименовать базу данных на целевом сервере, введите новое имя в этом поле.</span><span class="sxs-lookup"><span data-stu-id="84f8c-115">To rename the database on the destination server, type the new name in this field.</span></span>  
  
 <span data-ttu-id="84f8c-116">**DestinationDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="84f8c-116">**DestinationDatabaseFiles**</span></span>  
 <span data-ttu-id="84f8c-117">Указывает имена и местоположения файлов базы данных на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="84f8c-117">Specifies the names and locations of the database files on the destination server.</span></span>  
  
 <span data-ttu-id="84f8c-118">Чтобы автоматически заполнить это поле именами и местоположениями файлов базы данных-источника, укажите сначала **SourceConnection**, **SourceDatabaseName**и **SourceDatabaseFiles** .</span><span class="sxs-lookup"><span data-stu-id="84f8c-118">To automatically populate this field with the source database file names and locations, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first.</span></span>  
  
 <span data-ttu-id="84f8c-119">Чтобы переименовать файлы базы данных или указать новые местоположения на целевом сервере, заполните это поле сведениями о базе данных-источнике, а затем нажмите кнопку обзора.</span><span class="sxs-lookup"><span data-stu-id="84f8c-119">To rename the database files or to specify the new locations on the destination server, populate this field with the source database information, and then click the browse button.</span></span> <span data-ttu-id="84f8c-120">В диалоговом окне **Файлы целевой базы данных** измените пункты **Файл назначения**, **Целевая папка**или **Сетевая общая папка**.</span><span class="sxs-lookup"><span data-stu-id="84f8c-120">In the **Destination database files** dialog box, edit the **Destination File**, **Destination Folder**, or **Network File Share**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84f8c-121">В случае выбора файлов базы данных с помощью кнопки обзора расположение файла вводится с использованием обозначения локального диска, например c:\\.</span><span class="sxs-lookup"><span data-stu-id="84f8c-121">If you locate the database files by using the browse button, the file location is entered using the local drive notation: for example, c:\\.</span></span> <span data-ttu-id="84f8c-122">Необходимо заменить это значение на путь к сетевому ресурсу, в который входит имя компьютера и имя общей папки.</span><span class="sxs-lookup"><span data-stu-id="84f8c-122">You must replace this with the network share notation, including the computer name and share name.</span></span> <span data-ttu-id="84f8c-123">Если используется административная общая папка по умолчанию, необходимо использовать обозначение с символом $ и иметь административный доступ к общей папке.</span><span class="sxs-lookup"><span data-stu-id="84f8c-123">If the default administrative share is used, you must use the $ notation, and have administrative access to the share.</span></span>  
  
 <span data-ttu-id="84f8c-124">**DestinationOverwrite**</span><span class="sxs-lookup"><span data-stu-id="84f8c-124">**DestinationOverwrite**</span></span>  
 <span data-ttu-id="84f8c-125">Укажите, может ли база данных на целевом сервере быть перезаписана.</span><span class="sxs-lookup"><span data-stu-id="84f8c-125">Specify whether the database on the destination server can be overwritten.</span></span>  
  
 <span data-ttu-id="84f8c-126">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="84f8c-126">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="84f8c-127">Значение</span><span class="sxs-lookup"><span data-stu-id="84f8c-127">Value</span></span>|<span data-ttu-id="84f8c-128">Описание</span><span class="sxs-lookup"><span data-stu-id="84f8c-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="84f8c-129">**True**</span><span class="sxs-lookup"><span data-stu-id="84f8c-129">**True**</span></span>|<span data-ttu-id="84f8c-130">Перезаписать базу данных целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="84f8c-130">Overwrite destination server database.</span></span>|  
|<span data-ttu-id="84f8c-131">**False**</span><span class="sxs-lookup"><span data-stu-id="84f8c-131">**False**</span></span>|<span data-ttu-id="84f8c-132">Не перезаписывать базу данных целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="84f8c-132">Do not overwrite destination server database.</span></span>|  
  
> [!CAUTION]  
>  <span data-ttu-id="84f8c-133">Данные в базе данных целевого сервера будут перезаписаны, если для параметра **DestinationOverwrite** будет указано значение **True**, что может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="84f8c-133">The data in the destination server database will be overwritten if you specify **True** for **DestinationOverwrite**, which may result in data loss.</span></span> <span data-ttu-id="84f8c-134">Чтобы избежать этого, создайте резервную копию базы данных целевого сервера в другом местоположении, прежде чем приступить к выполнению задачи «Передача базы данных».</span><span class="sxs-lookup"><span data-stu-id="84f8c-134">To avoid this, back up the destination server database to another location before executing the Transfer Database task.</span></span>  
  
 <span data-ttu-id="84f8c-135">**Действие**</span><span class="sxs-lookup"><span data-stu-id="84f8c-135">**Action**</span></span>  
 <span data-ttu-id="84f8c-136">Укажите, следует ли при выполнении задачи **Копировать** или **Переместить** базу данных на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="84f8c-136">Specify whether the task will **Copy** or **Move** the database to the destination server.</span></span>  
  
 <span data-ttu-id="84f8c-137">**Метод**</span><span class="sxs-lookup"><span data-stu-id="84f8c-137">**Method**</span></span>  
 <span data-ttu-id="84f8c-138">Укажите, будет ли при выполнении задачи база данных на исходном сервере работать в сети или вне сети.</span><span class="sxs-lookup"><span data-stu-id="84f8c-138">Specify whether the task will be executed while the database on the source server is in online or offline mode.</span></span>  
  
 <span data-ttu-id="84f8c-139">Для передачи базы данных с использованием режима вне сети пользователь, выполняющий пакет, должен быть членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="84f8c-139">To transfer a database using offline mode, the user that runs the package must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="84f8c-140">Для передачи базы данных с использованием режима в сети пользователь, выполняющий пакет, должен быть членом предопределенной роли сервера **sysadmin** или владельцем выбранной базы данных (**dbo**).</span><span class="sxs-lookup"><span data-stu-id="84f8c-140">To transfer a database using the online mode, the user that runs the package must be a member of the **sysadmin** fixed server role, or the database owner (**dbo**) of the selected database.</span></span>  
  
 <span data-ttu-id="84f8c-141">**SourceDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="84f8c-141">**SourceDatabaseName**</span></span>  
 <span data-ttu-id="84f8c-142">Выберите имя базы данных, подлежащей копированию или перемещению.</span><span class="sxs-lookup"><span data-stu-id="84f8c-142">Select the name of the database to be copied or moved.</span></span>  
  
 <span data-ttu-id="84f8c-143">**SourceDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="84f8c-143">**SourceDatabaseFiles**</span></span>  
 <span data-ttu-id="84f8c-144">Нажмите кнопку обзора, чтобы выбрать файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="84f8c-144">Click the browse button to select the database files.</span></span>  
  
 <span data-ttu-id="84f8c-145">**ReattachSourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="84f8c-145">**ReattachSourceDatabase**</span></span>  
 <span data-ttu-id="84f8c-146">Укажите, должна ли задача предпринять попытку повторно присоединить базу данных-источник при возникновении сбоя.</span><span class="sxs-lookup"><span data-stu-id="84f8c-146">Specify whether the task will attempt to reattach the source database if a failure occurs.</span></span>  
  
 <span data-ttu-id="84f8c-147">Параметры этого свойства приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="84f8c-147">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="84f8c-148">Значение</span><span class="sxs-lookup"><span data-stu-id="84f8c-148">Value</span></span>|<span data-ttu-id="84f8c-149">Описание</span><span class="sxs-lookup"><span data-stu-id="84f8c-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="84f8c-150">**True**</span><span class="sxs-lookup"><span data-stu-id="84f8c-150">**True**</span></span>|<span data-ttu-id="84f8c-151">Присоединить повторно базу данных-источник.</span><span class="sxs-lookup"><span data-stu-id="84f8c-151">Reattach source database.</span></span>|  
|<span data-ttu-id="84f8c-152">**False**</span><span class="sxs-lookup"><span data-stu-id="84f8c-152">**False**</span></span>|<span data-ttu-id="84f8c-153">Не присоединять повторно базу данных-источник.</span><span class="sxs-lookup"><span data-stu-id="84f8c-153">Do not reattach source database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84f8c-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="84f8c-154">See Also</span></span>  
 <span data-ttu-id="84f8c-155">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="84f8c-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="84f8c-156">[Задачи служб Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="84f8c-156">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="84f8c-157">[Редактор задачи "Перемещение базы данных" &#40;общие&#41;страницы](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="84f8c-157">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="84f8c-158">[Страница «Выражения»](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="84f8c-158">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="84f8c-159">Диспетчер соединений SMO</span><span class="sxs-lookup"><span data-stu-id="84f8c-159">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
