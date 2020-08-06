---
title: Установка точек останова | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.setbreakpoints.f1
helpviewer_keywords:
- Set Breakpoints dialog box
ms.assetid: 876e61b7-875c-43f4-bbce-d7eeb90f6730
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8115fcd845ee5ff415d13aa4fe36230234e33ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738114"
---
# <a name="set-breakpoints"></a><span data-ttu-id="dbe07-102">Задание точек останова</span><span class="sxs-lookup"><span data-stu-id="dbe07-102">Set Breakpoints</span></span>
  <span data-ttu-id="dbe07-103">Диалоговое окно **Установка точек останова** используется для указания событий, для которых будут включены точки останова, а также управления поведением точек останова.</span><span class="sxs-lookup"><span data-stu-id="dbe07-103">Use the **Set Breakpoints** dialog box to specify the events on which to enable breakpoints and to control the behavior of the breakpoint.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dbe07-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="dbe07-104">Options</span></span>  
 <span data-ttu-id="dbe07-105">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="dbe07-105">**Enabled**</span></span>  
 <span data-ttu-id="dbe07-106">Выберите, чтобы включить точку останова для события.</span><span class="sxs-lookup"><span data-stu-id="dbe07-106">Select to enable a breakpoint on an event.</span></span>  
  
 <span data-ttu-id="dbe07-107">**Break Condition**</span><span class="sxs-lookup"><span data-stu-id="dbe07-107">**Break Condition**</span></span>  
 <span data-ttu-id="dbe07-108">Позволяет просмотреть список доступных событий, для которых можно установить точки останова.</span><span class="sxs-lookup"><span data-stu-id="dbe07-108">View a list of available events on which to set breakpoints.</span></span>  
  
 <span data-ttu-id="dbe07-109">**Hit Count Type**</span><span class="sxs-lookup"><span data-stu-id="dbe07-109">**Hit Count Type**</span></span>  
 <span data-ttu-id="dbe07-110">Позволяет указать условия срабатывания точки останова.</span><span class="sxs-lookup"><span data-stu-id="dbe07-110">Specify when the breakpoint takes effect.</span></span>  
  
|<span data-ttu-id="dbe07-111">Значение</span><span class="sxs-lookup"><span data-stu-id="dbe07-111">Value</span></span>|<span data-ttu-id="dbe07-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dbe07-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dbe07-113">**Всегда**</span><span class="sxs-lookup"><span data-stu-id="dbe07-113">**Always**</span></span>|<span data-ttu-id="dbe07-114">Выполнение приостанавливается при каждом попадании в точку останова.</span><span class="sxs-lookup"><span data-stu-id="dbe07-114">Execution is always suspended when the breakpoint is hit.</span></span>|  
|<span data-ttu-id="dbe07-115">**Число попаданий**</span><span class="sxs-lookup"><span data-stu-id="dbe07-115">**Hit count equals**</span></span>|<span data-ttu-id="dbe07-116">Выполнение приостанавливается, если число попаданий в точку останова равно значению счетчика попаданий.</span><span class="sxs-lookup"><span data-stu-id="dbe07-116">Execution is suspended when the number of times the breakpoint has occurred is equal to the hit count.</span></span>|  
|<span data-ttu-id="dbe07-117">**Число попаданий больше или равно**</span><span class="sxs-lookup"><span data-stu-id="dbe07-117">**Hit greater or equal**</span></span>|<span data-ttu-id="dbe07-118">Выполнение приостанавливается, если число попаданий в точку останова становится равным или больше значения, заданного счетчиком попаданий.</span><span class="sxs-lookup"><span data-stu-id="dbe07-118">Execution is suspended when the number of times the breakpoint has occurred is equal to or greater than the hit count.</span></span>|  
|<span data-ttu-id="dbe07-119">**Число попаданий кратно**</span><span class="sxs-lookup"><span data-stu-id="dbe07-119">**Hit count multiple**</span></span>|<span data-ttu-id="dbe07-120">Выполнение приостанавливается, если число попаданий в точку останова кратно установленному.</span><span class="sxs-lookup"><span data-stu-id="dbe07-120">Execution is suspended when a multiple of the hit count occurs.</span></span> <span data-ttu-id="dbe07-121">Например, если значение этого параметра равно 5, выполнение приостанавливается на каждой пятой точке прерывания.</span><span class="sxs-lookup"><span data-stu-id="dbe07-121">For example, if you set this option to 5, execution is suspended every fifth time.</span></span>|  
  
 <span data-ttu-id="dbe07-122">**Число попаданий**</span><span class="sxs-lookup"><span data-stu-id="dbe07-122">**Hit Count**</span></span>  
 <span data-ttu-id="dbe07-123">Позволяет задать число попаданий в точку останова, необходимое для приостановки выполнения.</span><span class="sxs-lookup"><span data-stu-id="dbe07-123">Specify the number of hits at which to trigger a break.</span></span> <span data-ttu-id="dbe07-124">Этот параметр недоступен, если точка останова настроена на срабатывание всегда.</span><span class="sxs-lookup"><span data-stu-id="dbe07-124">This option is not available if the breakpoint is always in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe07-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="dbe07-125">See Also</span></span>  
 [<span data-ttu-id="dbe07-126">Отладка потока управления</span><span class="sxs-lookup"><span data-stu-id="dbe07-126">Debugging Control Flow</span></span>](../../../integration-services/troubleshooting/debugging-control-flow.md)  
  
  
