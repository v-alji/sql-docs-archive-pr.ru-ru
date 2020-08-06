---
title: Метод PauseService (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PauseService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PauseService method
ms.assetid: 5c3a8feb-58b8-4385-b4c8-bf33cf4d276d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8286e123bbbc279ba461336c5716eeb208c5b238
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664061"
---
# <a name="pauseservice-method-sqlservice-class"></a><span data-ttu-id="4bc5f-102">Метод PauseService (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="4bc5f-102">PauseService Method (SqlService Class)</span></span>
  <span data-ttu-id="4bc5f-103">Пытается перевести службу в состояние приостановки.</span><span class="sxs-lookup"><span data-stu-id="4bc5f-103">Attempts to place the service in the paused state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bc5f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bc5f-104">Syntax</span></span>  
  
```  
  
object  
.PauseService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="4bc5f-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="4bc5f-105">Parts</span></span>  
 <span data-ttu-id="4bc5f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4bc5f-106">*object*</span></span>  
 <span data-ttu-id="4bc5f-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="4bc5f-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4bc5f-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4bc5f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="4bc5f-109">Значение uint32, равное 0, если служба была успешно остановлена, равное 1, если запрос не поддерживается, и равное любому другому числу для указания ошибки.</span><span class="sxs-lookup"><span data-stu-id="4bc5f-109">A uint32 value, which is 0 if the service was successfully stopped, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bc5f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="4bc5f-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc5f-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="4bc5f-111">See Also</span></span>  
 <span data-ttu-id="4bc5f-112">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4bc5f-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
