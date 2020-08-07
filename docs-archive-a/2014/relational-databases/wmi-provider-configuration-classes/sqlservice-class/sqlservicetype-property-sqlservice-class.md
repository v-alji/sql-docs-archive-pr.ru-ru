---
title: Свойство SqlServiceType (класс SqlService) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: dbff2968-3011-41d6-a141-52d814af0213
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 18e0fc741d19eefbb93dbcb7fb6fd4a221ce86d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733725"
---
# <a name="sqlservicetype-property-sqlservice-class"></a><span data-ttu-id="9d9d9-102">Свойство SqlServiceType (класс SqlService)</span><span class="sxs-lookup"><span data-stu-id="9d9d9-102">SqlServiceType Property (SqlService Class)</span></span>
  <span data-ttu-id="9d9d9-103">Возвращает тип управляемой службы.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-103">Gets the type of the managed service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d9d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d9d9-104">Syntax</span></span>  
  
```  
  
object  
.SqlServiceType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="9d9d9-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="9d9d9-105">Parts</span></span>  
 <span data-ttu-id="9d9d9-106">*object*</span><span class="sxs-lookup"><span data-stu-id="9d9d9-106">*object*</span></span>  
 <span data-ttu-id="9d9d9-107">Объект [класса SqlService](sqlservice-class.md) , представляющий службу.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9d9d9-108">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9d9d9-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="9d9d9-109">Значение uint32, задающее тип службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d9d9-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d9d9-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="9d9d9-110">Remarks</span></span>  
 <span data-ttu-id="9d9d9-111">Может возвращаться одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="9d9d9-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="9d9d9-112">Тип</span><span class="sxs-lookup"><span data-stu-id="9d9d9-112">Type</span></span>|<span data-ttu-id="9d9d9-113">Определение</span><span class="sxs-lookup"><span data-stu-id="9d9d9-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="9d9d9-114">*1*</span><span class="sxs-lookup"><span data-stu-id="9d9d9-114">*1*</span></span>|<span data-ttu-id="9d9d9-115">MSSQLSERVER — служба [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d9d9-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="9d9d9-116">*2*</span><span class="sxs-lookup"><span data-stu-id="9d9d9-116">*2*</span></span>|<span data-ttu-id="9d9d9-117">SQLSERVERAGENT — служба « [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , агент».</span><span class="sxs-lookup"><span data-stu-id="9d9d9-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="9d9d9-118">*3*</span><span class="sxs-lookup"><span data-stu-id="9d9d9-118">*3*</span></span>|<span data-ttu-id="9d9d9-119">MSFTESQL — служба средства полнотекстового поиска [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d9d9-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="9d9d9-120">*4*</span><span class="sxs-lookup"><span data-stu-id="9d9d9-120">*4*</span></span>|<span data-ttu-id="9d9d9-121">MsDtsServer — служба [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d9d9-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="9d9d9-122">*5*</span><span class="sxs-lookup"><span data-stu-id="9d9d9-122">*5*</span></span>|<span data-ttu-id="9d9d9-123">MSSQLServerOLAPService — служба [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d9d9-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="9d9d9-124">*6*</span><span class="sxs-lookup"><span data-stu-id="9d9d9-124">*6*</span></span>|<span data-ttu-id="9d9d9-125">ReportServer — служба [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d9d9-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="9d9d9-126">*7*</span><span class="sxs-lookup"><span data-stu-id="9d9d9-126">*7*</span></span>|<span data-ttu-id="9d9d9-127">SQLBrowser — служба « [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , обозреватель».</span><span class="sxs-lookup"><span data-stu-id="9d9d9-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d9d9-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d9d9-128">See Also</span></span>  
 <span data-ttu-id="9d9d9-129">[Запуск и остановка служб](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9d9d9-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
