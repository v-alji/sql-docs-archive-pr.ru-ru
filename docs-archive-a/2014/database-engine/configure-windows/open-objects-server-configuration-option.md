---
title: Параметр конфигурации сервера "open objects" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- open objects option
ms.assetid: c8424d3c-86ba-4cc5-bf0c-be4ce44bdd04
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6d22a3d6dd358afe9cf921376664c2d25705a6a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728674"
---
# <a name="open-objects-server-configuration-option"></a><span data-ttu-id="c9365-102">Параметр конфигурации сервера «open objects»</span><span class="sxs-lookup"><span data-stu-id="c9365-102">open objects Server Configuration Option</span></span>
  <span data-ttu-id="c9365-103">Этот параметр по-прежнему поддерживается хранимой процедурой **sp_configure**, хотя его функциональность в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отключена.</span><span class="sxs-lookup"><span data-stu-id="c9365-103">This option is still present in **sp_configure**, although its functionality has been disabled in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c9365-104">(Параметр не влияет на работу сервера.) В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] количество открытых объектов базы данных управляется динамически и ограничено только объемом доступной памяти.</span><span class="sxs-lookup"><span data-stu-id="c9365-104">(The setting has no effect.) In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the number of open database objects is managed dynamically and is limited only by the available memory.</span></span> <span data-ttu-id="c9365-105">Параметр **open objects** поддерживается процедурой **SP_CONFIGURE** для обеспечения обратной совместимости с существующими скриптами.</span><span class="sxs-lookup"><span data-stu-id="c9365-105">The **open objects** option available in **sp_configure** for backward compatibility with existing scripts.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c9365-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9365-106">See Also</span></span>  
 [<span data-ttu-id="c9365-107">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c9365-107">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
