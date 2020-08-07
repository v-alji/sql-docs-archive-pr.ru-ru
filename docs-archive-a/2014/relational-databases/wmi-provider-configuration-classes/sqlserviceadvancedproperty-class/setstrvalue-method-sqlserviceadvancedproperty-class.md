---
title: Метод SetStrValue (класс класс sqlserviceadvancedproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 1fededc3-81ba-4b08-83f9-189b96140799
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d977eb9845c820c4128d1d60337151eeb3893eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733689"
---
# <a name="setstrvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="3fce4-102">Метод SetStrValue (класс SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="3fce4-102">SetStrValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="3fce4-103">Задает строковое значение свойства.</span><span class="sxs-lookup"><span data-stu-id="3fce4-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fce4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fce4-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="3fce4-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="3fce4-105">Parts</span></span>  
 <span data-ttu-id="3fce4-106">*object*</span><span class="sxs-lookup"><span data-stu-id="3fce4-106">*object*</span></span>  
 <span data-ttu-id="3fce4-107">Объект [класса SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) , представляющий дополнительное свойство.</span><span class="sxs-lookup"><span data-stu-id="3fce4-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3fce4-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="3fce4-108">Parameters</span></span>  
  
|<span data-ttu-id="3fce4-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="3fce4-109">Parameter</span></span>|<span data-ttu-id="3fce4-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3fce4-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3fce4-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="3fce4-111">*StrValue*</span></span>|<span data-ttu-id="3fce4-112">Строка, указывающая значение дополнительного свойства.</span><span class="sxs-lookup"><span data-stu-id="3fce4-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3fce4-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3fce4-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="3fce4-114">Значение uint32, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="3fce4-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fce4-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="3fce4-115">Remarks</span></span>  
 <span data-ttu-id="3fce4-116">Чтобы задать строковое значение, свойство должно иметь тип *string* .</span><span class="sxs-lookup"><span data-stu-id="3fce4-116">The property value type must be *string* to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fce4-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="3fce4-117">See Also</span></span>  
 <span data-ttu-id="3fce4-118">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3fce4-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
