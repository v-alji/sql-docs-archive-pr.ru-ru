---
title: Передача файлов в папку | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing reports [Reporting Services], uploading files
- reports [Reporting Services], publishing
- uploading reports [Reporting Services]
- uploading files [Reporting Services]
- files [Reporting Services], uploading
- files [Reporting Services]
- folders [Reporting Services], uploading files to
ms.assetid: 2f99a288-d4aa-4c64-b310-e457a2aef2c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cfb595ed6059436d17cb82262f5d1975a8397dbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659329"
---
# <a name="upload-files-to-a-folder"></a><span data-ttu-id="39224-102">Передача файлов в папку</span><span class="sxs-lookup"><span data-stu-id="39224-102">Upload Files to a Folder</span></span>
  <span data-ttu-id="39224-103">Предусмотрена возможность передавать файлы из файловой системы и сохранять их в качестве управляемых элементов в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="39224-103">You can upload files from the file system and store them as managed items in a report server database.</span></span> <span data-ttu-id="39224-104">Действия системы при передаче зависят от типа файла.</span><span class="sxs-lookup"><span data-stu-id="39224-104">What happens when you upload a file depends on the file type.</span></span>

-   <span data-ttu-id="39224-105">Передача RDL-файла эквивалентна публикации отчета.</span><span class="sxs-lookup"><span data-stu-id="39224-105">Uploading an .rdl file is equivalent to publishing a report.</span></span>

-   <span data-ttu-id="39224-106">Передача любого другого файла добавляет его в базу данных сервера отчетов как один двоичный объект.</span><span class="sxs-lookup"><span data-stu-id="39224-106">Uploading any other file adds it to the report server database as a single binary object.</span></span> <span data-ttu-id="39224-107">Эти файлы публикуются на сервере отчетов как ресурсы.</span><span class="sxs-lookup"><span data-stu-id="39224-107">These files are published to a report server as a resource.</span></span> <span data-ttu-id="39224-108">Ресурсами могут быть файлы любого типа.</span><span class="sxs-lookup"><span data-stu-id="39224-108">Resources can be any file type.</span></span> <span data-ttu-id="39224-109">Если расширение файла совпадает с известным типом MIME, для идентификации типа ресурса используется значок этого типа MIME.</span><span class="sxs-lookup"><span data-stu-id="39224-109">If the file extension matches a known MIME type, an icon for that MIME type is used to identify the resource type.</span></span> <span data-ttu-id="39224-110">В противном случае ресурс показывает универсальный значок файла.</span><span class="sxs-lookup"><span data-stu-id="39224-110">Otherwise, a generic file icon indicates a resource.</span></span>

> [!NOTE]
>  <span data-ttu-id="39224-111">Нельзя передавать файл источника данных отчета (RDS) для создания общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="39224-111">You cannot upload a report data source (.rds) file to create a shared data source.</span></span> <span data-ttu-id="39224-112">RDS-файл используется только в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="39224-112">An .rds file is used only in Report Designer.</span></span> <span data-ttu-id="39224-113">Он не может предоставлять содержимое для совместно используемого элемента источника данных, определенного и управляемого с помощью диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="39224-113">It cannot provide the content for a shared data source item that you define and manage through Report Manager.</span></span> <span data-ttu-id="39224-114">В качестве альтернативы передачи можно написать скрипт, который создает общий источник данных на основе RDS-файла.</span><span class="sxs-lookup"><span data-stu-id="39224-114">As an alternative to uploading, you can write a script that creates a shared data source based on a .rds file.</span></span>

 <span data-ttu-id="39224-115">Максимальный размер файла для передаваемых элементов определяется [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39224-115">The maximum file size for uploaded items is determined by [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span></span> <span data-ttu-id="39224-116">По умолчанию максимальный размер равен 4 мегабайтам (МБ).</span><span class="sxs-lookup"><span data-stu-id="39224-116">By default, the maximum size is 4 megabytes (MB).</span></span>

 <span data-ttu-id="39224-117">Визуально файлы, передаваемые в базу данных сервера отчетов, представляются в иерархии папок с помощью следующих значков:</span><span class="sxs-lookup"><span data-stu-id="39224-117">Visually, files that you upload to a report server database are represented in the folder hierarchy with the following icons.</span></span>

 <span data-ttu-id="39224-118">![Report icon](../media/hlp-16doc.gif "Значок отчета") Значок отчета значка отчета</span><span class="sxs-lookup"><span data-stu-id="39224-118">![Report icon](../media/hlp-16doc.gif "Report icon") report icon</span></span>

 <span data-ttu-id="39224-119">Значок ![модели](../media/model-icon.gif "Значок модели") значок модели отчета</span><span class="sxs-lookup"><span data-stu-id="39224-119">![Model icon](../media/model-icon.gif "Model icon") report model icon</span></span>

 <span data-ttu-id="39224-120">![универсальный](../media/hlp-16file.gif "универсальный значок ресурса") значок ресурса значок универсального ресурса</span><span class="sxs-lookup"><span data-stu-id="39224-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon") generic resource icon</span></span>

 <span data-ttu-id="39224-121">При передаче файл всегда помещается в текущую выбранную папку.</span><span class="sxs-lookup"><span data-stu-id="39224-121">When you upload a file, it is always placed in the folder that is currently selected.</span></span> <span data-ttu-id="39224-122">Можно либо сразу перейти в папку, куда следует сохранить файл, либо передать файл и затем переместить его в нужное место.</span><span class="sxs-lookup"><span data-stu-id="39224-122">You can navigate to the folder that you want to contain the item first, or you can upload a file and then move it to a final location later.</span></span>

 <span data-ttu-id="39224-123">Файл передается с помощью диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="39224-123">To upload a file, use Report Manager.</span></span> <span data-ttu-id="39224-124">Возможность передачи файлов на сервер отчетов зависит от задач, которые входят в назначенную роль.</span><span class="sxs-lookup"><span data-stu-id="39224-124">Whether you can upload files to a report server depends on tasks that are part of your role assignment.</span></span> <span data-ttu-id="39224-125">Если используются настройки безопасности по умолчанию, локальные администраторы могут добавлять элементы в сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="39224-125">If you are using default security, local administrators can add items to a report server.</span></span> <span data-ttu-id="39224-126">Если включены «Мои отчеты», любой пользователь, для которого создана папка «Мои отчеты», имеет разрешения на передачу в нее элементов.</span><span class="sxs-lookup"><span data-stu-id="39224-126">If My Reports is enabled, any user who has a My Reports folder has permission to upload items to that folder.</span></span> <span data-ttu-id="39224-127">Если используются пользовательские назначения ролей, то назначение роли должно включать задачи, поддерживающие управление папками.</span><span class="sxs-lookup"><span data-stu-id="39224-127">If you use custom role assignments, the role assignment must include tasks that support folder management.</span></span>

|<span data-ttu-id="39224-128">Требуемое действие</span><span class="sxs-lookup"><span data-stu-id="39224-128">To do this</span></span>|<span data-ttu-id="39224-129">Необходимо включить следующие задачи</span><span class="sxs-lookup"><span data-stu-id="39224-129">Include these tasks</span></span>|
|----------------|-------------------------|
|<span data-ttu-id="39224-130">Передача RDL-файла в папку</span><span class="sxs-lookup"><span data-stu-id="39224-130">Upload an .rdl file to a folder</span></span>|<span data-ttu-id="39224-131">Управление отчетами</span><span class="sxs-lookup"><span data-stu-id="39224-131">Manage reports</span></span>|
|<span data-ttu-id="39224-132">Передача любого файла как двоичного объекта</span><span class="sxs-lookup"><span data-stu-id="39224-132">Upload any file as a binary object</span></span>|<span data-ttu-id="39224-133">Управление ресурсами</span><span class="sxs-lookup"><span data-stu-id="39224-133">Manage resources</span></span>|
|<span data-ttu-id="39224-134">Просмотр содержимого папки</span><span class="sxs-lookup"><span data-stu-id="39224-134">View the contents of a folder</span></span>|<span data-ttu-id="39224-135">Просмотр ресурсов, просмотр отчетов</span><span class="sxs-lookup"><span data-stu-id="39224-135">View resources, View reports</span></span>|

## <a name="see-also"></a><span data-ttu-id="39224-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="39224-136">See Also</span></span>
 <span data-ttu-id="39224-137">[Диспетчер отчетов &#40;служб SSRS в собственном режиме&#41;].. /report-manager-ssrs-native-mode.md) [предоставление разрешений для](../security/granting-permissions-on-a-native-mode-report-server.md) [задач и разрешений](../security/tasks-and-permissions.md) сервера отчетов в собственном режиме [отправка файла или отчета &#40;диспетчер отчетов&#41;](../reports/upload-a-file-or-report-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="39224-137">[Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md) [Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) [Tasks and Permissions](../security/tasks-and-permissions.md) [Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md)</span></span>


