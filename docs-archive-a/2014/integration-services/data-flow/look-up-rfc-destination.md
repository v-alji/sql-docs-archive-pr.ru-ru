---
title: Поиск назначения RFC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db9404d8-4c42-45e5-a100-c7a84b056109
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 397298fce16509e667aa4baccaee62c6ff0f5cca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750048"
---
# <a name="look-up-rfc-destination"></a><span data-ttu-id="d38bd-102">Поиск назначения RFC</span><span class="sxs-lookup"><span data-stu-id="d38bd-102">Look Up RFC Destination</span></span>
  <span data-ttu-id="d38bd-103">Используйте диалоговое окно **Поиск назначения RFC** для поиска назначения RFC, определенного в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d38bd-103">Use the **Look Up RFC Destination** dialog box to look up an RFC destination that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="d38bd-104">После открытия списка доступных назначений RFC выберите необходимое назначение и компонент заполнит связанные параметры необходимыми значениями.</span><span class="sxs-lookup"><span data-stu-id="d38bd-104">When the list of available RFC destinations appears, select the destination that you want, and the component will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="d38bd-105">Источник и назначение SAP BW используют диалоговое окно **Поиск назначения RFC** .</span><span class="sxs-lookup"><span data-stu-id="d38bd-105">Both the SAP BW source and the SAP BW destination use the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="d38bd-106">Дополнительные сведения об этих компонентах [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. в разделах [Источник SAP BW](sap-bw-source.md) и [Назначение SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d38bd-106">For more information about these components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md) and [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d38bd-107">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d38bd-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d38bd-108">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="d38bd-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="d38bd-109">**Открытие диалогового окно «Поиск назначения RFC»**</span><span class="sxs-lookup"><span data-stu-id="d38bd-109">**To open the Look Up RFC Destination dialog box**</span></span>  
  
1.  <span data-ttu-id="d38bd-110">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий источник или назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d38bd-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source or destination.</span></span>  
  
2.  <span data-ttu-id="d38bd-111">На вкладке **Поток данных** дважды щелкните источник или назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d38bd-111">On the **Data Flow** tab, double-click the SAP BW source or destination.</span></span>  
  
3.  <span data-ttu-id="d38bd-112">В **Редактор источников SAP BW** или **Редактор назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="d38bd-112">In the **SAP BW Source Editor** or the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="d38bd-113">На странице **Диспетчер соединений** в поле группы **Назначение RFC** щелкните **Поиск** , чтобы открыть диалоговое окно **Поиск назначения RFC** .</span><span class="sxs-lookup"><span data-stu-id="d38bd-113">On the **Connection Manager** page, in the **RFC Destination** group box, click **Look up** to display the **Look Up RFC Destination** dialog box.</span></span>  
  
     <span data-ttu-id="d38bd-114">На вкладке **Редактор источников SAP BW**поле группы **Назначение RFC** отображается только в случае, если параметр **Режим выполнения** имеет значение **P — запустить цепочку процесса** или **W — ждать уведомления**.</span><span class="sxs-lookup"><span data-stu-id="d38bd-114">In the **SAP BW Source Editor**, the **RFC Destination** group box appears only if the value for **Execution mode** is **P - Trigger process chain** or **W - Wait for notify**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d38bd-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="d38bd-115">Options</span></span>  
 <span data-ttu-id="d38bd-116">**Назначение**</span><span class="sxs-lookup"><span data-stu-id="d38bd-116">**Destination**</span></span>  
 <span data-ttu-id="d38bd-117">Просмотрите имя назначения RFC, определенное в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d38bd-117">View the name of the RFC destination that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="d38bd-118">**Узел шлюза**</span><span class="sxs-lookup"><span data-stu-id="d38bd-118">**Gateway Host**</span></span>  
 <span data-ttu-id="d38bd-119">Просмотрите имя или IP-адрес сервера узла шлюза.</span><span class="sxs-lookup"><span data-stu-id="d38bd-119">View the server name or IP address of the gateway host.</span></span> <span data-ttu-id="d38bd-120">Обычно имя или IP-адрес совпадают с аналогичными данными сервера приложений SAP.</span><span class="sxs-lookup"><span data-stu-id="d38bd-120">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="d38bd-121">**Служба шлюза**</span><span class="sxs-lookup"><span data-stu-id="d38bd-121">**Gateway Service**</span></span>  
 <span data-ttu-id="d38bd-122">Просмотрите имя службы шлюза в формате `sapgwNN`, где `NN` — номер системы.</span><span class="sxs-lookup"><span data-stu-id="d38bd-122">View the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="d38bd-123">**ID программы**</span><span class="sxs-lookup"><span data-stu-id="d38bd-123">**Program ID**</span></span>  
 <span data-ttu-id="d38bd-124">Просмотрите идентификатор программы, связанный с назначением RFC.</span><span class="sxs-lookup"><span data-stu-id="d38bd-124">View the Program ID that is associated with the RFC destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38bd-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d38bd-125">See Also</span></span>  
 <span data-ttu-id="d38bd-126">[Редактор источника SAP BW (страница "Диспетчер подключений")](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d38bd-126">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d38bd-127">[Редактор назначений SAP BW (страница "Диспетчер подключений")](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d38bd-127">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="d38bd-128">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="d38bd-128">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
