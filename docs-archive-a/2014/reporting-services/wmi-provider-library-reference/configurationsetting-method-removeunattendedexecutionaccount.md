---
title: Метод RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveUnattendedExecutionAccount method
ms.assetid: 77e371c1-7c26-44f9-9119-7c8dc838db32
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efe0523c9aa13315399c043367ef05a63da46e91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734918"
---
# <a name="removeunattendedexecutionaccount-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ef8f7-102">Метод RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ef8f7-102">RemoveUnattendedExecutionAccount Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ef8f7-103">Удаляет из файла конфигурации сервера отчетов учетную запись автоматического выполнения.</span><span class="sxs-lookup"><span data-stu-id="ef8f7-103">Deletes the unattended execution account entry from the report server configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef8f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef8f7-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveUnattendedExecutionAccount(ByRef HRESULT as Int32)  
```  
  
```csharp  
public void RemoveUnattendedExecutionAccount (out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef8f7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef8f7-105">Parameters</span></span>  
 <span data-ttu-id="ef8f7-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="ef8f7-106">*HRESULT*</span></span>  
 <span data-ttu-id="ef8f7-107">[out] Значение, которое указывает, окончился ли вызов успехом или сбоем.</span><span class="sxs-lookup"><span data-stu-id="ef8f7-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef8f7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ef8f7-108">Return Value</span></span>  
 <span data-ttu-id="ef8f7-109">Возвращает значение *HRESULT* , являющееся признаком успешного или неуспешного завершение вызова метода.</span><span class="sxs-lookup"><span data-stu-id="ef8f7-109">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="ef8f7-110">Значение 0 указывает, что вызов метода завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="ef8f7-110">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="ef8f7-111">Ненулевое значение указывает, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="ef8f7-111">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef8f7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ef8f7-112">Requirements</span></span>  
 <span data-ttu-id="ef8f7-113">**Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef8f7-113">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef8f7-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="ef8f7-114">See Also</span></span>  
 [<span data-ttu-id="ef8f7-115">Элементы MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ef8f7-115">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
