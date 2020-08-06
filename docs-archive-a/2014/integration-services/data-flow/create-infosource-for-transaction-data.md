---
title: Создание InfoSource для данных транзакции | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab5f23e2-cd4e-4507-83d9-ac5ef721c171
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e3a60bb93da17e79087982473e92c35fa0856d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728557"
---
# <a name="create-infosource-for-transaction-data"></a><span data-ttu-id="200d1-102">Создание InfoSource для данных транзакции</span><span class="sxs-lookup"><span data-stu-id="200d1-102">Create InfoSource for Transaction Data</span></span>
  <span data-ttu-id="200d1-103">Используйте диалоговое окно **Создание InfoSource для данных транзакции** , чтобы создать новый InfoSource для данных транзакции в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="200d1-103">Use the **Create InfoSource for Transaction Data** dialog box to create a new InfoSource for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="200d1-104">Можно открыть диалоговое окно **Создание InfoSource для данных транзакции** на странице **Диспетчер соединений** **Редактора назначений SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="200d1-104">You can open the **Create InfoSource for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="200d1-105">Дополнительные сведения о назначении SAP BW см. в статье [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="200d1-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="200d1-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="200d1-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="200d1-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="200d1-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="200d1-108">**Открытие диалогового окна «Создание InfoSource для данных транзакции»**</span><span class="sxs-lookup"><span data-stu-id="200d1-108">**To open the Create InfoSource for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="200d1-109">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="200d1-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="200d1-110">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="200d1-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="200d1-111">В **Редакторе назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="200d1-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="200d1-112">На вкладке **Диспетчер соединений** в поле группы **Создание объектов SAP BW** выберите **InfoSource**и щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="200d1-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="200d1-113">В диалоговом окне **Создание InfoSource** выберите **Данные транзакции**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="200d1-113">In the **Create InfoSource** dialog box, select **Transaction data**, and then click **OK**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="200d1-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="200d1-114">General Options</span></span>  
 <span data-ttu-id="200d1-115">**Имя InfoSource**</span><span class="sxs-lookup"><span data-stu-id="200d1-115">**InfoSource name**</span></span>  
 <span data-ttu-id="200d1-116">Введите имя нового InfoSource.</span><span class="sxs-lookup"><span data-stu-id="200d1-116">Enter a name for the new InfoSource.</span></span>  
  
 <span data-ttu-id="200d1-117">**Краткое описание**</span><span class="sxs-lookup"><span data-stu-id="200d1-117">**Short description**</span></span>  
 <span data-ttu-id="200d1-118">Введите краткое описание нового InfoSource.</span><span class="sxs-lookup"><span data-stu-id="200d1-118">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="200d1-119">**Полное описание**</span><span class="sxs-lookup"><span data-stu-id="200d1-119">**Long description**</span></span>  
 <span data-ttu-id="200d1-120">Введите полное описание нового InfoSource.</span><span class="sxs-lookup"><span data-stu-id="200d1-120">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="200d1-121">**Исходная система**</span><span class="sxs-lookup"><span data-stu-id="200d1-121">**Source system**</span></span>  
 <span data-ttu-id="200d1-122">Выберите исходную систему, связанную с InfoSource.</span><span class="sxs-lookup"><span data-stu-id="200d1-122">Select the source system associated with the InfoSource.</span></span>  
  
 <span data-ttu-id="200d1-123">**Сохранить и активировать**</span><span class="sxs-lookup"><span data-stu-id="200d1-123">**Save & Activate**</span></span>  
 <span data-ttu-id="200d1-124">Сохраните и активируйте новый InfoSource.</span><span class="sxs-lookup"><span data-stu-id="200d1-124">Save and activate the new InfoSource.</span></span>  
  
## <a name="infosource-transfer-structure-options"></a><span data-ttu-id="200d1-125">Параметры переноса структуры InfoSource</span><span class="sxs-lookup"><span data-stu-id="200d1-125">InfoSource Transfer Structure Options</span></span>  
 <span data-ttu-id="200d1-126">Средство переноса InfoSource позволяет сопоставить столбцы потока данных и источники InfoSource.</span><span class="sxs-lookup"><span data-stu-id="200d1-126">The InfoSource transfer structure lets you associate data flow columns to InfoSources.</span></span>  
  
 <span data-ttu-id="200d1-127">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="200d1-127">**PipelineElement**</span></span>  
 <span data-ttu-id="200d1-128">Отображает столбец среди выходных данных потока, подключенного к целевому месту SAP BW.</span><span class="sxs-lookup"><span data-stu-id="200d1-128">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="200d1-129">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="200d1-129">**PipelineDataType**</span></span>  
 <span data-ttu-id="200d1-130">Отображает тип данных [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] для столбца потока данных.</span><span class="sxs-lookup"><span data-stu-id="200d1-130">Displays the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type of the data flow column.</span></span>  
  
 <span data-ttu-id="200d1-131">**Iobject — поиск**</span><span class="sxs-lookup"><span data-stu-id="200d1-131">**Iobject - Search**</span></span>  
 <span data-ttu-id="200d1-132">Сопоставьте существующий InfoObject со столбцом потока данных для текущей строки.</span><span class="sxs-lookup"><span data-stu-id="200d1-132">Associate an existing InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="200d1-133">Чтобы создать это сопоставление, щелкните **Найти**, а затем используйте диалоговое окно **Поиск InfoObject** для выбора существующего InfoObject.</span><span class="sxs-lookup"><span data-stu-id="200d1-133">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="200d1-134">Дополнительные сведения об этом диалоговом окне см. в разделе [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="200d1-134">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="200d1-135">После выбора существующего InfoObject компонент заполняет столбцы **InfoObject** и **Тип** выбранными значениями.</span><span class="sxs-lookup"><span data-stu-id="200d1-135">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="200d1-136">**Iobject — создать**</span><span class="sxs-lookup"><span data-stu-id="200d1-136">**Iobject - New**</span></span>  
 <span data-ttu-id="200d1-137">Создайте новый InfoObject и свяжите этот новый InfoObject со столбцом потока данных в текущей строке.</span><span class="sxs-lookup"><span data-stu-id="200d1-137">Create a new InfoObject and associate this new InfoObect to the data flow column in the current row.</span></span> <span data-ttu-id="200d1-138">Для создания нового InfoObject щелкните **Создать**, а затем используйте диалоговое окно **Создание InfoObject** для создания InfoObject.</span><span class="sxs-lookup"><span data-stu-id="200d1-138">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="200d1-139">Дополнительные сведения об этом диалоговом окне см. в разделе [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="200d1-139">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="200d1-140">После создания нового InfoObject компонент заполняет столбцы **InfoObject** и **Тип** новыми значениями.</span><span class="sxs-lookup"><span data-stu-id="200d1-140">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="200d1-141">**Iobject — удаление**</span><span class="sxs-lookup"><span data-stu-id="200d1-141">**Iobject - Remove**</span></span>  
 <span data-ttu-id="200d1-142">Удаляет взаимосвязь между InfoObject и столбцом потока данных для текущей строки.</span><span class="sxs-lookup"><span data-stu-id="200d1-142">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="200d1-143">Чтобы удалить эту связь, нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="200d1-143">To remove this association, click **Remove**.</span></span>  
  
 <span data-ttu-id="200d1-144">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="200d1-144">**InfoObject**</span></span>  
 <span data-ttu-id="200d1-145">Отображает имя InfoObject, связанное со столбцом потока данных.</span><span class="sxs-lookup"><span data-stu-id="200d1-145">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="200d1-146">**Тип**</span><span class="sxs-lookup"><span data-stu-id="200d1-146">**Type**</span></span>  
 <span data-ttu-id="200d1-147">Отображает тип InfoObject, связанный со столбцом потока данных.</span><span class="sxs-lookup"><span data-stu-id="200d1-147">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="200d1-148">В следующей таблице приводятся возможные значения типа.</span><span class="sxs-lookup"><span data-stu-id="200d1-148">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="200d1-149">Значение</span><span class="sxs-lookup"><span data-stu-id="200d1-149">Value</span></span>|<span data-ttu-id="200d1-150">Description</span><span class="sxs-lookup"><span data-stu-id="200d1-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="200d1-151">CHA</span><span class="sxs-lookup"><span data-stu-id="200d1-151">CHA</span></span>|<span data-ttu-id="200d1-152">Характеристики</span><span class="sxs-lookup"><span data-stu-id="200d1-152">Characteristics</span></span>|  
|<span data-ttu-id="200d1-153">UNI</span><span class="sxs-lookup"><span data-stu-id="200d1-153">UNI</span></span>|<span data-ttu-id="200d1-154">Units</span><span class="sxs-lookup"><span data-stu-id="200d1-154">Units</span></span>|  
|<span data-ttu-id="200d1-155">KYF</span><span class="sxs-lookup"><span data-stu-id="200d1-155">KYF</span></span>|<span data-ttu-id="200d1-156">Ключевые цифры</span><span class="sxs-lookup"><span data-stu-id="200d1-156">Key figures</span></span>|  
|<span data-ttu-id="200d1-157">TIM</span><span class="sxs-lookup"><span data-stu-id="200d1-157">TIM</span></span>|<span data-ttu-id="200d1-158">Характеристики времени</span><span class="sxs-lookup"><span data-stu-id="200d1-158">Time characteristics</span></span>|  
  
 <span data-ttu-id="200d1-159">**Поле единицы**</span><span class="sxs-lookup"><span data-stu-id="200d1-159">**Unit Field**</span></span>  
 <span data-ttu-id="200d1-160">Укажите единицы, которые будут использоваться в InfoObject.</span><span class="sxs-lookup"><span data-stu-id="200d1-160">Specify the units that the InfoObject will use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200d1-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="200d1-161">See Also</span></span>  
 <span data-ttu-id="200d1-162">[Создание InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="200d1-162">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="200d1-163">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="200d1-163">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
