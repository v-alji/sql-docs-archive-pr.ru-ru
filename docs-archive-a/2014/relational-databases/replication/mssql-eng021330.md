---
title: MSSQL_ENG021330 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021330 error
ms.assetid: e2bb2e21-62a7-4689-b68b-bdfba3fdd985
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4338756a641b23bfc6f52da6b3de296bb6415756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730502"
---
# <a name="mssql_eng021330"></a><span data-ttu-id="f3ecb-102">MSSQL_ENG021330</span><span class="sxs-lookup"><span data-stu-id="f3ecb-102">MSSQL_ENG021330</span></span>
    
## <a name="message-details"></a><span data-ttu-id="f3ecb-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="f3ecb-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3ecb-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="f3ecb-104">Product Name</span></span>|<span data-ttu-id="f3ecb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3ecb-105">SQL Server</span></span>|  
|<span data-ttu-id="f3ecb-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f3ecb-106">Event ID</span></span>|<span data-ttu-id="f3ecb-107">21330</span><span class="sxs-lookup"><span data-stu-id="f3ecb-107">21330</span></span>|  
|<span data-ttu-id="f3ecb-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="f3ecb-108">Event Source</span></span>|<span data-ttu-id="f3ecb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f3ecb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f3ecb-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="f3ecb-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="f3ecb-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="f3ecb-111">Symbolic Name</span></span>||  
|<span data-ttu-id="f3ecb-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="f3ecb-112">Message Text</span></span>|<span data-ttu-id="f3ecb-113">Не удалось создать вложенный каталог в рабочем каталоге репликации.(%ls)</span><span class="sxs-lookup"><span data-stu-id="f3ecb-113">Failed to create a sub-directory under the replication working directory.(%ls)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f3ecb-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="f3ecb-114">Explanation</span></span>  
 <span data-ttu-id="f3ecb-115">Эта ошибка может произойти при ручной инициализации подписки, существует ошибка при создании каталога, в котором хранятся скрипты репликации.</span><span class="sxs-lookup"><span data-stu-id="f3ecb-115">This error can occur when a subscription is initialized manually, and there is a problem creating the directory in which replication scripts are stored.</span></span> <span data-ttu-id="f3ecb-116">Ошибка может быть вызвана недостатком разрешений: если инициализация подписки выполняется без применения моментального снимка, то учетная запись, от имени которой выполняется служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на издателе, должна обладать разрешением на запись в папку моментальных снимков распространителя.</span><span class="sxs-lookup"><span data-stu-id="f3ecb-116">The error can be caused by a permissions issue: when a subscription is initialized without using a snapshot, the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher must have write permissions on the snapshot folder at the Distributor.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3ecb-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="f3ecb-117">User Action</span></span>  
 <span data-ttu-id="f3ecb-118">Проверьте правильность указанного пути к папке моментальных снимков, а также убедитесь, что учетная запись, под которой работает служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] издателя, обладает всеми необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="f3ecb-118">Ensure that the correct path has been specified for the snapshot folder and that the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher has sufficient permissions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ecb-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3ecb-119">See Also</span></span>  
 <span data-ttu-id="f3ecb-120">[Укажите расположение моментальных снимков по умолчанию](snapshot-options.md#snapshot-folder-locations) </span><span class="sxs-lookup"><span data-stu-id="f3ecb-120">[Specify the Default Snapshot Location](snapshot-options.md#snapshot-folder-locations) </span></span>  
 <span data-ttu-id="f3ecb-121">[Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="f3ecb-121">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="f3ecb-122">Инициализация транзакционной подписки без моментального снимка</span><span class="sxs-lookup"><span data-stu-id="f3ecb-122">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
