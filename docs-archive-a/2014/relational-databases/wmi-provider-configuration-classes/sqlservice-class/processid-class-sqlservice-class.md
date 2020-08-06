---
title: Класс ProcessId (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProcessId Class (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProcessId property
ms.assetid: 99b5a2e9-b44a-48a0-993e-04bd15c7fef4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7c4c40eea826b5009e52d26b1d930eaf5febbcdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664060"
---
# <a name="processid-class-sqlservice-class"></a><span data-ttu-id="fe14f-102">Класс ProcessId (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="fe14f-102">ProcessId Class (SqlService Class)</span></span>
  <span data-ttu-id="fe14f-103">Возвращает идентификатор системного процесса, уникально определяющий службу.</span><span class="sxs-lookup"><span data-stu-id="fe14f-103">Gets the system process ID that uniquely identifies a service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe14f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe14f-104">Syntax</span></span>  
  
```  
  
object  
.ProcessId [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="fe14f-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="fe14f-105">Parts</span></span>  
 <span data-ttu-id="fe14f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="fe14f-106">*object*</span></span>  
 <span data-ttu-id="fe14f-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="fe14f-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="fe14f-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe14f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="fe14f-109">Значение `uint32`, указывающее идентификатор, уникально определяющий процесс.</span><span class="sxs-lookup"><span data-stu-id="fe14f-109">A `uint32` value that specifies the ID that uniquely identifies the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe14f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe14f-110">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe14f-111">Пример</span><span class="sxs-lookup"><span data-stu-id="fe14f-111">Example</span></span>  
  
```  
mysqlservice.ProcessId = 324  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe14f-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe14f-112">See Also</span></span>  
 <span data-ttu-id="fe14f-113">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fe14f-113">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
