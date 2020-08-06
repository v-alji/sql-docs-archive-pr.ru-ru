---
title: Метод ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ListReportServersInDatabase method
ms.assetid: a4bf5968-c46f-484f-a510-65e2dde65a0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9eaea72c0737124d89c86b55281326073597fb38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658623"
---
# <a name="listreportserversindatabase-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="889fc-102">Метод ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="889fc-102">ListReportServersInDatabase Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="889fc-103">Возвращает список установок сервера отчетов, которые находятся в базе данных сервера отчетов независимо от наличия доступа к защищенным сведениям.</span><span class="sxs-lookup"><span data-stu-id="889fc-103">Returns the list of report server installations that are present in the report server database, regardless of whether they have access to secure information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="889fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="889fc-104">Syntax</span></span>  
  
```vb  
Public Sub ListReportServersInDatabase(ByRef MachineNames() As String, _  
    ByRef InstanceNames() As String, ByRef InstallationIDs() As String, _  
    ByRef IsInitialized() As Boolean, ByRef Length As Int32, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] MachineNames,   
    out string[] InstanceNames, out string[] InstallationIDs,   
    out Boolean[] IsInitialized,out Int32 Length, out Int32 HRESULT,    
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="889fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="889fc-105">Parameters</span></span>  
 <span data-ttu-id="889fc-106">*MachineNames[]*</span><span class="sxs-lookup"><span data-stu-id="889fc-106">*MachineNames[]*</span></span>  
 <span data-ttu-id="889fc-107">[out] Массив, который содержит имена компьютеров, где установлен сервер отчетов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="889fc-107">[out] An array containing the machine names for the report server installations in the database.</span></span>  
  
 <span data-ttu-id="889fc-108">*InstanceNames[]*</span><span class="sxs-lookup"><span data-stu-id="889fc-108">*InstanceNames[]*</span></span>  
 <span data-ttu-id="889fc-109">[out] Массив, который содержит имена экземпляров каждого установленного сервера отчетов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="889fc-109">[out] An array containing the instance names of each of the report server installations in the database.</span></span>  
  
 <span data-ttu-id="889fc-110">*InstallationIDs[]*</span><span class="sxs-lookup"><span data-stu-id="889fc-110">*InstallationIDs[]*</span></span>  
 <span data-ttu-id="889fc-111">[out] Массив, который содержит коды установки каждого установленного сервера отчетов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="889fc-111">[out] An array containing the installation IDs of each report server installation in the database.</span></span>  
  
 <span data-ttu-id="889fc-112">*IsInitialized[]*</span><span class="sxs-lookup"><span data-stu-id="889fc-112">*IsInitialized[]*</span></span>  
 <span data-ttu-id="889fc-113">[out] Массив, который содержит состояние инициализации каждого установленного сервера отчетов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="889fc-113">[out] An array containing initialization status for each report server installation in the database.</span></span>  
  
 <span data-ttu-id="889fc-114">*Длина*</span><span class="sxs-lookup"><span data-stu-id="889fc-114">*Length*</span></span>  
 <span data-ttu-id="889fc-115">[out] Длина массивов, возвращаемых методом.</span><span class="sxs-lookup"><span data-stu-id="889fc-115">[out] The length of the arrays returned by the method.</span></span> <span data-ttu-id="889fc-116">Все возвращенные массивы имеют одинаковую длину.</span><span class="sxs-lookup"><span data-stu-id="889fc-116">All returned arrays have the same length.</span></span>  
  
 <span data-ttu-id="889fc-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="889fc-117">*HRESULT*</span></span>  
 <span data-ttu-id="889fc-118">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="889fc-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="889fc-119">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="889fc-119">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="889fc-120">[out] Массив строк, содержащий дополнительные ошибки, возвращенные в результате вызова.</span><span class="sxs-lookup"><span data-stu-id="889fc-120">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="889fc-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="889fc-121">Return Value</span></span>  
 <span data-ttu-id="889fc-122">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="889fc-122">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="889fc-123">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="889fc-123">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="889fc-124">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="889fc-124">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="889fc-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="889fc-125">Remarks</span></span>  
 <span data-ttu-id="889fc-126">Метод ListReportServersInDatabase выводит список установленных серверов отчетов, которые имеются в базе данных сервера отчетов, независимо от наличия у них доступа к защищенным сведениям, и возвращает сопоставленный набор массивов с данными о каждом установленном сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="889fc-126">ListReportServersInDatabase lists the report server installations that are present in the report server database, regardless of whether they have access to secure information, and returns a matched set of arrays containing information about each installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="889fc-127">Требования</span><span class="sxs-lookup"><span data-stu-id="889fc-127">Requirements</span></span>  
 <span data-ttu-id="889fc-128">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="889fc-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="889fc-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="889fc-129">See Also</span></span>  
 [<span data-ttu-id="889fc-130">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="889fc-130">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
