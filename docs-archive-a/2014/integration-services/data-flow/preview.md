---
title: Предварительный просмотр | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 551494c4-9e27-4592-9200-c6bf19e80c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a795338122c1e7a37a23fdb6af6153f74b927e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657181"
---
# <a name="preview"></a><span data-ttu-id="1763c-102">Preview (Предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="1763c-102">Preview</span></span>
  <span data-ttu-id="1763c-103">В диалоговом окне **Предварительный просмотр** можно просмотреть данные, извлекаемые источником SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1763c-103">Use the **Preview** dialog box to preview the data that the SAP BW source will extract.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1763c-104">Параметр **Предварительный просмотр** , доступный на странице **Диспетчер соединений** **Редактора источника SAP BW**, непосредственно извлекает данные.</span><span class="sxs-lookup"><span data-stu-id="1763c-104">The **Preview** option, that is available on the **Connection Manager** page of the **SAP BW Source Editor**, actually extracts data.</span></span> <span data-ttu-id="1763c-105">Если настроить SAP Netweaver BW для извлечения только тех данных, которые изменились со времени предыдущего сеанса извлечения, то при выборе параметра **Предварительный просмотр** просматриваемые данные будут исключены из следующего сеанса извлечения.</span><span class="sxs-lookup"><span data-stu-id="1763c-105">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="1763c-106">Для получения дополнительных сведений о компоненте источника SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Источник SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="1763c-106">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1763c-107">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1763c-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="1763c-108">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="1763c-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1763c-109">Для извлечения данных из SAP Netweaver BW требуется дополнительная лицензия SAP.</span><span class="sxs-lookup"><span data-stu-id="1763c-109">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="1763c-110">Обратитесь к SAP, чтобы уточнить требования.</span><span class="sxs-lookup"><span data-stu-id="1763c-110">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="1763c-111">**Открытие диалогового окна «Предварительный просмотр»**</span><span class="sxs-lookup"><span data-stu-id="1763c-111">**To open the Preview dialog box**</span></span>  
  
1.  <span data-ttu-id="1763c-112">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1763c-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="1763c-113">На вкладке **Поток данных** дважды щелкните источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1763c-113">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="1763c-114">В **Редакторе источника SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="1763c-114">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="1763c-115">Настройте источник SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1763c-115">Configure the SAP BW source.</span></span>  
  
5.  <span data-ttu-id="1763c-116">После настройки источника SAP BW на странице **Диспетчер соединений** щелкните **Предварительный просмотр** для предварительного просмотра данных в диалоговом окне **Предварительный просмотр** .</span><span class="sxs-lookup"><span data-stu-id="1763c-116">After you configure the SAP BW source, on the **Connection Manager** page, click **Preview** to preview the data in the **Preview** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1763c-117">При щелчке **Предварительный просмотр** также открывается диалоговое окно **Журнал запросов** .</span><span class="sxs-lookup"><span data-stu-id="1763c-117">Clicking **Preview** also opens the **Request Log** dialog box.</span></span> <span data-ttu-id="1763c-118">Дополнительные сведения об этом диалоговом окне см. в разделе [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="1763c-118">For more information about this dialog box, see [Request Log](request-log.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1763c-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="1763c-119">Options</span></span>  
 <span data-ttu-id="1763c-120">В диалоговом окне **Предварительный просмотр** отображаются строки, запрошенные в системе SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1763c-120">The **Preview** dialog box displays the rows that are requested from the SAP Netweaver BW system.</span></span> <span data-ttu-id="1763c-121">Отображаемые столбцы — это столбцы, определенные в исходных данных.</span><span class="sxs-lookup"><span data-stu-id="1763c-121">The columns that are displayed are the columns that are defined in the source data.</span></span>  
  
 <span data-ttu-id="1763c-122">В этом диалоговом окне отсутствуют другие параметры.</span><span class="sxs-lookup"><span data-stu-id="1763c-122">There are no other options in this dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1763c-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="1763c-123">See Also</span></span>  
 <span data-ttu-id="1763c-124">[Редактор источника SAP BW (страница "Диспетчер подключений")](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="1763c-124">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="1763c-125">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="1763c-125">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
