---
title: Изменение хранимых процедур, в которых используются неподдерживаемые свойства полнотекстового поиска | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- discontinued properties [Full-Text Search]
- stored procedures [Full-Text Search]
ms.assetid: 8d9392d9-a9ba-4378-84e4-59f516b67ddb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12262a588742f0e3be094e32a2a0208a85b6f28a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659185"
---
# <a name="modify-stored-procedures-that-use-discontinued-full-text-search-properties"></a><span data-ttu-id="b3281-102">Измените хранимые процедуры, в которых используются неподдерживаемые свойства полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="b3281-102">Modify stored procedures that use discontinued Full-Text Search properties</span></span>
  <span data-ttu-id="b3281-103">Чтобы обеспечить правильную работу хранимых процедур, нужно изменить существующие процедуры, удалив свойства и настройки, связанные с полнотекстовым поиском, которые были удалены или устарели.</span><span class="sxs-lookup"><span data-stu-id="b3281-103">To ensure that your stored procedures perform correctly, you should edit existing procedures and remove those full-text related properties and settings that have been removed or deprecated.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b3281-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="b3281-104">Component</span></span>  
 <span data-ttu-id="b3281-105">Компонент Full-text Search</span><span class="sxs-lookup"><span data-stu-id="b3281-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="b3281-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b3281-106">Description</span></span>  
 <span data-ttu-id="b3281-107">Следующие свойства и настройки, связанные с полнотекстовым поиском, были удалены.</span><span class="sxs-lookup"><span data-stu-id="b3281-107">The following Full-Text Search-related properties and settings have been removed.</span></span>  
  
-   <span data-ttu-id="b3281-108">**DataTimeout**</span><span class="sxs-lookup"><span data-stu-id="b3281-108">**DataTimeout**</span></span>  
  
-   <span data-ttu-id="b3281-109">**ConnectTimeout**</span><span class="sxs-lookup"><span data-stu-id="b3281-109">**ConnectTimeout**</span></span>  
  
-   <span data-ttu-id="b3281-110">**Clean_up**</span><span class="sxs-lookup"><span data-stu-id="b3281-110">**Clean_up**</span></span>  
  
-   <span data-ttu-id="b3281-111">**LogSize**</span><span class="sxs-lookup"><span data-stu-id="b3281-111">**LogSize**</span></span>  
  
 <span data-ttu-id="b3281-112">Следующие свойства и настройки, связанные с полнотекстовым поиском, были удалены или устарели.</span><span class="sxs-lookup"><span data-stu-id="b3281-112">The following Full-Text Search-related properties and settings have been removed or deprecated:</span></span>  
  
-   <span data-ttu-id="b3281-113">Параметр Path полнотекстового каталога.</span><span class="sxs-lookup"><span data-stu-id="b3281-113">'Path' of the Full-Text Catalog.</span></span> <span data-ttu-id="b3281-114">Полнотекстовый каталог будет логическим объектом, не имеющим конкретного файлового пути.</span><span class="sxs-lookup"><span data-stu-id="b3281-114">The Full-Text Catalog will be a logic object without a specific file path in the system.</span></span>  
  
-   <span data-ttu-id="b3281-115">Включение или отключение полнотекстового поиска с помощью процедуры SP_FULLTEXT_DATABASE больше не работает, так как в [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] базы данных по умолчанию всегда доступны для полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="b3281-115">Enable/disable in SP_FULLTEXT_DATABASE has no effect anymore as databases are enabled for Full-Text Search at all times and by default in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b3281-116">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="b3281-116">Corrective Action</span></span>  
 <span data-ttu-id="b3281-117">Измените хранимые процедуры, чтобы удалить эти свойства.</span><span class="sxs-lookup"><span data-stu-id="b3281-117">Modify your stored procedures to remove these properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3281-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3281-118">See Also</span></span>  
 [<span data-ttu-id="b3281-119">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="b3281-119">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
