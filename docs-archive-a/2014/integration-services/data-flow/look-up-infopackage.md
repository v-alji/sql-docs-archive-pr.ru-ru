---
title: Поиск InfoPackage | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7c0cb7a4-cd07-44cc-85cb-eb1ad91f85fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e45477e8faeed07faa114850e10a3bc4bbcf170
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731925"
---
# <a name="look-up-infopackage"></a><span data-ttu-id="1ebd1-102">Поиск InfoPackage</span><span class="sxs-lookup"><span data-stu-id="1ebd1-102">Look Up InfoPackage</span></span>
  <span data-ttu-id="1ebd1-103">Используйте диалоговое окно **Поиск InfoPackage** для поиска InfoPackage, определенного в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-103">Use the **Look Up InfoPackage** dialog box to look up an InfoPackage that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="1ebd1-104">После открытия списка InfoPackage выберите необходимый InfoPackage, и назначение заполнит связанные параметры необходимыми значениями.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-104">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="1ebd1-105">Назначение SAP BW [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW использует диалоговое окно **Поиск цепочки процессов** .</span><span class="sxs-lookup"><span data-stu-id="1ebd1-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="1ebd1-106">Дополнительные сведения о назначении SAP BW см. в статье [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="1ebd1-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1ebd1-107">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="1ebd1-108">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="1ebd1-109">**Открытие диалогового окна «Поиск InfoPackage»**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-109">**To open the Look Up InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="1ebd1-110">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="1ebd1-111">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="1ebd1-112">В **Редакторе назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="1ebd1-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="1ebd1-113">На странице **Диспетчер соединений** в поле группы **InfoPackage/InfoSource** щелкните **Поиск** , чтобы открыть диалоговое окно **Поиск InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="1ebd1-113">On the **Connection Manager** page, in the **InfoPackage/InfoSource** group box, click **Look up** to display the **Look Up InfoPackage** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="1ebd1-114">Параметры поиска</span><span class="sxs-lookup"><span data-stu-id="1ebd1-114">Lookup Options</span></span>  
 <span data-ttu-id="1ebd1-115">В полях поиска можно фильтровать результаты с помощью символа-шаблона звездочки (\*) или с помощью частичной строки в сочетании с символом-шаблоном звездочки.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-115">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="1ebd1-116">Однако если оставить поле поиска пустым, то критериям поиска в этом поле будут соответствовать только пустые строки.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-116">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="1ebd1-117">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-117">**InfoPackage**</span></span>  
 <span data-ttu-id="1ebd1-118">Введите для поиска имя или часть имени InfoPackage с символом-шаблоном звездочки (\*).</span><span class="sxs-lookup"><span data-stu-id="1ebd1-118">Enter the name of the InfoPackage that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="1ebd1-119">Также можно использовать символ-шаблон звездочки для включения всех InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-119">Or, use the asterisk wildcard character alone to include all InfoPackages.</span></span>  
  
 <span data-ttu-id="1ebd1-120">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-120">**InfoSource**</span></span>  
 <span data-ttu-id="1ebd1-121">Введите имя или часть имени InfoSource с символом-шаблоном звездочки (\*).</span><span class="sxs-lookup"><span data-stu-id="1ebd1-121">Enter the name of the InfoSource, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="1ebd1-122">Также можно использовать символ-шаблон звездочки для включения всех InfoPackage независимо от InfoSource.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-122">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of InfoSource.</span></span>  
  
 <span data-ttu-id="1ebd1-123">**Исходная система**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-123">**Source system**</span></span>  
 <span data-ttu-id="1ebd1-124">Введите имя или часть имени исходной системы с символом-шаблоном звездочки (\*).</span><span class="sxs-lookup"><span data-stu-id="1ebd1-124">Enter the name of the source system, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="1ebd1-125">Также можно использовать символ-шаблон звездочки для включения всех InfoPackage независимо от исходных систем.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-125">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of source systems.</span></span>  
  
 <span data-ttu-id="1ebd1-126">**Найти**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-126">**Look up**</span></span>  
 <span data-ttu-id="1ebd1-127">Выполните поиск соответствующих InfoPackage, определенных в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-127">Look up matching InfoPackages that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="1ebd1-128">Результаты поиска</span><span class="sxs-lookup"><span data-stu-id="1ebd1-128">Lookup Results</span></span>  
 <span data-ttu-id="1ebd1-129">После нажатия кнопки «Поиск» список InfoPackage в системе SAP Netweaver BW отобразится в таблице со следующими заголовками столбцов.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-129">After you click the Look up button, a list of the InfoPackages in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="1ebd1-130">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-130">**InfoPackage**</span></span>  
 <span data-ttu-id="1ebd1-131">Отображается имя InfoPackage, определенное в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-131">Displays the name of the InfoPackage that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="1ebd1-132">**Тип**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-132">**Type**</span></span>  
 <span data-ttu-id="1ebd1-133">Отображается тип InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-133">Displays the type of the InfoPackage.</span></span> <span data-ttu-id="1ebd1-134">В следующей таблице приводятся возможные значения типа.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-134">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="1ebd1-135">Значение</span><span class="sxs-lookup"><span data-stu-id="1ebd1-135">Value</span></span>|<span data-ttu-id="1ebd1-136">Description</span><span class="sxs-lookup"><span data-stu-id="1ebd1-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1ebd1-137">транзакций</span><span class="sxs-lookup"><span data-stu-id="1ebd1-137">Trans.</span></span>|<span data-ttu-id="1ebd1-138">Данные транзакций.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-138">Transaction data.</span></span>|  
|<span data-ttu-id="1ebd1-139">Аттр.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-139">Attr.</span></span>|<span data-ttu-id="1ebd1-140">Данные атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-140">Attribute data.</span></span>|  
|<span data-ttu-id="1ebd1-141">Тексты</span><span class="sxs-lookup"><span data-stu-id="1ebd1-141">Texts</span></span>|<span data-ttu-id="1ebd1-142">Тексты.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-142">Texts.</span></span>|  
  
 <span data-ttu-id="1ebd1-143">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-143">**Description**</span></span>  
 <span data-ttu-id="1ebd1-144">Отображается описание InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-144">Displays the description of the InfoPackage.</span></span>  
  
 <span data-ttu-id="1ebd1-145">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-145">**InfoSource**</span></span>  
 <span data-ttu-id="1ebd1-146">Отображается имя InfoSource (если существует), которое связано с InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-146">Displays the name of the InfoSource, if any, that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="1ebd1-147">**Source System**</span><span class="sxs-lookup"><span data-stu-id="1ebd1-147">**Source System**</span></span>  
 <span data-ttu-id="1ebd1-148">Отображается имя исходной системы.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-148">Displays the name of the source system.</span></span>  
  
 <span data-ttu-id="1ebd1-149">После открытия списка InfoPackage выберите необходимый InfoPackage, и назначение заполнит связанные параметры необходимыми значениями.</span><span class="sxs-lookup"><span data-stu-id="1ebd1-149">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ebd1-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ebd1-150">See Also</span></span>  
 <span data-ttu-id="1ebd1-151">[Редактор назначений SAP BW (страница "Диспетчер подключений")](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="1ebd1-151">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="1ebd1-152">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="1ebd1-152">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
