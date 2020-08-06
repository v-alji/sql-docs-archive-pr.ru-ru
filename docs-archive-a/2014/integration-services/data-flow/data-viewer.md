---
title: Средство просмотра данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataviewer.f1
helpviewer_keywords:
- Data Viewer dialog box
ms.assetid: 6351309a-688f-4e82-9697-1712130f10a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dc576981e875eade84dd3576f4ed93b66784411f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665040"
---
# <a name="data-viewer"></a><span data-ttu-id="ac171-102">Средство просмотра данных</span><span class="sxs-lookup"><span data-stu-id="ac171-102">Data Viewer</span></span>
  <span data-ttu-id="ac171-103">Если настроен путь для применения средства просмотра данных, то это средство отображает данные буфер за буфером по мере перемещения данных между двумя компонентами потока данных.</span><span class="sxs-lookup"><span data-stu-id="ac171-103">If a path is configured to use a data viewer, the Data Viewer displays the data buffer by buffer as data moves between two data flow components.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac171-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac171-104">Options</span></span>  
 <span data-ttu-id="ac171-105">**Зеленая стрелка**</span><span class="sxs-lookup"><span data-stu-id="ac171-105">**Green arrow**</span></span>  
 <span data-ttu-id="ac171-106">Переход к данным в следующем буфере.</span><span class="sxs-lookup"><span data-stu-id="ac171-106">Click to display the data in the next buffer.</span></span> <span data-ttu-id="ac171-107">Если данные можно переместить в одиночный буфер, то этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="ac171-107">If the data can be moved in a single buffer, this option is not available.</span></span>  
  
 <span data-ttu-id="ac171-108">**Отсоединить**</span><span class="sxs-lookup"><span data-stu-id="ac171-108">**Detach**</span></span>  
 <span data-ttu-id="ac171-109">Отсоединить средство просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="ac171-109">Detach the data viewer.</span></span>  
  
 <span data-ttu-id="ac171-110">**Примечание.** Отсоединение средства просмотра данных не приводит к удалению самого средства.</span><span class="sxs-lookup"><span data-stu-id="ac171-110">**Note** Detaching a data viewer does not delete the data viewer.</span></span> <span data-ttu-id="ac171-111">При отсоединении средства просмотра данных данные продолжают следовать по пути, однако данные в средстве просмотра не обновляются для поддержания соответствия с данными в каждом буфере.</span><span class="sxs-lookup"><span data-stu-id="ac171-111">If the data viewer has been detached, data continues to flow through the path, but the data in the viewer is not updated to match the data in each buffer.</span></span>  
  
 <span data-ttu-id="ac171-112">**Присоединить**</span><span class="sxs-lookup"><span data-stu-id="ac171-112">**Attach**</span></span>  
 <span data-ttu-id="ac171-113">Присоединить средство просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="ac171-113">Attach a data viewer.</span></span>  
  
 <span data-ttu-id="ac171-114">**Примечание.** Когда средство просмотра данных присоединяется, оно отображает информация из каждого буфера потока данных, а затем приостанавливает свою работу.</span><span class="sxs-lookup"><span data-stu-id="ac171-114">**Note** When the data viewer is attached, it displays information from each buffer in the data flow and then pauses.</span></span> <span data-ttu-id="ac171-115">Можно перемещаться от буфера к буферу с помощью зеленой стрелки.</span><span class="sxs-lookup"><span data-stu-id="ac171-115">You can advance through the buffers by using the green arrow.</span></span>  
  
 <span data-ttu-id="ac171-116">**Скопировать данные**</span><span class="sxs-lookup"><span data-stu-id="ac171-116">**Copy Data**</span></span>  
 <span data-ttu-id="ac171-117">Копирование данных текущего буфера в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="ac171-117">Copy data in the current buffer to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac171-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac171-118">See Also</span></span>  
 [<span data-ttu-id="ac171-119">Отладка потока данных</span><span class="sxs-lookup"><span data-stu-id="ac171-119">Debugging Data Flow</span></span>](../troubleshooting/debugging-data-flow.md)  
  
  
