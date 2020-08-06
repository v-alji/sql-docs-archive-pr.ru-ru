---
title: Источник SAP BW | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 749afb64-3567-4dc9-8431-783d650c25db
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d64af5e0d881e3b7dbbd2cc4e005aa3dbef3c43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667336"
---
# <a name="sap-bw-source"></a><span data-ttu-id="f4789-102">Источник SAP BW</span><span class="sxs-lookup"><span data-stu-id="f4789-102">SAP BW Source</span></span>
  <span data-ttu-id="f4789-103">Источник SAP BW — это компонент источника Connector 1.1 для SAP BW [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4789-103">The SAP BW source is the source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="f4789-104">Таким образом, источник SAP BW извлекает данные из системы SAP Netweaver BW версии 7 и делает их доступными для потока данных в пакете [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4789-104">Thus, the SAP BW source extracts data from an SAP Netweaver BW version 7 system and makes this data available to the data flow in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="f4789-105">Данный источник содержит один выход и один выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="f4789-105">This source has one output and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f4789-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f4789-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="f4789-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="f4789-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f4789-108">Для извлечения данных из SAP Netweaver BW требуется дополнительная лицензия SAP.</span><span class="sxs-lookup"><span data-stu-id="f4789-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="f4789-109">Обратитесь к SAP, чтобы уточнить требования.</span><span class="sxs-lookup"><span data-stu-id="f4789-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="f4789-110">Для использования источника SAP BW необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="f4789-110">To use the SAP BW source, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="f4789-111">подготовка объектов SAP Netweaver BW;</span><span class="sxs-lookup"><span data-stu-id="f4789-111">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="f4789-112">подключение к системе SAP Netweaver BW;</span><span class="sxs-lookup"><span data-stu-id="f4789-112">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="f4789-113">Настройка источника SAP BW</span><span class="sxs-lookup"><span data-stu-id="f4789-113">Configure the SAP BW source</span></span>](#bkmk_Configure_Source)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-source-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="f4789-114">Подготовка объектов SAP Netweaver BW, необходимых для источника</span><span class="sxs-lookup"><span data-stu-id="f4789-114">Preparing the SAP Netweaver BW Objects That the Source Requires</span></span>  
 <span data-ttu-id="f4789-115">Для источника SAP BW для начала его функционирования необходимы определенные объекты в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f4789-115">The SAP BW source requires that certain objects are in the SAP Netweaver BW system before the source can function.</span></span> <span data-ttu-id="f4789-116">Если эти объекты не существуют, выполните следующие действия для создания и настройки этих объектов в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f4789-116">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f4789-117">Дополнительные сведения об этих объектах и следующих шагах настройки см. в документации SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f4789-117">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="f4789-118">Выполните вход в SAP Netweaver BW с помощью графического интерфейса SAP, введите код транзакции SM59 и создайте назначение RFC.</span><span class="sxs-lookup"><span data-stu-id="f4789-118">Log on to SAP Netweaver BW through the SAP GUI, enter transaction code SM59, and create an RFC destination:</span></span>  
  
    1.  <span data-ttu-id="f4789-119">Для параметра **Тип соединения**выберите **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="f4789-119">For **Connection Type**, select **TCP/IP**.</span></span>  
  
    2.  <span data-ttu-id="f4789-120">Для параметра **Тип активации**выберите **Программа зарегистрированного сервера**.</span><span class="sxs-lookup"><span data-stu-id="f4789-120">For **Activation Type**, select **Registered Server Program**.</span></span>  
  
    3.  <span data-ttu-id="f4789-121">Для параметра **Тип связи с целевой системой**выберите **Не Юникод (неактивные настройки MDMP)** .</span><span class="sxs-lookup"><span data-stu-id="f4789-121">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    4.  <span data-ttu-id="f4789-122">Назначьте соответствующий идентификатор программы.</span><span class="sxs-lookup"><span data-stu-id="f4789-122">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="f4789-123">Создайте открытое назначение концентратора.</span><span class="sxs-lookup"><span data-stu-id="f4789-123">Create an Open Hub Destination:</span></span>  
  
    1.  <span data-ttu-id="f4789-124">Перейдите в Administrator Workbench (код транзакции RSA1) и в левой панели выберите **Открыть назначение концентратора**.</span><span class="sxs-lookup"><span data-stu-id="f4789-124">Go to the Administrator Workbench (transaction code RSA1) and, in the left pane, select **Open Hub Destination**.</span></span>  
  
    2.  <span data-ttu-id="f4789-125">На центральной панели щелкните правой кнопкой мыши InfoArea, а затем выберите **"Создание назначения концентратора"** .</span><span class="sxs-lookup"><span data-stu-id="f4789-125">In the middle pane, right-click an InfoArea, and then select **"Create Open Hub Destination"**.</span></span>  
  
    3.  <span data-ttu-id="f4789-126">Для параметра **Тип назначения**выберите **«Средство стороннего производителя»** , а затем укажите ранее созданное назначение RFC.</span><span class="sxs-lookup"><span data-stu-id="f4789-126">For **Destination Type**, select **"Third Party Tool"**, and then enter the previously created RFC Destination.</span></span>  
  
    4.  <span data-ttu-id="f4789-127">Сохраните и активируйте новое открытое назначение концентратора.</span><span class="sxs-lookup"><span data-stu-id="f4789-127">Save and activate the new Open Hub Destination.</span></span>  
  
3.  <span data-ttu-id="f4789-128">Создание процесса передачи данных (DTP)</span><span class="sxs-lookup"><span data-stu-id="f4789-128">Create a Data Transfer Process (DTP):</span></span>  
  
    1.  <span data-ttu-id="f4789-129">На центральной панели InfoArea щелкните правой кнопкой мыши ранее созданное назначение, а затем выберите **"Создание процесса передачи данных"** .</span><span class="sxs-lookup"><span data-stu-id="f4789-129">In the middle pane of the InfoArea, right-click the previously created destination, and then select **"Create data transfer process"**.</span></span>  
  
    2.  <span data-ttu-id="f4789-130">Настройте, сохраните и активируйте DTP.</span><span class="sxs-lookup"><span data-stu-id="f4789-130">Configure, save, and activate the DTP.</span></span>  
  
    3.  <span data-ttu-id="f4789-131">В меню выберите пункт **Переход**, а затем выберите пункт **Параметры диспетчера пакета**.</span><span class="sxs-lookup"><span data-stu-id="f4789-131">On the menu, click **Goto**, and then click **Settings for Batch Manager**.</span></span>  
  
    4.  <span data-ttu-id="f4789-132">Обновите **Число процессов** до 1 для последовательного выполнения.</span><span class="sxs-lookup"><span data-stu-id="f4789-132">Update **Number of processes** to 1 for serial processing.</span></span>  
  
4.  <span data-ttu-id="f4789-133">Создание цепочки процессов</span><span class="sxs-lookup"><span data-stu-id="f4789-133">Create a process chain:</span></span>  
  
    1.  <span data-ttu-id="f4789-134">При настройке цепочки процессов выберите **Начать использование метаданных цепочки или API метаданных** в качестве **Параметров планирования** **Запуска процесса**, а затем добавьте ранее созданный DTP как следующий узел.</span><span class="sxs-lookup"><span data-stu-id="f4789-134">When configuring the process chain, select the **Start Using Metadata Chain or API** as the **Scheduling Options** of the **Start Process**, and then add the previously created DTP as the subsequent node.</span></span>  
  
    2.  <span data-ttu-id="f4789-135">Сохраните и активируйте цепочку процессов.</span><span class="sxs-lookup"><span data-stu-id="f4789-135">Save and activate the process chain.</span></span>  
  
     <span data-ttu-id="f4789-136">Источник SAP BW может вызывать цепочку процессов для активации процесса передачи данных.</span><span class="sxs-lookup"><span data-stu-id="f4789-136">The SAP BW source can call the process chain to activate the data transfer process.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="f4789-137">Подключение к системе SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="f4789-137">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="f4789-138">Для подключения к системе SAP Netweaver BW версии 7 источник SAP BW использует диспетчер соединений SAP BW, который является частью пакета Connector 1.1 для SAP BW [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4789-138">To connect to the SAP Netweaver BW version 7 system, the SAP BW source uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="f4789-139">Диспетчер соединений SAP BW является единственным диспетчером соединений [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , предназначенным для использования источником SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f4789-139">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW source can use.</span></span>  
  
 <span data-ttu-id="f4789-140">Дополнительные сведения о диспетчере соединений SAP BW см. в разделе [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f4789-140">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-source"></a><a name="bkmk_Configure_Source"></a> <span data-ttu-id="f4789-141">Настройка источника SAP BW</span><span class="sxs-lookup"><span data-stu-id="f4789-141">Configuring the SAP BW Source</span></span>  
 <span data-ttu-id="f4789-142">Для настройки источника SAP BW применяются следующие способы.</span><span class="sxs-lookup"><span data-stu-id="f4789-142">You can configure the SAP BW source in the following ways:</span></span>  
  
-   <span data-ttu-id="f4789-143">Воспользуйтесь поиском и выберите назначение службы открытого концентратора (OHS), используемого для извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="f4789-143">Look up and select the Open Hub Service (OHS) destination to use to extract data.</span></span>  
  
-   <span data-ttu-id="f4789-144">Выберите один из следующих методов для извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="f4789-144">Select one of the following methods for extracting data:</span></span>  
  
    -   <span data-ttu-id="f4789-145">Запустите цепочку процессов.</span><span class="sxs-lookup"><span data-stu-id="f4789-145">Trigger a process chain.</span></span> <span data-ttu-id="f4789-146">В этом случае пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] запустит процесс извлечения.</span><span class="sxs-lookup"><span data-stu-id="f4789-146">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="f4789-147">Дождитесь уведомления от системы SAP Netweaver BW для начала извлечения.</span><span class="sxs-lookup"><span data-stu-id="f4789-147">Wait for notification from the SAP Netweaver BW system to begin an extraction.</span></span> <span data-ttu-id="f4789-148">В этом случае система SAP Netweaver BW запустит процесс извлечения.</span><span class="sxs-lookup"><span data-stu-id="f4789-148">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="f4789-149">Выполните извлечение данных, связанных с запросом с определенным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="f4789-149">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="f4789-150">В этом случае система SAP Netweaver BW уже извлекла данные во внутреннюю таблицу и пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] просто считывает данные.</span><span class="sxs-lookup"><span data-stu-id="f4789-150">In this case, the SAP Netweaver BW system has already extracted the data to an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>  
  
-   <span data-ttu-id="f4789-151">В зависимости от выбранного метода извлечения данных укажите следующую дополнительную информацию.</span><span class="sxs-lookup"><span data-stu-id="f4789-151">Depending on the method selected for extracting data, provide the following additional information:</span></span>  
  
    -   <span data-ttu-id="f4789-152">Для параметра **P — запустить цепочку процесса** укажите имя узла шлюза, имя службы шлюза, идентификатор программы для назначения RFC и имя цепочки процессов.</span><span class="sxs-lookup"><span data-stu-id="f4789-152">For the **P - Trigger Process Chain** option, provide the gateway host name, gateway service name, program ID for the RFC destination, and name of the process chain.</span></span>  
  
    -   <span data-ttu-id="f4789-153">Для параметра **W — ждать уведомления** укажите имя узла шлюза, имя сервера шлюза и идентификатор программы для назначения RFC.</span><span class="sxs-lookup"><span data-stu-id="f4789-153">For the **W - Wait for Notify** option, provide the gateway host name, the gateway server name, and the program ID for the RFC destination.</span></span> <span data-ttu-id="f4789-154">Можно также указать время ожидания (в секундах).</span><span class="sxs-lookup"><span data-stu-id="f4789-154">You can also specify the timeout (in seconds).</span></span> <span data-ttu-id="f4789-155">Время ожидания — это максимальный период времени, в течение которого источник ожидает оповещения.</span><span class="sxs-lookup"><span data-stu-id="f4789-155">The timeout is the maximum period of time that the source will wait to be notified.</span></span>  
  
    -   <span data-ttu-id="f4789-156">Для параметра **E — только извлечь** укажите идентификатор запроса.</span><span class="sxs-lookup"><span data-stu-id="f4789-156">For the **E - Extract Only** option, provide the Request ID.</span></span>  
  
-   <span data-ttu-id="f4789-157">Укажите правила преобразования строк.</span><span class="sxs-lookup"><span data-stu-id="f4789-157">Specify rules for string conversion.</span></span> <span data-ttu-id="f4789-158">(Например, преобразование всех строк в зависимости от того, поддерживает ли система SAP Netweaver BW Юникод или преобразование всех строк в `varchar` или `nvarchar`.)</span><span class="sxs-lookup"><span data-stu-id="f4789-158">(For example, convert all strings depending on whether the SAP Netweaver BW system is Unicode or not, or convert all strings to `varchar` or `nvarchar`).</span></span>  
  
-   <span data-ttu-id="f4789-159">Используйте параметры, выбранные для предварительного просмотра извлекаемых данных.</span><span class="sxs-lookup"><span data-stu-id="f4789-159">Use the options that you have selected to preview the data to be extracted.</span></span>  
  
 <span data-ttu-id="f4789-160">Можно также включить ведение журнала вызовов функций RFC источником.</span><span class="sxs-lookup"><span data-stu-id="f4789-160">You can also enable logging of RFC function calls by the source.</span></span> <span data-ttu-id="f4789-161">(Это ведение журнала отделено от дополнительного ведения журналов, которое можно включить для пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .) Ведение журнала вызовов функций RFC включается при настройке диспетчера соединений SAP BW, используемого источником.</span><span class="sxs-lookup"><span data-stu-id="f4789-161">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the source will use.</span></span> <span data-ttu-id="f4789-162">Дополнительные сведения о настройке диспетчера соединений см. в разделе [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f4789-162">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="f4789-163">Если вы не знаете все значения, необходимые для настройки источника, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="f4789-163">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="f4789-164">Пошаговое руководство, в котором показано, как настроить и использовать диспетчер соединений, источник и назначение SAP BW, см. в техническом документе [Использование служб SQL Server 2008 Integration Services с SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="f4789-164">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="f4789-165">В этом техническом документе также показано, как настроить необходимые объекты в SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f4789-165">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="f4789-166">Использование конструктора служб SSIS для настройки источника</span><span class="sxs-lookup"><span data-stu-id="f4789-166">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="f4789-167">Дополнительные сведения о свойствах источника SAP BW, которые можно задать в конструкторе [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в одном из последующих разделов.</span><span class="sxs-lookup"><span data-stu-id="f4789-167">For more information about the properties of the SAP BW source that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f4789-168">Редактор источника SAP BW (страница "Диспетчер подключений")</span><span class="sxs-lookup"><span data-stu-id="f4789-168">SAP BW Source Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="f4789-169">Редактор источника SAP BW (страница "Столбцы")</span><span class="sxs-lookup"><span data-stu-id="f4789-169">SAP BW Source Editor &#40;Columns Page&#41;</span></span>](sap-bw-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="f4789-170">Редактор источника SAP BW (страница "Вывод ошибок")</span><span class="sxs-lookup"><span data-stu-id="f4789-170">SAP BW Source Editor &#40;Error Output Page&#41;</span></span>](sap-bw-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="f4789-171">Редактор источника SAP BW (страница "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="f4789-171">SAP BW Source Editor &#40;Advanced Page&#41;</span></span>](sap-bw-source-editor-advanced-page.md)  
  
 <span data-ttu-id="f4789-172">При настройке источника SAP BW можно также использовать другие диалоговые окна для поиска объектов SAP Netweaver BW и предварительного просмотра исходных данных.</span><span class="sxs-lookup"><span data-stu-id="f4789-172">While you are configuring the SAP BW source, you can also use various dialog boxes to look up SAP Netweaver BW objects or to preview the source data.</span></span> <span data-ttu-id="f4789-173">Дополнительные сведения об этих диалоговых окнах см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f4789-173">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f4789-174">Поиск назначения RFC</span><span class="sxs-lookup"><span data-stu-id="f4789-174">Look Up RFC Destination</span></span>](look-up-rfc-destination.md)  
  
-   [<span data-ttu-id="f4789-175">Поиск цепочки процессов</span><span class="sxs-lookup"><span data-stu-id="f4789-175">Look Up Process Chain</span></span>](look-up-process-chain.md)  
  
-   [<span data-ttu-id="f4789-176">Журнал запросов</span><span class="sxs-lookup"><span data-stu-id="f4789-176">Request Log</span></span>](request-log.md)  
  
-   [<span data-ttu-id="f4789-177">Предварительный просмотр</span><span class="sxs-lookup"><span data-stu-id="f4789-177">Preview</span></span>](preview.md)  
  
## <a name="see-also"></a><span data-ttu-id="f4789-178">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4789-178">See Also</span></span>  
 [<span data-ttu-id="f4789-179">Компоненты Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="f4789-179">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
