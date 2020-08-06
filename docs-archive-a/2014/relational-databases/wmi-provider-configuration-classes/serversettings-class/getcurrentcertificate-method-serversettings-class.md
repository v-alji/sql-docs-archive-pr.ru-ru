---
title: Метод GetCurrentCertificate (класс класс serversettings) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 450e33c6-91d4-420f-ab7c-1905111f5658
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b36a5fe7cd39da0f336d05fc4c450170fa21199d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729258"
---
# <a name="getcurrentcertificate-method-serversettings-class"></a><span data-ttu-id="bead7-102">Метод GetCurrentCertificate (класс ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="bead7-102">GetCurrentCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="bead7-103">Возвращает текущий сертификат безопасности.</span><span class="sxs-lookup"><span data-stu-id="bead7-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bead7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bead7-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="bead7-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="bead7-105">Parts</span></span>  
 <span data-ttu-id="bead7-106">*object*</span><span class="sxs-lookup"><span data-stu-id="bead7-106">*object*</span></span>  
 <span data-ttu-id="bead7-107">Объект `ServerSettings`, представляющий настройки сервера на экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bead7-107">A `ServerSettings` object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="bead7-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="bead7-108">Parameters</span></span>  
  
|<span data-ttu-id="bead7-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="bead7-109">Parameter</span></span>|<span data-ttu-id="bead7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="bead7-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bead7-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="bead7-111">*SHA*</span></span>|<span data-ttu-id="bead7-112">Строковое значение объекта (выходной параметр), в котором задает текущий сертификат безопасности после завершения работы метода.</span><span class="sxs-lookup"><span data-stu-id="bead7-112">A string object value (output parameter) that specifies the current security certificate after the method completes.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bead7-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bead7-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="bead7-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="bead7-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bead7-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="bead7-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bead7-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="bead7-116">See Also</span></span>  
 <span data-ttu-id="bead7-117">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="bead7-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
