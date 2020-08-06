---
title: Создание InfoCube для данных транзакции | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 673cea01-a260-4fce-a1a0-f73839289805
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a20fe051cfdd3e6afe285279996fcf696a83c21b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728573"
---
# <a name="create-infocube-for-transaction-data"></a><span data-ttu-id="a6660-102">Создание InfoCube для данных транзакции</span><span class="sxs-lookup"><span data-stu-id="a6660-102">Create InfoCube for Transaction Data</span></span>
  <span data-ttu-id="a6660-103">Используйте диалоговое окно **Создание InfoCube для данных транзакции** , чтобы создать новый InfoCube для данных транзакции в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a6660-103">Use the **Create InfoCube for Transaction Data** dialog box to create a new InfoCube for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="a6660-104">Можно открыть диалоговое окно **Создание InfoCube для данных транзакции** на странице **Диспетчер соединений** **Редактора назначений SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="a6660-104">You can open the **Create InfoCube for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="a6660-105">Дополнительные сведения о назначении SAP BW см. в статье [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a6660-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a6660-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a6660-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a6660-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="a6660-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a6660-108">**Открытие диалогового окна «Создание InfoCube для данных транзакции»**</span><span class="sxs-lookup"><span data-stu-id="a6660-108">**To open the Create InfoCube for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="a6660-109">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a6660-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="a6660-110">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a6660-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="a6660-111">В **Редакторе назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="a6660-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="a6660-112">На вкладке **Диспетчер соединений** в поле группы **Создание объектов SAP BW** выберите **InfoCube**и щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a6660-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoCube**, and then click **Create**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="a6660-113">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a6660-113">General Options</span></span>  
 <span data-ttu-id="a6660-114">**Имя InfoCube**</span><span class="sxs-lookup"><span data-stu-id="a6660-114">**InfoCube name**</span></span>  
 <span data-ttu-id="a6660-115">Введите имя для нового InfoCube.</span><span class="sxs-lookup"><span data-stu-id="a6660-115">Enter a name for the new InfoCube.</span></span>  
  
 <span data-ttu-id="a6660-116">**Полное описание**</span><span class="sxs-lookup"><span data-stu-id="a6660-116">**Long description**</span></span>  
 <span data-ttu-id="a6660-117">Введите описание нового InfoCube.</span><span class="sxs-lookup"><span data-stu-id="a6660-117">Enter a description for the new InfoCube.</span></span>  
  
 <span data-ttu-id="a6660-118">**Сохранить и активировать**</span><span class="sxs-lookup"><span data-stu-id="a6660-118">**Save & Activate**</span></span>  
 <span data-ttu-id="a6660-119">Сохраните и активируйте новый InfoCube.</span><span class="sxs-lookup"><span data-stu-id="a6660-119">Save and activate the new InfoCube.</span></span>  
  
## <a name="infocube-transfer-structure-options"></a><span data-ttu-id="a6660-120">Параметры переноса структуры InfoCube</span><span class="sxs-lookup"><span data-stu-id="a6660-120">InfoCube Transfer Structure Options</span></span>  
 <span data-ttu-id="a6660-121">Раздел переноса структуры InfoCube позволяет привязать столбцы потока данных в InfoObjects.</span><span class="sxs-lookup"><span data-stu-id="a6660-121">The InfoCube transfer structure section lets you associate data flow columns to InfoObjects.</span></span>  
  
 <span data-ttu-id="a6660-122">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="a6660-122">**PipelineElement**</span></span>  
 <span data-ttu-id="a6660-123">Отображает столбец среди выходных данных потока, подключенного к целевому месту SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a6660-123">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="a6660-124">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="a6660-124">**PipelineDataType**</span></span>  
 <span data-ttu-id="a6660-125">Отображает тип данных столбца потока данных.</span><span class="sxs-lookup"><span data-stu-id="a6660-125">Displays the data type of the data flow column.</span></span>  
  
 <span data-ttu-id="a6660-126">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="a6660-126">**InfoObject**</span></span>  
 <span data-ttu-id="a6660-127">Отображает имя InfoObject, связанное со столбцом потока данных.</span><span class="sxs-lookup"><span data-stu-id="a6660-127">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="a6660-128">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a6660-128">**Type**</span></span>  
 <span data-ttu-id="a6660-129">Отображает тип InfoObject, связанный со столбцом потока данных.</span><span class="sxs-lookup"><span data-stu-id="a6660-129">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="a6660-130">В следующей таблице приводятся возможные значения типа.</span><span class="sxs-lookup"><span data-stu-id="a6660-130">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="a6660-131">Значение</span><span class="sxs-lookup"><span data-stu-id="a6660-131">Value</span></span>|<span data-ttu-id="a6660-132">Description</span><span class="sxs-lookup"><span data-stu-id="a6660-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6660-133">CHA</span><span class="sxs-lookup"><span data-stu-id="a6660-133">CHA</span></span>|<span data-ttu-id="a6660-134">Характеристики</span><span class="sxs-lookup"><span data-stu-id="a6660-134">Characteristics</span></span>|  
|<span data-ttu-id="a6660-135">UNI</span><span class="sxs-lookup"><span data-stu-id="a6660-135">UNI</span></span>|<span data-ttu-id="a6660-136">Units</span><span class="sxs-lookup"><span data-stu-id="a6660-136">Units</span></span>|  
|<span data-ttu-id="a6660-137">KYF</span><span class="sxs-lookup"><span data-stu-id="a6660-137">KYF</span></span>|<span data-ttu-id="a6660-138">Ключевые цифры</span><span class="sxs-lookup"><span data-stu-id="a6660-138">Key figures</span></span>|  
|<span data-ttu-id="a6660-139">TIM</span><span class="sxs-lookup"><span data-stu-id="a6660-139">TIM</span></span>|<span data-ttu-id="a6660-140">Характеристики времени</span><span class="sxs-lookup"><span data-stu-id="a6660-140">Time characteristics</span></span>|  
  
 <span data-ttu-id="a6660-141">**Iobject — поиск**</span><span class="sxs-lookup"><span data-stu-id="a6660-141">**Iobject - Search**</span></span>  
 <span data-ttu-id="a6660-142">Сопоставьте существующий InfoObject со столбцом потока данных для текущей строки.</span><span class="sxs-lookup"><span data-stu-id="a6660-142">Associate an existing InfoObject to the data flow column for the current row.</span></span> <span data-ttu-id="a6660-143">Чтобы создать это сопоставление, щелкните **Найти**, а затем используйте диалоговое окно **Поиск InfoObject** для выбора существующего InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a6660-143">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="a6660-144">Дополнительные сведения об этом диалоговом окне см. в разделе [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="a6660-144">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="a6660-145">После выбора существующего InfoObject компонент заполняет столбцы **InfoObject** и **Тип** выбранными значениями.</span><span class="sxs-lookup"><span data-stu-id="a6660-145">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="a6660-146">**Iobject — создать**</span><span class="sxs-lookup"><span data-stu-id="a6660-146">**Iobject - New**</span></span>  
 <span data-ttu-id="a6660-147">Создайте новый InfoObject и свяжите этот новый InfoObject со столбцом потока данных в текущей строке.</span><span class="sxs-lookup"><span data-stu-id="a6660-147">Create a new InfoObject and associate this new InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="a6660-148">Для создания нового InfoObject щелкните **Создать**, а затем используйте диалоговое окно **Создание InfoObject** для создания InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a6660-148">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="a6660-149">Дополнительные сведения об этом диалоговом окне см. в разделе [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="a6660-149">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="a6660-150">После создания нового InfoObject компонент заполняет столбцы **InfoObject** и **Тип** новыми значениями.</span><span class="sxs-lookup"><span data-stu-id="a6660-150">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="a6660-151">**Iobject — удаление**</span><span class="sxs-lookup"><span data-stu-id="a6660-151">**Iobject - Remove**</span></span>  
 <span data-ttu-id="a6660-152">Удаляет взаимосвязь между InfoObject и столбцом потока данных для текущей строки.</span><span class="sxs-lookup"><span data-stu-id="a6660-152">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="a6660-153">Чтобы удалить эту связь, нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a6660-153">To remove this association, click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6660-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6660-154">See Also</span></span>  
 [<span data-ttu-id="a6660-155">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="a6660-155">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
