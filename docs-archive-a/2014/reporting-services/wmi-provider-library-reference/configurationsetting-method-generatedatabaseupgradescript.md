---
title: Метод GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseUpgradeScript method
ms.assetid: 88534e8e-2877-41cd-b5c2-b1d33a0fd203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a619584b9f1cc095f8f624670386d388426e4a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658629"
---
# <a name="generatedatabaseupgradescript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="88786-102">Метод GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="88786-102">GenerateDatabaseUpgradeScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="88786-103">Формирует скрипт, который можно использовать для обновления базы данных сервера отчетов до схемы [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="88786-103">Generates a script that can be used to upgrade the report server database to the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88786-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88786-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseUpgradeScript(DatabaseName as String, _  
    ServerVersion as String, ByRef Script as String, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GenerateDatabaseUpgradeScript (string DatabaseName,   
    string ServerVersion, out string Script,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88786-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88786-105">Parameters</span></span>  
 <span data-ttu-id="88786-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="88786-106">*Databasename*</span></span>  
 <span data-ttu-id="88786-107">Строка, которая содержит имя базы данных сервера отчетов для обновления.</span><span class="sxs-lookup"><span data-stu-id="88786-107">A string containing the name of the report server database to upgrade.</span></span>  
  
 <span data-ttu-id="88786-108">*ServerVersion*</span><span class="sxs-lookup"><span data-stu-id="88786-108">*ServerVersion*</span></span>  
 <span data-ttu-id="88786-109">Строка, которая содержит версию сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="88786-109">A string containing the version of the report server.</span></span>  
  
 <span data-ttu-id="88786-110">*Скрипт*</span><span class="sxs-lookup"><span data-stu-id="88786-110">*Script*</span></span>  
 <span data-ttu-id="88786-111">[out] Строка, содержащая сформированный скрипт SQL.</span><span class="sxs-lookup"><span data-stu-id="88786-111">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="88786-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="88786-112">*HRESULT*</span></span>  
 <span data-ttu-id="88786-113">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="88786-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88786-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="88786-114">Return Value</span></span>  
 <span data-ttu-id="88786-115">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="88786-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="88786-116">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="88786-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="88786-117">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="88786-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88786-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="88786-118">Remarks</span></span>  
 <span data-ttu-id="88786-119">Созданный скрипт поддерживает [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]и [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88786-119">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88786-120">Требования</span><span class="sxs-lookup"><span data-stu-id="88786-120">Requirements</span></span>  
 <span data-ttu-id="88786-121">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88786-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88786-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="88786-122">See Also</span></span>  
 [<span data-ttu-id="88786-123">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="88786-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
