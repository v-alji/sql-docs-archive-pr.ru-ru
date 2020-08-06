---
title: Метод SetValue (класс ServerSettingsGeneralFlag) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ServerSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: a889feac-c0e0-4635-b506-843863d86967
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 74c4c189b72b7a469794e0828faf062a88cdf46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752027"
---
# <a name="setvalue-method-serversettingsgeneralflag-class"></a><span data-ttu-id="760a2-102">Метод SetValue (класс ServerSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="760a2-102">SetValue Method (ServerSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="760a2-103">Задает все значения упоминаемого флага.</span><span class="sxs-lookup"><span data-stu-id="760a2-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="760a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="760a2-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="760a2-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="760a2-105">Parts</span></span>  
 <span data-ttu-id="760a2-106">*object*</span><span class="sxs-lookup"><span data-stu-id="760a2-106">*object*</span></span>  
 <span data-ttu-id="760a2-107">Объект [класса ServerSettingsGeneralFlag](serversettingsgeneralflag-class.md) , представляющий универсальный флаг для параметров сервера.</span><span class="sxs-lookup"><span data-stu-id="760a2-107">A [ServerSettingsGeneralFlag Class](serversettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="760a2-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="760a2-108">Parameters</span></span>  
  
|<span data-ttu-id="760a2-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="760a2-109">Parameter</span></span>|<span data-ttu-id="760a2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="760a2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="760a2-111">*Значение*</span><span class="sxs-lookup"><span data-stu-id="760a2-111">*Value*</span></span>|<span data-ttu-id="760a2-112">Логическое значение, указывающее состояние флага.</span><span class="sxs-lookup"><span data-stu-id="760a2-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="760a2-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="760a2-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="760a2-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="760a2-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="760a2-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="760a2-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760a2-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="760a2-116">See Also</span></span>  
 <span data-ttu-id="760a2-117">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="760a2-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
