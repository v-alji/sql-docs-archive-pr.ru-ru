---
title: Метод GetCurrentCertificate (класс класс securitycertificate) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 987a2671-1801-45c4-93e6-29f883c58720
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ab96b2e2a8fabf9e9ccce647e54be1983fe40ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729277"
---
# <a name="getcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="967f0-102">Метод GetCurrentCertificate (класс SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="967f0-102">GetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="967f0-103">Возвращает текущий сертификат безопасности.</span><span class="sxs-lookup"><span data-stu-id="967f0-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="967f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="967f0-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="967f0-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="967f0-105">Parts</span></span>  
 <span data-ttu-id="967f0-106">*object*</span><span class="sxs-lookup"><span data-stu-id="967f0-106">*object*</span></span>  
 <span data-ttu-id="967f0-107">Объект [класса SecurityCertificate](securitycertificate-class.md) , представляющий сертификат безопасности.</span><span class="sxs-lookup"><span data-stu-id="967f0-107">A [SecurityCertificate Class](securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="967f0-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="967f0-108">Parameters</span></span>  
  
|<span data-ttu-id="967f0-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="967f0-109">Parameter</span></span>|<span data-ttu-id="967f0-110">Описание</span><span class="sxs-lookup"><span data-stu-id="967f0-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="967f0-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="967f0-111">*SHA*</span></span>|<span data-ttu-id="967f0-112">Строковое значение (выходной параметр), определяющее текущий отпечаток сертификата безопасности SHA после завершения метода.</span><span class="sxs-lookup"><span data-stu-id="967f0-112">A string value (output parameter) that specifies the current security certificate SHA thumbprint after the method completes.</span></span>|  
|<span data-ttu-id="967f0-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="967f0-113">*SQLInstance*</span></span>|<span data-ttu-id="967f0-114">Строковое значение, указывающее экземпляр, для которого необходим сертификат.</span><span class="sxs-lookup"><span data-stu-id="967f0-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="967f0-115">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="967f0-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="967f0-116">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="967f0-116">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="967f0-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="967f0-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="967f0-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="967f0-118">See Also</span></span>  
 <span data-ttu-id="967f0-119">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="967f0-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
