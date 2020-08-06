---
title: Диспетчер подключения файлов | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- files [Integration Services]
- connection managers [Integration Services], File
- connections [Integration Services], files
- File connection manager
ms.assetid: 019078bc-44ee-4975-9169-0f9a89e3f3be
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cebb5438003c6b14c547d14012ff1bc1175a706d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738567"
---
# <a name="file-connection-manager"></a><span data-ttu-id="4e391-102">диспетчер соединения файлов</span><span class="sxs-lookup"><span data-stu-id="4e391-102">File Connection Manager</span></span>
  <span data-ttu-id="4e391-103">Диспетчер соединения файлов позволяет пакету ссылаться на существующий файл или папку или создавать файл или папку в процессе выполнения.</span><span class="sxs-lookup"><span data-stu-id="4e391-103">A File connection manager enables a package to reference an existing file or folder, or to create a file or folder at run time.</span></span> <span data-ttu-id="4e391-104">Например, можно установить ссылку на файл Excel.</span><span class="sxs-lookup"><span data-stu-id="4e391-104">For example, you can reference an Excel file.</span></span> <span data-ttu-id="4e391-105">Некоторые компоненты из служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] используют данные, хранящиеся в файлах, для выполнения своей работы.</span><span class="sxs-lookup"><span data-stu-id="4e391-105">Certain components in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] use information in files to perform their work.</span></span> <span data-ttu-id="4e391-106">Например, задача «Выполнение SQL» может ссылаться на файл, содержащий набор инструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="4e391-106">For example, an Execute SQL task can reference a file that contains the SQL statements that the task executes.</span></span> <span data-ttu-id="4e391-107">Другие компоненты выполняют операции с файлами.</span><span class="sxs-lookup"><span data-stu-id="4e391-107">Other components perform operations on files.</span></span> <span data-ttu-id="4e391-108">Например, задача «Файловая система» может ссылаться на файл для его копирования в другое расположение.</span><span class="sxs-lookup"><span data-stu-id="4e391-108">For example, the File System task can reference a file to copy it to a new location.</span></span>  
  
## <a name="usage-types-of-the-file-connection-manager"></a><span data-ttu-id="4e391-109">Типы применения в диспетчере соединения файлов</span><span class="sxs-lookup"><span data-stu-id="4e391-109">Usage Types of the File Connection Manager</span></span>  
 <span data-ttu-id="4e391-110">Свойство `FileUsageType` диспетчера соединения файлов определяет, как используется соединение файла.</span><span class="sxs-lookup"><span data-stu-id="4e391-110">The `FileUsageType` property of the File connection manager specifies how the file connection is used.</span></span> <span data-ttu-id="4e391-111">Диспетчер подключения файлов может создать файл или папку, а также использовать уже существующий файл или папку.</span><span class="sxs-lookup"><span data-stu-id="4e391-111">The File connection manager can create a file, create a folder, use an existing file, or use an existing folder.</span></span>  
  
 <span data-ttu-id="4e391-112">В следующей таблице приводятся значения `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="4e391-112">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="4e391-113">Значение</span><span class="sxs-lookup"><span data-stu-id="4e391-113">Value</span></span>|<span data-ttu-id="4e391-114">Description</span><span class="sxs-lookup"><span data-stu-id="4e391-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="4e391-115">Диспетчер подключения файлов использует существующий файл.</span><span class="sxs-lookup"><span data-stu-id="4e391-115">File connection manager uses an existing file.</span></span>|  
|`1`|<span data-ttu-id="4e391-116">Диспетчер подключения файлов создает файл.</span><span class="sxs-lookup"><span data-stu-id="4e391-116">File connection manager creates a file.</span></span>|  
|`2`|<span data-ttu-id="4e391-117">Диспетчер соединения файлов использует существующую папку.</span><span class="sxs-lookup"><span data-stu-id="4e391-117">File connection manager uses an existing folder.</span></span>|  
|`3`|<span data-ttu-id="4e391-118">Диспетчер соединения файлов создает папку.</span><span class="sxs-lookup"><span data-stu-id="4e391-118">File connection manager creates a folder.</span></span>|  
  
## <a name="multiple-file-or-folder-connections"></a><span data-ttu-id="4e391-119">Соединения с несколькими файлами или папками</span><span class="sxs-lookup"><span data-stu-id="4e391-119">Multiple File or Folder Connections</span></span>  
 <span data-ttu-id="4e391-120">Диспетчер соединения файлов может ссылаться только на один файл или папку.</span><span class="sxs-lookup"><span data-stu-id="4e391-120">The File connection manager can reference only one file or folder.</span></span> <span data-ttu-id="4e391-121">Для создания ссылки на несколько файлов или папок используйте диспетчер соединения нескольких файлов вместо диспетчера соединений с файлом.</span><span class="sxs-lookup"><span data-stu-id="4e391-121">To reference multiple files or folders, use a Multiple Files connection manager instead of a File connection manager.</span></span> <span data-ttu-id="4e391-122">Дополнительные сведения см. в статье [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4e391-122">For more information, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
## <a name="configuration-of-the-file-connection-manager"></a><span data-ttu-id="4e391-123">Настройка диспетчера соединения файлов</span><span class="sxs-lookup"><span data-stu-id="4e391-123">Configuration of the File Connection Manager</span></span>  
 <span data-ttu-id="4e391-124">Когда в пакет добавляется диспетчер подключения файлов, службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создают диспетчер соединений, который в процессе выполнения создает соединение файла, устанавливает свойства подключения файла и добавляет подключения файла в коллекцию `Connections` пакета.</span><span class="sxs-lookup"><span data-stu-id="4e391-124">When you add a File connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a File connection at run time, sets the File connection properties, and adds the File connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="4e391-125">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `FILE`.</span><span class="sxs-lookup"><span data-stu-id="4e391-125">The `ConnectionManagerType` property of the connection manager is set to `FILE`.</span></span>  
  
 <span data-ttu-id="4e391-126">Диспетчер соединения файлов можно настроить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4e391-126">You can configure a File connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="4e391-127">Определить тип применения.</span><span class="sxs-lookup"><span data-stu-id="4e391-127">Specify the usage type.</span></span>  
  
-   <span data-ttu-id="4e391-128">Определить файл или папку.</span><span class="sxs-lookup"><span data-stu-id="4e391-128">Specify a file or folder.</span></span>  
  
 <span data-ttu-id="4e391-129">Можно задать свойство ConnectionString для диспетчера соединений с файлами, указывая выражение в окне "Свойства" [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e391-129">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="4e391-130">Но чтобы избежать ошибки проверки при использовании выражения для указания файла или папки, добавьте путь к файлу или папке в пункте **Файл/папка**в **Редакторе диспетчера подключения файлов**.</span><span class="sxs-lookup"><span data-stu-id="4e391-130">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="4e391-131">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="4e391-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4e391-132">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в статье [Файл/папка](../file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4e391-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [File Connection Manager Editor](../file-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="4e391-133">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4e391-133">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
