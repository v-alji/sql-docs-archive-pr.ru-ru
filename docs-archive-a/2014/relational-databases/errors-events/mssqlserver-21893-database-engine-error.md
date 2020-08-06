---
title: MSSQLSERVER_21893 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21893 (Database Engine error)
ms.assetid: 1ab1195a-fe2a-4e06-b871-b177b6bea1fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 92479d7727ac2300d6a60d02492667d99a69b022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666655"
---
# <a name="mssqlserver_21893"></a><span data-ttu-id="55716-102">MSSQLSERVER_21893</span><span class="sxs-lookup"><span data-stu-id="55716-102">MSSQLSERVER_21893</span></span>
    
## <a name="details"></a><span data-ttu-id="55716-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="55716-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55716-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="55716-104">Product Name</span></span>|<span data-ttu-id="55716-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="55716-105">SQL Server</span></span>|  
|<span data-ttu-id="55716-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="55716-106">Event ID</span></span>|<span data-ttu-id="55716-107">21893</span><span class="sxs-lookup"><span data-stu-id="55716-107">21893</span></span>|  
|<span data-ttu-id="55716-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="55716-108">Event Source</span></span>|<span data-ttu-id="55716-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="55716-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="55716-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="55716-110">Component</span></span>|<span data-ttu-id="55716-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="55716-111">SQLEngine</span></span>|  
|<span data-ttu-id="55716-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="55716-112">Symbolic Name</span></span>|<span data-ttu-id="55716-113">SQLErrorNum21893</span><span class="sxs-lookup"><span data-stu-id="55716-113">SQLErrorNum21893</span></span>|  
|<span data-ttu-id="55716-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="55716-114">Message Text</span></span>|<span data-ttu-id="55716-115">Подписчики ( %s ) исходного издателя «%s» не отображаются как удаленные серверы на перенаправленном издателе «%s».</span><span class="sxs-lookup"><span data-stu-id="55716-115">The subscribers ( %s ) of original publisher '%s' do not appear as remote servers at redirected publisher '%s'.</span></span> <span data-ttu-id="55716-116">Запустите `sp_addlinkedserver` на перенаправленном издателе, чтобы добавить этих подписчиков в качестве удаленных серверов.</span><span class="sxs-lookup"><span data-stu-id="55716-116">Run `sp_addlinkedserver` at the redirected publisher to add these subscribers as remote servers .</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="55716-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="55716-117">Explanation</span></span>  
 <span data-ttu-id="55716-118">`sp_validate_redirected_publisher` использует таблицы метаданных подписки в базе данных издателя на удаленном сервере для определения связанных подписчиков, а также проверяет наличие связанных записей в таблице master.dbo.sysservers для подписчиков.</span><span class="sxs-lookup"><span data-stu-id="55716-118">`sp_validate_redirected_publisher` uses the subscription metadata tables of the publisher database at the remote server to identify its associated subscribers and verifies that there are associated entries in master.dbo.sysservers for the subscribers.</span></span> <span data-ttu-id="55716-119">Эта ошибка возвращается, если отсутствует какой-либо из идентифицированных подписчиков.</span><span class="sxs-lookup"><span data-stu-id="55716-119">This error is returned if any of the identified subscribers are not present.</span></span>  
  
 <span data-ttu-id="55716-120">Эта ошибка не считается неустранимой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="55716-120">This error is not considered a fatal error.</span></span> <span data-ttu-id="55716-121">Агенты, на которых возникает эта ошибка, регистрируют в журнале информацию об ошибке, но не прерывают работу, так как невозможность найти соответствующие записи подписчиков на новом издателе не оказывает серьезного влияния на репликацию.</span><span class="sxs-lookup"><span data-stu-id="55716-121">Agents encountering this error will log the error as informational but will not terminate, since a failure to have appropriate subscriber entries at the new publisher has limited impact on replication.</span></span> <span data-ttu-id="55716-122">Если для подписчика нет соответствующей записи в sysservers, некоторые операции по управлению подпиской могут завершаться ошибкой при вызове через [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55716-122">Without an appropriate entry for a subscriber in sysservers, some subscription management activities may fail when executed through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="55716-123">Однако те же операции можно успешно выполнять путем явного вызова хранимых процедур управления.</span><span class="sxs-lookup"><span data-stu-id="55716-123">However, these same activities can be successfully performed by executing the management stored procedures explicitly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55716-124">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="55716-124">User Action</span></span>  
 <span data-ttu-id="55716-125">Запустите `sp_addlinkedserver` на перенаправленном издателе для каждого из обнаруженных подписчиков, чтобы добавить их в качестве удаленных серверов.</span><span class="sxs-lookup"><span data-stu-id="55716-125">Run `sp_addlinkedserver` at the redirected publisher for each of the identified subscribers to add them as remote servers.</span></span> <span data-ttu-id="55716-126">Затем запустите `sp_serveroption`, чтобы установить бит подписчика для сервера.</span><span class="sxs-lookup"><span data-stu-id="55716-126">Then, run `sp_serveroption` to set the subscriber bit for the server.</span></span>  
  
  
