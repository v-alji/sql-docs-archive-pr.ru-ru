---
title: Редактор диспетчера подключения файлов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnectionmanager.f1
helpviewer_keywords:
- File Connection Manager Editor
ms.assetid: 051c48e5-3d86-49af-b554-ff62e3de3622
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f3261b836d4800787fc078b05b15e469d3c200d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667277"
---
# <a name="file-connection-manager-editor"></a><span data-ttu-id="c7fd0-102">редактор диспетчера подключения файлов</span><span class="sxs-lookup"><span data-stu-id="c7fd0-102">File Connection Manager Editor</span></span>
  <span data-ttu-id="c7fd0-103">Диалоговое окно **Редактор диспетчера подключения файлов** задает свойства, используемые при подключении к файлу или папке.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-103">Use the **File Connection Manager Editor** dialog box to specify the properties used to connect to a file or a folder.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7fd0-104">Можно задать свойство ConnectionString для диспетчера соединений с файлами, указывая выражение в окне "Свойства" [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7fd0-104">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c7fd0-105">Но чтобы избежать ошибки проверки при использовании выражения для указания файла или папки, добавьте путь к файлу или папке в пункте **Файл/папка**в **Редакторе диспетчера подключения файлов**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-105">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="c7fd0-106">Дополнительные сведения о диспетчере подключения файлов см. в разделе [File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-106">To learn more about the File connection manager, see [File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c7fd0-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="c7fd0-107">Options</span></span>  
 <span data-ttu-id="c7fd0-108">**Тип применения**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-108">**Usage Type**</span></span>  
 <span data-ttu-id="c7fd0-109">Укажите, будет ли **Диспетчер подключения файлов** подключаться к существующему файлу или папке или создаст новый файл или папку.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-109">Specify whether the **File Connection Manager** connects to an existing file or folder or creates a new file or folder.</span></span>  
  
|<span data-ttu-id="c7fd0-110">Значение</span><span class="sxs-lookup"><span data-stu-id="c7fd0-110">Value</span></span>|<span data-ttu-id="c7fd0-111">Описание</span><span class="sxs-lookup"><span data-stu-id="c7fd0-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c7fd0-112">Создать файл</span><span class="sxs-lookup"><span data-stu-id="c7fd0-112">Create file</span></span>|<span data-ttu-id="c7fd0-113">Во время выполнения создается новый файл.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-113">Create a new file at run time.</span></span>|  
|<span data-ttu-id="c7fd0-114">Существующий файл</span><span class="sxs-lookup"><span data-stu-id="c7fd0-114">Existing file</span></span>|<span data-ttu-id="c7fd0-115">Использовать существующий файл.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-115">Use an existing file.</span></span>|  
|<span data-ttu-id="c7fd0-116">Создать папку</span><span class="sxs-lookup"><span data-stu-id="c7fd0-116">Create folder</span></span>|<span data-ttu-id="c7fd0-117">Во время выполнения создается новая папка.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-117">Create a new folder at run time.</span></span>|  
|<span data-ttu-id="c7fd0-118">Существующая папка</span><span class="sxs-lookup"><span data-stu-id="c7fd0-118">Existing folder</span></span>|<span data-ttu-id="c7fd0-119">Использовать существующую папку.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-119">Use an existing folder.</span></span>|  
  
 <span data-ttu-id="c7fd0-120">**Файл / Папка**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-120">**File / Folder**</span></span>  
 <span data-ttu-id="c7fd0-121">Если **Файл**, укажите нужный файл.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-121">If **File**, specify the file to use.</span></span>  
  
 <span data-ttu-id="c7fd0-122">Если **Папка**, укажите нужную папку.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-122">If **Folder**, specify the folder to use.</span></span>  
  
 <span data-ttu-id="c7fd0-123">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-123">**Browse**</span></span>  
 <span data-ttu-id="c7fd0-124">Выберите файл или папку в диалоговом окне **Выбор файла** или **Выбор папки** .</span><span class="sxs-lookup"><span data-stu-id="c7fd0-124">Select the file or folder by using the **Select File** or **Browse for Folder** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7fd0-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-125">See Also</span></span>  
 [<span data-ttu-id="c7fd0-126">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="c7fd0-126">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
