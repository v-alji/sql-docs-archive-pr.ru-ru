---
title: Метод SetDatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseLogonTimeout method
ms.assetid: b8773596-5b98-4355-a4ab-4412e1317c67
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf93cd9158c3489db611446ac8523701f52831f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737736"
---
# <a name="setdatabaselogontimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ec580-102">Метод SetDatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ec580-102">SetDatabaseLogonTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ec580-103">Задает значение времени ожидания по умолчанию для подключений к базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="ec580-103">Specifies the default timeout value for report server database connections.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec580-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec580-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseLogonTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseLogonTimeout(Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec580-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec580-105">Parameters</span></span>  
 <span data-ttu-id="ec580-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="ec580-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="ec580-107">Значение времени ожидания по умолчанию в секундах для подключений к базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="ec580-107">The default time-out value, in seconds, for report server database connections.</span></span>  
  
 <span data-ttu-id="ec580-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="ec580-108">*HRESULT*</span></span>  
 <span data-ttu-id="ec580-109">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="ec580-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec580-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ec580-110">Return Value</span></span>  
 <span data-ttu-id="ec580-111">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="ec580-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="ec580-112">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="ec580-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="ec580-113">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="ec580-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec580-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ec580-114">Requirements</span></span>  
 <span data-ttu-id="ec580-115">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec580-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec580-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="ec580-116">See Also</span></span>  
 [<span data-ttu-id="ec580-117">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ec580-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
