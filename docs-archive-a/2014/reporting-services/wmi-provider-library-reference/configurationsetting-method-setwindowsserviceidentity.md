---
title: Метод SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetWindowsServiceIdentity method
ms.assetid: 9bbc734c-9e69-48c2-8bec-8abe7c6cc987
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 15d1b7fa5fc6d69a963785cdaf976c80623c47f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737685"
---
# <a name="setwindowsserviceidentity-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="57cfa-102">Метод SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="57cfa-102">SetWindowsServiceIdentity Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="57cfa-103">Обеспечивает запуск службы Windows сервера отчетов в качестве заданного пользователя Windows, а также предоставляет этой учетной записи достаточные разрешения, необходимые для работы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="57cfa-103">Makes the Report Server Windows service run as a specified Windows user, and grants this account sufficient file system permissions to allow the report server to operate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57cfa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57cfa-104">Syntax</span></span>  
  
```vb  
Public Sub SetWindowsServiceIdentity(UseBuiltInAccount as Boolean, _  
    Account as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetWindowsServiceIdentity(boolean UseBuiltInAccount,   
    string Account, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57cfa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57cfa-105">Parameters</span></span>  
 <span data-ttu-id="57cfa-106">*UseBuiltInAccount*</span><span class="sxs-lookup"><span data-stu-id="57cfa-106">*UseBuiltInAccount*</span></span>  
 <span data-ttu-id="57cfa-107">Показывает, является ли указанная учетная запись встроенной учетной записью Windows.</span><span class="sxs-lookup"><span data-stu-id="57cfa-107">Indicates whether the specified account is a built-in Windows account.</span></span>  
  
 <span data-ttu-id="57cfa-108">*Учетная запись*</span><span class="sxs-lookup"><span data-stu-id="57cfa-108">*Account*</span></span>  
 <span data-ttu-id="57cfa-109">Учетная запись Windows, которая используется для запуска службы Windows, имеет формат «ДОМЕН\псевдоним».</span><span class="sxs-lookup"><span data-stu-id="57cfa-109">The Windows account to use to run the Windows service, in the format "DOMAIN\alias".</span></span>  
  
 <span data-ttu-id="57cfa-110">*Пароль*</span><span class="sxs-lookup"><span data-stu-id="57cfa-110">*Password*</span></span>  
 <span data-ttu-id="57cfa-111">Пароль для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="57cfa-111">The password for the account.</span></span>  
  
 <span data-ttu-id="57cfa-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="57cfa-112">*HRESULT*</span></span>  
 <span data-ttu-id="57cfa-113">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="57cfa-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57cfa-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="57cfa-114">Return Value</span></span>  
 <span data-ttu-id="57cfa-115">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="57cfa-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="57cfa-116">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="57cfa-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="57cfa-117">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="57cfa-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57cfa-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="57cfa-118">Remarks</span></span>  
 <span data-ttu-id="57cfa-119">Если параметр *параметру usebuiltinaccount присвоено* имеет значение `true` и сервер отчетов работает под управлением Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] или Windows XP, значения параметров *имя*, *домен*и *пароль* игнорируются и используется учетная запись локальной системы.</span><span class="sxs-lookup"><span data-stu-id="57cfa-119">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] or Windows XP, the value of the *Name*, *Domain*, and *Password* parameters are ignored and the Local system account is used.</span></span>  
  
 <span data-ttu-id="57cfa-120">Если параметр *параметру usebuiltinaccount присвоено* имеет значение `true` и сервер отчетов работает под управлением Windows Server 2003, свойства *домена* и *пароля* не учитываются, а поле имени должно содержать значения "Builtin\NetworkService", "Builtin\System" или "Builtin\LocalService".</span><span class="sxs-lookup"><span data-stu-id="57cfa-120">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Windows Server 2003, the *Domain* and *Password* properties are ignored, and the name field must contain either "Builtin\NetworkService" or "Builtin\System" or "Builtin\LocalService".</span></span>  
  
 <span data-ttu-id="57cfa-121">Метод SetWindowsServiceIdentity задает разрешения для файлов и папок в установочном каталоге сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="57cfa-121">The SetWindowsServiceIdentity method sets file permissions on files and folders in the report server installation directory.</span></span>  
  
 <span data-ttu-id="57cfa-122">Учетной записи, указанной в параметре *Account* , требуются `LogonAsService` права в Windows.</span><span class="sxs-lookup"><span data-stu-id="57cfa-122">The account specified in the *Account* parameter requires `LogonAsService` rights in Windows.</span></span> <span data-ttu-id="57cfa-123">Метод предоставляет эти права указанной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="57cfa-123">The method grants this right to the specified account.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57cfa-124">Требования</span><span class="sxs-lookup"><span data-stu-id="57cfa-124">Requirements</span></span>  
 <span data-ttu-id="57cfa-125">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57cfa-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57cfa-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="57cfa-126">See Also</span></span>  
 [<span data-ttu-id="57cfa-127">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="57cfa-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
