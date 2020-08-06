---
title: Свойства диспетчера блокировок | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- lock manager properties [Analysis Services]
- LockWaitGranularityMS property
- DefaultLockTimeoutMS property
- DeadlockDetectionGranularityMS property
ms.assetid: 15fe9ead-825b-4ac3-9191-7a07caa2861b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d10927f1c549f00625b8affb801ec7b0831827c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752388"
---
# <a name="lock-manager-properties"></a><span data-ttu-id="609c7-102">Свойства диспетчера блокировок</span><span class="sxs-lookup"><span data-stu-id="609c7-102">Lock Manager Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="609c7-103">поддерживают свойства сервера диспетчера блокировок, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="609c7-103">supports the lock manager server properties listed in the following table.</span></span> <span data-ttu-id="609c7-104">Дополнительные сведения о дополнительных свойствах сервера и об их настройке см. в разделе [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="609c7-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="609c7-105">**Область применения:** многомерный и табличный режим сервера</span><span class="sxs-lookup"><span data-stu-id="609c7-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="609c7-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="609c7-106">Properties</span></span>  
 `DefaultLockTimeoutMS`  
 <span data-ttu-id="609c7-107">32-разрядное целочисленное свойство со знаком, которое определяет время ожидания блокировки по умолчанию в миллисекундах для внутренних запросов блокировки.</span><span class="sxs-lookup"><span data-stu-id="609c7-107">A signed 32-bit integer property that defines default lock timeout in milliseconds for internal lock requests.</span></span>  
  
 <span data-ttu-id="609c7-108">Значение по умолчанию для этого свойства -1, что соответствует отсутствию времени ожидания для внутренних запросов блокировки.</span><span class="sxs-lookup"><span data-stu-id="609c7-108">The default value for this property is -1, which indicates there is no timeout for internal lock requests.</span></span>  
  
 `LockWaitGranularityMS`  
 <span data-ttu-id="609c7-109">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="609c7-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DeadlockDetectionGranularityMS`  
 <span data-ttu-id="609c7-110">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="609c7-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="609c7-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="609c7-111">See Also</span></span>  
 <span data-ttu-id="609c7-112">[Настройка свойств сервера в Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="609c7-112">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="609c7-113">Определение режима работы сервера экземпляра служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="609c7-113">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
