---
title: Свойство PropertyValType (класс класс servernetworkprotocolproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PropertyValType Property (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PropertyValType property
ms.assetid: fbd42e8e-0642-4a19-b3c8-6ce88345145f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be6c42fbaa36080ec8144d95abb045a3b4328057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739608"
---
# <a name="propertyvaltype-property-servernetworkprotocolproperty-class"></a><span data-ttu-id="c113f-102">Свойство PropertyValType (класс ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="c113f-102">PropertyValType Property (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="c113f-103">Возвращает тип данных значения, хранящегося в указанном свойстве.</span><span class="sxs-lookup"><span data-stu-id="c113f-103">Gets the data type of the value stored in the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c113f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c113f-104">Syntax</span></span>  
  
```  
  
object  
.PropertyValType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="c113f-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="c113f-105">Parts</span></span>  
 <span data-ttu-id="c113f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c113f-106">*object*</span></span>  
 <span data-ttu-id="c113f-107">A [класса ServerNetworkProtocolProperty](servernetworkprotocolproperty-class.md) , который представляет атрибут сетевого протокола для экземпляра [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c113f-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c113f-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c113f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="c113f-109">Значение `uint32`, представляющее тип данных для значения свойства.</span><span class="sxs-lookup"><span data-stu-id="c113f-109">A `uint32` value that specifies the data type of the property value.</span></span> <span data-ttu-id="c113f-110">Возвращает 0 для строкового значения и 1 для числового типа.</span><span class="sxs-lookup"><span data-stu-id="c113f-110">It returns 0 for a string value and 1 for a numerical type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c113f-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="c113f-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c113f-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="c113f-112">See Also</span></span>  
 <span data-ttu-id="c113f-113">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c113f-113">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
