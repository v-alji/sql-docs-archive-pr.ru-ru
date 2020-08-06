---
title: Задача скачивания BLOB-объектов Azure | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdltask.f1
- sql11.dts.designer.afpblobdltask.f1
ms.assetid: 8a63bf44-71be-456d-9a5c-be7c31aff065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e2f61260b1fceaad3c27a0ce6ab6af28b15582bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729714"
---
# <a name="azure-blob-download-task"></a><span data-ttu-id="e6bf2-102">Задача скачивания BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="e6bf2-102">Azure Blob Download Task</span></span>
  <span data-ttu-id="e6bf2-103">Задача скачивания BLOB-объектов Azure позволяет пакету служб SSIS скачивать файлы из хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-103">The Azure Blob Download Task enables an SSIS package to download files from an Azure blob storage.</span></span>   
<span data-ttu-id="e6bf2-104">Чтобы добавить **задачу скачивания BLOB-объектов Azure**, перетащите ее в конструкторе служб SSIS и дважды щелкните или щелкните правой кнопкой мыши и выберите **Изменить** , чтобы вызвать диалоговое окно **Редактор задач скачивания BLOB-объектов Azure** .</span><span class="sxs-lookup"><span data-stu-id="e6bf2-104">To add an **Azure Blob Download Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Download Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="e6bf2-105">Следующая таблица содержит описание полей этого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-105">The following table provides description for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6bf2-106">**Поле**</span><span class="sxs-lookup"><span data-stu-id="e6bf2-106">**Field**</span></span>|<span data-ttu-id="e6bf2-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e6bf2-107">**Description**</span></span>|  
|<span data-ttu-id="e6bf2-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="e6bf2-108">AzureStorageConnection</span></span>|<span data-ttu-id="e6bf2-109">Создайте новый или укажите существующий диспетчер подключений службы хранилища Azure, который ссылается на учетную запись хранения Azure, указывающую на место размещения файлов BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="e6bf2-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="e6bf2-110">BlobContainer</span></span>|<span data-ttu-id="e6bf2-111">Указывает имя контейнера BLOB-объектов, который содержит скачиваемые файлы BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-111">Specifies the name of the blob container that contains the blob files to be downloaded.</span></span>|  
|<span data-ttu-id="e6bf2-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="e6bf2-112">BlobDirectory</span></span>|<span data-ttu-id="e6bf2-113">Указывает каталог больших двоичных объектов, который содержит скачиваемые файлы BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-113">Specifies the blob directory that contains the blob files to be downloaded.</span></span> <span data-ttu-id="e6bf2-114">Каталог больших двоичных объектов — это виртуальная иерархическая структура.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-114">The blob directory is a virtual hierarchical structure.</span></span>|  
|<span data-ttu-id="e6bf2-115">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="e6bf2-115">LocalDirectory</span></span>|<span data-ttu-id="e6bf2-116">Указывает локальный каталог для хранения скачанных файлов BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-116">Specifies the local directory where the downloaded blob files will be stored.</span></span>|  
|<span data-ttu-id="e6bf2-117">FileName</span><span class="sxs-lookup"><span data-stu-id="e6bf2-117">FileName</span></span>|<span data-ttu-id="e6bf2-118">Указывает имя фильтра для выбора файлов с указанным шаблоном имени.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-118">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="e6bf2-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="e6bf2-119">E.g.</span></span> <span data-ttu-id="e6bf2-120">MySheet\*.xls\* включает такие файлы, как MySheet001.xls и MySheetABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-120">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="e6bf2-121">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="e6bf2-121">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="e6bf2-122">Задает фильтр диапазона времени.</span><span class="sxs-lookup"><span data-stu-id="e6bf2-122">Specifies a time range filter.</span></span> <span data-ttu-id="e6bf2-123">Будут включены файлы, измененные после **TimeRangeFrom** и до **TimeRangeTo** .</span><span class="sxs-lookup"><span data-stu-id="e6bf2-123">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
