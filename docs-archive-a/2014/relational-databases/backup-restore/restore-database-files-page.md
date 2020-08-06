---
title: Восстановление базы данных (страница "Файлы") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoredb.files.f1 in the code
- sql12.swb.restoredb.files.f1
ms.assetid: 714c36ea-a9f9-43a4-99f9-a6f73d1baf8e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: edffd9454b51ea80a18311f735d29407f97f6eb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666679"
---
# <a name="restore-database-files-page"></a><span data-ttu-id="3581d-102">Восстановление базы данных (страница «Файлы»)</span><span class="sxs-lookup"><span data-stu-id="3581d-102">Restore Database (Files Page)</span></span>
  <span data-ttu-id="3581d-103">Используйте страницу **Файлы** диалогового окна **Восстановление базы данных** для выбора конкретных файлов, из которых будет восстановлена база данных.</span><span class="sxs-lookup"><span data-stu-id="3581d-103">Use the **Files** page of the **Restore Database** dialog box to manage the specific files you have chosen to restore within the database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3581d-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="3581d-104">Options</span></span>  
  
### <a name="restore-database-files-as"></a><span data-ttu-id="3581d-105">Восстановить файлы базы данных как</span><span class="sxs-lookup"><span data-stu-id="3581d-105">Restore database files as</span></span>  
 <span data-ttu-id="3581d-106">Используйте, чтобы назначить новый путь к восстановленным файлам и управлять им.</span><span class="sxs-lookup"><span data-stu-id="3581d-106">Use to assign and manage the new file path to the restored files.</span></span>  
  
 <span data-ttu-id="3581d-107">**Переместить все файлы в папку**</span><span class="sxs-lookup"><span data-stu-id="3581d-107">**Relocate all files to folder**</span></span>  
 <span data-ttu-id="3581d-108">Перемещение восстановленных файлов.</span><span class="sxs-lookup"><span data-stu-id="3581d-108">Relocates restored files.</span></span>  
  
|<span data-ttu-id="3581d-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="3581d-109">Option</span></span>|<span data-ttu-id="3581d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3581d-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3581d-111">**Папка файла данных**</span><span class="sxs-lookup"><span data-stu-id="3581d-111">**Data file folder**</span></span>|<span data-ttu-id="3581d-112">Введите или выполните поиск имени папки файла данных, в которую нужно переместить восстановленный файл или файлы данных.</span><span class="sxs-lookup"><span data-stu-id="3581d-112">Enter or search for the data file folder name that the restored data file or files should be relocated to.</span></span>|  
|<span data-ttu-id="3581d-113">**Папка файлов журнала**</span><span class="sxs-lookup"><span data-stu-id="3581d-113">**Log file folder**</span></span>|<span data-ttu-id="3581d-114">Введите или выполните поиск файла журнала или папки файлов, в которую нужно переместить восстановленный файл журнала.</span><span class="sxs-lookup"><span data-stu-id="3581d-114">Enter or search for the log file or files folder that the restored log file should be relocated to.</span></span>|  
  
 <span data-ttu-id="3581d-115">**Логическое имя файла**</span><span class="sxs-lookup"><span data-stu-id="3581d-115">**Logical File Name**</span></span>  
 <span data-ttu-id="3581d-116">Отображает одну строку для каждого восстанавливаемого файла базы данных.</span><span class="sxs-lookup"><span data-stu-id="3581d-116">Displays one row for each database file to be restored.</span></span>  
  
 <span data-ttu-id="3581d-117">**Тип файла**</span><span class="sxs-lookup"><span data-stu-id="3581d-117">**File Type**</span></span>  
 <span data-ttu-id="3581d-118">Отображает тип файла.</span><span class="sxs-lookup"><span data-stu-id="3581d-118">Displays the file type.</span></span>  
  
 <span data-ttu-id="3581d-119">**Имя исходного файла**</span><span class="sxs-lookup"><span data-stu-id="3581d-119">**Original File Name**</span></span>  
 <span data-ttu-id="3581d-120">Отображает исходный путь к файлу для каждого восстанавливаемого файла базы данных.</span><span class="sxs-lookup"><span data-stu-id="3581d-120">Displays the original file path for the restored file.</span></span>  
  
 <span data-ttu-id="3581d-121">**Восстановить как**</span><span class="sxs-lookup"><span data-stu-id="3581d-121">**Restore As**</span></span>  
 <span data-ttu-id="3581d-122">Перечисляет имена файлов, в которых будут сохранены восстанавливаемые файлы.</span><span class="sxs-lookup"><span data-stu-id="3581d-122">Lists the file names that the restored files are to be saved as.</span></span> <span data-ttu-id="3581d-123">Введите или найдите соответствующее имя файла.</span><span class="sxs-lookup"><span data-stu-id="3581d-123">Enter or search for the appropriate file name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3581d-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="3581d-124">See Also</span></span>  
 <span data-ttu-id="3581d-125">[Восстановление базы данных (страница "Общие")](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="3581d-125">[Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="3581d-126">[Восстановление базы данных (страница "Параметры")](restore-database-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="3581d-126">[Restore Database &#40;Options Page&#41;](restore-database-options-page.md) </span></span>  
 <span data-ttu-id="3581d-127">[Аргументы инструкции RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3581d-127">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="3581d-128">[Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3581d-128">[Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span></span>  
 [<span data-ttu-id="3581d-129">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3581d-129">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
