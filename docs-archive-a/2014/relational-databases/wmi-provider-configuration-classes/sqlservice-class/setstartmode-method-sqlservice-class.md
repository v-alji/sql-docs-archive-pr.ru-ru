---
title: Метод SetStartMode (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStartMode Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStartMode method
ms.assetid: f6f198b4-f9a4-468c-8977-76462ef06e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a9b7310623f526d7b106485ed9681df3aa100129
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654965"
---
# <a name="setstartmode-method-sqlservice-class"></a><span data-ttu-id="3be3f-102">Метод SetStartMode (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="3be3f-102">SetStartMode Method (SqlService Class)</span></span>
  <span data-ttu-id="3be3f-103">Изменяет режим запуска экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="3be3f-103">Modifies the start mode of the service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be3f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3be3f-104">Syntax</span></span>  
  
```  
  
object  
.SetStartMode(  
StartMode  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="3be3f-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="3be3f-105">Parts</span></span>  
 <span data-ttu-id="3be3f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="3be3f-106">*object*</span></span>  
 <span data-ttu-id="3be3f-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="3be3f-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3be3f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="3be3f-108">Parameters</span></span>  
 <span data-ttu-id="3be3f-109">*StartMode*</span><span class="sxs-lookup"><span data-stu-id="3be3f-109">*StartMode*</span></span>  
 <span data-ttu-id="3be3f-110">Значение `uint32`, определяющее режим запуска экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="3be3f-110">A `uint32` value that specifies the start mode of the service instance.</span></span>  
  
 <span data-ttu-id="3be3f-111">Допустимы следующие значения.</span><span class="sxs-lookup"><span data-stu-id="3be3f-111">The valid values are as follows:</span></span>  
  
 <span data-ttu-id="3be3f-112">Значение = 0.</span><span class="sxs-lookup"><span data-stu-id="3be3f-112">Value = 0.</span></span> <span data-ttu-id="3be3f-113">Загрузка — драйвер устройства запускается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3be3f-113">Boot - Device driver started by the operating system loader.</span></span> <span data-ttu-id="3be3f-114">Это значение допустимо только для служб драйверов.</span><span class="sxs-lookup"><span data-stu-id="3be3f-114">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="3be3f-115">Значение = 1.</span><span class="sxs-lookup"><span data-stu-id="3be3f-115">Value = 1.</span></span> <span data-ttu-id="3be3f-116">Загрузка — драйвер устройства запускается методом `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="3be3f-116">System - Device driver started by the `IoInitSystem` method.</span></span> <span data-ttu-id="3be3f-117">Это значение допустимо только для служб драйверов.</span><span class="sxs-lookup"><span data-stu-id="3be3f-117">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="3be3f-118">Значение = 2.</span><span class="sxs-lookup"><span data-stu-id="3be3f-118">Value = 2.</span></span> <span data-ttu-id="3be3f-119">Автоматически — служба запускается автоматически диспетчером управления службами во время запуска системы.</span><span class="sxs-lookup"><span data-stu-id="3be3f-119">Automatic - Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="3be3f-120">Значение = 3.</span><span class="sxs-lookup"><span data-stu-id="3be3f-120">Value = 3.</span></span> <span data-ttu-id="3be3f-121">Вручную — служба запускается оснасткой «Управление компьютером», когда процесс вызывает метод `StartService`.</span><span class="sxs-lookup"><span data-stu-id="3be3f-121">Manual - Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="3be3f-122">Значение = 4.</span><span class="sxs-lookup"><span data-stu-id="3be3f-122">Value = 4.</span></span> <span data-ttu-id="3be3f-123">Отключена — служба больше не запускается.</span><span class="sxs-lookup"><span data-stu-id="3be3f-123">Disabled - Service can no longer be started.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3be3f-124">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3be3f-124">Property Value/Return Value</span></span>  
 <span data-ttu-id="3be3f-125">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3be3f-125">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="3be3f-126">Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="3be3f-126">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3be3f-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="3be3f-127">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be3f-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="3be3f-128">See Also</span></span>  
 <span data-ttu-id="3be3f-129">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3be3f-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
