---
title: Метод SetCurrentCertificate (класс класс serversettings) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: f9c6e172-11be-42de-b19b-a5b3436e84da
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7071937a7d7e601597fe008187448bb16a5a15ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731437"
---
# <a name="setcurrentcertificate-method-serversettings-class"></a><span data-ttu-id="42978-102">Метод SetCurrentCertificate (класс ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="42978-102">SetCurrentCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="42978-103">Задает текущий сертификат безопасности.</span><span class="sxs-lookup"><span data-stu-id="42978-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42978-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42978-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="42978-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="42978-105">Parts</span></span>  
 <span data-ttu-id="42978-106">*object*</span><span class="sxs-lookup"><span data-stu-id="42978-106">*object*</span></span>  
 <span data-ttu-id="42978-107">Объект [класс serversettings Class] класс serversettings-class.md), представляющий параметр сервера в экземпляре [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42978-107">A [ServerSettings Class]serversettings-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="42978-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="42978-108">Parameters</span></span>  
  
|<span data-ttu-id="42978-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="42978-109">Parameter</span></span>|<span data-ttu-id="42978-110">Описание</span><span class="sxs-lookup"><span data-stu-id="42978-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42978-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="42978-111">*SHA*</span></span>|<span data-ttu-id="42978-112">Строковое значение, указывающее текущий сертификат безопасности.</span><span class="sxs-lookup"><span data-stu-id="42978-112">A string value that specifies the current security certificate.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="42978-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="42978-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="42978-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="42978-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42978-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="42978-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42978-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="42978-116">See Also</span></span>  
 <span data-ttu-id="42978-117">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="42978-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
