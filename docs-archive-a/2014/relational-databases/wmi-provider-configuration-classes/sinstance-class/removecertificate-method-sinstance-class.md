---
title: Метод RemoveCertificate (Класс Класс SInstance) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- RemoveCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveCertificate method
ms.assetid: 7e5dbafa-a634-4617-9622-510514fce0ce
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4b876cd75778d1da9c9a46f65f39b915ebee0552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729233"
---
# <a name="removecertificate-method-sinstance-class"></a><span data-ttu-id="7b937-102">Метод RemoveCertificate (класс SInstance)</span><span class="sxs-lookup"><span data-stu-id="7b937-102">RemoveCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="7b937-103">Удаляет текущий сертификат безопасности из экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b937-103">Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b937-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b937-104">Syntax</span></span>  
  
```  
  
object  
.RemoveCertificate()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="7b937-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="7b937-105">Parts</span></span>  
 <span data-ttu-id="7b937-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7b937-106">*object*</span></span>  
 <span data-ttu-id="7b937-107">Объект [класса SInstance](sinstance-class.md) , представляющий параметры сервера в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b937-107">An [SInstance Class](sinstance-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7b937-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7b937-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="7b937-109">Значение uint32, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="7b937-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b937-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="7b937-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b937-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b937-111">See Also</span></span>  
 <span data-ttu-id="7b937-112">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7b937-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
