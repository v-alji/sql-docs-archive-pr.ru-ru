---
title: Свойство SqlServiceType (класс класс sqlserviceadvancedproperty) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: 20f1663a-9a14-4f14-8c1b-8aa133e272c3
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 774c8599fd21e330fa3228336ab1ed3c73d65c85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668680"
---
# <a name="sqlservicetype-property-sqlserviceadvancedproperty-class"></a><span data-ttu-id="05e6d-102">Свойство SqlServiceType (класс SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="05e6d-102">SqlServiceType Property (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="05e6d-103">Возвращает тип управляемой службы, связанной с дополнительным свойством.</span><span class="sxs-lookup"><span data-stu-id="05e6d-103">Gets the type of the managed service associated with the advanced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05e6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05e6d-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="05e6d-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="05e6d-105">Parts</span></span>  
 <span data-ttu-id="05e6d-106">*object*</span><span class="sxs-lookup"><span data-stu-id="05e6d-106">*object*</span></span>  
 <span data-ttu-id="05e6d-107">Объект [класса SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) , представляющий дополнительное свойство.</span><span class="sxs-lookup"><span data-stu-id="05e6d-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="05e6d-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="05e6d-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="05e6d-109">Значение uint32, задающее тип службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05e6d-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05e6d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="05e6d-110">Remarks</span></span>  
 <span data-ttu-id="05e6d-111">Может возвращаться одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="05e6d-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="05e6d-112">Type</span><span class="sxs-lookup"><span data-stu-id="05e6d-112">Type</span></span>|<span data-ttu-id="05e6d-113">Определение</span><span class="sxs-lookup"><span data-stu-id="05e6d-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="05e6d-114">*1*</span><span class="sxs-lookup"><span data-stu-id="05e6d-114">*1*</span></span>|<span data-ttu-id="05e6d-115">MSSQLSERVER — служба [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05e6d-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="05e6d-116">*2*</span><span class="sxs-lookup"><span data-stu-id="05e6d-116">*2*</span></span>|<span data-ttu-id="05e6d-117">SQLSERVERAGENT — служба « [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , агент».</span><span class="sxs-lookup"><span data-stu-id="05e6d-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="05e6d-118">*3*</span><span class="sxs-lookup"><span data-stu-id="05e6d-118">*3*</span></span>|<span data-ttu-id="05e6d-119">MSFTESQL — служба средства полнотекстового поиска [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05e6d-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="05e6d-120">*4*</span><span class="sxs-lookup"><span data-stu-id="05e6d-120">*4*</span></span>|<span data-ttu-id="05e6d-121">MsDtsServer — служба [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05e6d-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="05e6d-122">*5*</span><span class="sxs-lookup"><span data-stu-id="05e6d-122">*5*</span></span>|<span data-ttu-id="05e6d-123">MSSQLServerOLAPService — служба [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05e6d-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="05e6d-124">*6*</span><span class="sxs-lookup"><span data-stu-id="05e6d-124">*6*</span></span>|<span data-ttu-id="05e6d-125">ReportServer — служба [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05e6d-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="05e6d-126">*7*</span><span class="sxs-lookup"><span data-stu-id="05e6d-126">*7*</span></span>|<span data-ttu-id="05e6d-127">SQLBrowser — служба « [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , обозреватель».</span><span class="sxs-lookup"><span data-stu-id="05e6d-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05e6d-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="05e6d-128">See Also</span></span>  
 <span data-ttu-id="05e6d-129">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="05e6d-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
