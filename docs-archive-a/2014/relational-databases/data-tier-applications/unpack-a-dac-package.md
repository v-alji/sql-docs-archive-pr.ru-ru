---
title: Распаковка пакета DAC | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- wizard [DAC], unpack
- data-tier application [SQL Server], unpack
- How to [DAC], unpack
- unpack DAC
ms.assetid: 697b69b3-f157-4e22-ac4e-f65c5fc2d0ad
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ba0930f79a47696a6c9a9c1bfe028316601f64b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668896"
---
# <a name="unpack-a-dac-package"></a><span data-ttu-id="3584a-102">Распаковка пакета DAC</span><span class="sxs-lookup"><span data-stu-id="3584a-102">Unpack a DAC Package</span></span>
  <span data-ttu-id="3584a-103">Чтобы распаковать скрипты и файлы из пакета приложения уровня данных (DAC), используйте диалоговое окно «Распаковка приложения уровня данных».</span><span class="sxs-lookup"><span data-stu-id="3584a-103">Use the Unpack Data-tier Application dialog box to unzip the scripts and files from a data-tier application (DAC) package.</span></span> <span data-ttu-id="3584a-104">Скрипты и файлы помещаются в папку, где их можно просмотреть перед тем, как использовать пакет для развертывания приложения уровня данных в рабочей системе.</span><span class="sxs-lookup"><span data-stu-id="3584a-104">The scripts and files are placed in a folder where they can be reviewed before the package is used to deploy the DAC into a production system.</span></span> <span data-ttu-id="3584a-105">Кроме того, содержимое одного приложения уровня данных можно сравнить с содержимым другого пакета, распакованного в другую папку.</span><span class="sxs-lookup"><span data-stu-id="3584a-105">The contents of one DAC can also be compared with the contents of another package unpacked to another folder.</span></span>  
  
1.  <span data-ttu-id="3584a-106">**Перед началом работы**  [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="3584a-106">**Before you begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="3584a-107">**Распаковка приложения уровня данных с использованием:**  [диалогового окна распаковки приложения уровня данных](#UnpackDACDial), [изучения содержимого пакета приложения уровня данных](#ExamDACPack)</span><span class="sxs-lookup"><span data-stu-id="3584a-107">**To unpack a DAC, using:**  [Unpack Data-tier Application Dialog](#UnpackDACDial), [Examine the Contents of a DAC Package](#ExamDACPack)</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3584a-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="3584a-108">Security</span></span>  
 <span data-ttu-id="3584a-109">Рекомендуется не выполнять развертывание пакетов DAC, полученных из неизвестных или ненадежных источников.</span><span class="sxs-lookup"><span data-stu-id="3584a-109">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="3584a-110">В этих пакетах может содержаться вредоносный код, вызывающий выполнение непредусмотренных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] или появление ошибок из-за изменения схемы.</span><span class="sxs-lookup"><span data-stu-id="3584a-110">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="3584a-111">Перед тем как использовать приложение уровня данных, полученное из неизвестного или ненадежного источника, разверните его на изолированном тестовом экземпляре компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)], распакуйте приложение уровня данных и изучите его код, например хранимые процедуры или другой определенный пользователем код.</span><span class="sxs-lookup"><span data-stu-id="3584a-111">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], unpack the DAC and examine the code, such as stored procedures or other user-defined code.</span></span>  
  
##  <a name="unpack-data-tier-application-dialog"></a><a name="UnpackDACDial"></a> <span data-ttu-id="3584a-112">диалоговое окно распаковки приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="3584a-112">Unpack Data-tier Application Dialog</span></span>  
 <span data-ttu-id="3584a-113">**Распаковка файла пакета приложения уровня данных**</span><span class="sxs-lookup"><span data-stu-id="3584a-113">**To Unpack a DAC Package File**</span></span>  
  
-   <span data-ttu-id="3584a-114">В **проводнике**перейдите к местоположению файла пакета приложения уровня данных (с расширением DACPAC).</span><span class="sxs-lookup"><span data-stu-id="3584a-114">In **Windows Explorer**, navigate to the location of a DAC package (.dacpac) file.</span></span>  
  
-   <span data-ttu-id="3584a-115">Используйте один из следующих двух методов для открытия диалога распаковки приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="3584a-115">Use one of these two methods to open the Unpack Data-tier Application dialog:</span></span>  
  
    1.  <span data-ttu-id="3584a-116">Щелкните правой кнопкой мыши файл пакета приложения уровня данных (с расширением DACPAC) и выберите команду **Распаковать**.</span><span class="sxs-lookup"><span data-stu-id="3584a-116">Right-click the DAC package (.dacpac) file and select **Unpack**.</span></span>  
  
    2.  <span data-ttu-id="3584a-117">Дважды щелкните файл пакета приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="3584a-117">Double-click the DAC package file.</span></span>  
  
-   <span data-ttu-id="3584a-118">Выполните шаги в диалоговых окнах.</span><span class="sxs-lookup"><span data-stu-id="3584a-118">Complete the dialogs:</span></span>  
  
    -   [<span data-ttu-id="3584a-119">Распаковать файл пакета Microsoft SQL Server DAC</span><span class="sxs-lookup"><span data-stu-id="3584a-119">Unpack Microsoft SQL Server DAC Package File</span></span>](#Unpack)  
  
    -   [<span data-ttu-id="3584a-120">Выбор папки</span><span class="sxs-lookup"><span data-stu-id="3584a-120">Browse for Folder</span></span>](#Browse)  
  
###  <a name="unpack-microsoft-sql-server-dac-package-file"></a><a name="Unpack"></a> <span data-ttu-id="3584a-121">Распаковать файл пакета Microsoft SQL Server DAC</span><span class="sxs-lookup"><span data-stu-id="3584a-121">Unpack Microsoft SQL Server DAC Package File</span></span>  
 <span data-ttu-id="3584a-122">На этой странице указывается целевая папка, в которую будут помещены файлы пакета, а затем запускается операция распаковки.</span><span class="sxs-lookup"><span data-stu-id="3584a-122">Use this page to specify the destination folder in which to place the unpacked files, and then run the unpack operation.</span></span>  
  
 <span data-ttu-id="3584a-123">**Файлы будут распакованы в следующую папку:** — укажите полный путь к папке для распакованных файлов.</span><span class="sxs-lookup"><span data-stu-id="3584a-123">**Files will be unpacked to this folder:** - Specify the full path to the folder for the unpacked files.</span></span> <span data-ttu-id="3584a-124">Если папка существует и полный путь к ней известен, введите его в это поле.</span><span class="sxs-lookup"><span data-stu-id="3584a-124">If the folder exists and you know the full path, type the path in the box.</span></span> <span data-ttu-id="3584a-125">Если нет, нажмите кнопку **Обзор** , чтобы перейти к папке или создать новую.</span><span class="sxs-lookup"><span data-stu-id="3584a-125">If not, click the **Browse** button to navigate to a folder or create a new folder.</span></span>  
  
 <span data-ttu-id="3584a-126">**Обзор** — открывает страницу **Выбор папки** , на которой можно выбрать папку, перемещаясь по иерархии файлов, или создать новую папку.</span><span class="sxs-lookup"><span data-stu-id="3584a-126">**Browse** - Opens the **Browse for Folder** page where you can choose a folder by navigating the file hierarchy, or create a new folder.</span></span>  
  
 <span data-ttu-id="3584a-127">**Распаковать** — запускает операцию распаковки.</span><span class="sxs-lookup"><span data-stu-id="3584a-127">**Unpack** - Starts the unpack operation.</span></span>  
  
 <span data-ttu-id="3584a-128">**Отмена** — закрывает диалоговое окно без распаковки пакета приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="3584a-128">**Cancel** - Terminates the dialog box without unpacking the DAC package.</span></span>  
  
###  <a name="browse-for-folder"></a><a name="Browse"></a> <span data-ttu-id="3584a-129">Выбор папки</span><span class="sxs-lookup"><span data-stu-id="3584a-129">Browse for Folder</span></span>  
 <span data-ttu-id="3584a-130">Эта страница используется для выбора целевой папки для операции распаковки.</span><span class="sxs-lookup"><span data-stu-id="3584a-130">Use this page to choose the destination folder for the unpack operation.</span></span> <span data-ttu-id="3584a-131">Кроме того, можно создать новую папку.</span><span class="sxs-lookup"><span data-stu-id="3584a-131">Optionally, you can also create a new folder.</span></span>  
  
 <span data-ttu-id="3584a-132">**Список папок** — отображает иерархию файлов компьютера.</span><span class="sxs-lookup"><span data-stu-id="3584a-132">**Folder list** - Displays the file hierarchy for your computer.</span></span> <span data-ttu-id="3584a-133">Раскрывайте узлы, чтобы перейти к папке, в которую будет распакован пакет приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="3584a-133">Expand the nodes to navigate to the folder in which to unpack the DAC package.</span></span> <span data-ttu-id="3584a-134">Щелкните папку, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3584a-134">Click on the folder and then click **OK**.</span></span>  
  
 <span data-ttu-id="3584a-135">**Создать папку** — открывает диалоговое окно, в котором можно указать имя папки, создаваемой в папке, выделенной в иерархии папок.</span><span class="sxs-lookup"><span data-stu-id="3584a-135">**Make New Folder** - Opens a dialog in which you can specify the name for a new folder to be created in the folder you have currently selected in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="3584a-136">**ОК** — помещает путь к выбранной папке в поле **Файлы будут распакованы в следующую папку** на странице **Распаковка файла пакета приложения уровня данных** и возвращает пользователя на эту страницу.</span><span class="sxs-lookup"><span data-stu-id="3584a-136">**OK** - Places the path to the folder you selected in the **Files will be unpacked to this folder** box of the **Unpack DAC Package File** page and returns you to that page.</span></span>  
  
 <span data-ttu-id="3584a-137">**Отмена** — закрывает диалоговое окно без выбора папки.</span><span class="sxs-lookup"><span data-stu-id="3584a-137">**Cancel** - Terminates the dialog box without selecting a folder.</span></span>  
  
##  <a name="examine-the-contents-of-a-dac-package"></a><a name="ExamDACPack"></a> <span data-ttu-id="3584a-138">изучение содержимого пакета приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="3584a-138">Examine the Contents of a DAC Package</span></span>  
 <span data-ttu-id="3584a-139">Распаковав пакет, можно изучить файлы, созданные диалоговым окном **Распаковка приложения уровня данных** .</span><span class="sxs-lookup"><span data-stu-id="3584a-139">After unpacking the package, you can examine the files produced by the **Unpack Data-tier Application** dialog.</span></span> <span data-ttu-id="3584a-140">Это диалоговое окно создает в указанной целевой папке следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="3584a-140">The dialog box builds the following files in the selected destination folder:</span></span>  
  
1.  <span data-ttu-id="3584a-141">Скрипт Transact-SQL, содержащий инструкции для создания объектов, определенных в приложении уровня данных.</span><span class="sxs-lookup"><span data-stu-id="3584a-141">A Transact-SQL script that contains the statements for creating the objects defined in the DAC.</span></span> <span data-ttu-id="3584a-142">Файл имеет следующее имя: *Имя_приложения_уровня_данных*.sql, где *Имя_приложения_уровня_данных* — это имя приложения уровня данных.</span><span class="sxs-lookup"><span data-stu-id="3584a-142">The file name is *DACName*.sql, where *DACName* is the name of the DAC.</span></span>  
  
2.  <span data-ttu-id="3584a-143">Все XML-файлы из пакета.</span><span class="sxs-lookup"><span data-stu-id="3584a-143">All XML files from the package.</span></span>  
  
3.  <span data-ttu-id="3584a-144">Все файлы из раздела приложения уровня данных «Extra Files», например файлы приложения уровня данных, выполняемые перед развертыванием и после.</span><span class="sxs-lookup"><span data-stu-id="3584a-144">All files from the Extra Files section of the DAC, such as the DAC pre-deployment or post-deployment files.</span></span>  
  
 <span data-ttu-id="3584a-145">Дополнительные сведения см. в статье [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="3584a-145">For more information, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3584a-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="3584a-146">See Also</span></span>  
 <span data-ttu-id="3584a-147">[Приложения уровня данных](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="3584a-147">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="3584a-148">[Развертывание приложения уровня данных](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="3584a-148">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="3584a-149">Обновление приложения уровня данных</span><span class="sxs-lookup"><span data-stu-id="3584a-149">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
  
  
