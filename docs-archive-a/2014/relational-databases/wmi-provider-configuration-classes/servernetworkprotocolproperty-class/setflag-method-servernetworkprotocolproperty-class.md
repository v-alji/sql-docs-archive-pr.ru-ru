---
title: Метод SetFlag (класс класс servernetworkprotocolproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 95288931-8eb1-4477-ad80-619cf7073e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1a90b4fca194f20cc0a2d70c947577594155f051
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730273"
---
# <a name="setflag-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="e13ca-102">Метод SetFlag (класс ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="e13ca-102">SetFlag Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="e13ca-103">Устанавливает флаг указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="e13ca-103">Sets the flag of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e13ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e13ca-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e13ca-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="e13ca-105">Parts</span></span>  
 <span data-ttu-id="e13ca-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e13ca-106">*object*</span></span>  
 <span data-ttu-id="e13ca-107">Объект [класс servernetworkprotocolproperty Class] класс servernetworkprotocolproperty-class.md), представляющий атрибут сетевого протокола в экземпляре [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e13ca-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e13ca-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="e13ca-108">Parameters</span></span>  
  
|<span data-ttu-id="e13ca-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="e13ca-109">Parameter</span></span>|<span data-ttu-id="e13ca-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e13ca-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e13ca-111">*булвалуе*</span><span class="sxs-lookup"><span data-stu-id="e13ca-111">*BoolValue*</span></span>|<span data-ttu-id="e13ca-112">Логическое значение, указывающее новое состояние флага.</span><span class="sxs-lookup"><span data-stu-id="e13ca-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e13ca-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e13ca-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e13ca-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="e13ca-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e13ca-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="e13ca-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e13ca-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e13ca-116">See Also</span></span>  
 <span data-ttu-id="e13ca-117">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e13ca-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
