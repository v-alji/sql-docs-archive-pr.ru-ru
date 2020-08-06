---
title: Свойства безопасности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], properties
- SecurityPackageList property
- BuiltinAdminsAreServerAdmins property
- DisableClientImpersonation property
- ErrorMessageMode property
- RequiredProtectionLevel property
- ServiceAccountIsServerAdmin property
- RequireClientAuthentication property
ms.assetid: 2fc7fe10-0cbb-49ac-aa8c-8ec3f7a7705f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 20133554835803908a340c5369eb66e86b119d72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659017"
---
# <a name="security-properties"></a><span data-ttu-id="08c36-102">Свойства безопасности</span><span class="sxs-lookup"><span data-stu-id="08c36-102">Security Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="08c36-103">поддерживают свойства сервера безопасности, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="08c36-103">supports the security server properties listed in the following table.</span></span> <span data-ttu-id="08c36-104">Дополнительные сведения о дополнительных свойствах сервера и об их настройке см. в разделе [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="08c36-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="08c36-105">**Область применения:** многомерный и табличный режим сервера</span><span class="sxs-lookup"><span data-stu-id="08c36-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="08c36-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="08c36-106">Properties</span></span>  
 `RequireClientAuthentication`  
 <span data-ttu-id="08c36-107">Логическое свойство, указывает, требуется ли проверка подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="08c36-107">A Boolean property that indicates whether client authentication is required.</span></span>  
  
 <span data-ttu-id="08c36-108">Значение по умолчанию True означает, что проверка подлинности необходима.</span><span class="sxs-lookup"><span data-stu-id="08c36-108">The default value for this property is True, which indicates that client authentication is required.</span></span>  
  
 `SecurityPackageList`  
 <span data-ttu-id="08c36-109">Строковое свойство, содержащее разделенный запятыми список пакетов SSPI, при помощи которых сервер проверяет подлинность клиентов.</span><span class="sxs-lookup"><span data-stu-id="08c36-109">A string property that contains a comma-separated list of SSPI packages used by server for client authentication.</span></span>  
  
 `DisableClientImpersonation`  
 <span data-ttu-id="08c36-110">Логическое свойство, указывает, отключено ли олицетворение клиента (например, хранимые процедуры).</span><span class="sxs-lookup"><span data-stu-id="08c36-110">A Boolean property that indicates whether client impersonation (for example, from stored procedures) is disabled.</span></span>  
  
 <span data-ttu-id="08c36-111">Значение по умолчанию False означает, что олицетворение клиента включено.</span><span class="sxs-lookup"><span data-stu-id="08c36-111">The default value for this property is False, which indicates that client impersonation is enabled.</span></span>  
  
 `BuiltinAdminsAreServerAdmins`  
 <span data-ttu-id="08c36-112">Логическое свойство, указывает, являются ли члены группы администраторов локального компьютера администраторами служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08c36-112">A Boolean property that indicates whether members of the local machine administrators group are [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrators.</span></span>  
  
 `ServiceAccountIsServerAdmin`  
 <span data-ttu-id="08c36-113">Логическое свойство, указывает, является ли учетная запись службы администратором сервера.</span><span class="sxs-lookup"><span data-stu-id="08c36-113">A Boolean property that indicates whether the service account is a server administrator.</span></span>  
  
 <span data-ttu-id="08c36-114">Значение по умолчанию True означает, что учетная запись службы является администратором сервера.</span><span class="sxs-lookup"><span data-stu-id="08c36-114">The default value for this property is True, which indicates that the service account is a server administrator.</span></span>  
  
 `ErrorMessageMode`  
 <span data-ttu-id="08c36-115">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08c36-115">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="08c36-116">Целочисленное 32-разрядное свойство со знаком, определяющее требуемый уровень защиты для всех запросов клиентов.</span><span class="sxs-lookup"><span data-stu-id="08c36-116">A signed 32-bit integer property that defines the required protection level for all client requests.</span></span> <span data-ttu-id="08c36-117">Возможные значения этого свойства перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="08c36-117">This property has one of the values listed in the following table.</span></span>  
  
|<span data-ttu-id="08c36-118">Значение</span><span class="sxs-lookup"><span data-stu-id="08c36-118">Value</span></span>|<span data-ttu-id="08c36-119">Описание</span><span class="sxs-lookup"><span data-stu-id="08c36-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08c36-120">*0*</span><span class="sxs-lookup"><span data-stu-id="08c36-120">*0*</span></span>|<span data-ttu-id="08c36-121">Нет, допускается открытый текст.</span><span class="sxs-lookup"><span data-stu-id="08c36-121">None, clear text allowed.</span></span>|  
|<span data-ttu-id="08c36-122">*1*</span><span class="sxs-lookup"><span data-stu-id="08c36-122">*1*</span></span>|<span data-ttu-id="08c36-123">Значение по умолчанию. Открытый текст не регистрируется.</span><span class="sxs-lookup"><span data-stu-id="08c36-123">(Default) Encryption required, no clear-text logging.</span></span>|  
|<span data-ttu-id="08c36-124">*2*</span><span class="sxs-lookup"><span data-stu-id="08c36-124">*2*</span></span>|<span data-ttu-id="08c36-125">Допускается подписанный открытый текст (более слабая защита, чем шифрование).</span><span class="sxs-lookup"><span data-stu-id="08c36-125">Clear-text requests allowed but only with signatures (weaker protection than encryption).</span></span>|  
  
 `AdministrativeDataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="08c36-126">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08c36-126">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c36-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="08c36-127">See Also</span></span>  
 <span data-ttu-id="08c36-128">[Настройка свойств сервера в Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="08c36-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="08c36-129">Определение режима работы сервера экземпляра служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="08c36-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
