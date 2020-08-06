---
title: Редактор назначения «Необработанный файл» (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledestinationconnectionmanager.f1
ms.assetid: a0ec9643-3b44-4467-b855-f45ae4794f7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a693591921a5669eb9bc8160f0be076ab4d6869b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729593"
---
# <a name="raw-file-destination-editor-connection-manager-page"></a><span data-ttu-id="68653-102">Редактор назначения «Необработанный файл» (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="68653-102">Raw File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="68653-103">Для настройки назначения «Необработанный файл» на запись необработанных данных в файл используйте редактор назначения «Необработанный файл».</span><span class="sxs-lookup"><span data-stu-id="68653-103">Use the Raw File Destination Editor to configure the Raw File destination to write raw data to a file.</span></span>  
  
 <span data-ttu-id="68653-104">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="68653-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="68653-105">Открытие редактора назначения «Необработанный файл»</span><span class="sxs-lookup"><span data-stu-id="68653-105">Open the Raw File Destination Editor</span></span>](#open)  
  
-   [<span data-ttu-id="68653-106">Задание параметров на вкладке «Диспетчер соединений»</span><span class="sxs-lookup"><span data-stu-id="68653-106">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="68653-107">Задание параметров на вкладке «Столбцы»</span><span class="sxs-lookup"><span data-stu-id="68653-107">Set options on the Columns tab</span></span>](#mapping)  
  
##  <a name="open-the-raw-file-destination-editor"></a><a name="open"></a><span data-ttu-id="68653-108">Открытие редактора назначения «Необработанный файл»</span><span class="sxs-lookup"><span data-stu-id="68653-108">Open the Raw File Destination Editor</span></span>  
  
1.  <span data-ttu-id="68653-109">Добавление назначения «Необработанный файл» в пакет [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68653-109">Add the Raw File destination to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="68653-110">Щелкните правой кнопкой мыши компонент и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="68653-110">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a><span data-ttu-id="68653-111">Задание параметров на вкладке «Диспетчер соединений»</span><span class="sxs-lookup"><span data-stu-id="68653-111">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="68653-112">**Режим доступа**</span><span class="sxs-lookup"><span data-stu-id="68653-112">**Access mode**</span></span>  
 <span data-ttu-id="68653-113">Выберите порядок указания имени файла.</span><span class="sxs-lookup"><span data-stu-id="68653-113">Select how the file name is specified.</span></span> <span data-ttu-id="68653-114">Выберите пункт **Имя файла** , чтобы ввести имя файла и путь непосредственно, или пункт **Имя файла из переменной** , чтобы указать переменную, содержащую имя файла.</span><span class="sxs-lookup"><span data-stu-id="68653-114">Select **File name** to enter the file name and path directly, of **File name from variable** to specify a variable that contains the file name.</span></span>  
  
 <span data-ttu-id="68653-115">**Имя файла** или **Имя переменной**</span><span class="sxs-lookup"><span data-stu-id="68653-115">**File name** or **Variable name**</span></span>  
 <span data-ttu-id="68653-116">Введите имя необработанного файла и путь к нему или выберите переменную, содержащую имя файла.</span><span class="sxs-lookup"><span data-stu-id="68653-116">Enter the name and path of the raw file, or select the variable that contains the file name.</span></span>  
  
 <span data-ttu-id="68653-117">**Параметр записи**</span><span class="sxs-lookup"><span data-stu-id="68653-117">**Write option**</span></span>  
 <span data-ttu-id="68653-118">Выберите метод, используемый для создания файла и записи в файл.</span><span class="sxs-lookup"><span data-stu-id="68653-118">Select the method used to create and write to the file.</span></span>  
  
 <span data-ttu-id="68653-119">**Создание исходного необработанного файла**</span><span class="sxs-lookup"><span data-stu-id="68653-119">**Generate initial raw file**</span></span>  
 <span data-ttu-id="68653-120">Нажмите эту кнопку для создания пустого необработанного файла, который содержит только столбцы (файл только с метаданными), без необходимости запуска пакета.</span><span class="sxs-lookup"><span data-stu-id="68653-120">Click the button to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="68653-121">Файл содержит столбцы, выбранные на странице **Столбцы** окна **Редактор назначения «Необработанный файл»**.</span><span class="sxs-lookup"><span data-stu-id="68653-121">The file contains the columns that you selected on the **Columns** page of the **Raw File Destination Editor**.</span></span> <span data-ttu-id="68653-122">Можно указать источник «Необработанный файл» в файле, который содержит только эти метаданные.</span><span class="sxs-lookup"><span data-stu-id="68653-122">You can point the Raw File source to this metadata-only file.</span></span>  
  
 <span data-ttu-id="68653-123">После нажатия **Создать исходный необработанный файл**появляется окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="68653-123">When you click **Generate initial raw file**, a message box appears.</span></span> <span data-ttu-id="68653-124">Щелкните **ОК** , чтобы продолжить создание файла.</span><span class="sxs-lookup"><span data-stu-id="68653-124">Click **OK** to proceed with creating the file.</span></span> <span data-ttu-id="68653-125">Щелкните **Отмена** , чтобы выбрать другой список столбцов на странице **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="68653-125">Click **Cancel** to select a different list of columns on the **Columns** page.</span></span>  
  
##  <a name="set-options-on-the-columns-tab"></a><a name="mapping"></a><span data-ttu-id="68653-126">Задание параметров на вкладке «столбцы»</span><span class="sxs-lookup"><span data-stu-id="68653-126">Set options on the Columns tab</span></span>  
 <span data-ttu-id="68653-127">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="68653-127">**Available Input Columns**</span></span>  
 <span data-ttu-id="68653-128">Выберите один или несколько входных столбцов для записи в необработанный файл.</span><span class="sxs-lookup"><span data-stu-id="68653-128">Select one or more input columns to write to the raw file.</span></span>  
  
 <span data-ttu-id="68653-129">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="68653-129">**Input Column**</span></span>  
 <span data-ttu-id="68653-130">Входной столбец автоматически добавляется в эту таблицу во время выбора в списке **Доступные входные столбцы**. Также можно выбрать входной столбец непосредственно в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="68653-130">An input column is automatically added to this table when you select it under **Available Input Columns**, or you can select the input column directly in this table.</span></span>  
  
 <span data-ttu-id="68653-131">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="68653-131">**Output Alias**</span></span>  
 <span data-ttu-id="68653-132">Укажите альтернативное имя для выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="68653-132">Specify an alternate name to use for the output column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68653-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="68653-133">See Also</span></span>  
 [<span data-ttu-id="68653-134">Назначение «Необработанный файл»</span><span class="sxs-lookup"><span data-stu-id="68653-134">Raw File Destination</span></span>](data-flow/raw-file-destination.md)  
  
  
