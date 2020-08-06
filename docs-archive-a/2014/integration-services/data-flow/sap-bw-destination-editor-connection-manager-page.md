---
title: Редактор назначений SAP BW (страница "Диспетчер соединений") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 04ae38f8-5287-45a3-826a-8aac5dd15a91
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd628f1a0fec09490e0d3720610d1232882ed92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728550"
---
# <a name="sap-bw-destination-editor-connection-manager-page"></a><span data-ttu-id="f0964-102">Редактор назначений SAP BW (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="f0964-102">SAP BW Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="f0964-103">Используйте страницу **Диспетчер соединений** диалогового окна **Редактор назначений SAP BW** для выбора диспетчера соединений SAP BW, который будет использоваться назначением SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f0964-103">Use the **Connection Manager** page of the **SAP BW Destination Editor** to select the SAP BW connection manager that the SAP BW destination will use.</span></span> <span data-ttu-id="f0964-104">На этой странице можно также выбрать параметры для загрузки данных в систему SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f0964-104">On this page, you also select the parameters for loading the data into the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="f0964-105">Для получения дополнительных сведений о назначении SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Назначение SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="f0964-105">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f0964-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f0964-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="f0964-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="f0964-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="f0964-108">**Открытие страницы «Диспетчер соединений»**</span><span class="sxs-lookup"><span data-stu-id="f0964-108">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="f0964-109">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f0964-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="f0964-110">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="f0964-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="f0964-111">В **Редакторе назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="f0964-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0964-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0964-112">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0964-113">Если вы не знаете все значения, необходимые для настройки назначения, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="f0964-113">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="f0964-114">**Диспетчер соединений SAP BW**</span><span class="sxs-lookup"><span data-stu-id="f0964-114">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="f0964-115">Выберите из списка существующий диспетчер соединений или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f0964-115">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="f0964-116">**Создать**</span><span class="sxs-lookup"><span data-stu-id="f0964-116">**New**</span></span>  
 <span data-ttu-id="f0964-117">Создайте новый диспетчер соединений с помощью диалогового окна **Диспетчер соединений SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="f0964-117">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="f0964-118">**Пробная нагрузка**</span><span class="sxs-lookup"><span data-stu-id="f0964-118">**Test Load**</span></span>  
 <span data-ttu-id="f0964-119">Выполните тест процесса загрузки, в которой используются выбранные параметры и не загружается ни одной строки.</span><span class="sxs-lookup"><span data-stu-id="f0964-119">Perform a test of the loading process that uses the settings that you have selected and loads zero rows.</span></span>  
  
### <a name="infopackageinfosource-options"></a><span data-ttu-id="f0964-120">Параметры InfoPackage/InfoSource</span><span class="sxs-lookup"><span data-stu-id="f0964-120">InfoPackage/InfoSource Options</span></span>  
 <span data-ttu-id="f0964-121">Нет необходимости в изучении или вводе этих значений заранее.</span><span class="sxs-lookup"><span data-stu-id="f0964-121">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="f0964-122">Нажмите кнопку **Поиск** , чтобы найти и выбрать соответствующий InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="f0964-122">Use the **Look up** button to find and select the appropriate InfoPackage.</span></span> <span data-ttu-id="f0964-123">После выбора InfoPackage компонент вводит соответствующие значения для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="f0964-123">After you select an InfoPackage, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="f0964-124">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="f0964-124">**InfoPackage**</span></span>  
 <span data-ttu-id="f0964-125">Введите имя InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="f0964-125">Enter the name of the InfoPackage.</span></span>  
  
 <span data-ttu-id="f0964-126">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="f0964-126">**InfoSource**</span></span>  
 <span data-ttu-id="f0964-127">Введите имя InfoSource.</span><span class="sxs-lookup"><span data-stu-id="f0964-127">Enter the name of the InfoSource.</span></span>  
  
 <span data-ttu-id="f0964-128">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f0964-128">**Type**</span></span>  
 <span data-ttu-id="f0964-129">Введите один символ, который определяет тип InfoSource.</span><span class="sxs-lookup"><span data-stu-id="f0964-129">Enter the single-character that identifies the type of the InfoSource.</span></span> <span data-ttu-id="f0964-130">В следующей таблице перечислены допустимые значения, состоящие из одного символа.</span><span class="sxs-lookup"><span data-stu-id="f0964-130">The following table lists the acceptable single-character values.</span></span>  
  
|<span data-ttu-id="f0964-131">Значение</span><span class="sxs-lookup"><span data-stu-id="f0964-131">Value</span></span>|<span data-ttu-id="f0964-132">Description</span><span class="sxs-lookup"><span data-stu-id="f0964-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f0964-133">**D**</span><span class="sxs-lookup"><span data-stu-id="f0964-133">**D**</span></span>|<span data-ttu-id="f0964-134">Данные транзакций</span><span class="sxs-lookup"><span data-stu-id="f0964-134">Transaction data</span></span>|  
|<span data-ttu-id="f0964-135">**M**</span><span class="sxs-lookup"><span data-stu-id="f0964-135">**M**</span></span>|<span data-ttu-id="f0964-136">Основные данные</span><span class="sxs-lookup"><span data-stu-id="f0964-136">Master data</span></span>|  
|<span data-ttu-id="f0964-137">**T**</span><span class="sxs-lookup"><span data-stu-id="f0964-137">**T**</span></span>|<span data-ttu-id="f0964-138">Тексты</span><span class="sxs-lookup"><span data-stu-id="f0964-138">Texts</span></span>|  
|<span data-ttu-id="f0964-139">**H**</span><span class="sxs-lookup"><span data-stu-id="f0964-139">**H**</span></span>|<span data-ttu-id="f0964-140">Данные иерархии</span><span class="sxs-lookup"><span data-stu-id="f0964-140">Hierarchy data</span></span>|  
  
 <span data-ttu-id="f0964-141">**Логическая система**</span><span class="sxs-lookup"><span data-stu-id="f0964-141">**Logical system**</span></span>  
 <span data-ttu-id="f0964-142">Введите имя логической системы, связанной с InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="f0964-142">Enter the name of the logical system that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="f0964-143">**Найти**</span><span class="sxs-lookup"><span data-stu-id="f0964-143">**Look up**</span></span>  
 <span data-ttu-id="f0964-144">Выполните поиск InfoPackage с помощью диалогового окна **Поиск InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="f0964-144">Look up the InfoPackage by using the **Look Up InfoPackage** dialog box.</span></span> <span data-ttu-id="f0964-145">Дополнительные сведения об этом диалоговом окне см. в разделе [Look Up InfoPackage](look-up-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="f0964-145">For more information about this dialog box, see [Look Up InfoPackage](look-up-infopackage.md).</span></span>  
  
### <a name="rfc-destination-options"></a><span data-ttu-id="f0964-146">Параметры назначения RFC</span><span class="sxs-lookup"><span data-stu-id="f0964-146">RFC Destination Options</span></span>  
 <span data-ttu-id="f0964-147">Нет необходимости в изучении или вводе этих значений заранее.</span><span class="sxs-lookup"><span data-stu-id="f0964-147">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="f0964-148">Нажмите кнопку **Поиск** , чтобы найти и выбрать соответствующее назначение RFC.</span><span class="sxs-lookup"><span data-stu-id="f0964-148">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="f0964-149">После выбора назначения RFC компонент вводит соответствующие значения для этих параметров.</span><span class="sxs-lookup"><span data-stu-id="f0964-149">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="f0964-150">**Узел шлюза**</span><span class="sxs-lookup"><span data-stu-id="f0964-150">**Gateway host**</span></span>  
 <span data-ttu-id="f0964-151">Введите имя или IP-адрес сервера узла шлюза.</span><span class="sxs-lookup"><span data-stu-id="f0964-151">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="f0964-152">Обычно имя или IP-адрес совпадают с аналогичными данными сервера приложений SAP.</span><span class="sxs-lookup"><span data-stu-id="f0964-152">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="f0964-153">**Служба шлюза**</span><span class="sxs-lookup"><span data-stu-id="f0964-153">**Gateway service**</span></span>  
 <span data-ttu-id="f0964-154">Введите имя службы шлюза в формате `sapgwNN`, где `NN` — номер системы.</span><span class="sxs-lookup"><span data-stu-id="f0964-154">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="f0964-155">**ID программы**</span><span class="sxs-lookup"><span data-stu-id="f0964-155">**Program ID**</span></span>  
 <span data-ttu-id="f0964-156">Введите идентификатор программы, связанный с назначением RFC.</span><span class="sxs-lookup"><span data-stu-id="f0964-156">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="f0964-157">**Найти**</span><span class="sxs-lookup"><span data-stu-id="f0964-157">**Look up**</span></span>  
 <span data-ttu-id="f0964-158">Выполните поиск назначения RFC с помощью диалогового окна **Поиск назначения RFC** .</span><span class="sxs-lookup"><span data-stu-id="f0964-158">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="f0964-159">Дополнительные сведения об этом диалоговом окне см. в разделе [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="f0964-159">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="create-sap-bw-objects-options"></a><span data-ttu-id="f0964-160">Параметры создания объектов SAP BW</span><span class="sxs-lookup"><span data-stu-id="f0964-160">Create SAP BW Objects Options</span></span>  
 <span data-ttu-id="f0964-161">**Выбрать тип объекта**</span><span class="sxs-lookup"><span data-stu-id="f0964-161">**Select object type**</span></span>  
 <span data-ttu-id="f0964-162">Выберите тип объекта SAP Netweaver BW, который нужно создать.</span><span class="sxs-lookup"><span data-stu-id="f0964-162">Select the type of SAP Netweaver BW object that you want to create.</span></span> <span data-ttu-id="f0964-163">Можно выбрать один из следующих типов.</span><span class="sxs-lookup"><span data-stu-id="f0964-163">You can select one of the following types:</span></span>  
  
-   <span data-ttu-id="f0964-164">InfoObject</span><span class="sxs-lookup"><span data-stu-id="f0964-164">InfoObject</span></span>  
  
-   <span data-ttu-id="f0964-165">InfoCube</span><span class="sxs-lookup"><span data-stu-id="f0964-165">InfoCube</span></span>  
  
-   <span data-ttu-id="f0964-166">InfoSource</span><span class="sxs-lookup"><span data-stu-id="f0964-166">InfoSource</span></span>  
  
-   <span data-ttu-id="f0964-167">InfoPackage</span><span class="sxs-lookup"><span data-stu-id="f0964-167">InfoPackage</span></span>  
  
 <span data-ttu-id="f0964-168">**Создание**</span><span class="sxs-lookup"><span data-stu-id="f0964-168">**Create**</span></span>  
 <span data-ttu-id="f0964-169">Создается выбранный тип объекта SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="f0964-169">Create the selected type of SAP Netweaver BW object.</span></span>  
  
|<span data-ttu-id="f0964-170">Тип объекта</span><span class="sxs-lookup"><span data-stu-id="f0964-170">Object Type</span></span>|<span data-ttu-id="f0964-171">Результат</span><span class="sxs-lookup"><span data-stu-id="f0964-171">Result</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="f0964-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="f0964-172">**InfoObject**</span></span>|<span data-ttu-id="f0964-173">Создается новый InfoObject с помощью диалогового окна **Создание нового InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="f0964-173">Create a new InfoObject by using the **Create New InfoObject** dialog box.</span></span> <span data-ttu-id="f0964-174">Дополнительные сведения об этом диалоговом окне см. в разделе [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="f0964-174">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>|  
|<span data-ttu-id="f0964-175">**InfoCube**</span><span class="sxs-lookup"><span data-stu-id="f0964-175">**InfoCube**</span></span>|<span data-ttu-id="f0964-176">Создается новый InfoCube с помощью диалогового окна **Создание InfoCube для данных транзакции** .</span><span class="sxs-lookup"><span data-stu-id="f0964-176">Create a new InfoCube by using the **Create InfoCube for Transaction Data** dialog box.</span></span> <span data-ttu-id="f0964-177">Дополнительные сведения об этом диалоговом окне см. в разделе [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="f0964-177">For more information about this dialog box, see [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span></span>|  
|<span data-ttu-id="f0964-178">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="f0964-178">**InfoSource**</span></span>|<span data-ttu-id="f0964-179">Создайте новый InfoSource с помощью диалогового окна **Создание InfoSource** , а затем используйте для этого диалоговое окно **Создание InfoSource для данных транзакции** или **Создание InfoSource для основных данных** .</span><span class="sxs-lookup"><span data-stu-id="f0964-179">Create a new InfoSource by using the **Create InfoSource** dialog box, and then by using the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span> <span data-ttu-id="f0964-180">Дополнительные сведения об этих диалоговых окнах см. в разделах [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) и [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="f0964-180">For more information about these dialog boxes, see [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) and [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>|  
|<span data-ttu-id="f0964-181">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="f0964-181">**InfoPackage**</span></span>|<span data-ttu-id="f0964-182">Создайте новый InfoPackage, используя диалоговое окно **Создание InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="f0964-182">Create a new InfoPackage by using the **Create InfoPackage** dialog box.</span></span> <span data-ttu-id="f0964-183">Дополнительные сведения об этом диалоговом окне см. в разделе [Create InfoPackage](create-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="f0964-183">For more information about this dialog box, see [Create InfoPackage](create-infopackage.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0964-184">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0964-184">See Also</span></span>  
 <span data-ttu-id="f0964-185">[Редактор назначений SAP BW (страница "Сопоставления")](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="f0964-185">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="f0964-186">[Редактор назначений SAP BW (страница "Вывод ошибок")](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="f0964-186">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="f0964-187">[Редактор назначений SAP BW (страница "Дополнительно")](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="f0964-187">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="f0964-188">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="f0964-188">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
