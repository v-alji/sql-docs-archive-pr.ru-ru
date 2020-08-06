---
title: Метод GetDatabaseVersionDisplayName (WMI) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetDatabaseVersionDisplayName method
ms.assetid: e1286424-7043-4f12-a7ad-1cf69e81baa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b39ce39a4f26964c148631c903869b0234e2b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658627"
---
# <a name="getdatabaseversiondisplayname-method-wmi"></a><span data-ttu-id="0af78-102">Метод GetDatabaseVersionDisplayName (WMI)</span><span class="sxs-lookup"><span data-stu-id="0af78-102">GetDatabaseVersionDisplayName Method (WMI)</span></span>
  <span data-ttu-id="0af78-103">Возвращает отображаемое имя для указанной строки версии базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="0af78-103">Gets the display name for a given report server database version string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0af78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0af78-104">Syntax</span></span>  
  
```vb  
Public Sub GetDatabaseVersionDisplayName(Version As String, DisplayName As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetDatabaseVersionDisplayName(string Version, string DisplayName, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0af78-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0af78-105">Parameters</span></span>  
 <span data-ttu-id="0af78-106">*Версия*</span><span class="sxs-lookup"><span data-stu-id="0af78-106">*Version*</span></span>  
 <span data-ttu-id="0af78-107">Строка, содержащая строку версии базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="0af78-107">A string that contains the version string for a report server database.</span></span>  
  
 <span data-ttu-id="0af78-108">*DisplayName*</span><span class="sxs-lookup"><span data-stu-id="0af78-108">*DisplayName*</span></span>  
 <span data-ttu-id="0af78-109">[out] Строка, содержащая отображаемое имя, соответствующее заданной версии.</span><span class="sxs-lookup"><span data-stu-id="0af78-109">[out] A string that contains the display name that corresponds to the version supplied.</span></span>  
  
 <span data-ttu-id="0af78-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="0af78-110">*HRESULT*</span></span>  
 <span data-ttu-id="0af78-111">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="0af78-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0af78-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="0af78-112">Remarks</span></span>  
 <span data-ttu-id="0af78-113">Следующая таблица показывает сопоставления версий базы данных с отображаемыми строками.</span><span class="sxs-lookup"><span data-stu-id="0af78-113">The following table shows the mapping from database version to display string.</span></span>  
  
|<span data-ttu-id="0af78-114">**Выпуск**</span><span class="sxs-lookup"><span data-stu-id="0af78-114">**Release**</span></span>|`Version`|<span data-ttu-id="0af78-115">**Отображаемое имя**</span><span class="sxs-lookup"><span data-stu-id="0af78-115">**Display Name**</span></span>|  
|-----------------|-----------------|----------------------|  
|<span data-ttu-id="0af78-116">Службы Reporting Services 2005 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="0af78-116">RS 2005 SP2</span></span>|<span data-ttu-id="0af78-117">@DBVersion = 'C.0.8.54'</span><span class="sxs-lookup"><span data-stu-id="0af78-117">@DBVersion = 'C.0.8.54'</span></span>|<span data-ttu-id="0af78-118">SQL Server 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="0af78-118">SQL Server 2005 SP2</span></span>|  
|<span data-ttu-id="0af78-119">Службы Reporting Services 2005 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="0af78-119">RS 2005 SP1</span></span>|<span data-ttu-id="0af78-120">@DBVersion = 'C.0.8.43'</span><span class="sxs-lookup"><span data-stu-id="0af78-120">@DBVersion = 'C.0.8.43'</span></span>|<span data-ttu-id="0af78-121">SQL Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="0af78-121">SQL Server 2005 SP1</span></span>|  
|<span data-ttu-id="0af78-122">Службы Reporting Services 2005, RTM-версия</span><span class="sxs-lookup"><span data-stu-id="0af78-122">RS 2005 RTM</span></span>|<span data-ttu-id="0af78-123">@DBVersion = 'C.0.8.40'</span><span class="sxs-lookup"><span data-stu-id="0af78-123">@DBVersion = 'C.0.8.40'</span></span>|<span data-ttu-id="0af78-124">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="0af78-124">SQL Server 2005</span></span>|  
|<span data-ttu-id="0af78-125">Службы Reporting Services 2000 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="0af78-125">RS 2000 SP2</span></span>|<span data-ttu-id="0af78-126">@DBVersion = 'C.0.6.54'</span><span class="sxs-lookup"><span data-stu-id="0af78-126">@DBVersion = 'C.0.6.54'</span></span>|<span data-ttu-id="0af78-127">SQL Server 2000 с пакетом обновления 2 (SP2)</span><span class="sxs-lookup"><span data-stu-id="0af78-127">SQL Server 2000 SP2</span></span>|  
|<span data-ttu-id="0af78-128">Службы Reporting Services 2000 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="0af78-128">RS 2000 SP1</span></span>|<span data-ttu-id="0af78-129">@DBVersion = 'C.0.6.51'</span><span class="sxs-lookup"><span data-stu-id="0af78-129">@DBVersion = 'C.0.6.51'</span></span>|<span data-ttu-id="0af78-130">SQL Server 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="0af78-130">SQL Server 2000 SP1</span></span>|  
|<span data-ttu-id="0af78-131">Службы Reporting Services 2000, RTM-версия</span><span class="sxs-lookup"><span data-stu-id="0af78-131">RS 2000 RTM</span></span>|<span data-ttu-id="0af78-132">@DBVersion = 'C.0.6.43'</span><span class="sxs-lookup"><span data-stu-id="0af78-132">@DBVersion = 'C.0.6.43'</span></span>|<span data-ttu-id="0af78-133">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="0af78-133">SQL Server 2000</span></span>|  
|<span data-ttu-id="0af78-134">Исправление</span><span class="sxs-lookup"><span data-stu-id="0af78-134">Hotfix</span></span>||<span data-ttu-id="0af78-135">Ближайшая применимая версия</span><span class="sxs-lookup"><span data-stu-id="0af78-135">Closest applicable version</span></span>|  
  
 <span data-ttu-id="0af78-136">Для *версий* , предшествующих [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000, возвращается значение типа HRESULT параметра ACT_E_BAD_VERSION.</span><span class="sxs-lookup"><span data-stu-id="0af78-136">For a *Version* prior to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 an HRESULT of ACT_E_BAD_VERSION is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0af78-137">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0af78-137">Return Value</span></span>  
 <span data-ttu-id="0af78-138">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="0af78-138">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="0af78-139">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="0af78-139">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="0af78-140">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="0af78-140">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0af78-141">Требования</span><span class="sxs-lookup"><span data-stu-id="0af78-141">Requirements</span></span>  
 <span data-ttu-id="0af78-142">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0af78-142">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0af78-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="0af78-143">See Also</span></span>  
 [<span data-ttu-id="0af78-144">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="0af78-144">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
