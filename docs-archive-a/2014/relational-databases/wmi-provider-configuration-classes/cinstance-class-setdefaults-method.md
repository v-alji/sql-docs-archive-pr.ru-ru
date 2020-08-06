---
title: Метод SetDefaults (класс CInstance) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (CInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: ed9e99c2-3e28-4ee8-bc20-61ca05984973
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5e589796f973592d7f9f549bffbbf8dfbe49cc27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654095"
---
# <a name="setdefaults-method-cinstance-class"></a><span data-ttu-id="46ee2-102">Метод SetDefaults (класс CInstance)</span><span class="sxs-lookup"><span data-stu-id="46ee2-102">SetDefaults Method (CInstance Class)</span></span>
  <span data-ttu-id="46ee2-103">Задает все значения по умолчанию для экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] клиента с возможностью перезаписи существующих данных.</span><span class="sxs-lookup"><span data-stu-id="46ee2-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ee2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46ee2-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="46ee2-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="46ee2-105">Parts</span></span>  
 <span data-ttu-id="46ee2-106">*object*</span><span class="sxs-lookup"><span data-stu-id="46ee2-106">*object*</span></span>  
 <span data-ttu-id="46ee2-107">Объект [класса CInstance](cinstance-class.md) , представляющий экземпляр клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="46ee2-107">A [CInstance Class](cinstance-class.md) object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="46ee2-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="46ee2-108">Parameters</span></span>  
  
|<span data-ttu-id="46ee2-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="46ee2-109">Parameter</span></span>|<span data-ttu-id="46ee2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="46ee2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46ee2-111">*овервритеалл*</span><span class="sxs-lookup"><span data-stu-id="46ee2-111">*OverwriteAll*</span></span>|<span data-ttu-id="46ee2-112">Логическое значение, указывающее, следует ли перезаписывать существующие значения в экземпляре клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. `true`, если следует; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="46ee2-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="46ee2-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46ee2-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="46ee2-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="46ee2-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46ee2-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="46ee2-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ee2-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="46ee2-116">See Also</span></span>  
 [<span data-ttu-id="46ee2-117">Настройка клиентских протоколов</span><span class="sxs-lookup"><span data-stu-id="46ee2-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
