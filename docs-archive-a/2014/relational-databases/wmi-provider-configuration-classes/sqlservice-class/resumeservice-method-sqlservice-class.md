---
title: Метод ResumeService (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ResumeService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ResumeService method
ms.assetid: 0b0a5f08-b95e-4626-bf81-309da7a0aacd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 53d07c8697c6303bc371f442745e2d1864682e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658673"
---
# <a name="resumeservice-method-sqlservice-class"></a><span data-ttu-id="b0c64-102">Метод ResumeService (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="b0c64-102">ResumeService Method (SqlService Class)</span></span>
  <span data-ttu-id="b0c64-103">Пытается перевести службу в состояние возобновления.</span><span class="sxs-lookup"><span data-stu-id="b0c64-103">Attempts to place the service in the resumed state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0c64-104">Syntax</span></span>  
  
```  
  
object  
.ResumeService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="b0c64-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="b0c64-105">Parts</span></span>  
 <span data-ttu-id="b0c64-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b0c64-106">*object*</span></span>  
 <span data-ttu-id="b0c64-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="b0c64-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b0c64-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b0c64-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="b0c64-109">Значение uint32, равное 0, если запрос `ResumeService` был принят; равное 1, если запрос не поддерживается; и равное любому другому числу для указания ошибки.</span><span class="sxs-lookup"><span data-stu-id="b0c64-109">A uint32 value, which is 0 if the `ResumeService` request was accepted, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0c64-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b0c64-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c64-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="b0c64-111">See Also</span></span>  
 <span data-ttu-id="b0c64-112">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b0c64-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
