---
title: Свойство SecureConnectionLevel (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SecureConnectionLevel
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SecureConnectionLevel property
ms.assetid: fd5549e7-b874-41e2-866e-2f58caf6f733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5d1b3bccc8a7fee3899fa21208d83a718a33f5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737631"
---
# <a name="secureconnectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="63930-102">Свойство SecureConnectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="63930-102">SecureConnectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="63930-103">Возвращает уровень безопасного соединения, заданный в файле RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="63930-103">Returns the secure connection level specified in the RSReportServer.config file.</span></span> <span data-ttu-id="63930-104">Только для чтения.</span><span class="sxs-lookup"><span data-stu-id="63930-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63930-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63930-105">Syntax</span></span>  
  
```vb  
Public Dim SecureConnectionLevel As Integer  
```  
  
```csharp  
public Integer SecureConnectionLevel;  
```  
  
## <a name="property-values"></a><span data-ttu-id="63930-106">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="63930-106">Property Values</span></span>  
 <span data-ttu-id="63930-107">Значение `Integer`, представляющее уровень безопасного соединения.</span><span class="sxs-lookup"><span data-stu-id="63930-107">An `Integer` value that represents the secure connection level.</span></span> <span data-ttu-id="63930-108">Возвращаемые значения указывают, была произведена настройка SSL или нет.</span><span class="sxs-lookup"><span data-stu-id="63930-108">The return values indicate that the SSL is either configured or not.</span></span> <span data-ttu-id="63930-109">Значение, которое больше или равно 1, указывает на то, что протокол SSL включен.</span><span class="sxs-lookup"><span data-stu-id="63930-109">A value of greater than or equal to 1 indicates that SSL is turned on.</span></span> <span data-ttu-id="63930-110">Значение 0 указывает на то, что протокол SSL отключен.</span><span class="sxs-lookup"><span data-stu-id="63930-110">A value of 0 indicates that SSL is turned off.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="63930-111">Пример кода</span><span class="sxs-lookup"><span data-stu-id="63930-111">Example Code</span></span>  
 [<span data-ttu-id="63930-112">Класс MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="63930-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="63930-113">Требования</span><span class="sxs-lookup"><span data-stu-id="63930-113">Requirements</span></span>  
 <span data-ttu-id="63930-114">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63930-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63930-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="63930-115">See Also</span></span>  
 [<span data-ttu-id="63930-116">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="63930-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
