---
title: Задача "Очистка после обслуживания" (план обслуживания) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.cleanup.f1
helpviewer_keywords:
- Maintenance Cleanup Task dialog box
ms.assetid: 022b679c-6799-4c13-9185-814224a20412
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9023881ff5cf5ba5ddd8c61aa179c5881162bf44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664895"
---
# <a name="maintenance-cleanup-task-maintenance-plan"></a><span data-ttu-id="d8862-102">Задача «Очистка после обслуживания» (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="d8862-102">Maintenance Cleanup Task (Maintenance Plan)</span></span>
  <span data-ttu-id="d8862-103">С помощью диалогового окна **Задача «Очистка после обслуживания»** можно удалить старые файлы, связанные с планами обслуживания, включая текстовые отчеты, созданные планами обслуживания, и файлы резервных копий базы данных.</span><span class="sxs-lookup"><span data-stu-id="d8862-103">Use the **Maintenance Cleanup Task** to remove old files related to maintenance plans, including text reports created by maintenance plans and database backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8862-104">Задача «Очистка после обслуживания» автоматически не удаляет файлы во вложенных папках указанного каталога.</span><span class="sxs-lookup"><span data-stu-id="d8862-104">The Maintenance Cleanup task does not automatically delete files in the subfolders of the specified directory.</span></span> <span data-ttu-id="d8862-105">Это снижает вероятность того, что злоумышленник сможет удалить файлы с помощью задачи «Очистка после обслуживания».</span><span class="sxs-lookup"><span data-stu-id="d8862-105">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span> <span data-ttu-id="d8862-106">Если нужно удалять файлы во вложенных папках первого уровня, установите флажок **Включить вложенные папки первого уровня**.</span><span class="sxs-lookup"><span data-stu-id="d8862-106">If you want to delete files in first-level subfolders, you must select **Include first-level subfolders**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d8862-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8862-107">Options</span></span>  
 <span data-ttu-id="d8862-108">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="d8862-108">**Connection**</span></span>  
 <span data-ttu-id="d8862-109">Отображает текущее соединение.</span><span class="sxs-lookup"><span data-stu-id="d8862-109">Displays the current connection.</span></span>  
  
 <span data-ttu-id="d8862-110">**Создать**</span><span class="sxs-lookup"><span data-stu-id="d8862-110">**New**</span></span>  
 <span data-ttu-id="d8862-111">Создать новое соединение с сервером для его использования при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="d8862-111">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="d8862-112">Диалоговое окно **Создание соединения** описано ниже.</span><span class="sxs-lookup"><span data-stu-id="d8862-112">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="d8862-113">**Файлы резервных копий**</span><span class="sxs-lookup"><span data-stu-id="d8862-113">**Backup files**</span></span>  
 <span data-ttu-id="d8862-114">Удаляет файлы резервной копии.</span><span class="sxs-lookup"><span data-stu-id="d8862-114">Delete backup files.</span></span>  
  
 <span data-ttu-id="d8862-115">**Текстовые отчеты плана обслуживания**</span><span class="sxs-lookup"><span data-stu-id="d8862-115">**Maintenance Plan text reports**</span></span>  
 <span data-ttu-id="d8862-116">Удаляет текстовые отчеты предыдущих запусков планов обслуживания.</span><span class="sxs-lookup"><span data-stu-id="d8862-116">Delete text reports of previously run maintenance plans.</span></span>  
  
 <span data-ttu-id="d8862-117">**Удалить определенный файл**</span><span class="sxs-lookup"><span data-stu-id="d8862-117">**Delete specific file**</span></span>  
 <span data-ttu-id="d8862-118">Удаляет определенный файл, указанный в поле **Имя файла** .</span><span class="sxs-lookup"><span data-stu-id="d8862-118">Delete the specific file provided in the **File name** box.</span></span>  
  
 <span data-ttu-id="d8862-119">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="d8862-119">**File name**</span></span>  
 <span data-ttu-id="d8862-120">Путь к удаляемому файлу и его имя.</span><span class="sxs-lookup"><span data-stu-id="d8862-120">Path and name of the file to be deleted.</span></span>  
  
 <span data-ttu-id="d8862-121">**Удалить из папки файлы с определенным расширением**</span><span class="sxs-lookup"><span data-stu-id="d8862-121">**Search folder and delete files based on an extension**</span></span>  
 <span data-ttu-id="d8862-122">Удаляет все файлы с определенным расширением в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="d8862-122">Delete all files with the specified extension in the specified folder.</span></span> <span data-ttu-id="d8862-123">Позволяет удалить сразу несколько файлов, например все файлы резервных копий с расширением BAK из папки «Вторник».</span><span class="sxs-lookup"><span data-stu-id="d8862-123">Use this to delete multiple files at once, such as all backup files with the .bak extension, in the Tuesday folder.</span></span>  
  
 <span data-ttu-id="d8862-124">**Папка**</span><span class="sxs-lookup"><span data-stu-id="d8862-124">**Folder**</span></span>  
 <span data-ttu-id="d8862-125">Путь к папке, содержащей удаляемые файлы, и ее имя.</span><span class="sxs-lookup"><span data-stu-id="d8862-125">Path and name of the folder containing the files to be deleted.</span></span>  
  
 <span data-ttu-id="d8862-126">**Расширение файла**</span><span class="sxs-lookup"><span data-stu-id="d8862-126">**File extension**</span></span>  
 <span data-ttu-id="d8862-127">Введите расширение удаляемых файлов.</span><span class="sxs-lookup"><span data-stu-id="d8862-127">Provide the file extension of the files to be deleted.</span></span>  
  
 <span data-ttu-id="d8862-128">**Включить вложенные папки первого уровня**</span><span class="sxs-lookup"><span data-stu-id="d8862-128">**Include first-level subfolders**</span></span>  
 <span data-ttu-id="d8862-129">Удаляет файлы с расширением, заданным в поле **Расширение файла** , из вложенных папок первого уровня относительно поля **Папка**.</span><span class="sxs-lookup"><span data-stu-id="d8862-129">Delete files with the extension specified for **File extension** from first-level subfolders under **Folder**.</span></span>  
  
 <span data-ttu-id="d8862-130">**Удалять файлы в зависимости от их возраста во время выполнения задачи**</span><span class="sxs-lookup"><span data-stu-id="d8862-130">**Delete files based on the age of the file at task run time**</span></span>  
 <span data-ttu-id="d8862-131">Задайте минимальный возраст удаляемых файлов, указав числовое значение и единицу времени в поле **Удалить все файлы старше чем** .</span><span class="sxs-lookup"><span data-stu-id="d8862-131">Specify the minimum age of the files that you want to delete by providing a number, and unit of time in the **Delete files older than the following** box.</span></span>  
  
 <span data-ttu-id="d8862-132">**Удалить все файлы старше чем**</span><span class="sxs-lookup"><span data-stu-id="d8862-132">**Delete files older than the following**</span></span>  
 <span data-ttu-id="d8862-133">Задайте минимальный возраст удаляемых файлов, указав числовое значение и временную единицу (день, неделя, месяц или год).</span><span class="sxs-lookup"><span data-stu-id="d8862-133">Specify the minimum age of the files that you want to delete by providing a number, and unit of time (Day, Week, Month, or Year).</span></span> <span data-ttu-id="d8862-134">Файлы, старше указанного временного интервала, будут удалены.</span><span class="sxs-lookup"><span data-stu-id="d8862-134">Files older than the time frame specified will be deleted.</span></span>  
  
 <span data-ttu-id="d8862-135">**Просмотр T-SQL**</span><span class="sxs-lookup"><span data-stu-id="d8862-135">**View T-SQL**</span></span>  
 <span data-ttu-id="d8862-136">Просмотрите инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняемые для данной задачи по отношению к серверу, на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="d8862-136">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8862-137">Если количество затронутых объектов велико, построение этого отображения может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="d8862-137">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="d8862-138">Диалоговое окно «Создание соединения»</span><span class="sxs-lookup"><span data-stu-id="d8862-138">New Connection Dialog Box</span></span>  
 <span data-ttu-id="d8862-139">**Имя соединения**</span><span class="sxs-lookup"><span data-stu-id="d8862-139">**Connection name**</span></span>  
 <span data-ttu-id="d8862-140">Введите имя нового соединения.</span><span class="sxs-lookup"><span data-stu-id="d8862-140">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="d8862-141">**Выберите или введите имя сервера**</span><span class="sxs-lookup"><span data-stu-id="d8862-141">**Select or enter a server name**</span></span>  
 <span data-ttu-id="d8862-142">Выберите сервер для подключения при выполнении этой задачи.</span><span class="sxs-lookup"><span data-stu-id="d8862-142">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="d8862-143">**...**</span><span class="sxs-lookup"><span data-stu-id="d8862-143">**...**</span></span>  
 <span data-ttu-id="d8862-144">Выберите для просмотра списка доступных серверов.</span><span class="sxs-lookup"><span data-stu-id="d8862-144">Select to view the list of available servers.</span></span>  
  
 <span data-ttu-id="d8862-145">**Введите данные для входа на сервер**</span><span class="sxs-lookup"><span data-stu-id="d8862-145">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="d8862-146">Укажите способ проверки подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="d8862-146">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="d8862-147">**Использовать встроенную безопасность Windows**</span><span class="sxs-lookup"><span data-stu-id="d8862-147">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="d8862-148">Подключение к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d8862-148">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="d8862-149">**Использовать указанные имя пользователя и пароль**</span><span class="sxs-lookup"><span data-stu-id="d8862-149">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="d8862-150">Подключение к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] с использованием проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d8862-150">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="d8862-151">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="d8862-151">This option is not available.</span></span>  
  
 <span data-ttu-id="d8862-152">**User name**</span><span class="sxs-lookup"><span data-stu-id="d8862-152">**User name**</span></span>  
 <span data-ttu-id="d8862-153">Укажите имя входа, используемое при проверке подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8862-153">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="d8862-154">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="d8862-154">This option is not available.</span></span>  
  
 <span data-ttu-id="d8862-155">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="d8862-155">**Password**</span></span>  
 <span data-ttu-id="d8862-156">Укажите используемый при проверке подлинности пароль.</span><span class="sxs-lookup"><span data-stu-id="d8862-156">Provide a password to use when authenticating.</span></span> <span data-ttu-id="d8862-157">Этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="d8862-157">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8862-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8862-158">See Also</span></span>  
 [<span data-ttu-id="d8862-159">Планы обслуживания</span><span class="sxs-lookup"><span data-stu-id="d8862-159">Maintenance Plans</span></span>](maintenance-plans.md)  
  
  
