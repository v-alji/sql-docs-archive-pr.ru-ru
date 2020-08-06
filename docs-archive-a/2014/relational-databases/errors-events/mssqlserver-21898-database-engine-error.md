---
title: MSSQLSERVER_21898 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21898 (Database Engine error)
ms.assetid: 02405b21-3d4e-4c2d-b4b3-d7b1ec05edb4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 78ce7eacf7f026bf9977af2c367b954a3639b357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731645"
---
# <a name="mssqlserver_21898"></a><span data-ttu-id="7ad64-102">MSSQLSERVER_21898</span><span class="sxs-lookup"><span data-stu-id="7ad64-102">MSSQLSERVER_21898</span></span>
    
## <a name="details"></a><span data-ttu-id="7ad64-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="7ad64-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ad64-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="7ad64-104">Product Name</span></span>|<span data-ttu-id="7ad64-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7ad64-105">SQL Server</span></span>|  
|<span data-ttu-id="7ad64-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7ad64-106">Event ID</span></span>|<span data-ttu-id="7ad64-107">21898</span><span class="sxs-lookup"><span data-stu-id="7ad64-107">21898</span></span>|  
|<span data-ttu-id="7ad64-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="7ad64-108">Event Source</span></span>|<span data-ttu-id="7ad64-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7ad64-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7ad64-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="7ad64-110">Component</span></span>|<span data-ttu-id="7ad64-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7ad64-111">SQLEngine</span></span>|  
|<span data-ttu-id="7ad64-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="7ad64-112">Symbolic Name</span></span>|<span data-ttu-id="7ad64-113">SQLErrorNum21898</span><span class="sxs-lookup"><span data-stu-id="7ad64-113">SQLErrorNum21898</span></span>|  
|<span data-ttu-id="7ad64-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="7ad64-114">Message Text</span></span>|<span data-ttu-id="7ad64-115">Издатель «%s» использует базу данных распространителя «%s», а не «%s», которая необходима для размещения базы данных публикации «%s».</span><span class="sxs-lookup"><span data-stu-id="7ad64-115">The publisher '%s' uses distribution database '%s' and not '%s' which is required in order to host the publishing database '%s'.</span></span> <span data-ttu-id="7ad64-116">Запустите `sp_changedistpublisher` на распространителе «%s», чтобы сменить базу данных распространителя, используемую издателем для «%s».</span><span class="sxs-lookup"><span data-stu-id="7ad64-116">Run `sp_changedistpublisher` at distributor '%s' to change the distribution database used by the publisher to '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ad64-117">Пояснение</span><span class="sxs-lookup"><span data-stu-id="7ad64-117">Explanation</span></span>  
 <span data-ttu-id="7ad64-118">`sp_validate_redirected_publisher` выполняет запросы к msdb.dbo.MSdistpublishers на локальном распространителе, чтобы убедиться, что база данных распространителя, используемая новым издателем, совпадает с базой данных распространителя, которая используется первоначальным издателем.</span><span class="sxs-lookup"><span data-stu-id="7ad64-118">`sp_validate_redirected_publisher` queries msdb.dbo.MSdistpublishers at the local distributor to verify that the distribution database used by the new publisher is the same as the distribution database used by the original publisher.</span></span> <span data-ttu-id="7ad64-119">Эта ошибка возвращается, если эти базы данных различаются, в результате издатель становится непригодным для размещения базы данных издателя.</span><span class="sxs-lookup"><span data-stu-id="7ad64-119">This error is returned when these databases are different, making the publisher an unsuitable host for the publisher database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ad64-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="7ad64-120">User Action</span></span>  
 <span data-ttu-id="7ad64-121">Выполните хранимую процедуру `sp_changedistpublisher`, чтобы изменить базу данных распространителя для нового издателя на базу данных, которая использовалась первоначальным издателем.</span><span class="sxs-lookup"><span data-stu-id="7ad64-121">Execute stored procedure `sp_changedistpublisher` to change the distribution database for the new publisher to that used by the original publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ad64-122">Запуск `sp_changedistpublisher` устранит проблему, если во время запуска `sp_adddistpublisher` на распространителе для издателя была введена неверная база данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="7ad64-122">Running `sp_changedistpublisher` will address the problem if the wrong distribution database was entered when `sp_adddistpublisher` was run at the distributor for the publisher.</span></span> <span data-ttu-id="7ad64-123">Однако если на удаленном издателе имеются существующие публикации из другой базы данных публикации, использующие указанную базу данных распространителя, то выполнять такое изменение не следует.</span><span class="sxs-lookup"><span data-stu-id="7ad64-123">However, if the remote publisher has existing publications from another publishing database that make use of the identified distribution database, this change is not appropriate.</span></span> <span data-ttu-id="7ad64-124">Необходимо системно удалить репликацию, использующую именованную базу данных распространителя, а затем установить ее повторно с использованием базы данных распространителя первоначального издателя, чтобы стало возможным размещение на новом издателе.</span><span class="sxs-lookup"><span data-stu-id="7ad64-124">Replication using the named distribution database needs to be systematically removed and then reestablished using the original publisher's distribution database in order for the new publisher to function as a suitable host.</span></span>  
  
  
