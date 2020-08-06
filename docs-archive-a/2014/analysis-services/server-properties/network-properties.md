---
title: Свойства сети | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LingerTimeout property
- EnableNagleAlgorithm property
- MinPendingAcceptExCount property
- MaxPendingSendCount property
- EnableBinaryXML property
- MinPendingReceiveCount property
- MaxCompletedReceiveCount property
- DisableNonblockingMode property
- RequestSizeThreshold property
- CompressionLevel property
- ReceiveBufferSize property
- EnableCompression property
- ServerSendTimeout property
- IPV4Support property
- MaxPendingReceiveCount property
- MaxPendingAcceptExCount property
- IPV6Support property
- MaxAllowedRequestSize property
- ServerReceiveTimeout property
- EnableLingerOnClose property
- InitialConnectTimeout property
- SendBufferSize property
- ScatterReceiveMultiplier property
- network properties [Analysis Services]
ms.assetid: ef4251e2-abe5-4c5b-9868-7549782d0244
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10ad5bbbcffdfc3d3c4fefe3111e4c4425919915
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659022"
---
# <a name="network-properties"></a><span data-ttu-id="328d5-102">Свойства сети</span><span class="sxs-lookup"><span data-stu-id="328d5-102">Network Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="328d5-103">поддерживают свойства сервера, перечисленные в следующих таблицах.</span><span class="sxs-lookup"><span data-stu-id="328d5-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="328d5-104">Дополнительные сведения о дополнительных свойствах сервера и об их настройке см. в разделе [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="328d5-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="328d5-105">**Область применения:** многомерный и табличный режим сервера</span><span class="sxs-lookup"><span data-stu-id="328d5-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="general"></a><span data-ttu-id="328d5-106">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="328d5-106">General</span></span>  
 `ListenOnlyOnLocalConnections`  
 <span data-ttu-id="328d5-107">Логическое свойство, указывающее прослушивание только локальных соединений, например локального сервера.</span><span class="sxs-lookup"><span data-stu-id="328d5-107">A Boolean property that identifies whether to listen only on local connections, for example localhost.</span></span>  
  
## <a name="listener"></a><span data-ttu-id="328d5-108">Прослушиватель</span><span class="sxs-lookup"><span data-stu-id="328d5-108">Listener</span></span>  
 `IPV4Support`  
 <span data-ttu-id="328d5-109">Свойство с 32-разрядным целочисленным значением со знаком, определяющее поддержку протокола IPv4.</span><span class="sxs-lookup"><span data-stu-id="328d5-109">A signed 32-bit integer property that defines support for IPv4 protocol.</span></span> <span data-ttu-id="328d5-110">Это свойство имеет одно из значений, содержащихся в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="328d5-110">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="328d5-111">Значение</span><span class="sxs-lookup"><span data-stu-id="328d5-111">Value</span></span>|<span data-ttu-id="328d5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="328d5-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="328d5-113">*0*</span><span class="sxs-lookup"><span data-stu-id="328d5-113">*0*</span></span>|<span data-ttu-id="328d5-114">Протокол IPv4 отключен; подключение клиентов невозможно.</span><span class="sxs-lookup"><span data-stu-id="328d5-114">IPv4 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="328d5-115">*1*</span><span class="sxs-lookup"><span data-stu-id="328d5-115">*1*</span></span>|<span data-ttu-id="328d5-116">(По умолчанию) необходим протокол IPv4; сервер невозможно запустить без прослушивания по IPv4.</span><span class="sxs-lookup"><span data-stu-id="328d5-116">(Default) IPv4 is required; server won't start if it cannot listen to IPv4.</span></span>|  
|<span data-ttu-id="328d5-117">*2*</span><span class="sxs-lookup"><span data-stu-id="328d5-117">*2*</span></span>|<span data-ttu-id="328d5-118">Дополнительный протокол IPv4; сервер пытается прослушать по протоколу IPv4, но запускается в любом случае.</span><span class="sxs-lookup"><span data-stu-id="328d5-118">IPv4 is optional; server tries to listen to IPv4 but starts even if unable to.</span></span>|  
  
 `IPV6Support`  
 <span data-ttu-id="328d5-119">Свойство с 32-разрядным целочисленным значением со знаком, определяющее поддержку протокола IPv6.</span><span class="sxs-lookup"><span data-stu-id="328d5-119">A signed 32-bit integer property that defines support for IPv6 protocol.</span></span> <span data-ttu-id="328d5-120">Это свойство имеет одно из значений, содержащихся в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="328d5-120">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="328d5-121">Значение</span><span class="sxs-lookup"><span data-stu-id="328d5-121">Value</span></span>|<span data-ttu-id="328d5-122">Описание</span><span class="sxs-lookup"><span data-stu-id="328d5-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="328d5-123">*0*</span><span class="sxs-lookup"><span data-stu-id="328d5-123">*0*</span></span>|<span data-ttu-id="328d5-124">Протокол IPv6 отключен; подключение клиентов невозможно.</span><span class="sxs-lookup"><span data-stu-id="328d5-124">IPv6 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="328d5-125">*1*</span><span class="sxs-lookup"><span data-stu-id="328d5-125">*1*</span></span>|<span data-ttu-id="328d5-126">(По умолчанию) необходим протокол IPv6; сервер невозможно запустить без прослушивания по IPv6.</span><span class="sxs-lookup"><span data-stu-id="328d5-126">(Default) IPv6 is required; server won't start if it cannot listen to IPv6.</span></span>|  
|<span data-ttu-id="328d5-127">*2*</span><span class="sxs-lookup"><span data-stu-id="328d5-127">*2*</span></span>|<span data-ttu-id="328d5-128">Дополнительный протокол IPv6; сервер пытается прослушать по протоколу IPv6, но запускается в любом случае.</span><span class="sxs-lookup"><span data-stu-id="328d5-128">IPv6 is optional; server tries to listen to IPv6 but starts even if unable to.</span></span>|  
  
 `MaxAllowedRequestSize`  
 <span data-ttu-id="328d5-129">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-129">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RequestSizeThreshold`  
 <span data-ttu-id="328d5-130">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-130">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerReceiveTimeout`  
 <span data-ttu-id="328d5-131">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-131">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerSendTimeout`  
 <span data-ttu-id="328d5-132">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-132">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="requests"></a><span data-ttu-id="328d5-133">Requests</span><span class="sxs-lookup"><span data-stu-id="328d5-133">Requests</span></span>  
 `EnableBinaryXML`  
 <span data-ttu-id="328d5-134">Логическое свойство, определяющее, распознает ли сервер запросы в двоичном XML-формате.</span><span class="sxs-lookup"><span data-stu-id="328d5-134">A Boolean property that specifies whether the server will recognize requests binary xml format.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="328d5-135">Логическое свойство, определяющее сжатие запросов.</span><span class="sxs-lookup"><span data-stu-id="328d5-135">A Boolean property that specifies whether compression is enabled for requests.</span></span>  
  
## <a name="responses"></a><span data-ttu-id="328d5-136">Ответы</span><span class="sxs-lookup"><span data-stu-id="328d5-136">Responses</span></span>  
 `CompressionLevel`  
 <span data-ttu-id="328d5-137">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-137">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `EnableBinaryXML`  
 <span data-ttu-id="328d5-138">Логическое свойство, определяющее включение на сервере двоичных XML-ответов.</span><span class="sxs-lookup"><span data-stu-id="328d5-138">A Boolean property that specifies whether the server is enabled for binary xml responses.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="328d5-139">Логическое свойство, определяющее сжатие ответов клиентам.</span><span class="sxs-lookup"><span data-stu-id="328d5-139">A Boolean property that specifies whether compression is enabled for responses to client requests.</span></span>  
  
## <a name="tcp"></a><span data-ttu-id="328d5-140">TCP</span><span class="sxs-lookup"><span data-stu-id="328d5-140">TCP</span></span>  
 `InitialConnectTimeout`  
 <span data-ttu-id="328d5-141">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxCompletedReceiveCount`  
 <span data-ttu-id="328d5-142">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingAcceptExCount`  
 <span data-ttu-id="328d5-143">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-143">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingReceiveCount`  
 <span data-ttu-id="328d5-144">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingSendCount`  
 <span data-ttu-id="328d5-145">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-145">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingAcceptExCount`  
 <span data-ttu-id="328d5-146">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingReceiveCount`  
 <span data-ttu-id="328d5-147">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ScatterReceiveMultiplier`  
 <span data-ttu-id="328d5-148">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ DisableNonblockingMode`  
 <span data-ttu-id="328d5-149">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ EnableLingerOnClose`  
 <span data-ttu-id="328d5-150">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\EnableNagleAlgorithm`  
 <span data-ttu-id="328d5-151">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ LingerTimeout`  
 <span data-ttu-id="328d5-152">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ ReceiveBufferSize`  
 <span data-ttu-id="328d5-153">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-153">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ SendBufferSize`  
 <span data-ttu-id="328d5-154">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="328d5-154">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328d5-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="328d5-155">See Also</span></span>  
 <span data-ttu-id="328d5-156">[Настройка свойств сервера в Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="328d5-156">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="328d5-157">Определение режима работы сервера экземпляра служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="328d5-157">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
