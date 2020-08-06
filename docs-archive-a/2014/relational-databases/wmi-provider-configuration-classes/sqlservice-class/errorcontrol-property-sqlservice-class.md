---
title: Свойство ErrorControl (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ErrorControl Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ErrorControl property
ms.assetid: cbb1e0fa-5bfc-4b1b-a6ed-f7d5cfad4d73
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 73c726af514f2880484cf927282fc0e007f07e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738105"
---
# <a name="errorcontrol-property-sqlservice-class"></a><span data-ttu-id="ca2fc-102">Свойство ErrorControl (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="ca2fc-102">ErrorControl Property (SqlService Class)</span></span>
  <span data-ttu-id="ca2fc-103">Возвращает или задает серьезность ошибки, если служба не запускается во время запуска системы.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-103">Gets or sets the severity of the error if the service fails to start during startup.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca2fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca2fc-104">Syntax</span></span>  
  
```  
  
object  
.ErrorControl [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="ca2fc-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="ca2fc-105">Parts</span></span>  
 <span data-ttu-id="ca2fc-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ca2fc-106">*object*</span></span>  
 <span data-ttu-id="ca2fc-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ca2fc-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ca2fc-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="ca2fc-109">Строковое значение, определяющее серьезность ошибки, если служба не запускается во время запуска системы.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-109">A string value that specifies the error severity reported if the service fails during startup.</span></span> <span data-ttu-id="ca2fc-110">В следующей таблице приводятся возможные значения.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-110">The following table shows the possible values.</span></span>  
  
 <span data-ttu-id="ca2fc-111">Игнорировать</span><span class="sxs-lookup"><span data-stu-id="ca2fc-111">Ignore</span></span>  
 <span data-ttu-id="ca2fc-112">Пользователь не получает уведомление.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-112">User is not notified.</span></span>  
  
 <span data-ttu-id="ca2fc-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-113">Normal</span></span>  
 <span data-ttu-id="ca2fc-114">Пользователь получает уведомление.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-114">User is notified.</span></span>  
  
 <span data-ttu-id="ca2fc-115">Severe</span><span class="sxs-lookup"><span data-stu-id="ca2fc-115">Severe</span></span>  
 <span data-ttu-id="ca2fc-116">Система перезапускается в последней известной рабочей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-116">System is restarted with the last-known-good configuration.</span></span>  
  
 <span data-ttu-id="ca2fc-117">Критически важно</span><span class="sxs-lookup"><span data-stu-id="ca2fc-117">Critical</span></span>  
 <span data-ttu-id="ca2fc-118">Попытка перезапустить систему в рабочей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-118">System attempts to restart with a good configuration.</span></span>  
  
 <span data-ttu-id="ca2fc-119">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="ca2fc-119">Unknown</span></span>  
 <span data-ttu-id="ca2fc-120">Серьезность ошибки неизвестна.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-120">The severity is unknown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca2fc-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca2fc-121">Remarks</span></span>  
 <span data-ttu-id="ca2fc-122">Значение задает действие, предпринимаемое программой запуска при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-122">The value indicates the action taken by the startup program if a failure occurs.</span></span> <span data-ttu-id="ca2fc-123">Все ошибки записываются в журнал системой компьютера.</span><span class="sxs-lookup"><span data-stu-id="ca2fc-123">All errors are logged by the computer system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca2fc-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca2fc-124">See Also</span></span>  
 <span data-ttu-id="ca2fc-125">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ca2fc-125">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
