---
title: Метод GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseCreationScript method
ms.assetid: 25232dc7-00fe-4cd1-8a1c-7e36d552de00
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e798aa25bec1cc478a6ec2cbdd0c21f44fa8215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658632"
---
# <a name="generatedatabasecreationscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="06033-102">Метод GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="06033-102">GenerateDatabaseCreationScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="06033-103">Формирует скрипт SQL, который можно использовать для создания базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="06033-103">Generates a SQL Script that can be used to create a report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06033-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06033-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseCreationScript(ByVal DatabaseName As String, _  
    ByVal Lcid As Int32, ByVal IsSharePointMode As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseCreationScript(string DatabaseName, Int32 Lcid,   
    Boolean IsSharePointMode, out string Script, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06033-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="06033-105">Parameters</span></span>  
 <span data-ttu-id="06033-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="06033-106">*Databasename*</span></span>  
 <span data-ttu-id="06033-107">Строка, которая содержит имя создаваемой базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="06033-107">A string containing the name of the report server database to create.</span></span>  
  
 <span data-ttu-id="06033-108">*Код языка*</span><span class="sxs-lookup"><span data-stu-id="06033-108">*Lcid*</span></span>  
 <span data-ttu-id="06033-109">Значение, используемое для локализованных имен ролей.</span><span class="sxs-lookup"><span data-stu-id="06033-109">Value used for localization of role names.</span></span>  
  
 <span data-ttu-id="06033-110">*IsSharePointMode*</span><span class="sxs-lookup"><span data-stu-id="06033-110">*IsSharePointMode*</span></span>  
 <span data-ttu-id="06033-111">Указывает, следует ли создать базу данных в собственном режиме или в режиме SharePoint.</span><span class="sxs-lookup"><span data-stu-id="06033-111">Indicates whether to create database in native mode or SharePoint mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="06033-112">Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , *исшарепоинтмоде* = `True` не поддерживается, так как в режиме интеграции с SharePoint [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] является общей службой SharePoint и не контролируется поставщиком WMI.</span><span class="sxs-lookup"><span data-stu-id="06033-112">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], *IsSharePointMode*=`True` is not supported because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is a SharePoint shared service and is not controlled by the WMI provider.</span></span> <span data-ttu-id="06033-113">Этот параметр должен всегда быть установлен в значение `False`.</span><span class="sxs-lookup"><span data-stu-id="06033-113">You should always set this parameter to `False`.</span></span>  
  
 <span data-ttu-id="06033-114">*Скрипт*</span><span class="sxs-lookup"><span data-stu-id="06033-114">*Script*</span></span>  
 <span data-ttu-id="06033-115">[out] Строка, содержащая сформированный скрипт SQL.</span><span class="sxs-lookup"><span data-stu-id="06033-115">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="06033-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="06033-116">*HRESULT*</span></span>  
 <span data-ttu-id="06033-117">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="06033-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06033-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="06033-118">Return Value</span></span>  
 <span data-ttu-id="06033-119">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="06033-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="06033-120">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="06033-120">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="06033-121">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="06033-121">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06033-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="06033-122">Remarks</span></span>  
 <span data-ttu-id="06033-123">Этот метод формирует скрипт SQL, создающий базы данных сервера отчетов для версии сервера отчетов, подключенного в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="06033-123">This method generates an SQL script that creates report server databases for the version of the report server currently connected to.</span></span>  
  
 <span data-ttu-id="06033-124">Значение, переданное в параметре *DatabaseName* , должно соответствовать контексту именования в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="06033-124">The value supplied in the *DatabaseName* parameter must conform to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database naming conventions.</span></span>  
  
 <span data-ttu-id="06033-125">При создании скрипта этот метод не проверяет существование базы данных.</span><span class="sxs-lookup"><span data-stu-id="06033-125">The method does not check the existence of the database when generating the script.</span></span>  
  
 <span data-ttu-id="06033-126">Этот метод не проверяет при создании скрипта наличие базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="06033-126">This method does not check for the existence of the report server database when generating the script.</span></span>  
  
 <span data-ttu-id="06033-127">Созданный скрипт поддерживает [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 и [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06033-127">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06033-128">Требования</span><span class="sxs-lookup"><span data-stu-id="06033-128">Requirements</span></span>  
 <span data-ttu-id="06033-129">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06033-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06033-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="06033-130">See Also</span></span>  
 [<span data-ttu-id="06033-131">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="06033-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
