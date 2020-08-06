---
title: Средство полнотекстового поиска (Майкрософт) для SQL Server не будет загружать сторонние компоненты без знака по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Full-Text Engine for SQL service
- MSFTESQL service
ms.assetid: 029f9895-7232-4149-9362-3ab1a4133d21
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12ff188fb6aa6ac286817a7cc1c3ad726483c886
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669264"
---
# <a name="the-microsoft-full-text-engine-for-sql-server-will-not-load-unsigned-third-party-components-by-default"></a><span data-ttu-id="c7891-102">По умолчанию средство полнотекстового поиска (Майкрософт) для SQL Server не загружает компоненты сторонних производителей, не имеющие подписи</span><span class="sxs-lookup"><span data-stu-id="c7891-102">The Microsoft Full-Text Engine for SQL Server will not load unsigned third-party components by default</span></span>
  <span data-ttu-id="c7891-103">По умолчанию [!INCLUDE[msCoName](../../includes/msconame-md.md)] средство полнотекстового поиска для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не будет загружать компоненты, которые не подписаны [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7891-103">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Full-Text Engine for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not load components that are not signed by [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="c7891-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="c7891-104">Component</span></span>  
 <span data-ttu-id="c7891-105">Компонент Full-text Search</span><span class="sxs-lookup"><span data-stu-id="c7891-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="c7891-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c7891-106">Description</span></span>  
 <span data-ttu-id="c7891-107">Сторонний фильтр, например фильтр в формате PDF, установленный на сервере, не будет загружен средством полнотекстового поиска по [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] умолчанию после обновления.</span><span class="sxs-lookup"><span data-stu-id="c7891-107">A third-party filter, such as a PDF filter, that is currently installed on the server will not be loaded by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Full-Text Engine for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by default after upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c7891-108">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="c7891-108">Corrective Action</span></span>  
 <span data-ttu-id="c7891-109">Чтобы загрузить фильтр стороннего производителя, необходимо задать *load_os_resource* и отключить *verify_signature* на этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="c7891-109">To load a third party filter, you must set *load_os_resource* and turn off *verify_signature* on that instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7891-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7891-110">See Also</span></span>  
 [<span data-ttu-id="c7891-111">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="c7891-111">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
