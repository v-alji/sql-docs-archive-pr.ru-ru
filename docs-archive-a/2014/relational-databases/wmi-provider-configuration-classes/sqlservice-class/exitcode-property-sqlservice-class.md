---
title: Свойство ExitCode (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ExitCode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ExitCode property
ms.assetid: e6b8bff2-946f-4abe-bd50-1f7bb11fdddf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f7f5414afd8507a1fc9c592d6b8226692e9683a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657593"
---
# <a name="exitcode-property-sqlservice-class"></a><span data-ttu-id="26b85-102">Свойство ExitCode (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="26b85-102">ExitCode Property (SqlService Class)</span></span>
  <span data-ttu-id="26b85-103">Возвращает или задает код ошибки [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32, которая определяет проблемы, происходящие при запуске и остановке службы.</span><span class="sxs-lookup"><span data-stu-id="26b85-103">Gets or sets the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 error code that defines problems encountered when starting and stopping the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26b85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26b85-104">Syntax</span></span>  
  
```  
  
object  
.ExitCode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="26b85-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="26b85-105">Parts</span></span>  
 <span data-ttu-id="26b85-106">*object*</span><span class="sxs-lookup"><span data-stu-id="26b85-106">*object*</span></span>  
 <span data-ttu-id="26b85-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="26b85-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="26b85-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="26b85-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="26b85-109">Значение `uint32`, определяющее код завершения.</span><span class="sxs-lookup"><span data-stu-id="26b85-109">A `uint32` value that specifies the exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26b85-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="26b85-110">Remarks</span></span>  
 <span data-ttu-id="26b85-111">Это свойство имеет значение ERROR_SERVICE_SPECIFIC_ERROR (1066), если ошибка уникальна для службы, представленной этим классом.</span><span class="sxs-lookup"><span data-stu-id="26b85-111">This property is set to ERROR_SERVICE_SPECIFIC_ERROR (1066) when the error is unique to the service represented by this class.</span></span> <span data-ttu-id="26b85-112">Во время выполнения и после нормального завершения работы служба присваивает этому параметру значение NO_ERROR.</span><span class="sxs-lookup"><span data-stu-id="26b85-112">The service sets this value to NO_ERROR when running, and again upon normal termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b85-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="26b85-113">See Also</span></span>  
 <span data-ttu-id="26b85-114">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="26b85-114">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
