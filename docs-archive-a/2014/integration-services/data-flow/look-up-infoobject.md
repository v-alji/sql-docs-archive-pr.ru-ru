---
title: Поиск InfoObject | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7f4c132-a5ec-49d8-a964-45775432731f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1616b4fcb368afc9e3f1157a3fc2511d4a7e8cce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731926"
---
# <a name="look-up-infoobject"></a><span data-ttu-id="2e861-102">Поиск InfoObject</span><span class="sxs-lookup"><span data-stu-id="2e861-102">Look Up InfoObject</span></span>
  <span data-ttu-id="2e861-103">Используйте диалоговое окно **Поиск InfoObject** для поиска InfoObject, заданного в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="2e861-103">Use the **Look Up InfoObject** dialog box to look up an InfoObject that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="2e861-104">После открытия списка объектов InfoObject выберите нужный объект InfoObject, после чего целевой объект SAP BW заполнит связанные параметры необходимыми значениями.</span><span class="sxs-lookup"><span data-stu-id="2e861-104">When the list of available InfoObjects appears, select the InfoObject that you want, and the SAP BW destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="2e861-105">Целевой объект SAP BW [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW использует диалоговое окно **Найти InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="2e861-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up InfoObject** dialog box.</span></span> <span data-ttu-id="2e861-106">Дополнительные сведения о назначении SAP BW см. в статье [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="2e861-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2e861-107">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="2e861-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="2e861-108">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="2e861-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="2e861-109">**Открытие диалогового окна «Поиск InfoObject»**</span><span class="sxs-lookup"><span data-stu-id="2e861-109">**To open the Look Up InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="2e861-110">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="2e861-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="2e861-111">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="2e861-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="2e861-112">В **Редакторе назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="2e861-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="2e861-113">На странице **Диспетчер соединений** в разделе **Создание объектов SAP BW** выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="2e861-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select one of the following options:</span></span>  
  
    1.  <span data-ttu-id="2e861-114">Выберите **InfoCube**.</span><span class="sxs-lookup"><span data-stu-id="2e861-114">Select **InfoCube**.</span></span> <span data-ttu-id="2e861-115">Затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="2e861-115">Then, click **Create**.</span></span> <span data-ttu-id="2e861-116">В диалоговом окне **Создание InfoCube для данных транзакции** выберите **Найти** в столбце **IObject** в одной из строк в списке.</span><span class="sxs-lookup"><span data-stu-id="2e861-116">In the **Create InfoCube for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="2e861-117">Каждая строка представляет собой столбец в потоке данных пакета.</span><span class="sxs-lookup"><span data-stu-id="2e861-117">Each row represents a column in the data flow of the package.</span></span>  
  
    2.  <span data-ttu-id="2e861-118">Выберите **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="2e861-118">Select **InfoSource**.</span></span> <span data-ttu-id="2e861-119">Затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="2e861-119">Then click **Create**.</span></span> <span data-ttu-id="2e861-120">В диалоговом окне **Создание InfoSource** выберите **Данные транзакций**.</span><span class="sxs-lookup"><span data-stu-id="2e861-120">In the **Create InfoSource** dialog box, select **Transaction data**.</span></span> <span data-ttu-id="2e861-121">В диалоговом окне **Создание InfoSource для данных транзакции** выберите **Найти** в столбце **IObject** в одной из строк в списке.</span><span class="sxs-lookup"><span data-stu-id="2e861-121">In the **Create InfoSource for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="2e861-122">Каждая строка представляет собой столбец в потоке данных пакета.</span><span class="sxs-lookup"><span data-stu-id="2e861-122">Each row represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="2e861-123">Выберите **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="2e861-123">Select **InfoSource**.</span></span> <span data-ttu-id="2e861-124">Затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="2e861-124">Then click **Create**.</span></span> <span data-ttu-id="2e861-125">В диалоговом окне **Создание InfoSource** выберите **Главные данные**.</span><span class="sxs-lookup"><span data-stu-id="2e861-125">In the **Create InfoSource** dialog box, select **Master data**.</span></span> <span data-ttu-id="2e861-126">В диалоговом окне **Создание InfoSource для основных данных** нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="2e861-126">In the **Create InfoSource for Master Data** dialog box, click **Look up**.</span></span>  
  
 <span data-ttu-id="2e861-127">Также можно открыть диалоговое окно **Найти InfoObject** , щелкнув **Создать** в разделе **Атрибуты** диалогового окна **Создание нового InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="2e861-127">You can also open the **Look Up InfoObject** dialog box by clicking **Add** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="2e861-128">Параметры поиска</span><span class="sxs-lookup"><span data-stu-id="2e861-128">Lookup Options</span></span>  
 <span data-ttu-id="2e861-129">В текстовых полях поиска можно фильтровать результаты с помощью символа-шаблона звездочки (\*) или с помощью частичной строки в сочетании с символом-шаблоном звездочки.</span><span class="sxs-lookup"><span data-stu-id="2e861-129">In the lookup field text boxes, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="2e861-130">Однако если оставить поле поиска пустым, то процесс поиска будет находить только пустые строки в этом поле.</span><span class="sxs-lookup"><span data-stu-id="2e861-130">However, if you leave a lookup field empty, the lookup process will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="2e861-131">**Характеристики**</span><span class="sxs-lookup"><span data-stu-id="2e861-131">**Characteristics**</span></span>  
 <span data-ttu-id="2e861-132">Поиск объектов InfoObject, которые являются выражением характеристик.</span><span class="sxs-lookup"><span data-stu-id="2e861-132">Look up InfoObjects that represent characteristics.</span></span>  
  
 <span data-ttu-id="2e861-133">**Единицы измерения**</span><span class="sxs-lookup"><span data-stu-id="2e861-133">**Units**</span></span>  
 <span data-ttu-id="2e861-134">Поиск объектов InfoObject, которые представляют собой единицы.</span><span class="sxs-lookup"><span data-stu-id="2e861-134">Look up InfoObjects that represent units.</span></span>  
  
 <span data-ttu-id="2e861-135">**Ключевые цифры**</span><span class="sxs-lookup"><span data-stu-id="2e861-135">**Key figures**</span></span>  
 <span data-ttu-id="2e861-136">Поиск объектов InfoObject, которые представляют собой ключевые цифры.</span><span class="sxs-lookup"><span data-stu-id="2e861-136">Look up InfoObjects that represent key figures.</span></span>  
  
 <span data-ttu-id="2e861-137">**Характеристики времени**</span><span class="sxs-lookup"><span data-stu-id="2e861-137">**Time characteristics**</span></span>  
 <span data-ttu-id="2e861-138">Поиск объектов InfoObject, которые являются выражением характеристик времени.</span><span class="sxs-lookup"><span data-stu-id="2e861-138">Look up InfoObjects that represent time characteristics.</span></span>  
  
 <span data-ttu-id="2e861-139">**Название**</span><span class="sxs-lookup"><span data-stu-id="2e861-139">**Name**</span></span>  
 <span data-ttu-id="2e861-140">Введите имя InfoObject для поиска или часть имени с символом-шаблоном звездочки (\*).</span><span class="sxs-lookup"><span data-stu-id="2e861-140">Enter the name of the InfoObject that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="2e861-141">Также можно использовать символ-шаблон звездочки для включения всех объектов InfoObject.</span><span class="sxs-lookup"><span data-stu-id="2e861-141">Or, use the asterisk wildcard character alone to include all InfoObjects.</span></span>  
  
 <span data-ttu-id="2e861-142">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2e861-142">**Description**</span></span>  
 <span data-ttu-id="2e861-143">Введите описание или частичное описание с символом-шаблоном звездочки (\*).</span><span class="sxs-lookup"><span data-stu-id="2e861-143">Enter the description, or a partial description with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="2e861-144">Также можно использовать символ-шаблон звездочки для включения всех объектов InfoObject независимо от описания.</span><span class="sxs-lookup"><span data-stu-id="2e861-144">Or, use the asterisk wildcard character alone to include all InfoObjects regardless of description.</span></span>  
  
 <span data-ttu-id="2e861-145">**Найти**</span><span class="sxs-lookup"><span data-stu-id="2e861-145">**Look up**</span></span>  
 <span data-ttu-id="2e861-146">Выполните поиск соответствующих объектов InfoObject, определенных в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="2e861-146">Look up matching InfoObjects that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="2e861-147">Результаты поиска</span><span class="sxs-lookup"><span data-stu-id="2e861-147">Lookup Results</span></span>  
 <span data-ttu-id="2e861-148">После нажатия кнопки «Поиск» список объектов InfoObject в системе SAP Netweaver BW отобразится в таблице со следующими заголовками столбцов.</span><span class="sxs-lookup"><span data-stu-id="2e861-148">After you click the Look up button, a list of the InfoObjects in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="2e861-149">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="2e861-149">**InfoObject**</span></span>  
 <span data-ttu-id="2e861-150">Отображается имя объекта InfoObject, определенное в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="2e861-150">Displays the name of the InfoObject that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="2e861-151">**Текст (краткий)**</span><span class="sxs-lookup"><span data-stu-id="2e861-151">**Text (short)**</span></span>  
 <span data-ttu-id="2e861-152">Отображает краткий текст, связанный с объектом InfoObject.</span><span class="sxs-lookup"><span data-stu-id="2e861-152">Displays the short text that is associated with the InfoObject.</span></span>  
  
 <span data-ttu-id="2e861-153">После открытия списка объектов InfoObject выберите нужный объект InfoObject, после чего целевой объект заполнит связанные параметры необходимыми значениями.</span><span class="sxs-lookup"><span data-stu-id="2e861-153">When the list of available InfoObjects appears, select the InfoObject that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e861-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e861-154">See Also</span></span>  
 <span data-ttu-id="2e861-155">[Создание InfoCube для данных транзакции](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="2e861-155">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="2e861-156">[Создание InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="2e861-156">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="2e861-157">[Создание InfoSource для данных транзакции](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="2e861-157">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="2e861-158">[Создание InfoSource для основных данных](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="2e861-158">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 <span data-ttu-id="2e861-159">[Создание InfoObject](create-new-infoobject.md) </span><span class="sxs-lookup"><span data-stu-id="2e861-159">[Create New InfoObject](create-new-infoobject.md) </span></span>  
 <span data-ttu-id="2e861-160">[Редактор назначений SAP BW (страница "Диспетчер подключений")](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="2e861-160">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="2e861-161">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="2e861-161">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
