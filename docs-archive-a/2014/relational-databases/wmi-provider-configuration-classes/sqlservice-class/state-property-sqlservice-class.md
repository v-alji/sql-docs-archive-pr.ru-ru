---
title: Свойство State (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- State Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- State property
ms.assetid: 9e09f419-947c-4d4b-9a49-2d3396c847cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a7456113d9ec4444507d1057892a65adf241992f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733710"
---
# <a name="state-property-sqlservice-class"></a><span data-ttu-id="9ad1b-102">Свойство State (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="9ad1b-102">State Property (SqlService Class)</span></span>
  <span data-ttu-id="9ad1b-103">Возвращает или задает текущее состояние службы.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-103">Gets or sets the current state of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ad1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ad1b-104">Syntax</span></span>  
  
```  
  
object  
.State [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="9ad1b-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="9ad1b-105">Parts</span></span>  
 <span data-ttu-id="9ad1b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="9ad1b-106">*object*</span></span>  
 <span data-ttu-id="9ad1b-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9ad1b-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9ad1b-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="9ad1b-109">Значение uint32, определяющее состояние службы.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-109">A uint32 value that specifies the state of the service.</span></span>  
  
 <span data-ttu-id="9ad1b-110">Может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="9ad1b-111">1</span><span class="sxs-lookup"><span data-stu-id="9ad1b-111">1</span></span>  
 <span data-ttu-id="9ad1b-112">Остановлена.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-112">Stopped.</span></span> <span data-ttu-id="9ad1b-113">служба остановлена.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-113">The service is stopped.</span></span>  
  
 <span data-ttu-id="9ad1b-114">2</span><span class="sxs-lookup"><span data-stu-id="9ad1b-114">2</span></span>  
 <span data-ttu-id="9ad1b-115">Ожидание запуска.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-115">Start Pending.</span></span> <span data-ttu-id="9ad1b-116">Служба ожидает запуска.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-116">The service is waiting to start.</span></span>  
  
 <span data-ttu-id="9ad1b-117">3</span><span class="sxs-lookup"><span data-stu-id="9ad1b-117">3</span></span>  
 <span data-ttu-id="9ad1b-118">Ожидание остановки.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-118">Stop Pending.</span></span> <span data-ttu-id="9ad1b-119">Служба ожидает остановки.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-119">The service is waiting to stop.</span></span>  
  
 <span data-ttu-id="9ad1b-120">4</span><span class="sxs-lookup"><span data-stu-id="9ad1b-120">4</span></span>  
 <span data-ttu-id="9ad1b-121">Выполняется.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-121">Running.</span></span> <span data-ttu-id="9ad1b-122">Служба запущена.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-122">The service is running.</span></span>  
  
 <span data-ttu-id="9ad1b-123">5</span><span class="sxs-lookup"><span data-stu-id="9ad1b-123">5</span></span>  
 <span data-ttu-id="9ad1b-124">Ожидание продолжения.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-124">Continue Pending.</span></span> <span data-ttu-id="9ad1b-125">Служба ожидает продолжения.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-125">The service is waiting to continue.</span></span>  
  
 <span data-ttu-id="9ad1b-126">6</span><span class="sxs-lookup"><span data-stu-id="9ad1b-126">6</span></span>  
 <span data-ttu-id="9ad1b-127">Ожидание приостановки.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-127">Pause Pending.</span></span> <span data-ttu-id="9ad1b-128">Служба ожидает приостановки.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-128">The service is waiting to pause.</span></span>  
  
 <span data-ttu-id="9ad1b-129">7</span><span class="sxs-lookup"><span data-stu-id="9ad1b-129">7</span></span>  
 <span data-ttu-id="9ad1b-130">приостановлено</span><span class="sxs-lookup"><span data-stu-id="9ad1b-130">Paused.</span></span> <span data-ttu-id="9ad1b-131">Служба приостановлена.</span><span class="sxs-lookup"><span data-stu-id="9ad1b-131">The service is paused.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ad1b-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="9ad1b-132">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad1b-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ad1b-133">See Also</span></span>  
 <span data-ttu-id="9ad1b-134">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9ad1b-134">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
