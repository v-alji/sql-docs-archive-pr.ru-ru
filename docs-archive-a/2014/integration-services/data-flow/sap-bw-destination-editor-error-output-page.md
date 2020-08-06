---
title: Редактор назначения SAP BW (страница "Вывод ошибок") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a543d811-0bd2-4890-a0d3-f5fdcd4524b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ffd58580865a71626252aa2d177530e41156537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728542"
---
# <a name="sap-bw-destination-editor-error-output-page"></a><span data-ttu-id="08edb-102">Редактор назначений SAP BW (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="08edb-102">SAP BW Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="08edb-103">Используйте страницу **Вывод ошибок** диалогового окна **Редактор назначений SAP BW** для задания параметров обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="08edb-103">Use the **Error Output** page of the **SAP BW Destination Editor** to specify error handling options.</span></span>  
  
 <span data-ttu-id="08edb-104">Для получения дополнительных сведений о назначении SAP BW для [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 для SAP BW см. раздел [Назначение SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="08edb-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="08edb-105">Документация по Microsoft Connector 1.1 для SAP BW предполагает, что читатель знаком со средой SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="08edb-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="08edb-106">Дополнительные сведения о SAP Netweaver BW или сведения о настройке объектов и процессов SAP Netweaver BW см. в документации SAP.</span><span class="sxs-lookup"><span data-stu-id="08edb-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="08edb-107">**Открытие страницы «Вывод ошибок»**</span><span class="sxs-lookup"><span data-stu-id="08edb-107">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="08edb-108">В [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="08edb-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="08edb-109">На вкладке **Поток данных** дважды щелкните назначение SAP BW.</span><span class="sxs-lookup"><span data-stu-id="08edb-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="08edb-110">В окне **Редактор назначений SAP BW**щелкните **Вывод ошибок** , чтобы открыть страницу редактора **Вывод ошибок** .</span><span class="sxs-lookup"><span data-stu-id="08edb-110">In the **SAP BW Destination Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="08edb-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="08edb-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08edb-112">Если вы не знаете все значения, необходимые для настройки назначения, может потребоваться связаться с администратором SAP.</span><span class="sxs-lookup"><span data-stu-id="08edb-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="08edb-113">**Вход или выход**</span><span class="sxs-lookup"><span data-stu-id="08edb-113">**Input or Output**</span></span>  
 <span data-ttu-id="08edb-114">Просмотрите имя входных данных.</span><span class="sxs-lookup"><span data-stu-id="08edb-114">View the name of the input.</span></span>  
  
 <span data-ttu-id="08edb-115">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="08edb-115">**Column**</span></span>  
 <span data-ttu-id="08edb-116">Данный параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="08edb-116">This option is not used.</span></span>  
  
 <span data-ttu-id="08edb-117">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="08edb-117">**Error**</span></span>  
 <span data-ttu-id="08edb-118">Задайте действие, которое необходимо выполнить в назначении при возникновении ошибки: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="08edb-118">Specify what the destination should do when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="08edb-119">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="08edb-119">**Truncation**</span></span>  
 <span data-ttu-id="08edb-120">Данный параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="08edb-120">This option is not used.</span></span>  
  
 <span data-ttu-id="08edb-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="08edb-121">**Description**</span></span>  
 <span data-ttu-id="08edb-122">Просмотрите описание операции.</span><span class="sxs-lookup"><span data-stu-id="08edb-122">View the description of the operation.</span></span>  
  
 <span data-ttu-id="08edb-123">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="08edb-123">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="08edb-124">Укажите действие, которое необходимо применить в назначении ко всем выбранным ячейкам при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="08edb-124">Specify what the destination should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="08edb-125">**Применить**</span><span class="sxs-lookup"><span data-stu-id="08edb-125">**Apply**</span></span>  
 <span data-ttu-id="08edb-126">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="08edb-126">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08edb-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="08edb-127">See Also</span></span>  
 <span data-ttu-id="08edb-128">[Редактор назначений SAP BW (страница "Диспетчер подключений")](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="08edb-128">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="08edb-129">[Редактор назначений SAP BW (страница "Сопоставления")](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="08edb-129">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="08edb-130">[Редактор назначений SAP BW (страница "Дополнительно")](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="08edb-130">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="08edb-131">Справка F1 по Microsoft Connector 1.1 для SAP BW</span><span class="sxs-lookup"><span data-stu-id="08edb-131">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
