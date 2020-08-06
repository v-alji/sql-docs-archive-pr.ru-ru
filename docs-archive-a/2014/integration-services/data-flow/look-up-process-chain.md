---
title: Поиск цепочки процессов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f6303ea4-fbbf-4cba-bc60-828df62be8c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2e0d3743071d018a8a82f60eeaf04fd86dec3e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731922"
---
# <a name="look-up-process-chain"></a><span data-ttu-id="8a6c4-102">Поиск цепочки процессов</span><span class="sxs-lookup"><span data-stu-id="8a6c4-102">Look Up Process Chain</span></span>
  <span data-ttu-id="8a6c4-103">Используйте диалоговое окно **Поиск цепочки процессов** для поиска цепочки процессов, определенной в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-103">Use the **Look Up Process Chain** dialog box to look up a process chain that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="8a6c4-104">После отображения списка доступных цепочек процесса выберите необходимую цепочку, и источник заполнит связанные параметры необходимыми значениями.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-104">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="8a6c4-105">Источник SAP BW [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW использует диалоговое окно **Поиск цепочки процессов** .</span><span class="sxs-lookup"><span data-stu-id="8a6c4-105">The SAP BW source of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="8a6c4-106">Дополнительные сведения об источнике SAP BW см. в разделе [SAP BW Source](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="8a6c4-106">To learn more about the SAP BW source, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8a6c4-107">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="8a6c4-108">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="8a6c4-109">**Открытие диалогового окна поиска цепочки процессов**</span><span class="sxs-lookup"><span data-stu-id="8a6c4-109">**To open the Look Up Process Chain dialog box**</span></span>  
  
1.  <span data-ttu-id="8a6c4-110">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="8a6c4-111">На вкладке **Поток данных** дважды щелкните источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="8a6c4-112">В **Редакторе источника SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="8a6c4-112">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="8a6c4-113">В поле группы **Цепочка процессов** щелкните **Поиск** , чтобы открыть диалоговое окно **Поиск цепочки процессов** .</span><span class="sxs-lookup"><span data-stu-id="8a6c4-113">In the **Process Chain** group box, click **Look up** to display the **Look Up Process Chain** dialog box.</span></span>  
  
     <span data-ttu-id="8a6c4-114">Поле группы **Цепочка процессов** появляется только в том случае, если параметр **Режим выполнения** имеет значение **P — запустить цепочку процессов**.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-114">The **Process Chain** group box appears only if the value for **Execution mode** is **P - Trigger process chain**.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="8a6c4-115">Параметры поиска</span><span class="sxs-lookup"><span data-stu-id="8a6c4-115">Lookup Options</span></span>  
 <span data-ttu-id="8a6c4-116">В полях поиска можно фильтровать результаты с помощью символа-шаблона звездочки (\*) или с помощью частичной строки в сочетании с символом-шаблоном звездочки.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-116">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="8a6c4-117">Однако если оставить поле поиска пустым, то критериям поиска в этом поле будут соответствовать только пустые строки.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-117">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="8a6c4-118">**Цепочка процесса**</span><span class="sxs-lookup"><span data-stu-id="8a6c4-118">**Process chain**</span></span>  
 <span data-ttu-id="8a6c4-119">Введите имя цепочки процессов для поиска или введите часть имени с символом-шаблоном звездочки (\*).</span><span class="sxs-lookup"><span data-stu-id="8a6c4-119">Enter the name of the process chain that you want to look up, or enter a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="8a6c4-120">Также можно использовать только символ-шаблон звездочки для включения всех цепочек процессов.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-120">Or, use the asterisk wildcard character alone to include all process chains.</span></span>  
  
 <span data-ttu-id="8a6c4-121">**Найти**</span><span class="sxs-lookup"><span data-stu-id="8a6c4-121">**Look up**</span></span>  
 <span data-ttu-id="8a6c4-122">Выполните поиск соответствующих цепочек процессов, определенных в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-122">Look up matching process chains that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="8a6c4-123">Результаты поиска</span><span class="sxs-lookup"><span data-stu-id="8a6c4-123">Lookup Results</span></span>  
 <span data-ttu-id="8a6c4-124">После нажатия кнопки «Поиск» список цепочек процессов в системе SAP Netweaver BW отобразится в таблице со следующими заголовками столбцов.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-124">After you click the Look up button, a list of the process chains in the SAP Netweaver BW system appears in a table with the following column headings:</span></span>  
  
 <span data-ttu-id="8a6c4-125">**Цепочка процессов**</span><span class="sxs-lookup"><span data-stu-id="8a6c4-125">**Process Chain**</span></span>  
 <span data-ttu-id="8a6c4-126">Отображается имя цепочки процессов, определенной в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-126">Displays the name of the process chain that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="8a6c4-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8a6c4-127">**Description**</span></span>  
 <span data-ttu-id="8a6c4-128">Отображается описание цепочки процессов.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-128">Displays the description of the process chain.</span></span>  
  
 <span data-ttu-id="8a6c4-129">После отображения списка доступных цепочек процесса выберите необходимую цепочку, и источник заполнит связанные параметры необходимыми значениями.</span><span class="sxs-lookup"><span data-stu-id="8a6c4-129">When the list of available process chains appears, select the chain that you want, and the source will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6c4-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a6c4-130">See Also</span></span>  
 <span data-ttu-id="8a6c4-131">[Редактор источника SAP BW (страница "Диспетчер подключений")](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="8a6c4-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="8a6c4-132">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="8a6c4-132">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
