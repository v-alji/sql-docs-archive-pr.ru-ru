---
title: Свойство DatabaseLogonAccount (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonAccount
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonAccount property
ms.assetid: 55f2863f-1ac1-4519-b512-e7f11c0ea5ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9e844ff1d1447bd5abfefad8e82939575c7f47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737679"
---
# <a name="databaselogonaccount-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="a80f6-102">Свойство DatabaseLogonAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="a80f6-102">DatabaseLogonAccount Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="a80f6-103">Позволяет задать учетную запись входа, используемую сервером отчетов при соединении с его базой данных.</span><span class="sxs-lookup"><span data-stu-id="a80f6-103">Specifies the logon account that the report server uses when connecting to the report server database.</span></span> <span data-ttu-id="a80f6-104">Только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a80f6-104">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a80f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a80f6-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonAccount As String  
```  
  
```csharp  
public string DatabaseLogonAccount;  
```  
  
## <a name="property-values"></a><span data-ttu-id="a80f6-106">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="a80f6-106">Property Values</span></span>  
 <span data-ttu-id="a80f6-107">Объект `String`, который представляет имя учетной записи входа.</span><span class="sxs-lookup"><span data-stu-id="a80f6-107">A `String` object that represents the logon account name.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="a80f6-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="a80f6-108">Example Code</span></span>  
 [<span data-ttu-id="a80f6-109">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a80f6-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="a80f6-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a80f6-110">Remarks</span></span>  
 <span data-ttu-id="a80f6-111">Допустимые значения этого свойства различаются в зависимости от значения свойства [DatabaseLogonType](configurationsetting-property-databaselogontype.md) .</span><span class="sxs-lookup"><span data-stu-id="a80f6-111">Valid values for this property will vary depending on the value of the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property.</span></span>  
  
 <span data-ttu-id="a80f6-112">Это свойство пропускается, если свойство [DatabaseLogonType](configurationsetting-property-databaselogontype.md) имеет значение `2 (Service)` .</span><span class="sxs-lookup"><span data-stu-id="a80f6-112">This property is ignored if the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property is set to `2 (Service)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a80f6-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a80f6-113">Requirements</span></span>  
 <span data-ttu-id="a80f6-114">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a80f6-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a80f6-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="a80f6-115">See Also</span></span>  
 [<span data-ttu-id="a80f6-116">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a80f6-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
