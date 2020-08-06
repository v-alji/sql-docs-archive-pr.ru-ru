---
title: Редактор источника SAP BW (страница "Диспетчер соединений")
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2a6dc531-85ca-43c5-a65f-3ad3f7d537c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c6b1782daf8c00b3b3d3a7d13b5ffa00adeeba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728538"
---
# <a name="sap-bw-source-editor-connection-manager-page"></a><span data-ttu-id="e2636-102">Редактор источников SAP BW (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="e2636-102">SAP BW Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="e2636-103">Используйте страницу **Диспетчер соединений** диалогового окна **Редактор источника SAP BW** , чтобы выбрать диспетчер соединений SAP BW для источника SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e2636-103">Use the **Connection Manager** page of the **SAP BW Source Editor** to select the SAP BW connection manager for the SAP BW source.</span></span> <span data-ttu-id="e2636-104">На этой странице можно также выбрать режим выполнения и параметры для извлечения данных из источника данных системы SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e2636-104">On this page, you also select the execution mode and the parameters for extracting the data from the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="e2636-105">Для получения дополнительных сведений о компоненте источника SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Источник SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="e2636-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e2636-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e2636-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="e2636-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="e2636-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e2636-108">Для извлечения данных из SAP Netweaver BW требуется дополнительная лицензия SAP.</span><span class="sxs-lookup"><span data-stu-id="e2636-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="e2636-109">Обратитесь к SAP, чтобы уточнить требования.</span><span class="sxs-lookup"><span data-stu-id="e2636-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="e2636-110">**Открытие страницы «Диспетчер соединений»**</span><span class="sxs-lookup"><span data-stu-id="e2636-110">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="e2636-111">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e2636-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="e2636-112">На вкладке **Поток данных** дважды щелкните источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e2636-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="e2636-113">В **Редакторе источника SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="e2636-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="e2636-114">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="e2636-114">Static Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2636-115">Если вы не знаете все значения, необходимые для настройки источника, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="e2636-115">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="e2636-116">**Диспетчер соединений SAP BW**</span><span class="sxs-lookup"><span data-stu-id="e2636-116">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="e2636-117">Выберите из списка существующий диспетчер соединений или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e2636-117">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="e2636-118">**Создать**</span><span class="sxs-lookup"><span data-stu-id="e2636-118">**New**</span></span>  
 <span data-ttu-id="e2636-119">Создайте новый диспетчер соединений с помощью диалогового окна **Диспетчер соединений SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="e2636-119">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="e2636-120">Дополнительные сведения об этом диалоговом окне см. в разделе [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e2636-120">For more information about this dialog box, see [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="e2636-121">**Назначение OHS**</span><span class="sxs-lookup"><span data-stu-id="e2636-121">**OHS destination**</span></span>  
 <span data-ttu-id="e2636-122">Выберите пункт назначения концентратора службы (OHS) для извлечения данных из источника.</span><span class="sxs-lookup"><span data-stu-id="e2636-122">Select the Open Hub Service (OHS) destination to use to extract data from the source.</span></span>  
  
 <span data-ttu-id="e2636-123">**Режим выполнения**</span><span class="sxs-lookup"><span data-stu-id="e2636-123">**Execution mode**</span></span>  
 <span data-ttu-id="e2636-124">Укажите метод извлечения данных из источника.</span><span class="sxs-lookup"><span data-stu-id="e2636-124">Specify the method for extracting data from the source.</span></span>  
  
|<span data-ttu-id="e2636-125">Параметр</span><span class="sxs-lookup"><span data-stu-id="e2636-125">Option</span></span>|<span data-ttu-id="e2636-126">Description</span><span class="sxs-lookup"><span data-stu-id="e2636-126">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e2636-127">**P – запустить цепочку процесса**</span><span class="sxs-lookup"><span data-stu-id="e2636-127">**P - Trigger Process Chain**</span></span>|<span data-ttu-id="e2636-128">Запустите цепочку процессов.</span><span class="sxs-lookup"><span data-stu-id="e2636-128">Trigger a process chain.</span></span> <span data-ttu-id="e2636-129">В этом случае пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] запустит процесс извлечения.</span><span class="sxs-lookup"><span data-stu-id="e2636-129">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>|  
|<span data-ttu-id="e2636-130">**W – ждать уведомления**</span><span class="sxs-lookup"><span data-stu-id="e2636-130">**W - Wait for Notify**</span></span>|<span data-ttu-id="e2636-131">Подождите уведомления системы SAP Netweaver BW перед тем, как начать извлечение данных.</span><span class="sxs-lookup"><span data-stu-id="e2636-131">Wait for notification from the SAP Netweaver BW system to begin extracting the data.</span></span> <span data-ttu-id="e2636-132">В этом случае система SAP Netweaver BW запустит процесс извлечения.</span><span class="sxs-lookup"><span data-stu-id="e2636-132">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>|  
|<span data-ttu-id="e2636-133">**E – только извлечь**</span><span class="sxs-lookup"><span data-stu-id="e2636-133">**E - Extract Only**</span></span>|<span data-ttu-id="e2636-134">Выполните извлечение данных, связанных с запросом с определенным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="e2636-134">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="e2636-135">В этом случае система SAP Netweaver BW уже извлекла данные во внутреннюю таблицу и пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] просто считывает данные.</span><span class="sxs-lookup"><span data-stu-id="e2636-135">In this case, the SAP Netweaver BW system has already extracted the data into an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>|  
  
 <span data-ttu-id="e2636-136">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="e2636-136">**Preview**</span></span>  
 <span data-ttu-id="e2636-137">Откройте диалоговое окно **Предварительный просмотр** , в котором можно просмотреть предварительные результаты.</span><span class="sxs-lookup"><span data-stu-id="e2636-137">Open the **Preview** dialog box in which you can preview results.</span></span> <span data-ttu-id="e2636-138">Дополнительные сведения см. в статье [Preview](preview.md).</span><span class="sxs-lookup"><span data-stu-id="e2636-138">For more information, see [Preview](preview.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e2636-139">Параметр **Предварительный просмотр** , доступный на странице **Диспетчер соединений** Редактора источника SAP BW, непосредственно извлекает данные.</span><span class="sxs-lookup"><span data-stu-id="e2636-139">The **Preview** option, that is available on the **Connection Manager** page of the SAP BW Source Editor, actually extracts data.</span></span> <span data-ttu-id="e2636-140">Если настроить SAP Netweaver BW для извлечения только тех данных, которые изменились со времени предыдущего сеанса извлечения, то при выборе параметра **Предварительный просмотр** просматриваемые данные будут исключены из следующего сеанса извлечения.</span><span class="sxs-lookup"><span data-stu-id="e2636-140">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="e2636-141">При нажатии кнопки **Предварительный просмотр**можно также открыть диалоговое окно **Журнал запросов** .</span><span class="sxs-lookup"><span data-stu-id="e2636-141">When you click **Preview**, you also open the **Request Log** dialog box.</span></span> <span data-ttu-id="e2636-142">Это диалоговое окно может использоваться для просмотра событий, зарегистрированных в момент запроса, который выполняется в системе SAP Netweaver BW для образцов данных.</span><span class="sxs-lookup"><span data-stu-id="e2636-142">You can use this dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="e2636-143">Дополнительные сведения см. в статье [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="e2636-143">For more information, see [Request Log](request-log.md).</span></span>  
  
## <a name="execution-mode-dynamic-options"></a><span data-ttu-id="e2636-144">Динамические параметры режима выполнения</span><span class="sxs-lookup"><span data-stu-id="e2636-144">Execution Mode Dynamic Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e2636-145">Если вы не знаете все значения, необходимые для настройки источника, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="e2636-145">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
### <a name="execution-mode--p---trigger-process-chain"></a><span data-ttu-id="e2636-146">Режим выполнения = p — цепь обработки триггера.</span><span class="sxs-lookup"><span data-stu-id="e2636-146">Execution Mode = P - Trigger Process Chain</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="e2636-147">Параметры назначения RFC</span><span class="sxs-lookup"><span data-stu-id="e2636-147">RFC Destination Options</span></span>  
 <span data-ttu-id="e2636-148">Нет необходимости в изучении или вводе этих значений заранее.</span><span class="sxs-lookup"><span data-stu-id="e2636-148">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="e2636-149">Нажмите кнопку **Поиск** , чтобы найти и выбрать соответствующее назначение RFC.</span><span class="sxs-lookup"><span data-stu-id="e2636-149">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="e2636-150">После выбора назначения RFC компонент вводит соответствующие значения для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="e2636-150">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="e2636-151">**Узел шлюза**</span><span class="sxs-lookup"><span data-stu-id="e2636-151">**Gateway host**</span></span>  
 <span data-ttu-id="e2636-152">Введите имя или IP-адрес сервера узла шлюза.</span><span class="sxs-lookup"><span data-stu-id="e2636-152">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="e2636-153">Обычно имя или IP-адрес совпадают с аналогичными данными сервера приложений SAP.</span><span class="sxs-lookup"><span data-stu-id="e2636-153">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="e2636-154">**Служба шлюза**</span><span class="sxs-lookup"><span data-stu-id="e2636-154">**Gateway service**</span></span>  
 <span data-ttu-id="e2636-155">Введите имя службы шлюза в формате `sapgwNN`, где `NN` — номер системы.</span><span class="sxs-lookup"><span data-stu-id="e2636-155">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="e2636-156">**ID программы**</span><span class="sxs-lookup"><span data-stu-id="e2636-156">**Program ID**</span></span>  
 <span data-ttu-id="e2636-157">Введите идентификатор программы, связанный с назначением RFC.</span><span class="sxs-lookup"><span data-stu-id="e2636-157">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="e2636-158">**Найти**</span><span class="sxs-lookup"><span data-stu-id="e2636-158">**Look up**</span></span>  
 <span data-ttu-id="e2636-159">Выполните поиск назначения RFC с помощью диалогового окна **Поиск назначения RFC** .</span><span class="sxs-lookup"><span data-stu-id="e2636-159">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="e2636-160">Дополнительные сведения об этом диалоговом окне см. в разделе [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="e2636-160">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
#### <a name="process-chain-options"></a><span data-ttu-id="e2636-161">Параметры обработки цепочек</span><span class="sxs-lookup"><span data-stu-id="e2636-161">Process Chain Options</span></span>  
 <span data-ttu-id="e2636-162">Нет необходимости в изучении или вводе этих значений заранее.</span><span class="sxs-lookup"><span data-stu-id="e2636-162">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="e2636-163">Нажмите кнопку **Поиск** , чтобы найти и выбрать соответствующую цепочку процессов.</span><span class="sxs-lookup"><span data-stu-id="e2636-163">Use the **Look up** button to find and select the appropriate process chain.</span></span> <span data-ttu-id="e2636-164">После выбора цепочки процесса компонент вводит нужное значение для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="e2636-164">After you select a process chain, the component enters the appropriate value for the option.</span></span>  
  
 <span data-ttu-id="e2636-165">**Цепочка процесса**</span><span class="sxs-lookup"><span data-stu-id="e2636-165">**Process chain**</span></span>  
 <span data-ttu-id="e2636-166">Введите имя процесса цепочки, которое будет вызвано источником.</span><span class="sxs-lookup"><span data-stu-id="e2636-166">Enter the name of the process chain to be triggered by the source.</span></span>  
  
 <span data-ttu-id="e2636-167">**Найти**</span><span class="sxs-lookup"><span data-stu-id="e2636-167">**Look up**</span></span>  
 <span data-ttu-id="e2636-168">Выполните поиск цепочки процесса при помощи диалогового окна **Найти цепочку процесса** .</span><span class="sxs-lookup"><span data-stu-id="e2636-168">Look up the process chain by using the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="e2636-169">Дополнительные сведения об этом диалоговом окне см. в разделе [Look Up Process Chain](look-up-process-chain.md).</span><span class="sxs-lookup"><span data-stu-id="e2636-169">For more information about this dialog box, see [Look Up Process Chain](look-up-process-chain.md).</span></span>  
  
### <a name="execution-mode--w---wait-for-notify"></a><span data-ttu-id="e2636-170">Режим выполнения — W = Ожидать уведомления</span><span class="sxs-lookup"><span data-stu-id="e2636-170">Execution Mode = W - Wait for Notify</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="e2636-171">Параметры назначения RFC</span><span class="sxs-lookup"><span data-stu-id="e2636-171">RFC Destination Options</span></span>  
 <span data-ttu-id="e2636-172">Нет необходимости в изучении или вводе этих значений заранее.</span><span class="sxs-lookup"><span data-stu-id="e2636-172">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="e2636-173">Нажмите кнопку **Поиск** , чтобы найти и выбрать соответствующее назначение RFC.</span><span class="sxs-lookup"><span data-stu-id="e2636-173">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="e2636-174">После выбора назначения RFC компонент вводит соответствующие значения для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="e2636-174">After you select an RFC destination, the component enters the appropriate values for the options.</span></span>  
  
 <span data-ttu-id="e2636-175">**Узел шлюза**</span><span class="sxs-lookup"><span data-stu-id="e2636-175">**Gateway host**</span></span>  
 <span data-ttu-id="e2636-176">Введите имя или IP-адрес сервера узла шлюза.</span><span class="sxs-lookup"><span data-stu-id="e2636-176">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="e2636-177">Обычно имя или IP-адрес совпадают с аналогичными данными сервера приложений SAP.</span><span class="sxs-lookup"><span data-stu-id="e2636-177">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="e2636-178">**Служба шлюза**</span><span class="sxs-lookup"><span data-stu-id="e2636-178">**Gateway service**</span></span>  
 <span data-ttu-id="e2636-179">Введите имя службы шлюза в формате `sapgwNN`, где `NN` — номер системы.</span><span class="sxs-lookup"><span data-stu-id="e2636-179">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="e2636-180">**ID программы**</span><span class="sxs-lookup"><span data-stu-id="e2636-180">**Program ID**</span></span>  
 <span data-ttu-id="e2636-181">Введите идентификатор программы, связанный с назначением RFC.</span><span class="sxs-lookup"><span data-stu-id="e2636-181">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="e2636-182">**Найти**</span><span class="sxs-lookup"><span data-stu-id="e2636-182">**Look up**</span></span>  
 <span data-ttu-id="e2636-183">Выполните поиск назначения RFC с помощью диалогового окна **Поиск назначения RFC** .</span><span class="sxs-lookup"><span data-stu-id="e2636-183">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="e2636-184">Дополнительные сведения об этом диалоговом окне см. в разделе [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="e2636-184">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="execution-mode--e---extract-only"></a><span data-ttu-id="e2636-185">Режим выполнения = E — только извлечение</span><span class="sxs-lookup"><span data-stu-id="e2636-185">Execution Mode = E - Extract Only</span></span>  
 <span data-ttu-id="e2636-186">**Идентификатор запроса**</span><span class="sxs-lookup"><span data-stu-id="e2636-186">**Request ID**</span></span>  
 <span data-ttu-id="e2636-187">Введите идентификатор запроса, связанный с извлечением.</span><span class="sxs-lookup"><span data-stu-id="e2636-187">Enter the Request ID that is associated with the extraction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2636-188">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2636-188">See Also</span></span>  
 <span data-ttu-id="e2636-189">[Редактор источника SAP BW (страница "Столбцы")](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="e2636-189">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="e2636-190">[Редактор источника SAP BW (страница "Вывод ошибок")](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="e2636-190">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="e2636-191">[Редактор источника SAP BW (страница "Дополнительно")](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="e2636-191">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="e2636-192">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="e2636-192">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
