---
title: Задание параметров обработки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services deployments, processing options
- input files [Analysis Services]
- deploying [Analysis Services], processing options
- modifying processing options
- Analysis Services Deployment Wizard, processing options
ms.assetid: e9e50817-908e-4210-bc3d-8e2957568241
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9690aaa7e1d3b3870eb6ab01630b98027263655f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728882"
---
# <a name="specifying-processing-options"></a><span data-ttu-id="2c01c-102">Указание параметров обработки</span><span class="sxs-lookup"><span data-stu-id="2c01c-102">Specifying Processing Options</span></span>
  <span data-ttu-id="2c01c-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]Мастер развертывания считывает параметры обработки из \<*project name*> файла deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="2c01c-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the processing options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="2c01c-104">создает этот файл при сборке [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="2c01c-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="2c01c-105">использует параметры обработки, указанные на странице **развертывание** *\<project name>* диалогового окна **страницы свойств** , для создания \<*project name*> файла deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="2c01c-105">uses the processing options specified on the **Deployment** page of *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.deploymentoptions file.</span></span>  
  
## <a name="reviewing-the-processing-options-for-deployment"></a><span data-ttu-id="2c01c-106">Просмотр параметров обработки для развертывания</span><span class="sxs-lookup"><span data-stu-id="2c01c-106">Reviewing the Processing Options for Deployment</span></span>  
 <span data-ttu-id="2c01c-107">Ниже приведены параметры конфигурации, хранящиеся в \<*project name*> файле deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="2c01c-107">The configuration settings stored within the \<*project name*>.deploymentoptions file are as follows:</span></span>  
  
-   <span data-ttu-id="2c01c-108">**Метод обработки** Эта настройка контролирует, обрабатываются ли развернутые объекты после развертывания, а также тип обработки, который будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="2c01c-108">**Processing Method** This setting controls whether the deployed objects are processed after deployment and the type of processing that will be performed.</span></span> <span data-ttu-id="2c01c-109">Существуют три параметра обработки.</span><span class="sxs-lookup"><span data-stu-id="2c01c-109">There are three processing options:</span></span>  
  
    -   <span data-ttu-id="2c01c-110">Обработка по умолчанию (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="2c01c-110">Default processing (default)</span></span>  
  
    -   <span data-ttu-id="2c01c-111">Полная обработка.</span><span class="sxs-lookup"><span data-stu-id="2c01c-111">Full processing</span></span>  
  
    -   <span data-ttu-id="2c01c-112">Нет</span><span class="sxs-lookup"><span data-stu-id="2c01c-112">None</span></span>  
  
-   <span data-ttu-id="2c01c-113">**Параметры таблицы обратной записи.** Если включена обратная запись для проекта служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , то эта настройка определяет обработку обратной записи.</span><span class="sxs-lookup"><span data-stu-id="2c01c-113">**Writeback Table Options** If writeback is enabled in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, this setting defines how writeback is handled.</span></span> <span data-ttu-id="2c01c-114">Существуют три параметра таблицы обратной записи.</span><span class="sxs-lookup"><span data-stu-id="2c01c-114">There are three writeback table options:</span></span>  
  
    -   <span data-ttu-id="2c01c-115">По умолчанию: если таблица обратной записи существует, то она будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="2c01c-115">By default, if a writeback table exists, it will be used.</span></span> <span data-ttu-id="2c01c-116">Если таблицы обратной записи не существует, то будет создана новая таблица обратной записи.</span><span class="sxs-lookup"><span data-stu-id="2c01c-116">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="2c01c-117">Если таблица обратной записи уже существует, то развертывание окончится сбоем.</span><span class="sxs-lookup"><span data-stu-id="2c01c-117">If a writeback table already exists, the deployment fails.</span></span> <span data-ttu-id="2c01c-118">Если таблицы обратной записи не существует, то будет создана новая таблица обратной записи.</span><span class="sxs-lookup"><span data-stu-id="2c01c-118">If a writeback table does not exist, a new writeback table will be created.</span></span>  
  
    -   <span data-ttu-id="2c01c-119">Вне зависимости от того, существует ли уже таблица обратной записи, будет создана новая таблица обратной записи.</span><span class="sxs-lookup"><span data-stu-id="2c01c-119">Regardless of whether a writeback table already exists, a new writeback table will be created.</span></span> <span data-ttu-id="2c01c-120">В этом случае мастер развертывания служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] удалит существующую таблицу и заменит ее новой таблицей обратной записи.</span><span class="sxs-lookup"><span data-stu-id="2c01c-120">In this case, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard will delete any existing table and replace it with a new writeback table.</span></span>  
  
-   <span data-ttu-id="2c01c-121">**Транзакционное развертывание** Эта настройка контролирует, обрабатываются ли изменения развертывания метаданных и команды обработки в одной транзакции или в отдельных транзакциях.</span><span class="sxs-lookup"><span data-stu-id="2c01c-121">**Transactional Deployment** This setting controls whether the deployment of metadata changes and process commands occurs in a single transaction or in separate transactions.</span></span>  
  
    -   <span data-ttu-id="2c01c-122">Если значение этого параметра установлено равным `True` (по умолчанию), то службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] развертывают все изменения метаданных и все команды обработки в одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="2c01c-122">If this option is `True` (default), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys all metadata changes and all process commands within a single transaction.</span></span>  
  
    -   <span data-ttu-id="2c01c-123">Если значение этого параметра установлено равным `False`, то службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] развертывают изменения метаданных в одной транзакции и развертывают каждую команду обработки в ее собственной транзакции.</span><span class="sxs-lookup"><span data-stu-id="2c01c-123">If this option is `False`, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deploys the metadata changes in a single transaction, and deploys each processing command in its own transaction.</span></span>  
  
## <a name="modifying-the-processing-options-for-deployment"></a><span data-ttu-id="2c01c-124">Изменение параметров обработки для развертывания</span><span class="sxs-lookup"><span data-stu-id="2c01c-124">Modifying the Processing Options for Deployment</span></span>  
 <span data-ttu-id="2c01c-125">Однако может потребоваться развернуть [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проект, используя параметры обработки, отличные от тех, которые хранятся в \<*project name*> deploymentoptions-файле.</span><span class="sxs-lookup"><span data-stu-id="2c01c-125">However, you may need to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different processing options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="2c01c-126">Например может быть необходимо полностью обработать все объекты или обработать их с использованием параметра обработки по умолчанию, или не обрабатывать вообще.</span><span class="sxs-lookup"><span data-stu-id="2c01c-126">For example, you may want to have all objects fully processed, or processed using the default processing option, or have no processing occur.</span></span> <span data-ttu-id="2c01c-127">Если разрешена запись в кубы или измерения, то можно указать, будет ли использоваться новая или существующая таблица обратной записи.</span><span class="sxs-lookup"><span data-stu-id="2c01c-127">If the cubes or dimensions are write-enabled, you can specify whether a new or existing writeback table be used.</span></span>  
  
 <span data-ttu-id="2c01c-128">Чтобы изменить параметры обработки во время развертывания, можно либо исправить и повторно собрать проект, либо изменить параметры обработки во входном файле, используя один из методов, описанных в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="2c01c-128">To modify the processing options used during deployment, you can either edit and rebuild the project, or change the processing options in the input file by using one of the methods as described in the following procedure.</span></span>  
  
#### <a name="to-change-processing-options-after-the-input-files-have-been-generated"></a><span data-ttu-id="2c01c-129">Изменение параметров обработки после формирования входных файлов</span><span class="sxs-lookup"><span data-stu-id="2c01c-129">To change processing options after the input files have been generated</span></span>  
  
-   <span data-ttu-id="2c01c-130">Запустите мастер развертывания служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="2c01c-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="2c01c-131">На странице **Параметры обработки** укажите параметры обработки для развертываемого проекта.</span><span class="sxs-lookup"><span data-stu-id="2c01c-131">On the **Processing Options** page, specify the processing options for the project being deployed.</span></span>  
  
     <span data-ttu-id="2c01c-132">-или-</span><span class="sxs-lookup"><span data-stu-id="2c01c-132">-or-</span></span>  
  
-   <span data-ttu-id="2c01c-133">Запустите мастер развертывания служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] из командной строки и настройте его на работу в режиме файла ответов.</span><span class="sxs-lookup"><span data-stu-id="2c01c-133">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="2c01c-134">Дополнительные сведения о режиме файла ответов см. в разделе [Запуск мастера развертывания служб Analysis Services](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2c01c-134">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="2c01c-135">-или-</span><span class="sxs-lookup"><span data-stu-id="2c01c-135">-or-</span></span>  
  
-   <span data-ttu-id="2c01c-136">Измените \<*project name*> файл deploymentoptions с помощью любого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="2c01c-136">Modify the \<*project name*>.deploymentoptions file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c01c-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c01c-137">See Also</span></span>  
 <span data-ttu-id="2c01c-138">[Указание целевого объекта установки](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="2c01c-138">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="2c01c-139">[Указание параметров развертывания секций и ролей](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="2c01c-139">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 [<span data-ttu-id="2c01c-140">Указание настроек конфигурации для развертывания решения</span><span class="sxs-lookup"><span data-stu-id="2c01c-140">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
  
