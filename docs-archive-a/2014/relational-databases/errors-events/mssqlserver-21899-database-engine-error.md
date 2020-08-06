---
title: MSSQLSERVER_21899 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21899 (Database Engine error)
ms.assetid: 32b87a7c-5380-4638-b147-dd78618f6625
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb1af04b56685d0e1b5a703b812d08d88909b693
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731641"
---
# <a name="mssqlserver_21899"></a><span data-ttu-id="1586c-102">MSSQLSERVER_21899</span><span class="sxs-lookup"><span data-stu-id="1586c-102">MSSQLSERVER_21899</span></span>
    
## <a name="details"></a><span data-ttu-id="1586c-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1586c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1586c-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1586c-104">Product Name</span></span>|<span data-ttu-id="1586c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1586c-105">SQL Server</span></span>|  
|<span data-ttu-id="1586c-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1586c-106">Event ID</span></span>|<span data-ttu-id="1586c-107">21899</span><span class="sxs-lookup"><span data-stu-id="1586c-107">21899</span></span>|  
|<span data-ttu-id="1586c-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1586c-108">Event Source</span></span>|<span data-ttu-id="1586c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1586c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1586c-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1586c-110">Component</span></span>|<span data-ttu-id="1586c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1586c-111">SQLEngine</span></span>|  
|<span data-ttu-id="1586c-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1586c-112">Symbolic Name</span></span>|<span data-ttu-id="1586c-113">SQLErrorNum21899</span><span class="sxs-lookup"><span data-stu-id="1586c-113">SQLErrorNum21899</span></span>|  
|<span data-ttu-id="1586c-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1586c-114">Message Text</span></span>|<span data-ttu-id="1586c-115">Запрос на перенаправленном издателе "%s", для определения того, имеются ли на нем записи sysserver для подписчиков исходного издателя "%s", завершился с ошибкой "%d"; сообщение об ошибке: "%s".</span><span class="sxs-lookup"><span data-stu-id="1586c-115">The query at the redirected publisher '%s' to determine whether there were sysserver entries for the subscribers of the original publisher '%s' failed with error '%d', error message '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1586c-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1586c-116">Explanation</span></span>  
 <span data-ttu-id="1586c-117">`sp_validate_redirected_publisher` запрашивает таблицы метаданных подписки в базе данных издателя на удаленном сервере, чтобы определить связанных с ним подписчиков.</span><span class="sxs-lookup"><span data-stu-id="1586c-117">`sp_validate_redirected_publisher` queries the subscription metadata tables of the publisher database at the remote server to determine its associated subscribers.</span></span> <span data-ttu-id="1586c-118">Если выполнить этот запрос не удается, возвращается ошибка 21899.</span><span class="sxs-lookup"><span data-stu-id="1586c-118">Error 21899 is returned if this query fails.</span></span> <span data-ttu-id="1586c-119">Запросу проверки необходим доступ к опубликованной базе данных на перенаправленном издателе.</span><span class="sxs-lookup"><span data-stu-id="1586c-119">The validation query requires access to the published database at the redirected publisher.</span></span> <span data-ttu-id="1586c-120">Если имя входа, указанное при вызове хранимой процедуры `sp_adddistpublisher` для первоначального издателя, не имеет прав на доступ к опубликованной базе данных на перенаправленном издателе, возвращается ошибка 21899.</span><span class="sxs-lookup"><span data-stu-id="1586c-120">If the login specified when `sp_adddistpublisher` is called for the original publisher is not authorized to access the published database at the redirected publisher, error 21899 is returned.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1586c-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1586c-121">User Action</span></span>  
 <span data-ttu-id="1586c-122">Просмотрите приведенное сообщение об ошибке, чтобы определить причину ошибки и предпринять соответствующие действия по ее исправлению</span><span class="sxs-lookup"><span data-stu-id="1586c-122">Review the cited error message to determine the cause of the failure and take appropriate corrective action</span></span>  
  
  
