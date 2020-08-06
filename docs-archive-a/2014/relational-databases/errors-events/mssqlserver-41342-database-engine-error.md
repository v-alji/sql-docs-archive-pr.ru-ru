---
title: MSSQLSERVER_41342 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41342 (Database Engine error)
ms.assetid: 28270d98-c543-4e7d-b40c-2200e38dce1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c0269322b30cee88e5ba3d50b6d391464b735f54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666092"
---
# <a name="mssqlserver_41342"></a><span data-ttu-id="dcf08-102">MSSQLSERVER_41342</span><span class="sxs-lookup"><span data-stu-id="dcf08-102">MSSQLSERVER_41342</span></span>
    
## <a name="details"></a><span data-ttu-id="dcf08-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="dcf08-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dcf08-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="dcf08-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="dcf08-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="dcf08-105">Event ID</span></span>|<span data-ttu-id="dcf08-106">41342</span><span class="sxs-lookup"><span data-stu-id="dcf08-106">41342</span></span>|  
|<span data-ttu-id="dcf08-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="dcf08-107">Event Source</span></span>|<span data-ttu-id="dcf08-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dcf08-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dcf08-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="dcf08-109">Component</span></span>|<span data-ttu-id="dcf08-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dcf08-110">SQLEngine</span></span>|  
|<span data-ttu-id="dcf08-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="dcf08-111">Symbolic Name</span></span>|<span data-ttu-id="dcf08-112">HK_HW_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="dcf08-112">HK_HW_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="dcf08-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="dcf08-113">Message Text</span></span>|<span data-ttu-id="dcf08-114">Модель процессора в системе не поддерживает создание *конструкция*.</span><span class="sxs-lookup"><span data-stu-id="dcf08-114">The model of the processor on the system does not support creating *construct*.</span></span> <span data-ttu-id="dcf08-115">Эта ошибка обычно возникает со старыми процессорами.</span><span class="sxs-lookup"><span data-stu-id="dcf08-115">This error typically occurs with older processors.</span></span> <span data-ttu-id="dcf08-116">Дополнительные сведения о поддерживаемых моделях см. в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcf08-116">See [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online for information on supported models.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dcf08-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="dcf08-117">Explanation</span></span>  
 <span data-ttu-id="dcf08-118">Для оптимизированных для памяти таблиц требуется модель процессора, которая поддерживает операции сравнения и обмена с 128-разрядными значениями, для чего требуется инструкция сборки CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="dcf08-118">Memory-optimized tables require a processor model that supports atomic compare-and-exchange operations on 128-bit values, which require the assembly instruction CMPXCHG16B.</span></span> <span data-ttu-id="dcf08-119">Некоторые старые модели процессоров AMD не поддерживают инструкцию CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="dcf08-119">Certain older AMD processor models do not support the CMPXCHG16B instruction.</span></span> <span data-ttu-id="dcf08-120">Кроме того, некоторые среды виртуализации не включают эту инструкцию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dcf08-120">Also, certain virtualization environments do not enable this instruction by default.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dcf08-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="dcf08-121">User Action</span></span>  
 <span data-ttu-id="dcf08-122">Обновите процессор.</span><span class="sxs-lookup"><span data-stu-id="dcf08-122">Upgrade your processor.</span></span> <span data-ttu-id="dcf08-123">Если процессор поддерживает инструкцию и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняется в виртуальной машине, измените конфигурацию для поддержки инструкции CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="dcf08-123">If your processor supports the instruction and you are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a virtual machine, change the configuration to support the instruction CMPXCHG16B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf08-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="dcf08-124">See Also</span></span>  
 [<span data-ttu-id="dcf08-125">Выполняющаяся в памяти OLTP (оптимизация в памяти)</span><span class="sxs-lookup"><span data-stu-id="dcf08-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
