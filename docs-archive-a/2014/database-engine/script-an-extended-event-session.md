---
title: Создание скрипта для сеанса расширенных событий | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f9fdde-1f13-4292-a4fc-55da826be3b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11adc60ae7c7e0f8b8012d06f56c83874d3708ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658384"
---
# <a name="script-an-extended-event-session"></a><span data-ttu-id="95da5-102">создать скрипт сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="95da5-102">Script an Extended Event Session</span></span>
  <span data-ttu-id="95da5-103">В этом разделе описано создание скрипта сеанса событий.</span><span class="sxs-lookup"><span data-stu-id="95da5-103">This topic describes how to script an event session.</span></span> <span data-ttu-id="95da5-104">Экспортировать, изменить или удалить сеанс событий либо удалить и создать сеанс событий можно в следующем:</span><span class="sxs-lookup"><span data-stu-id="95da5-104">You can export, alter, or drop the event session, or drop and create the event session to the following:</span></span>  
  
-   <span data-ttu-id="95da5-105">**Новое окно редактора запросов**</span><span class="sxs-lookup"><span data-stu-id="95da5-105">**New Query Editor Window**</span></span>  
  
-   <span data-ttu-id="95da5-106">**Файл**</span><span class="sxs-lookup"><span data-stu-id="95da5-106">**File**</span></span>  
  
-   <span data-ttu-id="95da5-107">**Буфер обмена**</span><span class="sxs-lookup"><span data-stu-id="95da5-107">**Clipboard**</span></span>  
  
-   <span data-ttu-id="95da5-108">**Задании агента**</span><span class="sxs-lookup"><span data-stu-id="95da5-108">**Agent Job**</span></span>  
  
### <a name="to-script-an-existing-event-session"></a><span data-ttu-id="95da5-109">Создание скрипта для существующего сеанса событий</span><span class="sxs-lookup"><span data-stu-id="95da5-109">To script an existing event session</span></span>  
  
1.  <span data-ttu-id="95da5-110">В обозревателе объектов разверните узел **Управление** , затем узел **Расширенные события**.</span><span class="sxs-lookup"><span data-stu-id="95da5-110">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="95da5-111">Щелкните правой кнопкой мыши сеанс, для которого нужно создать скрипт, укажите **Создать скрипт сеанса как**, укажите **СОЗДАТЬ в**и выберите, где создать скрипт сеанса.</span><span class="sxs-lookup"><span data-stu-id="95da5-111">Right-click the session you want to script, point to **Script Session as**, point to **CREATE to**, and then select where you want to script the session.</span></span>  
  
### <a name="to-script-a-new-event-session"></a><span data-ttu-id="95da5-112">Создание скрипта для нового сеанса событий</span><span class="sxs-lookup"><span data-stu-id="95da5-112">To script a new event session</span></span>  
  
1.  <span data-ttu-id="95da5-113">В обозревателе объектов разверните узел **Управление** , затем узел **Расширенные события**.</span><span class="sxs-lookup"><span data-stu-id="95da5-113">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="95da5-114">Щелкните правой кнопкой мыши **Сеансы**и выберите **Создать сеанс**.</span><span class="sxs-lookup"><span data-stu-id="95da5-114">Right-click **Sessions**, and then click **New Session**.</span></span>  
  
3.  <span data-ttu-id="95da5-115">В окне **Создание сеанса** создайте сеанс событий, затем в раскрывающемся списке **Скрипт** выберите, где следует создать скрипт сеанса событий.</span><span class="sxs-lookup"><span data-stu-id="95da5-115">In the **New Session** UI, create the event session, and then select where you want to script the event session from the **Script** drop-down list.</span></span>  
  
### <a name="to-script-a-modified-event-session"></a><span data-ttu-id="95da5-116">Создание скрипта измененного сеанса событий</span><span class="sxs-lookup"><span data-stu-id="95da5-116">To script a modified event session</span></span>  
  
1.  <span data-ttu-id="95da5-117">В обозревателе объектов разверните узел **Управление** , затем узел **Расширенные события**.</span><span class="sxs-lookup"><span data-stu-id="95da5-117">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="95da5-118">Щелкните правой кнопкой мыши сеанс, который нужно изменить, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="95da5-118">Right-click the session you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="95da5-119">В диалоговом окне **Свойства сеанса** измените сеанс событий и выберите в раскрывающемся списке **Скрипт** , где нужно создать скрипт измененного сеанса из списка.</span><span class="sxs-lookup"><span data-stu-id="95da5-119">In the **Session Properties** dialog box, modify the event session, and then select where you want to script the modified session from the **Script** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95da5-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="95da5-120">See Also</span></span>  
 [<span data-ttu-id="95da5-121">Расширенные события</span><span class="sxs-lookup"><span data-stu-id="95da5-121">Extended Events</span></span>](../relational-databases/extended-events/extended-events.md)  
  
  
