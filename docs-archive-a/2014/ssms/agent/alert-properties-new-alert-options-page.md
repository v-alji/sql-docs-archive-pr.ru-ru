---
title: 'Свойства предупреждения: новое оповещение (страница "Параметры") | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.options.f1
ms.assetid: 6e4f41aa-832d-46ba-b6b5-cf1d3b15d33f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a1507372aa1516c2a88b8682faa77a7d57e58f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737496"
---
# <a name="alert-properties-new-alert-options-page"></a><span data-ttu-id="c7c9e-102">Свойства оповещения: создание оповещения (страница "Параметры")</span><span class="sxs-lookup"><span data-stu-id="c7c9e-102">Alert Properties: New Alert (Options Page)</span></span>
  <span data-ttu-id="c7c9e-103">Эта страница используется для просмотра и изменения параметров [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предупреждений агента.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-103">Use this page to view and modify options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c7c9e-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="c7c9e-104">Options</span></span>  
 <span data-ttu-id="c7c9e-105">**Электронных**</span><span class="sxs-lookup"><span data-stu-id="c7c9e-105">**E-mail**</span></span>  
 <span data-ttu-id="c7c9e-106">Включает текст сообщения об ошибке от события, при наличии таковой, в уведомления, доставляемые по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-106">Include error text from the event, if any, in e-mail notifications.</span></span>  
  
 <span data-ttu-id="c7c9e-107">**Пейджер**</span><span class="sxs-lookup"><span data-stu-id="c7c9e-107">**Pager**</span></span>  
 <span data-ttu-id="c7c9e-108">Включает текст сообщения об ошибке от события, при наличии таковой, в уведомления, доставляемые на пейджер.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-108">Include error text from the event, if any, in pager notifications.</span></span>  
  
 <span data-ttu-id="c7c9e-109">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="c7c9e-109">**Net send**</span></span>  
 <span data-ttu-id="c7c9e-110">Включает текст сообщения об ошибке от события, при наличии таковой, в уведомления, доставляемые службой net send.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-110">Include error text from the event, if any, in net send notifications.</span></span>  
  
 <span data-ttu-id="c7c9e-111">**Дополнительное сообщение уведомления**</span><span class="sxs-lookup"><span data-stu-id="c7c9e-111">**Additional notification message to send**</span></span>  
 <span data-ttu-id="c7c9e-112">Введите любой дополнительный текст для включения в уведомления.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-112">Type any additional text to include in notification messages.</span></span>  
  
 <span data-ttu-id="c7c9e-113">**Задержка между ответами**</span><span class="sxs-lookup"><span data-stu-id="c7c9e-113">**Delay between responses**</span></span>  
 <span data-ttu-id="c7c9e-114">Укажите время задержки между повторными наступлениями события.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-114">Specify a delay for repeated occurrences of the event.</span></span> <span data-ttu-id="c7c9e-115">Некоторые события могут происходить часто в течение короткого периода времени.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-115">Some events may occur frequently during a short period of time.</span></span> <span data-ttu-id="c7c9e-116">В таком случае, вероятно, необходимо будет узнать о наступлении события, но не обязательно, чтобы для каждого события выдавался ответ.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-116">In this case, you may want to know that the event has occurred, but you may not want a response for every event.</span></span> <span data-ttu-id="c7c9e-117">Используйте этот параметр, чтобы указать время ожидания. С задержкой, после того, как предупреждение реагирует на событие, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Агент ждет, когда задерживается задержка, заданная перед ответом, независимо от того, возникает ли это событие во время задержки.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-117">Use this option to specify a time-out. With a delay, after the alert responds to an event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for the delay specified before responding again, regardless of whether the event occurs during the delay.</span></span>  
  
 <span data-ttu-id="c7c9e-118">**Тезис**</span><span class="sxs-lookup"><span data-stu-id="c7c9e-118">**Minutes**</span></span>  
 <span data-ttu-id="c7c9e-119">Укажите задержку в минутах.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-119">Specify a delay in minutes.</span></span> <span data-ttu-id="c7c9e-120">Для ответа при каждом наступлении события укажите 0 минут и 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-120">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
 <span data-ttu-id="c7c9e-121">**Несколько**</span><span class="sxs-lookup"><span data-stu-id="c7c9e-121">**Seconds**</span></span>  
 <span data-ttu-id="c7c9e-122">Укажите задержку в секундах.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-122">Specify a delay in seconds.</span></span> <span data-ttu-id="c7c9e-123">Для ответа при каждом наступлении события укажите 0 минут и 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="c7c9e-123">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c9e-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7c9e-124">See Also</span></span>  
 [<span data-ttu-id="c7c9e-125">Оповещения</span><span class="sxs-lookup"><span data-stu-id="c7c9e-125">Alerts</span></span>](alerts.md)  
  
  
