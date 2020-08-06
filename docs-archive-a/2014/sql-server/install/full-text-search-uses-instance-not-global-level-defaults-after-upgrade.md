---
title: Обновление приведет к тому, что полнотекстовый поиск будет использовать по умолчанию, а не глобальные, разделители слов и фильтры на уровне экземпляра | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 93ee8fcb-d11c-49fa-8fac-51ed31a8f008
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b6cea7ab63351fad25f0205a614e364328171a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669259"
---
# <a name="upgrading-will-cause-full-text-search-to-use-instance-level-not-global-word-breakers-and-filters-by-default"></a><span data-ttu-id="2b993-102">После обновления компонент Full-Text Search будет по умолчанию использовать средства разбиения по словам и фильтры не глобального уровня, а уровня экземпляра</span><span class="sxs-lookup"><span data-stu-id="2b993-102">Upgrading will cause Full-Text Search to use instance-level, not global, word breakers and filters by default</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2b993-103">обеспечивает регистрацию новых средств разбиения по словам и фильтров на уровне экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2b993-103">provides a way to allow instance-level registration of new word breakers and filters.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2b993-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="2b993-104">Component</span></span>  
 <span data-ttu-id="2b993-105">Компонент Full-text Search</span><span class="sxs-lookup"><span data-stu-id="2b993-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="2b993-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2b993-106">Description</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2b993-107">позволяет регистрацию новых средств разбиения по словам и фильтров на уровне экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2b993-107">allows the instance-level registration of new word breakers and filters.</span></span> <span data-ttu-id="2b993-108">Регистрация на уровне экземпляра обеспечивает функциональную изоляцию и изоляцию безопасности между экземплярами.</span><span class="sxs-lookup"><span data-stu-id="2b993-108">This instance-level registration provides functional and security isolation between instances.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="2b993-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="2b993-109">Corrective Action</span></span>  
 <span data-ttu-id="2b993-110">После обновления используйте процедуру `sp_fulltext_service` для определения свойств службы и аргумент `load_os_resources`, разрешающий загрузку компонентов.</span><span class="sxs-lookup"><span data-stu-id="2b993-110">After upgrading, use the `sp_fulltext_service` to set the service property and `load_os_resources`, which allows the components to be loaded.</span></span> <span data-ttu-id="2b993-111">Необходимо выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2b993-111">You must run the following:</span></span>  
  
 `sp_fulltext_service 'load_os_resources', 1`  
  
## <a name="see-also"></a><span data-ttu-id="2b993-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="2b993-112">See Also</span></span>  
 [<span data-ttu-id="2b993-113">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="2b993-113">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
