---
title: Метод SetBoolValue (класс класс sqlserviceadvancedproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SetBoolValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetBoolValue method
ms.assetid: 5252b439-fce5-446a-8e57-99e3054bee69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0c7142d6f192e94e9850b3c1a8a9481dc15a222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730289"
---
# <a name="setboolvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="3d51b-102">Метод SetBoolValue (класс SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="3d51b-102">SetBoolValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="3d51b-103">Задает логическое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="3d51b-103">Sets the Boolean value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d51b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d51b-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="3d51b-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="3d51b-105">Parts</span></span>  
 <span data-ttu-id="3d51b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="3d51b-106">*object*</span></span>  
 <span data-ttu-id="3d51b-107">Объект [класса SqlServiceAdvancedProperty](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) , представляющий дополнительное свойство.</span><span class="sxs-lookup"><span data-stu-id="3d51b-107">A [SqlServiceAdvancedProperty Class](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3d51b-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d51b-108">Parameters</span></span>  
  
|<span data-ttu-id="3d51b-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="3d51b-109">Parameter</span></span>|<span data-ttu-id="3d51b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3d51b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d51b-111">*булвалуе*</span><span class="sxs-lookup"><span data-stu-id="3d51b-111">*BoolValue*</span></span>|<span data-ttu-id="3d51b-112">Логическое значение дополнительного свойства.</span><span class="sxs-lookup"><span data-stu-id="3d51b-112">A Boolean value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3d51b-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d51b-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="3d51b-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="3d51b-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d51b-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="3d51b-115">Remarks</span></span>  
 <span data-ttu-id="3d51b-116">Чтобы задать логическое значение, свойство должно иметь логический тип.</span><span class="sxs-lookup"><span data-stu-id="3d51b-116">The property value type must be Boolean to set the property to a Boolean value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d51b-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d51b-117">See Also</span></span>  
 <span data-ttu-id="3d51b-118">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3d51b-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
