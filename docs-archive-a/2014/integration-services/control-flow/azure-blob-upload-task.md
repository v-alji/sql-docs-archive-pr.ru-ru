---
title: Задача передачи больших двоичных объектов Azure | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobuptask.f1
- sql11.dts.designer.afpblobuptask.f1
ms.assetid: 6ea068b0-4cd8-45b5-b89d-09b8f25040c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ca15c5a77a2694293981121f4e5927be8ec0e1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729713"
---
# <a name="azure-blob-upload-task"></a><span data-ttu-id="20344-102">Задача передачи больших двоичных объектов Azure</span><span class="sxs-lookup"><span data-stu-id="20344-102">Azure Blob Upload Task</span></span>
  <span data-ttu-id="20344-103">Задача передачи BLOB-объектов Azure позволяет пакету служб SSIS передавать файлы в хранилище BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="20344-103">The Azure Blob Upload Task enables an SSIS package to upload files to an Azure blob storage.</span></span>   
<span data-ttu-id="20344-104">Чтобы добавить **задачу передачи BLOB-объектов Azure**, перетащите ее в конструктор служб SSIS и дважды щелкните или щелкните правой кнопкой мыши, а затем выберите **Изменить** , чтобы открыть диалоговое окно **Редактор задач передачи BLOB-объектов Azure** .</span><span class="sxs-lookup"><span data-stu-id="20344-104">To add an **Azure Blob Upload Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Upload Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="20344-105">Следующая таблица содержит описания полей этого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="20344-105">The following table provides descriptions for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="20344-106">**Поле**</span><span class="sxs-lookup"><span data-stu-id="20344-106">**Field**</span></span>|<span data-ttu-id="20344-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="20344-107">**Description**</span></span>|  
|<span data-ttu-id="20344-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="20344-108">AzureStorageConnection</span></span>|<span data-ttu-id="20344-109">Создайте новый или укажите существующий диспетчер подключений службы хранилища Azure, который ссылается на учетную запись хранения Azure, указывающую на место размещения файлов BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="20344-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="20344-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="20344-110">BlobContainer</span></span>|<span data-ttu-id="20344-111">Задает имя контейнера BLOB-объектов, который будет содержать переданные файлы в виде больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="20344-111">Specifies the name of the blob container that will hold the uploaded files as blobs.</span></span>|  
|<span data-ttu-id="20344-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="20344-112">BlobDirectory</span></span>|<span data-ttu-id="20344-113">Указывает каталог больших двоичных объектов, где загруженный файл будет храниться в виде блочного BLOB-объекта.</span><span class="sxs-lookup"><span data-stu-id="20344-113">Specifies the blob directory where the uploaded file will be stored as a block blob.</span></span> <span data-ttu-id="20344-114">Каталог больших двоичных объектов — это виртуальная иерархическая структура.</span><span class="sxs-lookup"><span data-stu-id="20344-114">The blob directory is a virtual hierarchical structure.</span></span> <span data-ttu-id="20344-115">Если большой двоичный объект уже существует, он будет заменен.</span><span class="sxs-lookup"><span data-stu-id="20344-115">If the blob already exists, it will be replaced.</span></span>|  
|<span data-ttu-id="20344-116">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="20344-116">LocalDirectory</span></span>|<span data-ttu-id="20344-117">Укажите локальный каталог, который содержит файлы для отправки.</span><span class="sxs-lookup"><span data-stu-id="20344-117">Specify the local directory that contains the files to be uploaded.</span></span>|  
|<span data-ttu-id="20344-118">FileName</span><span class="sxs-lookup"><span data-stu-id="20344-118">FileName</span></span>|<span data-ttu-id="20344-119">Указывает имя фильтра для выбора файлов с указанным шаблоном имени.</span><span class="sxs-lookup"><span data-stu-id="20344-119">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="20344-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="20344-120">E.g.</span></span> <span data-ttu-id="20344-121">MySheet\*.xls\* включает такие файлы, как MySheet001.xls и MySheetABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="20344-121">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="20344-122">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="20344-122">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="20344-123">Задает фильтр диапазона времени.</span><span class="sxs-lookup"><span data-stu-id="20344-123">Specifies a time range filter.</span></span> <span data-ttu-id="20344-124">Будут включены файлы, измененные после **TimeRangeFrom** и до **TimeRangeTo** .</span><span class="sxs-lookup"><span data-stu-id="20344-124">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
