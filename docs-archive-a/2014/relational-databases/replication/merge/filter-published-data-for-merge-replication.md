---
title: Фильтрация опубликованных данных для репликации слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication [SQL Server replication], filtering published data
- replication [SQL Server], filtering published data
ms.assetid: 46c5023d-7a3b-4455-becc-e159fcb5d6c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ad9ad45a64f57a6bef8255373180ea943af9893f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654214"
---
# <a name="filter-published-data-for-merge-replication"></a><span data-ttu-id="25cd6-102">Фильтрация опубликованных данных для репликации слиянием</span><span class="sxs-lookup"><span data-stu-id="25cd6-102">Filter Published Data for Merge Replication</span></span>
  <span data-ttu-id="25cd6-103">Кроме статических фильтров строк и фильтров столбцов, которые можно определять с другими типами репликации, репликация слиянием позволяет определять параметризованные фильтры строк и фильтры соединения.</span><span class="sxs-lookup"><span data-stu-id="25cd6-103">In addition to the static row filters and column filters you can define with other types of replication, merge replication offers parameterized row filters and join filters.</span></span> <span data-ttu-id="25cd6-104">Дополнительные сведения о статических фильтрах строк и фильтрах столбцов см. в разделе [Фильтрация опубликованных данных](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="25cd6-104">For more information about static row filters and column filters, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
 <span data-ttu-id="25cd6-105">Репликация слиянием используется во многих приложениях, поддерживающих мобильных пользователей; эти приложения обычно имеют большое количество подписок, при этом каждая подписка получает уникальный набор данных.</span><span class="sxs-lookup"><span data-stu-id="25cd6-105">Merge replication is used in many applications that support mobile users; these applications usually have a large number of subscriptions with each subscription receiving a unique data set.</span></span> <span data-ttu-id="25cd6-106">Параметризованные фильтры в сочетании с фильтрами соединения позволяют администратору настраивать одну публикацию (или в крайнем случае небольшое количество публикаций) и тем не менее предоставлять пользователям различные наборы данных, сокращая затраты на управление, связанные с созданием многочисленных публикаций.</span><span class="sxs-lookup"><span data-stu-id="25cd6-106">Parameterized filters combined with join filters allow an administrator to set up one publication (or at most a small number of publications) and yet provide different data sets to users, reducing the management overhead introduced by creating multiple publications.</span></span>  
  
-   <span data-ttu-id="25cd6-107">Параметризованные фильтры позволяют посылать разным подписчикам разные сегменты данных без необходимости создавать многочисленные публикации.</span><span class="sxs-lookup"><span data-stu-id="25cd6-107">Parameterized filters allow different partitions of data to be sent to different Subscribers without requiring multiple publications to be created.</span></span> <span data-ttu-id="25cd6-108">Например, можно отфильтровать таблицу, чтобы данные для определенного продавца реплицировались только этому представителю.</span><span class="sxs-lookup"><span data-stu-id="25cd6-108">For example, a table can be filtered so that data for a given sales representative is replicated only to that representative.</span></span> <span data-ttu-id="25cd6-109">Параметризованные фильтры имеют множество параметров, позволяющих подстраивать фильтрацию для оптимизации производительности и лучшего соответствия требованиям данных и приложений.</span><span class="sxs-lookup"><span data-stu-id="25cd6-109">Parameterized filters have a variety of options that allow you to tailor filtering to optimize performance and best match your data and application requirements.</span></span> <span data-ttu-id="25cd6-110">Дополнительные сведения см. в разделе [Параметризованные фильтры строк](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="25cd6-110">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
-   <span data-ttu-id="25cd6-111">Для распространения фильтрации на связанные таблицы фильтры соединения обычно используются совместно с параметризованными фильтрами (они также могут использоваться совместно со статическими фильтрами).</span><span class="sxs-lookup"><span data-stu-id="25cd6-111">Join filters are typically used in conjunction with parameterized filters to extend filtering to related tables (they can also be used in conjunction with static filters).</span></span> <span data-ttu-id="25cd6-112">Например, торговый представитель обычно имеет данные в разных таблицах, таких как таблицы клиентов и заказов.</span><span class="sxs-lookup"><span data-stu-id="25cd6-112">For example, the sales representative typically has data in other tables such as customer and order tables.</span></span> <span data-ttu-id="25cd6-113">Эти данные могут быть отфильтрованы, чтобы продавец получал только данные по своим клиентам и заказам своих клиентов.</span><span class="sxs-lookup"><span data-stu-id="25cd6-113">This data can be filtered so the sales representative receives only the data on her customers and her customers' orders.</span></span> <span data-ttu-id="25cd6-114">Дополнительные сведения см. в статье [Join Filters](join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="25cd6-114">For more information, see [Join Filters](join-filters.md).</span></span>  
  
 <span data-ttu-id="25cd6-115">Фильтр не должен включать столбец `rowguidcol`, который используется в процессе репликации для идентификации строк.</span><span class="sxs-lookup"><span data-stu-id="25cd6-115">A filter must not include the `rowguidcol` used by replication to identify rows.</span></span> <span data-ttu-id="25cd6-116">По умолчанию этот столбец добавляется в момент настройки репликации слиянием и называется **rowguid**.</span><span class="sxs-lookup"><span data-stu-id="25cd6-116">By default this is the column added at the time you set up merge replication and is named **rowguid**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25cd6-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="25cd6-117">See Also</span></span>  
 [<span data-ttu-id="25cd6-118">Публикация данных и объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="25cd6-118">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  
