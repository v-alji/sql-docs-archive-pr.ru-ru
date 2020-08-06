---
title: Создание InfoSource для основных данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b52a9a89-8380-4a02-8a83-dcfb46ae860e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bb90bc5cf27f37dc89df236b765db98088a5804a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728565"
---
# <a name="create-infosource-for-master-data"></a><span data-ttu-id="41478-102">Создание InfoSource для основных данных</span><span class="sxs-lookup"><span data-stu-id="41478-102">Create InfoSource for Master Data</span></span>
  <span data-ttu-id="41478-103">Используйте диалоговое окно **Создание InfoSource для основных данных** для создания нового InfoSource для основных данных в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="41478-103">Use the **Create InfoSource for Master Data** dialog box to create a new InfoSource for master data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="41478-104">Диалоговое окно **Создание InfoSource для основных данных** можно открыть на странице **Диспетчер соединений** **Редактора назначений SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="41478-104">You can open the **Create InfoSource for Master Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="41478-105">Дополнительные сведения о назначении SAP BW см. в статье [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="41478-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="41478-106">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="41478-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="41478-107">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="41478-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="41478-108">**Открытие диалогового окна «Создание InfoSource для основных данных»**</span><span class="sxs-lookup"><span data-stu-id="41478-108">**To open the Create InfoSource for Master Data dialog box**</span></span>  
  
1.  <span data-ttu-id="41478-109">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="41478-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="41478-110">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="41478-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="41478-111">В **Редакторе назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="41478-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="41478-112">На вкладке **Диспетчер соединений** в поле группы **Создание объектов SAP BW** выберите **InfoSource**и щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="41478-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="41478-113">В диалоговом окне **Создание InfoSource** выберите **Основные данные**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="41478-113">In the **Create InfoSource** dialog box, select **Master data**, and then click **OK**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="41478-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="41478-114">Options</span></span>  
 <span data-ttu-id="41478-115">**Имя InfoObject**</span><span class="sxs-lookup"><span data-stu-id="41478-115">**InfoObject name**</span></span>  
 <span data-ttu-id="41478-116">Введите имя InfoObject, на основе которого должен быть создан новый InfoSource.</span><span class="sxs-lookup"><span data-stu-id="41478-116">Enter the name of the InfoObject on which the new InfoSource should be based.</span></span>  
  
 <span data-ttu-id="41478-117">**Найти**</span><span class="sxs-lookup"><span data-stu-id="41478-117">**Look up**</span></span>  
 <span data-ttu-id="41478-118">Поиск InfoObject.</span><span class="sxs-lookup"><span data-stu-id="41478-118">Look up the InfoObject.</span></span> <span data-ttu-id="41478-119">Этот параметр открывает диалоговое окно **Поиск InfoObject** , в котором можно выбрать InfoObject.</span><span class="sxs-lookup"><span data-stu-id="41478-119">This option opens the **Look Up InfoObject** dialog box in which you can select the InfoObject.</span></span> <span data-ttu-id="41478-120">Дополнительные сведения об этом диалоговом окне см. в разделе [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="41478-120">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="41478-121">После выбора InfoObject компонент указывает в текстовом поле **Имя InfoObject** имя выбранного InfoObject.</span><span class="sxs-lookup"><span data-stu-id="41478-121">After you select an InfoObject, the component populates the **InfoObject name** text box with the name of the selected InfoObject.</span></span>  
  
 <span data-ttu-id="41478-122">**Создать**</span><span class="sxs-lookup"><span data-stu-id="41478-122">**New**</span></span>  
 <span data-ttu-id="41478-123">Создание нового InfoObject</span><span class="sxs-lookup"><span data-stu-id="41478-123">Create a new InfoObject.</span></span> <span data-ttu-id="41478-124">Этот параметр открывает диалоговое окно **Создание InfoObject**, в котором можно создать InfoObject.</span><span class="sxs-lookup"><span data-stu-id="41478-124">This option opens the **Create New InfoObject** dialog box in which you can create the new InfoObject.</span></span> <span data-ttu-id="41478-125">Дополнительные сведения об этом диалоговом окне см. в разделе [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="41478-125">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="41478-126">После создания InfoObject компонент указывает в текстовом поле **Имя InfoObject** имя нового InfoObject.</span><span class="sxs-lookup"><span data-stu-id="41478-126">After you create an InfoObject, the component populates the **InfoObject name** text box with the name of the new InfoObject.</span></span>  
  
 <span data-ttu-id="41478-127">**Краткое описание**</span><span class="sxs-lookup"><span data-stu-id="41478-127">**Short description**</span></span>  
 <span data-ttu-id="41478-128">Введите краткое описание нового InfoSource.</span><span class="sxs-lookup"><span data-stu-id="41478-128">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="41478-129">**Полное описание**</span><span class="sxs-lookup"><span data-stu-id="41478-129">**Long description**</span></span>  
 <span data-ttu-id="41478-130">Введите полное описание нового InfoSource.</span><span class="sxs-lookup"><span data-stu-id="41478-130">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="41478-131">**Исходная система**</span><span class="sxs-lookup"><span data-stu-id="41478-131">**Source system**</span></span>  
 <span data-ttu-id="41478-132">Выберите исходную систему, которая будет связана с новым InfoSource.</span><span class="sxs-lookup"><span data-stu-id="41478-132">Select the source system to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="41478-133">**Приложение**</span><span class="sxs-lookup"><span data-stu-id="41478-133">**Application**</span></span>  
 <span data-ttu-id="41478-134">Введите имя приложения, которое необходимо связать с новым InfoSource.</span><span class="sxs-lookup"><span data-stu-id="41478-134">Enter the name of the application to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="41478-135">**Атрибуты**</span><span class="sxs-lookup"><span data-stu-id="41478-135">**Attributes**</span></span>  
 <span data-ttu-id="41478-136">Указывает, что основные данные состоят из атрибутов.</span><span class="sxs-lookup"><span data-stu-id="41478-136">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="41478-137">**Тексты**</span><span class="sxs-lookup"><span data-stu-id="41478-137">**Texts**</span></span>  
 <span data-ttu-id="41478-138">Указывает, что основные данные состоят из атрибутов.</span><span class="sxs-lookup"><span data-stu-id="41478-138">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="41478-139">**Сохранить и активировать**</span><span class="sxs-lookup"><span data-stu-id="41478-139">**Save & Activate**</span></span>  
 <span data-ttu-id="41478-140">Сохраните и активируйте новый InfoSource.</span><span class="sxs-lookup"><span data-stu-id="41478-140">Save and activate the new InfoSource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41478-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="41478-141">See Also</span></span>  
 <span data-ttu-id="41478-142">[Создание InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="41478-142">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="41478-143">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="41478-143">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
