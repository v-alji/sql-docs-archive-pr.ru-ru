---
title: Свойство DatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseQueryTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseQueryTimeout property
ms.assetid: 96faed97-9799-4bbf-a66f-fdd532d3eace
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e92e3e0f6752ea99fe89c962ebe96e343c0195b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737658"
---
# <a name="databasequerytimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="419ca-102">Свойство DatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="419ca-102">DatabaseQueryTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="419ca-103">Задает число секунд, которое должно пройти до того, как сервер отчетов предположит, что при выполнении команды произошла ошибка или выполнение заняло слишком много времени.</span><span class="sxs-lookup"><span data-stu-id="419ca-103">Specifies the number of seconds that must elapse before the report server assumes the command failed or took too much time to perform.</span></span> <span data-ttu-id="419ca-104">Сервер отчетов привязывает запросы по времени к каталогу SQL, а не к источнику данных для отчета.</span><span class="sxs-lookup"><span data-stu-id="419ca-104">The report server is timing the querying against the SQL catalog, not a data source for the report.</span></span> <span data-ttu-id="419ca-105">Read/write.</span><span class="sxs-lookup"><span data-stu-id="419ca-105">Read/write.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="419ca-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="419ca-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseQueryTimeout As UInt32  
```  
  
```csharp  
public UInt32 DatabaseQueryTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="419ca-107">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="419ca-107">Property Values</span></span>  
 <span data-ttu-id="419ca-108">32-разрядный, но неподписанный объект `integer` представляет период времени в секундах, который отводится на выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="419ca-108">A 32-bit unsigned `integer` object that represents the number of seconds that the query is allowed to run.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="419ca-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="419ca-109">Example Code</span></span>  
 [<span data-ttu-id="419ca-110">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="419ca-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="419ca-111">Требования</span><span class="sxs-lookup"><span data-stu-id="419ca-111">Requirements</span></span>  
 <span data-ttu-id="419ca-112">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="419ca-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419ca-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="419ca-113">See Also</span></span>  
 [<span data-ttu-id="419ca-114">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="419ca-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
