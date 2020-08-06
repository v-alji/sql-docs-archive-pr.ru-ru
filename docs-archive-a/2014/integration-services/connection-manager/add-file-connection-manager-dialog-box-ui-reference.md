---
title: 'Справочник по пользовательскому интерфейсу: диалоговое окно "Добавление диспетчера подключения файлов" | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnection.f1
helpviewer_keywords:
- Add File Connection Manager
ms.assetid: 9370bfb5-5993-4ad8-a9cd-2de53f320f34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 044d8e2eaae9db17d7155cb354f8d009750f44d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738579"
---
# <a name="add-file-connection-manager-dialog-box-ui-reference"></a><span data-ttu-id="a7ae7-102">Добавление диспетчера соединения файлов диалогового окна пользовательского Интерфейса в справочник</span><span class="sxs-lookup"><span data-stu-id="a7ae7-102">Add File Connection Manager Dialog Box UI Reference</span></span>
  <span data-ttu-id="a7ae7-103">Используйте диалоговое окно **Добавление диспетчера соединения файлов** , чтобы определить соединение с группой файлов или папок.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-103">Use the **Add File Connection Manager** dialog box to define a connection to a group of files or folders.</span></span>  
  
 <span data-ttu-id="a7ae7-104">Дополнительные сведения о диспетчере соединений с несколькими файлами см. в разделе [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a7ae7-104">To learn more about the Multiple Files connection manager, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7ae7-105">Встроенные задачи и компоненты потока данных в службах [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] не используют диспетчер соединений с несколькими файлами.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-105">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="a7ae7-106">Однако можно использовать этот диспетчер соединений в задаче «Скрипт» и компоненте скрипта.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-106">However, you can use this connection manager in the Script task or Script component.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a7ae7-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7ae7-107">Options</span></span>  
 <span data-ttu-id="a7ae7-108">**Тип применения**</span><span class="sxs-lookup"><span data-stu-id="a7ae7-108">**Usage type**</span></span>  
 <span data-ttu-id="a7ae7-109">Укажите тип файлов для диспетчера подключения нескольких файлов.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-109">Specify the type of files to use for the multiple files connection manager.</span></span>  
  
|<span data-ttu-id="a7ae7-110">Значение</span><span class="sxs-lookup"><span data-stu-id="a7ae7-110">Value</span></span>|<span data-ttu-id="a7ae7-111">Description</span><span class="sxs-lookup"><span data-stu-id="a7ae7-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a7ae7-112">**Создать файлы**</span><span class="sxs-lookup"><span data-stu-id="a7ae7-112">**Create files**</span></span>|<span data-ttu-id="a7ae7-113">Диспетчер соединений создаст файлы.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-113">The connection manager will create the files.</span></span>|  
|<span data-ttu-id="a7ae7-114">**Существующие файлы**</span><span class="sxs-lookup"><span data-stu-id="a7ae7-114">**Existing files**</span></span>|<span data-ttu-id="a7ae7-115">Диспетчер соединений будет использовать существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-115">The connection manager will use existing files.</span></span>|  
|<span data-ttu-id="a7ae7-116">**Создать папки**</span><span class="sxs-lookup"><span data-stu-id="a7ae7-116">**Create folders**</span></span>|<span data-ttu-id="a7ae7-117">Диспетчер соединений создаст папки.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-117">The connection manager will create the folders.</span></span>|  
|<span data-ttu-id="a7ae7-118">**Существующие папки**</span><span class="sxs-lookup"><span data-stu-id="a7ae7-118">**Existing folders**</span></span>|<span data-ttu-id="a7ae7-119">Диспетчер соединений будет использовать существующие папки.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-119">The connection manager will use existing folders.</span></span>|  
  
 <span data-ttu-id="a7ae7-120">**Файлы или папки**</span><span class="sxs-lookup"><span data-stu-id="a7ae7-120">**Files / Folders**</span></span>  
 <span data-ttu-id="a7ae7-121">Просмотрите файлы или папки, добавленные при помощи описанных ниже кнопок.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-121">View the files or folders that you have added by using the buttons described as follows.</span></span>  
  
 <span data-ttu-id="a7ae7-122">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="a7ae7-122">**Add**</span></span>  
 <span data-ttu-id="a7ae7-123">Добавьте файл с помощью диалогового окна **Выбор файлов** или добавьте папку с помощью диалогового окна **Выбор папки** .</span><span class="sxs-lookup"><span data-stu-id="a7ae7-123">Add a file by using the **Select Files** dialog box, or add a folder by using the **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="a7ae7-124">**Edit** (Изменение)</span><span class="sxs-lookup"><span data-stu-id="a7ae7-124">**Edit**</span></span>  
 <span data-ttu-id="a7ae7-125">Выберите файл или папку, а затем замените их другим файлом или другой папкой с помощью диалогового окна **Выбор файлов** или **Выбор папки** .</span><span class="sxs-lookup"><span data-stu-id="a7ae7-125">Select a file or folder, and then replace it with a different file or folder by using the **Select Files** or **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="a7ae7-126">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="a7ae7-126">**Remove**</span></span>  
 <span data-ttu-id="a7ae7-127">Выберите файл или папку, а затем удалите их с помощью кнопки **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="a7ae7-127">Select a file or folder, and then remove it from the list by using the **Remove** button.</span></span>  
  
 <span data-ttu-id="a7ae7-128">**Стрелки**</span><span class="sxs-lookup"><span data-stu-id="a7ae7-128">**Arrow buttons**</span></span>  
 <span data-ttu-id="a7ae7-129">Выберите файл или папку, а затем при помощи стрелок переместите его вверх или вниз, чтобы указать последовательность доступа.</span><span class="sxs-lookup"><span data-stu-id="a7ae7-129">Select a file or folder, and then use the arrow buttons to move it up or down to specify the sequence of access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ae7-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7ae7-130">See Also</span></span>  
 [<span data-ttu-id="a7ae7-131">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="a7ae7-131">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
  
  
