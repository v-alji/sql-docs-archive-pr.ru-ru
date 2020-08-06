---
title: Свойство Dependencies (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Dependencies Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Dependencies property
ms.assetid: 92d54b7e-de2f-4978-b601-0196e37cbb41
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b5b64aee371a41bc0d58ec4a52a1a1526bc13388
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738123"
---
# <a name="dependencies-property-sqlservice-class"></a><span data-ttu-id="c9a88-102">Свойство Dependencies (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="c9a88-102">Dependencies Property (SqlService Class)</span></span>
  <span data-ttu-id="c9a88-103">Возвращает список служб, зависимых от указанной службы.</span><span class="sxs-lookup"><span data-stu-id="c9a88-103">Gets a list of services that are dependent on the referenced service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9a88-104">Syntax</span></span>  
  
```  
  
object  
.Dependencies [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="c9a88-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="c9a88-105">Parts</span></span>  
 <span data-ttu-id="c9a88-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c9a88-106">*object*</span></span>  
 <span data-ttu-id="c9a88-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="c9a88-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c9a88-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c9a88-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="c9a88-109">Массив значений string[], содержащий список служб, зависимых от указанной службы.</span><span class="sxs-lookup"><span data-stu-id="c9a88-109">A string[] array that contains a list of services dependent on the referenced service.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9a88-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c9a88-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a88-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9a88-111">See Also</span></span>  
 <span data-ttu-id="c9a88-112">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c9a88-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
