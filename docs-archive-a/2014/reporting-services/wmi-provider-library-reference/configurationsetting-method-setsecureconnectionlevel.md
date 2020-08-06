---
title: Метод SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetSecureConnectionLevel method
ms.assetid: 0fac7d5e-2670-4657-9439-331e7d93babb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4361f09eb38b3e5650b68ae6f86b7f2266bbf1a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737718"
---
# <a name="setsecureconnectionlevel-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="2dd0e-102">Метод SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="2dd0e-102">SetSecureConnectionLevel Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="2dd0e-103">Задает уровень безопасных соединений для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-103">Sets the secure connection level of the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd0e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2dd0e-104">Syntax</span></span>  
  
```vb  
Public Sub SetSecureConnectionLevel(Level as Integer, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Int32 Level,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dd0e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2dd0e-105">Parameters</span></span>  
 <span data-ttu-id="2dd0e-106">*Level*</span><span class="sxs-lookup"><span data-stu-id="2dd0e-106">*Level*</span></span>  
 <span data-ttu-id="2dd0e-107">Целое значение, представляющее уровень безопасного соединения.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-107">An integer value representing a secure connection level.</span></span>  
  
 <span data-ttu-id="2dd0e-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="2dd0e-108">*HRESULT*</span></span>  
 <span data-ttu-id="2dd0e-109">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2dd0e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2dd0e-110">Return Value</span></span>  
 <span data-ttu-id="2dd0e-111">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="2dd0e-112">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="2dd0e-113">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dd0e-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="2dd0e-114">Remarks</span></span>  
 <span data-ttu-id="2dd0e-115">При вызове метода свойство SecureConnectionLevel сервера отчетов получает заданное значение.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-115">When called, the report server SecureConnectionLevel property is set to the value specified.</span></span> <span data-ttu-id="2dd0e-116">Значение 0 указывает на то, что протокол SSL отключен.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-116">A value of 0 indicates that SSL is turned off.</span></span> <span data-ttu-id="2dd0e-117">Значение, которое больше или равно 1, указывает на то, что протокол SSL включен.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-117">A value greater than or equal to 1 indicates that SSL is turned on.</span></span>  
  
-   <span data-ttu-id="2dd0e-118">Если значение задано, элемент SecureConnectionLevel в файле конфигурации сервера отчетов изменяется, а `URLRoot` элемент в файле конфигурации задается как "https://", если указанный *уровень* больше или равен 1, или "http://", если указан *уровень* 0.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-118">When the value is set, the SecureConnectionLevel element in the report server configuration file is changed, and the `URLRoot` element in the configuration file is set to use "https://" if the specified *Level* is greater than or equal to 1, or "http://" if the specified *Level* is 0.</span></span>  
  
 <span data-ttu-id="2dd0e-119">В [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]элемент SecureConnectionLevel является двухфазным переключателем. Значение по умолчанию равно 0.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-119">In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], SecureConnectionLevel is made an on/off switch, default value is 0.</span></span> <span data-ttu-id="2dd0e-120">Для любого значения, которое больше или равно 1, переданного через API метода SetSecureConnectionLevel, SSL считается включенным, а свойство конфигурации SecureConnectionLevel в файле rsreportserver.config задается соответственно.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-120">For any value greater than or equal to 1 passed through SetSecureConnectionLevel method API, SSL is considered on and the configuration property SecureConnectionLevel is set accordingly in the rsreportserver.config file.</span></span> <span data-ttu-id="2dd0e-121">Значения 2 и 3 по-прежнему разрешены для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="2dd0e-121">Values of 2 and 3 are still allowed for backward compatibility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dd0e-122">Требования</span><span class="sxs-lookup"><span data-stu-id="2dd0e-122">Requirements</span></span>  
 <span data-ttu-id="2dd0e-123">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dd0e-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd0e-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="2dd0e-124">See Also</span></span>  
 [<span data-ttu-id="2dd0e-125">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="2dd0e-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
