---
title: Диспетчер подключений к нескольким файлам |  | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- Multiple Files connection manager
- connection managers [Integration Services], Multiple Files
- connections [Integration Services], files
- multiple file connections
ms.assetid: 10bdc56e-c5cd-4ddb-b2f7-375fe57fe8b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9ebd45aa4f0794d98be6a79125bf1874913d491
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667355"
---
# <a name="multiple-files-connection-manager"></a><span data-ttu-id="624f2-102">диспетчер соединений с несколькими файлами</span><span class="sxs-lookup"><span data-stu-id="624f2-102">Multiple Files Connection Manager</span></span>
  <span data-ttu-id="624f2-103">Диспетчер соединений с несколькими файлами позволяет пакету обращаться к существующим файлам и папкам или создавать файлы и папки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="624f2-103">A Multiple Files connection manager enables a package to reference existing files and folders, or to create files and folders at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="624f2-104">Встроенные задачи и компоненты потока данных в службах [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] не используют диспетчер соединений с несколькими файлами.</span><span class="sxs-lookup"><span data-stu-id="624f2-104">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="624f2-105">Однако можно использовать этот диспетчер соединений в задаче «Скрипт» и компоненте скрипта.</span><span class="sxs-lookup"><span data-stu-id="624f2-105">However, you can use this connection manager in the Script task or Script component.</span></span> <span data-ttu-id="624f2-106">Дополнительные сведения об использовании диспетчеров соединений в задаче «Скрипт» см. в разделе [Соединение с источниками данных в задаче «Скрипт»](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="624f2-106">For information about how to use connection managers in the Script task, see [Connecting to Data Sources in the Script Task](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span></span> <span data-ttu-id="624f2-107">Сведения об использовании диспетчеров соединений в компоненте скрипта см. в разделе [подключение к источникам данных в компоненте скрипта] (. /екстендинг-паккажес-скриптинг/дата-флов-скрипт-компонент/коннектинг-то-дата-саурцес-ин-се-скрипт-компонент.мд.</span><span class="sxs-lookup"><span data-stu-id="624f2-107">For information about how to use connection managers in the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span></span>  
  
## <a name="usage-types-of-the-multiple-files-connection-manager"></a><span data-ttu-id="624f2-108">Использование диспетчера соединений с несколькими файлами</span><span class="sxs-lookup"><span data-stu-id="624f2-108">Usage Types of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="624f2-109">Свойство `FileUsageType` диспетчера соединений с несколькими файлами определяет, как используется соединение.</span><span class="sxs-lookup"><span data-stu-id="624f2-109">The `FileUsageType` property of the Multiple Files connection manager specifies how the connection is used.</span></span> <span data-ttu-id="624f2-110">Диспетчер соединений с несколькими файлами может создавать файлы и папки, а также использовать существующие файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="624f2-110">The Multiple Files connection manager can create files, create folders, use existing files, and use existing folders.</span></span>  
  
 <span data-ttu-id="624f2-111">В следующей таблице приводятся значения `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="624f2-111">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="624f2-112">Значение</span><span class="sxs-lookup"><span data-stu-id="624f2-112">Value</span></span>|<span data-ttu-id="624f2-113">Description</span><span class="sxs-lookup"><span data-stu-id="624f2-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="624f2-114">**0**</span><span class="sxs-lookup"><span data-stu-id="624f2-114">**0**</span></span>|<span data-ttu-id="624f2-115">Диспетчер соединений с несколькими файлами использует существующий файл.</span><span class="sxs-lookup"><span data-stu-id="624f2-115">Multiple Files connection manager uses an existing file.</span></span>|  
|<span data-ttu-id="624f2-116">**1**</span><span class="sxs-lookup"><span data-stu-id="624f2-116">**1**</span></span>|<span data-ttu-id="624f2-117">Диспетчер соединений с несколькими файлами создает файл.</span><span class="sxs-lookup"><span data-stu-id="624f2-117">Multiple Files connection manager creates a file.</span></span>|  
|<span data-ttu-id="624f2-118">**2**</span><span class="sxs-lookup"><span data-stu-id="624f2-118">**2**</span></span>|<span data-ttu-id="624f2-119">Диспетчер соединений с несколькими файлами использует существующую папку.</span><span class="sxs-lookup"><span data-stu-id="624f2-119">Multiple Files connection manager uses an existing folder.</span></span>|  
|<span data-ttu-id="624f2-120">**3**</span><span class="sxs-lookup"><span data-stu-id="624f2-120">**3**</span></span>|<span data-ttu-id="624f2-121">Диспетчер соединений с несколькими файлами создает папку.</span><span class="sxs-lookup"><span data-stu-id="624f2-121">Multiple Files connection manager creates a folder.</span></span>|  
  
## <a name="configuration-of-the-multiple-files-connection-manager"></a><span data-ttu-id="624f2-122">Конфигурация диспетчера соединений с несколькими файлами</span><span class="sxs-lookup"><span data-stu-id="624f2-122">Configuration of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="624f2-123">Когда к пакету добавляется диспетчер соединений с несколькими файлами, службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создают диспетчер соединений, который разрешает подключение нескольких файлов во время выполнения, устанавливает свойства подключения нескольких файлов и добавляет соединения с несколькими файлами к коллекции пакета `Connections`.</span><span class="sxs-lookup"><span data-stu-id="624f2-123">When you add a Multiple Files connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a Multiple Files connection at run time, sets the Multiple Files connection properties, and adds the Multiple Files connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="624f2-124">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `MULTIFILE`.</span><span class="sxs-lookup"><span data-stu-id="624f2-124">The `ConnectionManagerType` property of the connection manager is set to `MULTIFILE`.</span></span>  
  
 <span data-ttu-id="624f2-125">Настроить диспетчер соединений с несколькими файлами можно следующими способами.</span><span class="sxs-lookup"><span data-stu-id="624f2-125">You can configure a Multiple Files connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="624f2-126">Определите тип использования файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="624f2-126">Specify the usage type of files and folders.</span></span>  
  
-   <span data-ttu-id="624f2-127">Определите файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="624f2-127">Specify files and folders.</span></span>  
  
-   <span data-ttu-id="624f2-128">Если используется множество файлов и папок, определите порядок, в котором будут обращаться к файлам и папкам.</span><span class="sxs-lookup"><span data-stu-id="624f2-128">If using multiple files or folders, specify the order in which the files and folders are accessed.</span></span>  
  
 <span data-ttu-id="624f2-129">Если диспетчер соединения с несколькими файлами ссылается на множество файлов и папок, пути файлов и папок разделяются символом «|».</span><span class="sxs-lookup"><span data-stu-id="624f2-129">If the Multiple Files connection manager references multiple files and folders, the paths of the files and folders are separated by the pipe (|) character.</span></span> <span data-ttu-id="624f2-130">Свойство `ConnectionString` диспетчера соединений имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="624f2-130">The `ConnectionString` property of the connection manager has the following format:</span></span>  
  
 \<*path*>|\<*path*>  
  
 <span data-ttu-id="624f2-131">Также можно определить множество файлов и папок, используя символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="624f2-131">You can also specify multiple files or folders using wildcard characters.</span></span> <span data-ttu-id="624f2-132">Например, чтобы сослаться на все текстовые файлы на диске C, `ConnectionString` можно задать для свойства значение C: \\ \*. txt.</span><span class="sxs-lookup"><span data-stu-id="624f2-132">For example, to reference all the text files on the C drive, the value of the `ConnectionString` property can be set to C:\\*.txt.</span></span>  
  
 <span data-ttu-id="624f2-133">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="624f2-133">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="624f2-134">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в разделе [Добавление диспетчера соединения файлов диалогового окна пользовательского Интерфейса в справочник](add-file-connection-manager-dialog-box-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="624f2-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add File Connection Manager Dialog Box UI Reference](add-file-connection-manager-dialog-box-ui-reference.md).</span></span>  
  
 <span data-ttu-id="624f2-135">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="624f2-135">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
