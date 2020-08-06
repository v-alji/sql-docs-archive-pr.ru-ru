---
title: Свойство ConnectionPoolSize (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ConnectionPoolSize
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ConnectionPoolSize property
ms.assetid: b80c8e5d-b725-4fe4-aec6-02fb18ec4434
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 24a180fde90ff406d40a0f0c89bf82dfe5138b88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737682"
---
# <a name="connectionpoolsize-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="50d87-102">Свойство ConnectionPoolSize (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="50d87-102">ConnectionPoolSize Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="50d87-103">Размер пула соединений, используемого сервером отчетов для связи с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , где находится база данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="50d87-103">The connection pool size used by the report server to communicate with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the report server database.</span></span> <span data-ttu-id="50d87-104">Только для чтения.</span><span class="sxs-lookup"><span data-stu-id="50d87-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50d87-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50d87-105">Syntax</span></span>  
  
```vb  
Public Dim ConnectionPoolSize As UInt32  
```  
  
```csharp  
public UInt32 ConnectionPoolSize;  
```  
  
## <a name="property-values"></a><span data-ttu-id="50d87-106">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="50d87-106">Property Values</span></span>  
 <span data-ttu-id="50d87-107">**Целочисленный** объект только для чтения, возвращающий значение `768` .</span><span class="sxs-lookup"><span data-stu-id="50d87-107">A read-only **integer** object that returns a value of `768`.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="50d87-108">Пример кода</span><span class="sxs-lookup"><span data-stu-id="50d87-108">Example Code</span></span>  
 [<span data-ttu-id="50d87-109">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="50d87-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="50d87-110">Требования</span><span class="sxs-lookup"><span data-stu-id="50d87-110">Requirements</span></span>  
 <span data-ttu-id="50d87-111">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50d87-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d87-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="50d87-112">See Also</span></span>  
 [<span data-ttu-id="50d87-113">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="50d87-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
