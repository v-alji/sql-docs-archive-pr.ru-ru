---
title: Свойство DatabaseLogonType (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonType
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonType property
ms.assetid: 6b592582-4c35-4029-ab86-982fff47d8d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bb5a4149c29fb7532b7140a2616dd856e6db2b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737664"
---
# <a name="databaselogontype-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="9e6f2-102">Свойство DatabaseLogonType (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="9e6f2-102">DatabaseLogonType Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="9e6f2-103">Определяет, какая учетная запись используется для доступа к базе данных сервера отчетов: учетная запись службы [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, учетная запись пользователя Windows, либо имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e6f2-103">Specifies whether the report server uses a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows service account, a Windows user account, or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to access the report server database.</span></span> <span data-ttu-id="9e6f2-104">Только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e6f2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e6f2-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonType As Integer  
```  
  
```csharp  
public int DatabaseLogonType;  
```  
  
## <a name="property-values"></a><span data-ttu-id="9e6f2-106">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="9e6f2-106">Property Values</span></span>  
 <span data-ttu-id="9e6f2-107">Объект `integer` представляет тип входа.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-107">An `integer` object that represents the login type.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="9e6f2-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="9e6f2-108">Example Code</span></span>  
 [<span data-ttu-id="9e6f2-109">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="9e6f2-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="9e6f2-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e6f2-110">Remarks</span></span>  
 <span data-ttu-id="9e6f2-111">Возможны следующие значения.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-111">Values are:</span></span>  
  
-   <span data-ttu-id="9e6f2-112">0 для имени входа Windows</span><span class="sxs-lookup"><span data-stu-id="9e6f2-112">0 for Windows login</span></span>  
  
-   <span data-ttu-id="9e6f2-113">1 для имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e6f2-113">1 for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login</span></span>  
  
-   <span data-ttu-id="9e6f2-114">2 для входа в качестве службы</span><span class="sxs-lookup"><span data-stu-id="9e6f2-114">2 to log in as a service</span></span>  
  
 <span data-ttu-id="9e6f2-115">Если указывается значение 0 (Windows), в свойстве [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) необходимо задать соответствующую учетную запись пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-115">If you specify 0 (Windows), you must set the value in the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) property to a corresponding a valid Windows user account.</span></span>  
  
 <span data-ttu-id="9e6f2-116">Если указывается значение 1 (SQL Server), в свойстве [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) должно быть задано допустимое имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9e6f2-116">If you specify 1 (SQL Server), make sure the value of the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) corresponds to a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="9e6f2-117">Если указывается значение 2 (служба Windows), сервер отчетов использует для доступа к своей базе данных учетную запись [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] и учетную запись службы Windows.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-117">If you specify 2 (Windows service), the report server uses an [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account and the Windows service account to access the report server database.</span></span> <span data-ttu-id="9e6f2-118">Свойство DatabaseLogonAccount игнорируется.</span><span class="sxs-lookup"><span data-stu-id="9e6f2-118">The DatabaseLogonAccount property is ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e6f2-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9e6f2-119">Requirements</span></span>  
 <span data-ttu-id="9e6f2-120">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e6f2-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6f2-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e6f2-121">See Also</span></span>  
 [<span data-ttu-id="9e6f2-122">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="9e6f2-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
