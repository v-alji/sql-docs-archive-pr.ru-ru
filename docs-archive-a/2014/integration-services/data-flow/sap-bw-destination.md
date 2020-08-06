---
title: Назначение SAP BW | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a612ed91-b89b-4173-a0b1-0bce381e1e28
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a0d7c5b75da89e665dbe60bbd7e29ce74da67db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666199"
---
# <a name="sap-bw-destination"></a><span data-ttu-id="e75f2-102">Назначение SAP BW</span><span class="sxs-lookup"><span data-stu-id="e75f2-102">SAP BW Destination</span></span>
  <span data-ttu-id="e75f2-103">Назначение SAP BW — компонент назначения [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-103">The SAP BW destination is the destination component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="e75f2-104">Таким образом, назначение SAP BW загружает данные из потока данных в пакете служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] в систему SAP Netweaver BW версии 7.</span><span class="sxs-lookup"><span data-stu-id="e75f2-104">Thus, the SAP BW destination loads data from the data flow in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package into an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="e75f2-105">Это назначение имеет один вход и один выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="e75f2-105">This destination has one input and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e75f2-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="e75f2-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="e75f2-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="e75f2-108">Для использования источника SAP BW необходимо выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="e75f2-108">To use the SAP BW destination, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="e75f2-109">подготовка объектов SAP Netweaver BW;</span><span class="sxs-lookup"><span data-stu-id="e75f2-109">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="e75f2-110">подключение к системе SAP Netweaver BW;</span><span class="sxs-lookup"><span data-stu-id="e75f2-110">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="e75f2-111">настройка цели SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-111">Configure the SAP BW destination</span></span>](#bkmk_Configure_Destination)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-destination-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="e75f2-112">Подготовка объектов SAP Netweaver BW, необходимых для цели</span><span class="sxs-lookup"><span data-stu-id="e75f2-112">Preparing the SAP Netweaver BW Objects That the Destination Requires</span></span>  
 <span data-ttu-id="e75f2-113">Цели SAP BW для функционирования необходимы определенные объекты в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-113">The SAP BW destination requires that certain objects are in the SAP Netweaver BW system before the destination can function.</span></span> <span data-ttu-id="e75f2-114">Если эти объекты не существуют, выполните следующие действия для создания и настройки этих объектов в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-114">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e75f2-115">Дополнительные сведения об этих объектах и следующих шагах настройки см. в документации SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-115">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="e75f2-116">Создайте новую исходную систему.</span><span class="sxs-lookup"><span data-stu-id="e75f2-116">Create a new Source System:</span></span>  
  
    1.  <span data-ttu-id="e75f2-117">Выберите тип **"Сторонние/промежуточные BAPI"** .</span><span class="sxs-lookup"><span data-stu-id="e75f2-117">Select the type, **"Third Party/Staging BAPIs"**.</span></span>  
  
    2.  <span data-ttu-id="e75f2-118">Для параметра **Тип связи с целевой системой**выберите **Не Юникод (неактивные настройки MDMP)** .</span><span class="sxs-lookup"><span data-stu-id="e75f2-118">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    3.  <span data-ttu-id="e75f2-119">Назначьте соответствующий идентификатор программы.</span><span class="sxs-lookup"><span data-stu-id="e75f2-119">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="e75f2-120">Назначьте исходную систему для InfoSource.</span><span class="sxs-lookup"><span data-stu-id="e75f2-120">Assign the Source System to an InfoSource.</span></span>  
  
3.  <span data-ttu-id="e75f2-121">Создайте InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="e75f2-121">Create an InfoPackage.</span></span>  
  
     <span data-ttu-id="e75f2-122">InfoPackage — это самый важный объект, который требуется для цели SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-122">The InfoPackage is the most important object that is required by the SAP BW destination.</span></span>  
  
 <span data-ttu-id="e75f2-123">Также можно создать дополнительные объекты InfoObject, Infocube, InfoSource и InfoPackage, которые необходимы для поддержки загрузки данных в систему SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-123">You can also create additional InfoObjects, InfoCubes, InfoSources, and InfoPackages that are required to support loading data into the SAP Netweaver BW system.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="e75f2-124">Подключение к системе SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="e75f2-124">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="e75f2-125">Для подключения к системе SAP Netweaver BW версии 7 цель SAP BW использует диспетчер соединений SAP BW, который является частью пакета [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-125">To connect to the SAP Netweaver BW version 7 system, the SAP BW destination uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="e75f2-126">Диспетчер соединений SAP BW является единственным диспетчером соединений [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , который может использоваться целью SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-126">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW destination can use.</span></span>  
  
 <span data-ttu-id="e75f2-127">Дополнительные сведения о диспетчере соединений SAP BW см. в разделе [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e75f2-127">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-destination"></a><a name="bkmk_Configure_Destination"></a> <span data-ttu-id="e75f2-128">Настройка целевого объекта SAP BW</span><span class="sxs-lookup"><span data-stu-id="e75f2-128">Configuring the SAP BW Destination</span></span>  
 <span data-ttu-id="e75f2-129">Целевой объект SAP BW может быть настроен следующими способами.</span><span class="sxs-lookup"><span data-stu-id="e75f2-129">You can configure the SAP BW destination in the following ways:</span></span>  
  
-   <span data-ttu-id="e75f2-130">Найдите и выберите InfoPackage, который будет использоваться для загрузки данных.</span><span class="sxs-lookup"><span data-stu-id="e75f2-130">Look up and select the InfoPackage to use to load data.</span></span>  
  
-   <span data-ttu-id="e75f2-131">Сопоставьте каждый столбец потока данных соответствующему объекту InfoObject в пакете InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="e75f2-131">Map each column in the data flow to the appropriate InfoObject in the InfoPackage.</span></span>  
  
-   <span data-ttu-id="e75f2-132">Укажите, сколько строк данных будут переданы одновременно путем настройки свойства `PackageSize`.</span><span class="sxs-lookup"><span data-stu-id="e75f2-132">Specify how many rows of data will be transferred at a time by configuring the `PackageSize` property.</span></span>  
  
-   <span data-ttu-id="e75f2-133">Выберите ожидание, пока не будет выполнена загрузка данных системой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-133">Choose to wait until the loading of data is completed by the SAP Netweaver BW system.</span></span>  
  
-   <span data-ttu-id="e75f2-134">Выберите отказ от использования триггера пакета InfoPackage и ожидание уведомления о том, что система SAP Netweaver BW начала загрузку данных.</span><span class="sxs-lookup"><span data-stu-id="e75f2-134">Choose not to trigger the InfoPackage, but to wait for notification that the SAP Netweaver BW system has started the loading of data.</span></span>  
  
-   <span data-ttu-id="e75f2-135">Можно также вызывать другую последовательность процесса после завершения загрузки данных.</span><span class="sxs-lookup"><span data-stu-id="e75f2-135">Optionally, trigger another process chain after the loading of data is completed.</span></span>  
  
-   <span data-ttu-id="e75f2-136">Дополнительно можно создать объекты SAP Netweaver BW, которые требуются для целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="e75f2-136">Optionally, create the SAP Netweaver BW objects that are required by the destination.</span></span> <span data-ttu-id="e75f2-137">Сюда входит создание объектов InfoObject, Infocube, InfoSource и InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="e75f2-137">This includes creating InfoObjects, InfoCubes, InfoSources, and InfoPackages.</span></span>  
  
-   <span data-ttu-id="e75f2-138">Проверьте загрузку данных с выбранными параметрами.</span><span class="sxs-lookup"><span data-stu-id="e75f2-138">Test the loading of data with the options that you have selected.</span></span>  
  
 <span data-ttu-id="e75f2-139">Можно также включить ведение журнала вызовов функций RFC целевым объектом.</span><span class="sxs-lookup"><span data-stu-id="e75f2-139">You can also enable logging of RFC function calls by the destination.</span></span> <span data-ttu-id="e75f2-140">(Это ведение журнала отделено от дополнительного ведения журналов, которое можно включить для пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .) Ведение журнала вызовов функций RFC включается при настройке диспетчера соединений SAP BW, используемого целевым объектом.</span><span class="sxs-lookup"><span data-stu-id="e75f2-140">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the destination will use.</span></span> <span data-ttu-id="e75f2-141">Дополнительные сведения о настройке диспетчера соединений см. в разделе [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e75f2-141">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e75f2-142">Если вы не знаете все значения, необходимые для настройки назначения, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="e75f2-142">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="e75f2-143">Пошаговое руководство, в котором показано, как настроить и использовать диспетчер соединений, источник и назначение SAP BW, см. в техническом документе [Использование служб SQL Server 2008 Integration Services с SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="e75f2-143">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="e75f2-144">В этом техническом документе также показано, как настроить необходимые объекты в SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-144">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-destination"></a><span data-ttu-id="e75f2-145">Использование конструктора служб SSIS для настройки целевого объекта</span><span class="sxs-lookup"><span data-stu-id="e75f2-145">Using the SSIS Designer to Configure the Destination</span></span>  
 <span data-ttu-id="e75f2-146">Дополнительные сведения о свойствах целевого объекта SAP BW, который можно задать в конструкторе [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в одном из следующих разделов.</span><span class="sxs-lookup"><span data-stu-id="e75f2-146">For more information about the properties of the SAP BW destination that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e75f2-147">Редактор назначений SAP BW (страница "Диспетчер подключений")</span><span class="sxs-lookup"><span data-stu-id="e75f2-147">SAP BW Destination Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="e75f2-148">Редактор назначений SAP BW (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="e75f2-148">SAP BW Destination Editor &#40;Mappings Page&#41;</span></span>](sap-bw-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="e75f2-149">Редактор назначений SAP BW (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="e75f2-149">SAP BW Destination Editor &#40;Error Output Page&#41;</span></span>](sap-bw-destination-editor-error-output-page.md)  
  
-   [<span data-ttu-id="e75f2-150">Редактор назначений SAP BW (страница "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="e75f2-150">SAP BW Destination Editor &#40;Advanced Page&#41;</span></span>](sap-bw-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="e75f2-151">При настройке целевого объекта SAP BW можно также использовать другие диалоговые окна для уточняющих запросов или создать объекты SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e75f2-151">While you are configuring the SAP BW destination, you can also use various dialog boxes to look up or to create SAP Netweaver BW objects.</span></span> <span data-ttu-id="e75f2-152">Дополнительные сведения об этих диалоговых окнах см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="e75f2-152">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e75f2-153">Поиск InfoPackage</span><span class="sxs-lookup"><span data-stu-id="e75f2-153">Look Up InfoPackage</span></span>](look-up-infopackage.md)  
  
-   [<span data-ttu-id="e75f2-154">Создание InfoObject</span><span class="sxs-lookup"><span data-stu-id="e75f2-154">Create New InfoObject</span></span>](create-new-infoobject.md)  
  
-   [<span data-ttu-id="e75f2-155">Создание InfoCube для данных транзакции</span><span class="sxs-lookup"><span data-stu-id="e75f2-155">Create InfoCube for Transaction Data</span></span>](create-infocube-for-transaction-data.md)  
  
-   [<span data-ttu-id="e75f2-156">Поиск InfoObject</span><span class="sxs-lookup"><span data-stu-id="e75f2-156">Look Up InfoObject</span></span>](look-up-infoobject.md)  
  
-   [<span data-ttu-id="e75f2-157">Создание InfoSource</span><span class="sxs-lookup"><span data-stu-id="e75f2-157">Create InfoSource</span></span>](create-infosource.md)  
  
-   [<span data-ttu-id="e75f2-158">Создание InfoSource для данных транзакции</span><span class="sxs-lookup"><span data-stu-id="e75f2-158">Create InfoSource for Transaction Data</span></span>](create-infosource-for-transaction-data.md)  
  
-   [<span data-ttu-id="e75f2-159">Создание InfoSource для основных данных</span><span class="sxs-lookup"><span data-stu-id="e75f2-159">Create InfoSource for Master Data</span></span>](create-infosource-for-master-data.md)  
  
-   [<span data-ttu-id="e75f2-160">Создание InfoPackage</span><span class="sxs-lookup"><span data-stu-id="e75f2-160">Create InfoPackage</span></span>](create-infopackage.md)  
  
## <a name="see-also"></a><span data-ttu-id="e75f2-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="e75f2-161">See Also</span></span>  
 [<span data-ttu-id="e75f2-162">Компоненты Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="e75f2-162">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
