---
title: Параметр конфигурации сервера "filestream access level" | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], access level
- filestream access level
ms.assetid: b88f6ff2-795e-4730-bfb8-dbc6a958f2ad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dfa43b8e6e1762e87dd9c2abbdf7a583963e196e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668465"
---
# <a name="filestream-access-level-server-configuration-option"></a><span data-ttu-id="acb76-102">Параметр конфигурации сервера «уровень доступа файлового потока»</span><span class="sxs-lookup"><span data-stu-id="acb76-102">filestream access level Server Configuration Option</span></span>
  <span data-ttu-id="acb76-103">Параметр файлового потока filestream_access_level используется для изменения уровня доступа к данным типа FILESTREAM для данного экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acb76-103">Use the filestream_access_level option to change the FILESTREAM access level for this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="acb76-104">Чтобы этот параметр вступил в силу, необходимо включить настройки администрирования Windows для FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="acb76-104">Before this option has any effect, the Windows administration settings for FILESTREAM must be enabled.</span></span> <span data-ttu-id="acb76-105">Эти параметры можно включить при установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="acb76-105">You can enable these settings when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
|<span data-ttu-id="acb76-106">Значение</span><span class="sxs-lookup"><span data-stu-id="acb76-106">Value</span></span>|<span data-ttu-id="acb76-107">Определение</span><span class="sxs-lookup"><span data-stu-id="acb76-107">Definition</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="acb76-108">0</span><span class="sxs-lookup"><span data-stu-id="acb76-108">0</span></span>|<span data-ttu-id="acb76-109">Отключает поддержку FILESTREAM для данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="acb76-109">Disables FILESTREAM support for this instance.</span></span>|  
|<span data-ttu-id="acb76-110">1</span><span class="sxs-lookup"><span data-stu-id="acb76-110">1</span></span>|<span data-ttu-id="acb76-111">Включает FILESTREAM для доступа с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="acb76-111">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span>|  
|<span data-ttu-id="acb76-112">2</span><span class="sxs-lookup"><span data-stu-id="acb76-112">2</span></span>|<span data-ttu-id="acb76-113">Включает FILESTREAM для доступа с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)] и потокового доступа Win32.</span><span class="sxs-lookup"><span data-stu-id="acb76-113">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] and Win32 streaming access.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acb76-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="acb76-114">See Also</span></span>  
 <span data-ttu-id="acb76-115">[Настройка компонента Database Engine — Filestream](../../sql-server/install/database-engine-configuration-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="acb76-115">[Database Engine Configuration - Filestream](../../sql-server/install/database-engine-configuration-filestream.md) </span></span>  
 [<span data-ttu-id="acb76-116">Включение и настройка FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="acb76-116">Enable and Configure FILESTREAM</span></span>](../../relational-databases/blob/enable-and-configure-filestream.md)  
  
  
