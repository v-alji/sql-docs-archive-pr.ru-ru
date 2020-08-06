---
title: Метод SetNumValue (класс класс sqlserviceadvancedproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumValue method
ms.assetid: a5e1056b-0b75-4ad6-99c1-89246010d815
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 01388855a27dcf14754f677a42c13f8d29cbaacc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733694"
---
# <a name="setnumvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="0d6ab-102">Метод SetNumValue (класс SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="0d6ab-102">SetNumValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="0d6ab-103">Задает числовое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="0d6ab-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d6ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d6ab-104">Syntax</span></span>  
  
```  
  
object  
.SetNumValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="0d6ab-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="0d6ab-105">Parts</span></span>  
 <span data-ttu-id="0d6ab-106">*object*</span><span class="sxs-lookup"><span data-stu-id="0d6ab-106">*object*</span></span>  
 <span data-ttu-id="0d6ab-107">Объект [класса SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) , представляющий дополнительное свойство.</span><span class="sxs-lookup"><span data-stu-id="0d6ab-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="0d6ab-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d6ab-108">Parameters</span></span>  
  
|<span data-ttu-id="0d6ab-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="0d6ab-109">Parameter</span></span>|<span data-ttu-id="0d6ab-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0d6ab-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d6ab-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="0d6ab-111">*NumValue*</span></span>|<span data-ttu-id="0d6ab-112">Объект `uint32`, указывающий значение дополнительного свойства.</span><span class="sxs-lookup"><span data-stu-id="0d6ab-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0d6ab-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0d6ab-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="0d6ab-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="0d6ab-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d6ab-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="0d6ab-115">Remarks</span></span>  
 <span data-ttu-id="0d6ab-116">Чтобы для свойства можно было задать числовое значение, свойство должно иметь числовой тип.</span><span class="sxs-lookup"><span data-stu-id="0d6ab-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6ab-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d6ab-117">See Also</span></span>  
 <span data-ttu-id="0d6ab-118">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="0d6ab-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
