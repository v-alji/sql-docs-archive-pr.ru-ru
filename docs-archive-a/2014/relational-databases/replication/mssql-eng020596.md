---
title: MSSQL_ENG020596 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020596 error
ms.assetid: fa33627c-2e99-4be3-9424-52ab83446e07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b1c61f3683442e0d474ff36a65c89446dbd7bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668800"
---
# <a name="mssql_eng020596"></a><span data-ttu-id="b4b7b-102">MSSQL_ENG020596</span><span class="sxs-lookup"><span data-stu-id="b4b7b-102">MSSQL_ENG020596</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b4b7b-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="b4b7b-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4b7b-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b4b7b-104">Product Name</span></span>|<span data-ttu-id="b4b7b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4b7b-105">SQL Server</span></span>|  
|<span data-ttu-id="b4b7b-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b4b7b-106">Event ID</span></span>|<span data-ttu-id="b4b7b-107">20596</span><span class="sxs-lookup"><span data-stu-id="b4b7b-107">20596</span></span>|  
|<span data-ttu-id="b4b7b-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b4b7b-108">Event Source</span></span>|<span data-ttu-id="b4b7b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b4b7b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b4b7b-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b4b7b-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b4b7b-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b4b7b-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b4b7b-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b4b7b-112">Message Text</span></span>|<span data-ttu-id="b4b7b-113">Только '%s' или члены роли db_owner могут удалить анонимный агент.</span><span class="sxs-lookup"><span data-stu-id="b4b7b-113">Only '%s' or members of db_owner can drop the anonymous agent.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b4b7b-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b4b7b-114">Explanation</span></span>  
 <span data-ttu-id="b4b7b-115">У вас нет необходимых разрешений на удаление агента для анонимной подписки.</span><span class="sxs-lookup"><span data-stu-id="b4b7b-115">You do not have sufficient permissions to drop the agent for the anonymous subscription.</span></span> <span data-ttu-id="b4b7b-116">Имя входа, используемое при вызове [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql), должно принадлежать члену предопределенной роли сервера **sysadmin** на распространителе, или предопределенной роли базы данных **db_owner** в базе данных распространителя, или пользователю, который выполнял первый запуск этого агента.</span><span class="sxs-lookup"><span data-stu-id="b4b7b-116">The login used when calling [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) must be a member of the **sysadmin** fixed server role at the Distributor or **db_owner** fixed database role in the distribution database, or the user must be the one that initiated the first run of the agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b4b7b-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b4b7b-117">User Action</span></span>  
 <span data-ttu-id="b4b7b-118">Войдите в систему с соответствующими учетными данными и выполните **sp_dropanonymousagent**.</span><span class="sxs-lookup"><span data-stu-id="b4b7b-118">Login with the appropriate credentials, and execute **sp_dropanonymousagent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b7b-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4b7b-119">See Also</span></span>  
 [<span data-ttu-id="b4b7b-120">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="b4b7b-120">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
