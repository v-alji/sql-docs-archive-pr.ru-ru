---
title: Метод RemoveCertificate (класс класс serversettings) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- RemoveCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveCertificate method
ms.assetid: 9ffdbc39-93f5-48fb-859a-86a3ad545827
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 00731fab5c4bdec61848df93829dd5013a7454f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729237"
---
# <a name="removecertificate-method-serversettings-class"></a><span data-ttu-id="f9389-102">Метод RemoveCertificate (класс ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="f9389-102">RemoveCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="f9389-103">Удаляет текущий сертификат безопасности из экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9389-103">Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9389-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9389-104">Syntax</span></span>  
  
```  
  
object  
.RemoveCertificate()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f9389-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="f9389-105">Parts</span></span>  
 <span data-ttu-id="f9389-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f9389-106">*object*</span></span>  
 <span data-ttu-id="f9389-107">Объект [класса ServerSettings](serversettings-class.md) , представляющий параметры сервера в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9389-107">A [ServerSettings Class](serversettings-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f9389-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f9389-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f9389-109">Значение u`int32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="f9389-109">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9389-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9389-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9389-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9389-111">See Also</span></span>  
 <span data-ttu-id="f9389-112">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f9389-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
