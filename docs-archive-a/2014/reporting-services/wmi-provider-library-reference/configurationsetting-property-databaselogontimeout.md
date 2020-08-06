---
title: Свойство DatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonTimeout property
ms.assetid: 4a65162c-33de-485e-8fd3-2bd6bff8bf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4920f5ef2282478f4d12a19b0806cf6ff9632cac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737667"
---
# <a name="databaselogontimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="f3d4f-102">Свойство DatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="f3d4f-102">DatabaseLogonTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="f3d4f-103">Указывает число секунд ожидания перед тем, как попытка входа в базу данных сервера отчетов признается неуспешной.</span><span class="sxs-lookup"><span data-stu-id="f3d4f-103">Specifies the number of seconds to wait before an attempt to log on to the report server database fails.</span></span> <span data-ttu-id="f3d4f-104">Значение **0** указывает на бесконечное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="f3d4f-104">A value of **0** indicates an infinite wait time.</span></span> <span data-ttu-id="f3d4f-105">Только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f3d4f-105">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d4f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3d4f-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonTimeout As Int32  
```  
  
```csharp  
public Int32 DatabaseLogonTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="f3d4f-107">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="f3d4f-107">Property Values</span></span>  
 <span data-ttu-id="f3d4f-108">32-разрядное целое число со знаком, представляющее количество секунд.</span><span class="sxs-lookup"><span data-stu-id="f3d4f-108">A 32-bit signed integer object that represents the number of seconds.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="f3d4f-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="f3d4f-109">Example Code</span></span>  
 [<span data-ttu-id="f3d4f-110">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="f3d4f-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="f3d4f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f3d4f-111">Requirements</span></span>  
 <span data-ttu-id="f3d4f-112">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3d4f-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d4f-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3d4f-113">See Also</span></span>  
 [<span data-ttu-id="f3d4f-114">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="f3d4f-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
