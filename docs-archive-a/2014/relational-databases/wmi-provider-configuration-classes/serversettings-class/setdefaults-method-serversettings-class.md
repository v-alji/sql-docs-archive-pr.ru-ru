---
title: Метод SetDefaults (класс класс serversettings) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 76e4cfab-4b15-4da4-bb2f-8aac6f927f79
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 93dd2eee5a395d4d7463ebf9b85530fcf82d1888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731433"
---
# <a name="setdefaults-method-serversettings-class"></a><span data-ttu-id="f80e2-102">Метод SetDefaults (класс ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="f80e2-102">SetDefaults Method (ServerSettings Class)</span></span>
  <span data-ttu-id="f80e2-103">Задает все значения по умолчанию для экземпляра [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с параметром для перезаписи существующих данных.</span><span class="sxs-lookup"><span data-stu-id="f80e2-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f80e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f80e2-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f80e2-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="f80e2-105">Parts</span></span>  
 <span data-ttu-id="f80e2-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f80e2-106">*object*</span></span>  
 <span data-ttu-id="f80e2-107">Объект [класса класс serversettings](serversettings-class.md) , представляющий [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] экземпляр клиента.</span><span class="sxs-lookup"><span data-stu-id="f80e2-107">A [ServerSettings Class](serversettings-class.md) object that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="f80e2-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="f80e2-108">Parameters</span></span>  
  
|<span data-ttu-id="f80e2-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="f80e2-109">Parameter</span></span>|<span data-ttu-id="f80e2-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f80e2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f80e2-111">*овервритеалл*</span><span class="sxs-lookup"><span data-stu-id="f80e2-111">*OverwriteAll*</span></span>|<span data-ttu-id="f80e2-112">Логическое значение, указывающее, следует ли перезаписывать существующие значения в экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. `true`, если следует; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="f80e2-112">A Boolean value that specifies whether to overwrite existing values on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f80e2-113">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f80e2-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="f80e2-114">Значение u`int32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="f80e2-114">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f80e2-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="f80e2-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f80e2-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="f80e2-116">See Also</span></span>  
 <span data-ttu-id="f80e2-117">[Конфигурирование сетевых протоколов сервера и сетевых библиотек](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f80e2-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
