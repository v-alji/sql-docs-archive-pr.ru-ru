---
title: Целевые серверы (вкладка "Состояние целевого сервера") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.target.status.f1
ms.assetid: 010a4cab-d878-4889-8ac8-7d91db6345d6
author: stevestein
ms.author: sstein
ms.openlocfilehash: be51648a4642d25c59e52be65e43037844ec0909
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731314"
---
# <a name="target-servers-target-server-status-tab"></a><span data-ttu-id="ee952-102">Целевые серверы (вкладка «Состояние целевого сервера»)</span><span class="sxs-lookup"><span data-stu-id="ee952-102">Target Servers (Target Server Status Tab)</span></span>
  <span data-ttu-id="ee952-103">Эта страница позволяет просматривать состояние целевых серверов для данного главного сервера.</span><span class="sxs-lookup"><span data-stu-id="ee952-103">Use this page to view the status of the target servers for this master server.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ee952-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee952-104">Options</span></span>  
 <span data-ttu-id="ee952-105">**Целевой сервер**</span><span class="sxs-lookup"><span data-stu-id="ee952-105">**Target Server**</span></span>  
 <span data-ttu-id="ee952-106">Просмотр имени целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="ee952-106">View the name of the target server.</span></span>  
  
 <span data-ttu-id="ee952-107">**Местное время**</span><span class="sxs-lookup"><span data-stu-id="ee952-107">**Local time**</span></span>  
 <span data-ttu-id="ee952-108">Просмотр даты и времени целевого сервера в его местном часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="ee952-108">View the date and time of the target server in the local time zone for that server.</span></span>  
  
 <span data-ttu-id="ee952-109">**Последний опрос**</span><span class="sxs-lookup"><span data-stu-id="ee952-109">**Last polled**</span></span>  
 <span data-ttu-id="ee952-110">Просмотр местной даты и времени последнего опроса главного сервера целевым сервером.</span><span class="sxs-lookup"><span data-stu-id="ee952-110">View the local date and time that the target server last polled the master.</span></span>  
  
 <span data-ttu-id="ee952-111">**Непрочитанные инструкции**</span><span class="sxs-lookup"><span data-stu-id="ee952-111">**Unread instructions**</span></span>  
 <span data-ttu-id="ee952-112">Просмотр числа команд, еще не полученных целевым сервером.</span><span class="sxs-lookup"><span data-stu-id="ee952-112">View the number of instructions that the target server has not yet received.</span></span>  
  
 <span data-ttu-id="ee952-113">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="ee952-113">**Status**</span></span>  
 <span data-ttu-id="ee952-114">Просмотр состояния целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="ee952-114">View the status of the target server.</span></span>  
  
 <span data-ttu-id="ee952-115">**Принудительный опрос**</span><span class="sxs-lookup"><span data-stu-id="ee952-115">**Force Poll**</span></span>  
 <span data-ttu-id="ee952-116">Щелкните эту кнопку для принудительного опроса главного сервера выбранными целевыми серверами.</span><span class="sxs-lookup"><span data-stu-id="ee952-116">Click this button to force the selected target servers to poll the master server.</span></span>  
  
 <span data-ttu-id="ee952-117">**Принудительно исключить**</span><span class="sxs-lookup"><span data-stu-id="ee952-117">**Force Defection**</span></span>  
 <span data-ttu-id="ee952-118">Нажмите эту кнопку для принудительного исключения главного сервера от выбранных целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="ee952-118">Click this button to force the selected target servers to defect from the master server.</span></span>  
  
 <span data-ttu-id="ee952-119">**Инструкции**</span><span class="sxs-lookup"><span data-stu-id="ee952-119">**Post Instructions**</span></span>  
 <span data-ttu-id="ee952-120">Отправка инструкций на выбранные целевые серверы.</span><span class="sxs-lookup"><span data-stu-id="ee952-120">Post instructions to the selected target servers.</span></span>  
  
 <span data-ttu-id="ee952-121">**Включить автообновление**</span><span class="sxs-lookup"><span data-stu-id="ee952-121">**Enable Auto Refresh**</span></span>  
 <span data-ttu-id="ee952-122">Выберите этот параметр для автоматического обновления отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="ee952-122">Select this option to automatically refresh the information shown.</span></span>  
  
 <span data-ttu-id="ee952-123">**Частота обновления**</span><span class="sxs-lookup"><span data-stu-id="ee952-123">**Refresh every**</span></span>  
 <span data-ttu-id="ee952-124">Укажите, как часто обновлять данные на данной странице.</span><span class="sxs-lookup"><span data-stu-id="ee952-124">Specify how often the information on this page is refreshed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee952-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="ee952-125">See Also</span></span>  
 [<span data-ttu-id="ee952-126">Автоматизация администрирования в масштабах предприятия</span><span class="sxs-lookup"><span data-stu-id="ee952-126">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
