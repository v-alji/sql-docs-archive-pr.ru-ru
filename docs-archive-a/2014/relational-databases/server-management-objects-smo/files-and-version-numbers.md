---
title: Файлы и номера версий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, versions
- components [SMO]
- files [SMO], components
- SMO [SQL Server], versions
- versions [SMO]
ms.assetid: 510907b6-e7a9-41bd-b892-d6d99a5118e1
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1a7286f15af28f97e488b8b40fd745a0d320108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664129"
---
# <a name="files-and-version-numbers"></a><span data-ttu-id="99a38-102">Файлы и номера версий</span><span class="sxs-lookup"><span data-stu-id="99a38-102">Files and Version Numbers</span></span>
  <span data-ttu-id="99a38-103">Все необходимые [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] компоненты объектов SMO устанавливаются как часть экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="99a38-103">All required [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) components are installed as part of an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client or server.</span></span> <span data-ttu-id="99a38-104">Объекты SMO реализованы в нескольких управляемых сборках.</span><span class="sxs-lookup"><span data-stu-id="99a38-104">SMO is implemented in several managed assemblies.</span></span> <span data-ttu-id="99a38-105">Можно разрабатывать приложения объектов SMO либо на клиенте, либо на сервере.</span><span class="sxs-lookup"><span data-stu-id="99a38-105">You can develop SMO applications on either a client or a server.</span></span>  
  
|<span data-ttu-id="99a38-106">Каталог</span><span class="sxs-lookup"><span data-stu-id="99a38-106">Directory</span></span>|<span data-ttu-id="99a38-107">Файл</span><span class="sxs-lookup"><span data-stu-id="99a38-107">File</span></span>|<span data-ttu-id="99a38-108">Описание</span><span class="sxs-lookup"><span data-stu-id="99a38-108">Description</span></span>|  
|---------------|----------|-----------------|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="99a38-109">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="99a38-109">Microsoft.SqlServer.ConnectionInfo.dll</span></span>|<span data-ttu-id="99a38-110">Содержит поддержку для соединения с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99a38-110">Contains support for connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="99a38-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span><span class="sxs-lookup"><span data-stu-id="99a38-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span></span>|<span data-ttu-id="99a38-112">Содержит поддержку программирования компонента [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span><span class="sxs-lookup"><span data-stu-id="99a38-112">Contains support for programming the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span></span> <span data-ttu-id="99a38-113">Это требуется только в программах, которые используют компонент Service Broker.</span><span class="sxs-lookup"><span data-stu-id="99a38-113">This is required only in programs that access the Service Broker.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="99a38-114">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="99a38-114">Microsoft.SqlServer.Smo.dll</span></span>|<span data-ttu-id="99a38-115">Содержит большинство классов SMO.</span><span class="sxs-lookup"><span data-stu-id="99a38-115">Contains the most of the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="99a38-116">Microsoft.SqlServer.SmoExtended.dll</span><span class="sxs-lookup"><span data-stu-id="99a38-116">Microsoft.SqlServer.SmoExtended.dll</span></span><br /><br /> <span data-ttu-id="99a38-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="99a38-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span><br /><br /> <span data-ttu-id="99a38-118">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="99a38-118">Microsoft.SqlServer.SqlEnum.dll</span></span>|<span data-ttu-id="99a38-119">Содержит поддержку для классов SMO.</span><span class="sxs-lookup"><span data-stu-id="99a38-119">Contains support for the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="99a38-120">Microsoft.SqlServer.WmiEnum.dll</span><span class="sxs-lookup"><span data-stu-id="99a38-120">Microsoft.SqlServer.WmiEnum.dll</span></span>|<span data-ttu-id="99a38-121">Содержит классы поставщика инструментария управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="99a38-121">Contains the Windows Management Instrumentation (WMI) Provider classes.</span></span> <span data-ttu-id="99a38-122">Это требуется только для программ, которые используют классы поставщика WMI.</span><span class="sxs-lookup"><span data-stu-id="99a38-122">This is required only for programs that use the WMI Provider classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="99a38-123">Microsoft.SqlServer.RegSvrEnum.dll</span><span class="sxs-lookup"><span data-stu-id="99a38-123">Microsoft.SqlServer.RegSvrEnum.dll</span></span>|<span data-ttu-id="99a38-124">Содержит классы зарегистрированного сервера.</span><span class="sxs-lookup"><span data-stu-id="99a38-124">Contains the Registered Server classes.</span></span> <span data-ttu-id="99a38-125">Это требуется только для программ, которые используют классы зарегистрированного сервера.</span><span class="sxs-lookup"><span data-stu-id="99a38-125">This is required only for programs that use the Registered Server classes.</span></span>|  
  
  
