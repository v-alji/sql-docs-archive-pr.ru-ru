---
title: Метод SetNumericalValue (класс класс sqlserviceadvancedproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: 950ed1e8-0538-4db4-807c-a2c36f43cf6b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: db823938d77f4e2c67284cae0f11faca12aba6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738084"
---
# <a name="setnumericalvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="b9a44-102">Метод SetNumericalValue (класс SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="b9a44-102">SetNumericalValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="b9a44-103">Задает числовое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="b9a44-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9a44-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="b9a44-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="b9a44-105">Parts</span></span>  
 <span data-ttu-id="b9a44-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b9a44-106">*object*</span></span>  
 <span data-ttu-id="b9a44-107">Объект [класса SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) , представляющий дополнительное свойство.</span><span class="sxs-lookup"><span data-stu-id="b9a44-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="b9a44-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9a44-108">Parameters</span></span>  
  
|<span data-ttu-id="b9a44-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="b9a44-109">Parameter</span></span>|<span data-ttu-id="b9a44-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b9a44-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9a44-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="b9a44-111">*NumValue*</span></span>|<span data-ttu-id="b9a44-112">Объект `uint32`, указывающий значение дополнительного свойства.</span><span class="sxs-lookup"><span data-stu-id="b9a44-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b9a44-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b9a44-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="b9a44-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="b9a44-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9a44-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="b9a44-115">Remarks</span></span>  
 <span data-ttu-id="b9a44-116">Чтобы для свойства можно было задать числовое значение, свойство должно иметь числовой тип.</span><span class="sxs-lookup"><span data-stu-id="b9a44-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a44-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="b9a44-117">See Also</span></span>  
 <span data-ttu-id="b9a44-118">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b9a44-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
