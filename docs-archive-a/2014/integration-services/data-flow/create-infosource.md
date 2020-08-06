---
title: Создание InfoSource | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7db233b-5464-43de-9d26-6dd24c7ac1b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9620d3170310322c79679e8298ffe465067ae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728553"
---
# <a name="create-infosource"></a><span data-ttu-id="fbbc7-102">Создание InfoSource</span><span class="sxs-lookup"><span data-stu-id="fbbc7-102">Create InfoSource</span></span>
  <span data-ttu-id="fbbc7-103">Используйте диалоговое окно **Создание InfoSource** для создания нового InfoSource.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-103">Use the **Create InfoSource** dialog box to create a new InfoSource.</span></span> <span data-ttu-id="fbbc7-104">Для создания нового InfoSource используется либо диалоговое окно **Создание InfoSource для данных транзакции** , либо диалоговое окно **Создание InfoSource для основных данных** .</span><span class="sxs-lookup"><span data-stu-id="fbbc7-104">To create the new InfoSource, you use either the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span>  
  
 <span data-ttu-id="fbbc7-105">Диалоговое окно **Создание InfoSource** можно открыть на странице **Диспетчер соединений** **Редактора назначений SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-105">You can open the **Create InfoSource** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="fbbc7-106">Дополнительные сведения о назначении SAP BW см. в статье [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc7-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fbbc7-107">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="fbbc7-108">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="fbbc7-109">**Открытие диалогового окна «Создание InfoSource»**</span><span class="sxs-lookup"><span data-stu-id="fbbc7-109">**To open the Create InfoSource dialog box**</span></span>  
  
1.  <span data-ttu-id="fbbc7-110">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="fbbc7-111">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="fbbc7-112">В **Редакторе назначений SAP BW**щелкните **Диспетчер соединений** , чтобы открыть страницу редактора **Диспетчер соединений** .</span><span class="sxs-lookup"><span data-stu-id="fbbc7-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="fbbc7-113">На вкладке **Диспетчер соединений** в поле группы **Создание объектов SAP BW** выберите **InfoSource**и щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fbbc7-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbbc7-114">Options</span></span>  
 <span data-ttu-id="fbbc7-115">**Данные транзакций**</span><span class="sxs-lookup"><span data-stu-id="fbbc7-115">**Transaction data**</span></span>  
 <span data-ttu-id="fbbc7-116">Создание нового InfoSource для данных транзакции.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-116">Create a new InfoSource for transaction data.</span></span>  
  
 <span data-ttu-id="fbbc7-117">Если выбран этот параметр, то откроется диалоговое окно **Создание InfoSource для данных транзакции** .</span><span class="sxs-lookup"><span data-stu-id="fbbc7-117">If you select this option, the **Create InfoSource for Transaction Data** dialog box opens.</span></span> <span data-ttu-id="fbbc7-118">Используйте диалоговое окно **Создание InfoSource для данных транзакции** для создания нового InfoSource.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-118">You use the **Create InfoSource for Transaction Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="fbbc7-119">Дополнительные сведения об этом диалоговом окне см. в разделе [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc7-119">For more information about this dialog box, see [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md).</span></span>  
  
 <span data-ttu-id="fbbc7-120">**Основные данные**</span><span class="sxs-lookup"><span data-stu-id="fbbc7-120">**Master data**</span></span>  
 <span data-ttu-id="fbbc7-121">Создание нового InfoSource для основных данных.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-121">Create a new InfoSource for master data.</span></span>  
  
 <span data-ttu-id="fbbc7-122">Если выбран этот параметр, то откроется диалоговое окно **Создание InfoSource для основных данных** .</span><span class="sxs-lookup"><span data-stu-id="fbbc7-122">If you select this option, the **Create InfoSource for Master Data** dialog box opens.</span></span> <span data-ttu-id="fbbc7-123">Используйте диалоговое окно **Создание InfoSource для основных данных** для создания нового InfoSource.</span><span class="sxs-lookup"><span data-stu-id="fbbc7-123">You use the **Create InfoSource for Master Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="fbbc7-124">Дополнительные сведения об этом диалоговом окне см. в разделе [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc7-124">For more information about this dialog box, see [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbbc7-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="fbbc7-125">See Also</span></span>  
 [<span data-ttu-id="fbbc7-126">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="fbbc7-126">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
