---
title: Задача "Файловая система" для Azure Data Lake Store | Документы Майкрософт
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSTASK.F1
- SQL11.DTS.DESIGNER.AFPADLSTASK.F1
ms.assetid: 02b9edd7-6ef9-463e-abbf-e1830bcae875
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bc37e774c5346190635e50259deb47f2f22a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665515"
---
# <a name="azure-data-lake-store-file-system-task"></a><span data-ttu-id="949b0-102">Задача "Файловая система" для Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="949b0-102">Azure Data Lake Store File System Task</span></span>

<span data-ttu-id="949b0-103">**Задача "файловая система" Azure Data Lake Store** позволяет пользователям выполнять различные операции с файловой системой на [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span><span class="sxs-lookup"><span data-stu-id="949b0-103">The **Azure Data Lake Store File System Task** enables users to perform various file system operations on [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span></span>

<span data-ttu-id="949b0-104">Чтобы добавить в пакет задачу "Файловая система" для Azure Data Lake Store, перетащите ее с панели элементов служб SSIS на панель холста конструктора.</span><span class="sxs-lookup"><span data-stu-id="949b0-104">To add an Azure Data Lake Store File System Task to a package, drag it from SSIS Toolbox to the designer canvas.</span></span> <span data-ttu-id="949b0-105">Дважды щелкните задачу или щелкните ее правой кнопкой мыши и выберите **изменить**, чтобы открыть диалоговое окно Редактор задачи.</span><span class="sxs-lookup"><span data-stu-id="949b0-105">Then double-click the task, or right-click the task and select **Edit**, to open the task editor dialog box.</span></span>

<span data-ttu-id="949b0-106">Операция файловой системы, которая будет выполнена, задается свойством **Операция**.</span><span class="sxs-lookup"><span data-stu-id="949b0-106">The **Operation** property specifies the file system operation to perform.</span></span> <span data-ttu-id="949b0-107">Поддерживаются следующие операции:</span><span class="sxs-lookup"><span data-stu-id="949b0-107">The following operations are supported.</span></span>

* <span data-ttu-id="949b0-108">**CopyToADLS**. Загрузка файлов в ADLS.</span><span class="sxs-lookup"><span data-stu-id="949b0-108">**CopyToADLS:** Upload files to ADLS.</span></span>
* <span data-ttu-id="949b0-109">**CopyFromADLS**. Скачивание файлов из ADLS.</span><span class="sxs-lookup"><span data-stu-id="949b0-109">**CopyFromADLS:** Download files from ADLS.</span></span>

<span data-ttu-id="949b0-110">Для любой операции необходимо указать диспетчер подключений Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="949b0-110">For any operation, you have to specify an Azure Data Lake connection manager.</span></span>

<span data-ttu-id="949b0-111">Ниже приведены описания свойств, характерных для каждой операции.</span><span class="sxs-lookup"><span data-stu-id="949b0-111">Here are the descriptions of the properties specific to each operation.</span></span>

## <a name="copytoadls"></a><span data-ttu-id="949b0-112">CopyToADLS</span><span class="sxs-lookup"><span data-stu-id="949b0-112">CopyToADLS</span></span>

* <span data-ttu-id="949b0-113">**LocalDirectory:** Указывает исходный каталог, содержащий файлы для отправки.</span><span class="sxs-lookup"><span data-stu-id="949b0-113">**LocalDirectory:** Specifies the source directory which contains files to upload.</span></span>
* <span data-ttu-id="949b0-114">**FileNamePattern**. Определяет фильтр имен для исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="949b0-114">**FileNamePattern:** Specifies a file name filter for source files.</span></span> <span data-ttu-id="949b0-115">Будут отправлены только те файлы, имя которых соответствует указанному шаблону.</span><span class="sxs-lookup"><span data-stu-id="949b0-115">Only files whose name matches the specified pattern will be uploaded.</span></span> <span data-ttu-id="949b0-116">Поддерживаются подстановочные знаки `*` и `?`.</span><span class="sxs-lookup"><span data-stu-id="949b0-116">Wildcards `*` and `?` are supported.</span></span>
* <span data-ttu-id="949b0-117">**SearchRecursively**. Указывает, следует ли выполнять рекурсивный поиск файлов для загрузки в каталоге источника.</span><span class="sxs-lookup"><span data-stu-id="949b0-117">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to upload.</span></span>
* <span data-ttu-id="949b0-118">**AzureDataLakeDirectory**. Указывает каталог назначения ADLS, в который будут загружены файлы.</span><span class="sxs-lookup"><span data-stu-id="949b0-118">**AzureDataLakeDirectory:** Specifies the ADLS destination directory to upload files to.</span></span>
* <span data-ttu-id="949b0-119">**Филикспири:** Указывает дату и время истечения срока действия файлов, отправленных в ADLS, или оставьте это свойство пустым, чтобы указать, что срок действия файлов никогда не истечет.</span><span class="sxs-lookup"><span data-stu-id="949b0-119">**FileExpiry:** Specifies an expiration date and time for the files uploaded to ADLS, or leave this property blank to indicate that the files never expire.</span></span>

## <a name="copyfromadls"></a><span data-ttu-id="949b0-120">CopyFromADLS</span><span class="sxs-lookup"><span data-stu-id="949b0-120">CopyFromADLS</span></span>

* <span data-ttu-id="949b0-121">**AzureDataLakeDirectory**. Указывает каталог источника ADLS, в котором содержатся файлы для скачивания.</span><span class="sxs-lookup"><span data-stu-id="949b0-121">**AzureDataLakeDirectory:** Specifies the ADLS source directory which contains the files to download.</span></span>
* <span data-ttu-id="949b0-122">**SearchRecursively**. Указывает, следует ли выполнять рекурсивный поиск файлов для скачивания в каталоге источника.</span><span class="sxs-lookup"><span data-stu-id="949b0-122">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to download.</span></span>
* <span data-ttu-id="949b0-123">**LocalDirectory**. Указывает каталог назначения, в который будут сохранены скачанные файлы.</span><span class="sxs-lookup"><span data-stu-id="949b0-123">**LocalDirectory:** Specifies the destination directory to store downloaded files.</span></span>
