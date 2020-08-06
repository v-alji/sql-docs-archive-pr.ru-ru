---
title: MSSQL_ENG014120 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014120 error
ms.assetid: 6b169a3b-30da-4981-b998-b52d61811572
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7f3484d9344a203ca8c44fee6b79605163ea069
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654186"
---
# <a name="mssql_eng014120"></a><span data-ttu-id="a274a-102">MSSQL_ENG014120</span><span class="sxs-lookup"><span data-stu-id="a274a-102">MSSQL_ENG014120</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a274a-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="a274a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a274a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a274a-104">Product Name</span></span>|<span data-ttu-id="a274a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a274a-105">SQL Server</span></span>|  
|<span data-ttu-id="a274a-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a274a-106">Event ID</span></span>|<span data-ttu-id="a274a-107">14120</span><span class="sxs-lookup"><span data-stu-id="a274a-107">14120</span></span>|  
|<span data-ttu-id="a274a-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a274a-108">Event Source</span></span>|<span data-ttu-id="a274a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a274a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a274a-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a274a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a274a-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a274a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a274a-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a274a-112">Message Text</span></span>|<span data-ttu-id="a274a-113">Не удается удалить базу данных "%s" распространителя.</span><span class="sxs-lookup"><span data-stu-id="a274a-113">Could not drop the distribution database '%s'.</span></span> <span data-ttu-id="a274a-114">Эта база данных распространителя связана с издателем.</span><span class="sxs-lookup"><span data-stu-id="a274a-114">This distributor database is associated with a Publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a274a-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a274a-115">Explanation</span></span>  
 <span data-ttu-id="a274a-116">В базе данных распространителя хранятся метаданные и данные журнала для всех типов репликации и транзакций, относящихся к репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="a274a-116">The distribution database stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="a274a-117">Эта ошибка возникает при попытке удалить базу данных распространителя, связанную с одним или несколькими издателями.</span><span class="sxs-lookup"><span data-stu-id="a274a-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a274a-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a274a-118">User Action</span></span>  
 <span data-ttu-id="a274a-119">Для удаления базы данных распространителя следует вначале удалить связь между распространителем и издателем.</span><span class="sxs-lookup"><span data-stu-id="a274a-119">To drop a distribution database you must first drop the association between the Distributor and the Publisher.</span></span> <span data-ttu-id="a274a-120">Дополнительные сведения см. в статье [sp_addlinkedserver (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a274a-120">For more information, see [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a274a-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="a274a-121">See Also</span></span>  
 <span data-ttu-id="a274a-122">[Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="a274a-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="a274a-123">Настройка распространения</span><span class="sxs-lookup"><span data-stu-id="a274a-123">Configure Distribution</span></span>](configure-distribution.md)  
  
  
