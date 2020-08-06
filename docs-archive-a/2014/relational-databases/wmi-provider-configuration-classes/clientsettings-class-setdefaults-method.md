---
title: Метод SetDefaults (класс ClientSettings) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ClientSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 056508f3-a5c8-467c-a196-dc1ef1f5178f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b6985ebfa4a9145dd3474cec31f32cdab9c11cdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668114"
---
# <a name="setdefaults-method-clientsettings-class"></a><span data-ttu-id="c90dd-102">Метод SetDefaults (класс ClientSettings)</span><span class="sxs-lookup"><span data-stu-id="c90dd-102">SetDefaults Method (ClientSettings Class)</span></span>
  <span data-ttu-id="c90dd-103">Задает все значения по умолчанию для экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] клиента с возможностью перезаписи существующих данных.</span><span class="sxs-lookup"><span data-stu-id="c90dd-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c90dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c90dd-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="c90dd-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="c90dd-105">Parts</span></span>  
 <span data-ttu-id="c90dd-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c90dd-106">*object*</span></span>  
 <span data-ttu-id="c90dd-107">Объект `ClientSettings`, представляющий экземпляр клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c90dd-107">A `ClientSettings` object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c90dd-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c90dd-108">Parameters</span></span>  
  
|<span data-ttu-id="c90dd-109">Параметр</span><span class="sxs-lookup"><span data-stu-id="c90dd-109">Parameter</span></span>|<span data-ttu-id="c90dd-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c90dd-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c90dd-111">*овервритеалл*</span><span class="sxs-lookup"><span data-stu-id="c90dd-111">*OverwriteAll*</span></span>|<span data-ttu-id="c90dd-112">Логическое значение, указывающее, следует ли перезаписывать существующие значения в экземпляре клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c90dd-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client.</span></span> <span data-ttu-id="c90dd-113">`true` для перезаписи, `false` для сохранения существующих значений.</span><span class="sxs-lookup"><span data-stu-id="c90dd-113">`true` to overwrite existing data; `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c90dd-114">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c90dd-114">Property Value/Return Value</span></span>  
 <span data-ttu-id="c90dd-115">Значение `uint32`, равное 0, если служба изменена успешно, и 1, если запрос не поддерживается. Любое другое значение указывает на ошибку.</span><span class="sxs-lookup"><span data-stu-id="c90dd-115">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c90dd-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="c90dd-116">Remarks</span></span>  
  
