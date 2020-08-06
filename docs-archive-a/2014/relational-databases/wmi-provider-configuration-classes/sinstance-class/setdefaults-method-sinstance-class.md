---
title: Метод SetDefaults (Класс Класс SInstance) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: dc3c6a85-0711-4688-bf4f-91168c57af28
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c581834d3c97bed622d16fbb35e48704f8679531
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729230"
---
# <a name="setdefaults-method-sinstance-class"></a><span data-ttu-id="3d886-102">Метод SetDefaults (класс SInstance)</span><span class="sxs-lookup"><span data-stu-id="3d886-102">SetDefaults Method (SInstance Class)</span></span>
  <span data-ttu-id="3d886-103">Задает все значения по умолчанию для экземпляра [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с параметром для перезаписи существующих данных.</span><span class="sxs-lookup"><span data-stu-id="3d886-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d886-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d886-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="3d886-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="3d886-105">Parts</span></span>  
 <span data-ttu-id="3d886-106">*object*</span><span class="sxs-lookup"><span data-stu-id="3d886-106">*object*</span></span>  
 <span data-ttu-id="3d886-107">Объект [класса Класс SInstance](sinstance-class.md) , представляющий экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="3d886-107">An [SInstance Class](sinstance-class.md) object that represents a server instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3d886-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d886-108">Parameters</span></span>  
  
|<span data-ttu-id="3d886-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="3d886-109">Parameter</span></span>|<span data-ttu-id="3d886-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3d886-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d886-111">*овервритеалл*</span><span class="sxs-lookup"><span data-stu-id="3d886-111">*OverwriteAll*</span></span>|<span data-ttu-id="3d886-112">Логическое значение, указывающее, следует ли перезаписывать существующее значение в экземпляре клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. `true`, если следует; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="3d886-112">A Boolean value that specifies whether to overwrite existing value on the instance of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client: `true` if existing data is overwritten, or `false` if existing data is not overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3d886-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d886-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="3d886-114">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="3d886-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d886-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="3d886-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d886-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d886-116">See Also</span></span>  
 <span data-ttu-id="3d886-117">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3d886-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
