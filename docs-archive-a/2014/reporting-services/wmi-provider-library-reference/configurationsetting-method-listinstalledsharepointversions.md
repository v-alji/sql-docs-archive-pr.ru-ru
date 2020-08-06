---
title: Метод ListInstalledSharePointVersions (WMI) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListInstalledSharePointVersions method
ms.assetid: 8f0a5e9f-23f1-41e5-9a90-dfec19ef1df7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ceee23876461cf31cbd265ea39ae015ddcbc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658626"
---
# <a name="listinstalledsharepointversions-method-wmi"></a><span data-ttu-id="77abe-102">Метод ListInstalledSharePointVersions (WMI)</span><span class="sxs-lookup"><span data-stu-id="77abe-102">ListInstalledSharePointVersions Method (WMI)</span></span>
  <span data-ttu-id="77abe-103">Возвращает набор токенов, представляющих версии Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)][!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]или [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] , установленного на том же компьютере, что и сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="77abe-103">Returns a set of tokens that represent the versions of Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] that are installed on the same computer as the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77abe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77abe-104">Syntax</span></span>  
  
```vb  
Public Sub ListInstalledSharePointVersions(ByRef VersionTokens() _  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] VersionTokens,   
    out Int32 Length, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77abe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="77abe-105">Parameters</span></span>  
 <span data-ttu-id="77abe-106">*[VersionTokens]*</span><span class="sxs-lookup"><span data-stu-id="77abe-106">*VersionTokens[]*</span></span>  
 <span data-ttu-id="77abe-107">[out] Массив, который содержит токены, представляющие версию продукта или технологии SharePoint, совместимых с установленным сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="77abe-107">[out] An array that contains the tokens that represent the version of a SharePoint product or technology that is compatible with the installed report server.</span></span>  
  
 <span data-ttu-id="77abe-108">*Длина*</span><span class="sxs-lookup"><span data-stu-id="77abe-108">*Length*</span></span>  
 <span data-ttu-id="77abe-109">[out] Длина массива токенов версии.</span><span class="sxs-lookup"><span data-stu-id="77abe-109">[out] The length of the version tokens array.</span></span>  
  
 <span data-ttu-id="77abe-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="77abe-110">*HRESULT*</span></span>  
 <span data-ttu-id="77abe-111">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="77abe-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77abe-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="77abe-112">Return Value</span></span>  
 <span data-ttu-id="77abe-113">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="77abe-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="77abe-114">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="77abe-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="77abe-115">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="77abe-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77abe-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="77abe-116">Remarks</span></span>  
 <span data-ttu-id="77abe-117">Каждый возвращенный токен представляет версию [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] или [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] , совместимую с установленным в настоящий момент сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="77abe-117">Each token that is returned represents a version of [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] or [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] that is compatible with the currently installed report server.</span></span> <span data-ttu-id="77abe-118">Если версия SharePoint совместима с предыдущими версиями SharePoint, возвращаются токены для каждой совместимой версии SharePoint.</span><span class="sxs-lookup"><span data-stu-id="77abe-118">If a particular version of SharePoint is compatible with previous SharePoint versions, tokens for each compatible SharePoint version are returned.</span></span>  
  
 <span data-ttu-id="77abe-119">Ниже приведена таблица с возвращаемыми токенами SharePoint.</span><span class="sxs-lookup"><span data-stu-id="77abe-119">The following is a table of the SharePoint tokens that are returned.</span></span>  
  
|<span data-ttu-id="77abe-120">**Токены версий**</span><span class="sxs-lookup"><span data-stu-id="77abe-120">**Version Tokens**</span></span>|<span data-ttu-id="77abe-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="77abe-121">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="77abe-122">WSS_V2_Compatible</span><span class="sxs-lookup"><span data-stu-id="77abe-122">WSS_V2_Compatible</span></span>|<span data-ttu-id="77abe-123">Установлен экземпляр [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]или [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] , совместимый с [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span><span class="sxs-lookup"><span data-stu-id="77abe-123">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span></span>|  
|<span data-ttu-id="77abe-124">WSS_V3_Compatible</span><span class="sxs-lookup"><span data-stu-id="77abe-124">WSS_V3_Compatible</span></span>|<span data-ttu-id="77abe-125">Установлен экземпляр [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]или [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] , совместимый с [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span><span class="sxs-lookup"><span data-stu-id="77abe-125">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span></span>|  
|<span data-ttu-id="77abe-126">WSS_V4_Compatible</span><span class="sxs-lookup"><span data-stu-id="77abe-126">WSS_V4_Compatible</span></span>|<span data-ttu-id="77abe-127">Установлен экземпляр [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] или [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] , совместимый с Office 14.</span><span class="sxs-lookup"><span data-stu-id="77abe-127">A [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with Office 14.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77abe-128">Требования</span><span class="sxs-lookup"><span data-stu-id="77abe-128">Requirements</span></span>  
 <span data-ttu-id="77abe-129">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77abe-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77abe-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="77abe-130">See Also</span></span>  
 [<span data-ttu-id="77abe-131">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="77abe-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
