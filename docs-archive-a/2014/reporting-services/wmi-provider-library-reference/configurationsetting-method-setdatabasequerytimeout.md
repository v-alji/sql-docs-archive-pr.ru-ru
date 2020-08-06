---
title: Метод SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseQueryTimeout method
ms.assetid: bd2809e5-7848-45b3-a502-b04fc698b646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ab6b5bf27eca5e9d6d083d03af48c0ab71b4dd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737724"
---
# <a name="setdatabasequerytimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="e19dd-102">Метод SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="e19dd-102">SetDatabaseQueryTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="e19dd-103">Указывает время ожидания по умолчанию для запросов базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="e19dd-103">Specifies the default time-out value for report server database queries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e19dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e19dd-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseQueryTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseQueryTimeout (Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e19dd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e19dd-105">Parameters</span></span>  
 <span data-ttu-id="e19dd-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="e19dd-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="e19dd-107">Значение времени ожидания по умолчанию в секундах для запросов к базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="e19dd-107">The default timeout value, in seconds, for report server database queries.</span></span>  
  
 <span data-ttu-id="e19dd-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="e19dd-108">*HRESULT*</span></span>  
 <span data-ttu-id="e19dd-109">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="e19dd-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e19dd-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e19dd-110">Return Value</span></span>  
 <span data-ttu-id="e19dd-111">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="e19dd-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="e19dd-112">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e19dd-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="e19dd-113">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="e19dd-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e19dd-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e19dd-114">Requirements</span></span>  
 <span data-ttu-id="e19dd-115">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e19dd-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e19dd-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e19dd-116">See Also</span></span>  
 [<span data-ttu-id="e19dd-117">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e19dd-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
