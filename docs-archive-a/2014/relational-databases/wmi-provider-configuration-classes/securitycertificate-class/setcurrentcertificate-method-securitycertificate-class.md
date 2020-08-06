---
title: Метод SetCurrentCertificate (класс класс securitycertificate) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 04b1a76a-932d-4824-8506-e346afe7554e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4c7065946c858b775e319578eb67c2b7186338f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657615"
---
# <a name="setcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="d911f-102">Метод SetCurrentCertificate (класс SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="d911f-102">SetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="d911f-103">Задает текущий сертификат безопасности.</span><span class="sxs-lookup"><span data-stu-id="d911f-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d911f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d911f-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="d911f-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="d911f-105">Parts</span></span>  
 <span data-ttu-id="d911f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d911f-106">*object*</span></span>  
 <span data-ttu-id="d911f-107">Объект [класс securitycertificate Class] класс securitycertificate-class.md), представляющий сертификат безопасности.</span><span class="sxs-lookup"><span data-stu-id="d911f-107">A [SecurityCertificate Class]securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="d911f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="d911f-108">Parameters</span></span>  
  
|<span data-ttu-id="d911f-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="d911f-109">Parameter</span></span>|<span data-ttu-id="d911f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d911f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d911f-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="d911f-111">*SHA*</span></span>|<span data-ttu-id="d911f-112">Строковое значение, определяющее отпечаток безопасного хэш-алгоритма (SHA) для нужного сертификата безопасности.</span><span class="sxs-lookup"><span data-stu-id="d911f-112">A string value that specifies the secure hash algorithm (SHA) thumbprint for the required security certificate.</span></span>|  
|<span data-ttu-id="d911f-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="d911f-113">*SQLInstance*</span></span>|<span data-ttu-id="d911f-114">Строковое значение, указывающее экземпляр, для которого необходим сертификат.</span><span class="sxs-lookup"><span data-stu-id="d911f-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d911f-115">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d911f-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="d911f-116">Значение uint32, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="d911f-116">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d911f-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="d911f-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d911f-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="d911f-118">See Also</span></span>  
 <span data-ttu-id="d911f-119">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d911f-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
