---
title: Свойство StartMode (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartMode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartMode property
ms.assetid: c0c2c7f8-d4ae-44f2-ad8e-aecfcb7c2878
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bafffcc3c8f82f69896d0a22e9b0a9060e04cd10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733722"
---
# <a name="startmode-property-sqlservice-class"></a><span data-ttu-id="37a27-102">Свойство StartMode (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="37a27-102">StartMode Property (SqlService Class)</span></span>
  <span data-ttu-id="37a27-103">Возвращает режим запуска службы.</span><span class="sxs-lookup"><span data-stu-id="37a27-103">Gets the start mode of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37a27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37a27-104">Syntax</span></span>  
  
```  
  
object  
.StartMode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="37a27-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="37a27-105">Parts</span></span>  
 <span data-ttu-id="37a27-106">*object*</span><span class="sxs-lookup"><span data-stu-id="37a27-106">*object*</span></span>  
 <span data-ttu-id="37a27-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="37a27-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="37a27-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="37a27-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="37a27-109">Значение uint32, определяющее режим службы.</span><span class="sxs-lookup"><span data-stu-id="37a27-109">A uint32 value that specifies the mode of the service.</span></span>  
  
 <span data-ttu-id="37a27-110">Может иметь одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="37a27-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="37a27-111">Загрузка</span><span class="sxs-lookup"><span data-stu-id="37a27-111">Boot</span></span>  
 <span data-ttu-id="37a27-112">Значение = 0.</span><span class="sxs-lookup"><span data-stu-id="37a27-112">Value = 0.</span></span> <span data-ttu-id="37a27-113">Служба запускается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="37a27-113">Service started by the operating system loader.</span></span> <span data-ttu-id="37a27-114">Этот параметр допустим только для служб драйверов.</span><span class="sxs-lookup"><span data-stu-id="37a27-114">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="37a27-115">Система</span><span class="sxs-lookup"><span data-stu-id="37a27-115">System</span></span>  
 <span data-ttu-id="37a27-116">Значение = 1.</span><span class="sxs-lookup"><span data-stu-id="37a27-116">Value = 1.</span></span> <span data-ttu-id="37a27-117">Служба запускается методом `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="37a27-117">Service started by the `IoInitSystem` method.</span></span> <span data-ttu-id="37a27-118">Этот параметр допустим только для служб драйверов.</span><span class="sxs-lookup"><span data-stu-id="37a27-118">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="37a27-119">Автоматически</span><span class="sxs-lookup"><span data-stu-id="37a27-119">Automatic</span></span>  
 <span data-ttu-id="37a27-120">Значение = 2.</span><span class="sxs-lookup"><span data-stu-id="37a27-120">Value = 2.</span></span> <span data-ttu-id="37a27-121">Служба запускается автоматически диспетчером управления службами во время запуска системы.</span><span class="sxs-lookup"><span data-stu-id="37a27-121">Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="37a27-122">Вручную</span><span class="sxs-lookup"><span data-stu-id="37a27-122">Manual</span></span>  
 <span data-ttu-id="37a27-123">Значение = 3.</span><span class="sxs-lookup"><span data-stu-id="37a27-123">Value = 3.</span></span> <span data-ttu-id="37a27-124">Служба запускается оснасткой «Управление компьютером», когда процесс вызывает метод `StartService`.</span><span class="sxs-lookup"><span data-stu-id="37a27-124">Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="37a27-125">Выключено</span><span class="sxs-lookup"><span data-stu-id="37a27-125">Disabled</span></span>  
 <span data-ttu-id="37a27-126">Значение = 4.</span><span class="sxs-lookup"><span data-stu-id="37a27-126">Value = 4.</span></span> <span data-ttu-id="37a27-127">Служба не может быть запущена.</span><span class="sxs-lookup"><span data-stu-id="37a27-127">Service cannot be started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37a27-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="37a27-128">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a27-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="37a27-129">See Also</span></span>  
 <span data-ttu-id="37a27-130">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="37a27-130">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
