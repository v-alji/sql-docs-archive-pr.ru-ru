---
title: Метод "не в классе" (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StopService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StopService method
ms.assetid: ef8e1856-4930-417a-8f52-be470fd3f15c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 534db69b9c5474638ef5e893847f7d6b9bbb645d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733709"
---
# <a name="stopservice-method-sqlservice-class"></a><span data-ttu-id="7de3e-102">Метод StopService (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="7de3e-102">StopService Method (SqlService Class)</span></span>
  <span data-ttu-id="7de3e-103">Пытается перевести службу в остановленное состояние.</span><span class="sxs-lookup"><span data-stu-id="7de3e-103">Attempts to place the service in the stopped state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de3e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7de3e-104">Syntax</span></span>  
  
```  
  
object  
.StopService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="7de3e-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="7de3e-105">Parts</span></span>  
 <span data-ttu-id="7de3e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7de3e-106">*object*</span></span>  
 <span data-ttu-id="7de3e-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="7de3e-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7de3e-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7de3e-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="7de3e-109">Значение `uint32` равно 0, если запрос `ResumeService` был принят; равно 1, если запрос не поддерживается; и равно любому другому числу для указания ошибки.</span><span class="sxs-lookup"><span data-stu-id="7de3e-109">A `uint32` value, which is 0 if the `ResumeService` request was accepted, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7de3e-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7de3e-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de3e-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="7de3e-111">See Also</span></span>  
 <span data-ttu-id="7de3e-112">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7de3e-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
