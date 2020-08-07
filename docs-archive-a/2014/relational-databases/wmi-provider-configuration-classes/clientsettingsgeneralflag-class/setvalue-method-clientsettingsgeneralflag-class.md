---
title: Метод SetValue (класс класс clientsettingsgeneralflag) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ClientSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: 34443689-a0e0-4668-a811-17532c6fd271
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: fffa44bd8743f96a43ca4d1787d8d2afaad5e6cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729301"
---
# <a name="setvalue-method-clientsettingsgeneralflag-class"></a><span data-ttu-id="81c3c-102">Метод SetValue (класс ClientSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="81c3c-102">SetValue Method (ClientSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="81c3c-103">Задает все значения упоминаемого флага.</span><span class="sxs-lookup"><span data-stu-id="81c3c-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81c3c-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="81c3c-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="81c3c-105">Parts</span></span>  
 <span data-ttu-id="81c3c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="81c3c-106">*object*</span></span>  
 <span data-ttu-id="81c3c-107">Объект [класса ClientSettingsGeneralFlag](clientsettingsgeneralflag-class.md) , представляющий универсальный флаг для параметров сервера.</span><span class="sxs-lookup"><span data-stu-id="81c3c-107">A [ClientSettingsGeneralFlag Class](clientsettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="81c3c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="81c3c-108">Parameters</span></span>  
  
|<span data-ttu-id="81c3c-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="81c3c-109">Parameter</span></span>|<span data-ttu-id="81c3c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="81c3c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81c3c-111">*Значение*</span><span class="sxs-lookup"><span data-stu-id="81c3c-111">*Value*</span></span>|<span data-ttu-id="81c3c-112">Логическое значение, указывающее состояние флага.</span><span class="sxs-lookup"><span data-stu-id="81c3c-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="81c3c-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81c3c-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="81c3c-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="81c3c-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81c3c-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="81c3c-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c3c-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="81c3c-116">See Also</span></span>  
 [<span data-ttu-id="81c3c-117">Настройка клиентских протоколов</span><span class="sxs-lookup"><span data-stu-id="81c3c-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
