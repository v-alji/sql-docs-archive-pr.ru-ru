---
title: Включение ведения журнала пакетов в SQL Server Data Tools | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], enabling
ms.assetid: b69a8593-5bb0-4f04-87d2-f8e7bd7eb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d73dbca034047e853669dd503a62e105d1dd7b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665032"
---
# <a name="enable-package-logging-in-sql-server-data-tools"></a><span data-ttu-id="56dcd-102">Включение средств ведения журналов в SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="56dcd-102">Enable Package Logging in SQL Server Data Tools</span></span>
  <span data-ttu-id="56dcd-103">В этой процедуре описывается, как добавлять журналы в пакет, настраивать ведение журналов на уровне пакетов и сохранять настройку ведения журналов в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="56dcd-103">This procedure describes how to add logs to a package, configure package-level logging, and save the logging configuration to an XML file.</span></span> <span data-ttu-id="56dcd-104">Журнал можно добавить только на уровне пакета, однако пакеты не обязаны осуществлять ведение журналов, чтобы включить ведение журналов в контейнерах, которые содержатся в этих пакетах.</span><span class="sxs-lookup"><span data-stu-id="56dcd-104">You can add logs only at the package level, but the package does not have to perform logging to enable logging in the containers that the package includes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="56dcd-105">При развертывании проекта [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сервере [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] уровень ведения журнала, заданный для выполнения пакета, переопределяет уровень, настраиваемый с помощью среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56dcd-105">If you deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the logging level that you set for the package execution overrides the package logging that you configure using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="56dcd-106">По умолчанию к контейнерам в пакете применяются те же самые настройки ведения журналов, что и к их родительскому контейнеру.</span><span class="sxs-lookup"><span data-stu-id="56dcd-106">By default, the containers in the package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="56dcd-107">Дополнительные сведения об установке параметров ведения журналов для отдельных контейнеров см. в разделе [Настройка ведения журналов с помощью сохраненного файла конфигурации](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="56dcd-107">For information about setting logging options for individual containers, see [Configure Logging by Using a Saved Configuration File](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span></span>  
  
### <a name="to-enable-logging-in-a-package"></a><span data-ttu-id="56dcd-108">Включение ведения журналов в пакете</span><span class="sxs-lookup"><span data-stu-id="56dcd-108">To enable logging in a package</span></span>  
  
1.  <span data-ttu-id="56dcd-109">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="56dcd-109">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="56dcd-110">В меню **Службы SSIS** нажмите **Ведение журнала**.</span><span class="sxs-lookup"><span data-stu-id="56dcd-110">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="56dcd-111">Выберите регистратор из списка **Тип поставщика** и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="56dcd-111">Select a log provider in the **Provider type** list, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="56dcd-112">В столбце **Конфигурация** выберите диспетчер подключений или щелкните **\<New connection>** , чтобы создать диспетчер подключений, соответствующий регистратору.</span><span class="sxs-lookup"><span data-stu-id="56dcd-112">In the **Configuration** column, select a connection manager or click **\<New connection>** to create a new connection manager of the appropriate type for the log provider.</span></span> <span data-ttu-id="56dcd-113">В зависимости от выбранного регистратора может использоваться один из следующих диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="56dcd-113">Depending on the selected provider, use one of the following connection managers:</span></span>  
  
    -   <span data-ttu-id="56dcd-114">Для текстовых файлов используется диспетчер подключения файлов.</span><span class="sxs-lookup"><span data-stu-id="56dcd-114">For Text files, use a File connection manager.</span></span> <span data-ttu-id="56dcd-115">Дополнительные сведения см. в разделе [диспетчер подключения файлов](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="56dcd-115">For more information, see [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
    -   <span data-ttu-id="56dcd-116">Для [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]используется диспетчер подключения файлов.</span><span class="sxs-lookup"><span data-stu-id="56dcd-116">For [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use a File connection manager.</span></span>  
  
    -   <span data-ttu-id="56dcd-117">Для [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]используется диспетчер соединений OLE DB.</span><span class="sxs-lookup"><span data-stu-id="56dcd-117">For [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use an OLE DB connection manager.</span></span> <span data-ttu-id="56dcd-118">Дополнительные сведения см. в разделе [Диспетчер соединений OLE DB](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="56dcd-118">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
    -   <span data-ttu-id="56dcd-119">В журнале событий Windows выполнение действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="56dcd-119">For Windows Event Log, do nothing.</span></span> [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="56dcd-120">автоматически создадут журнал.</span><span class="sxs-lookup"><span data-stu-id="56dcd-120">automatically creates the log.</span></span>  
  
    -   <span data-ttu-id="56dcd-121">Для XML-файлов используется диспетчер подключения файлов.</span><span class="sxs-lookup"><span data-stu-id="56dcd-121">For XML files, use a File connection manager.</span></span>  
  
5.  <span data-ttu-id="56dcd-122">Для каждого журнала, используемого в пакете, повторите шаги 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="56dcd-122">Repeat steps 3 and 4 for each log to use in the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56dcd-123">Пакет может задействовать более одного журнала каждого типа.</span><span class="sxs-lookup"><span data-stu-id="56dcd-123">A package can use more than one log of each type.</span></span>  
  
6.  <span data-ttu-id="56dcd-124">При необходимости установите флажок уровня пакетов, выберите журналы для ведения на уровне пакетов и перейдите на вкладку **Подробности** .</span><span class="sxs-lookup"><span data-stu-id="56dcd-124">Optionally, select the package-level check box, select the logs to use for package-level logging, and then click the **Details** tab.</span></span>  
  
7.  <span data-ttu-id="56dcd-125">На вкладке **Подробности** установите флажок **События** для сохранения всех записей журнала или снимите флажок **События** , чтобы выбрать отдельные события.</span><span class="sxs-lookup"><span data-stu-id="56dcd-125">On the **Details** tab, select **Events** to log all log entries, or clear **Events** to select individual events.</span></span>  
  
8.  <span data-ttu-id="56dcd-126">При необходимости перейдите на вкладку **Дополнительно** , чтобы указать, какие именно данные следует вносить в журнал.</span><span class="sxs-lookup"><span data-stu-id="56dcd-126">Optionally, click **Advanced** to specify which information to log.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56dcd-127">По умолчанию в журнал вносятся все данные.</span><span class="sxs-lookup"><span data-stu-id="56dcd-127">By default, all information is logged.</span></span>  
  
9. <span data-ttu-id="56dcd-128">На вкладке **Подробности** нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="56dcd-128">On the **Details** tab, click **Save.**</span></span> <span data-ttu-id="56dcd-129">Отображается диалоговое окно **Сохранить как** .</span><span class="sxs-lookup"><span data-stu-id="56dcd-129">The **Save As** dialog box appears.</span></span> <span data-ttu-id="56dcd-130">Выберите папку для хранения настроек ведения журнала, введите имя файла для конфигурации нового журнала и щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="56dcd-130">Locate the folder in which to save the logging configuration, type a file name for the new log configuration, and then click **Save**.</span></span>  
  
10. <span data-ttu-id="56dcd-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56dcd-131">Click **OK**.</span></span>  
  
11. <span data-ttu-id="56dcd-132">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="56dcd-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56dcd-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="56dcd-133">See Also</span></span>  
 <span data-ttu-id="56dcd-134">[Ведение журнала&#41; Integration Services &#40;SSIS](performance/integration-services-ssis-logging.md) </span><span class="sxs-lookup"><span data-stu-id="56dcd-134">[Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md) </span></span>  
 [<span data-ttu-id="56dcd-135">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="56dcd-135">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
