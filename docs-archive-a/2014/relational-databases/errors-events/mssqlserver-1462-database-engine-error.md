---
title: MSSQLSERVER_1462 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1462 (Database Engine error)
ms.assetid: 680e9c1c-a9d6-4765-b601-956d0a83324c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 704b847bde2d7b4da9da91b4b24bfe2b9e2afa07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667167"
---
# <a name="mssqlserver_1462"></a><span data-ttu-id="27566-102">MSSQLSERVER_1462</span><span class="sxs-lookup"><span data-stu-id="27566-102">MSSQLSERVER_1462</span></span>
    
## <a name="details"></a><span data-ttu-id="27566-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="27566-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="27566-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="27566-104">Product Name</span></span>|<span data-ttu-id="27566-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="27566-105">SQL Server</span></span>|  
|<span data-ttu-id="27566-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="27566-106">Event ID</span></span>|<span data-ttu-id="27566-107">1462</span><span class="sxs-lookup"><span data-stu-id="27566-107">1462</span></span>|  
|<span data-ttu-id="27566-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="27566-108">Event Source</span></span>|<span data-ttu-id="27566-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="27566-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="27566-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="27566-110">Component</span></span>|<span data-ttu-id="27566-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="27566-111">SQLEngine</span></span>|  
|<span data-ttu-id="27566-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="27566-112">Symbolic Name</span></span>|<span data-ttu-id="27566-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span><span class="sxs-lookup"><span data-stu-id="27566-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span></span>|  
|<span data-ttu-id="27566-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="27566-114">Message Text</span></span>|<span data-ttu-id="27566-115">Зеркальное отображение базы данных отключено вследствие ошибки в ходе операции повторного выполнения.</span><span class="sxs-lookup"><span data-stu-id="27566-115">Database mirroring is disabled due to a failed redo operation.</span></span> <span data-ttu-id="27566-116">Не удалось возобновить операцию.</span><span class="sxs-lookup"><span data-stu-id="27566-116">Unable to resume.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="27566-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="27566-117">Explanation</span></span>  
 <span data-ttu-id="27566-118">Операции зеркального отображения базы данных не удалось повторить запись журнала на зеркальном сервере.</span><span class="sxs-lookup"><span data-stu-id="27566-118">Database mirroring failed to redo a log record on the mirror.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="27566-119">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="27566-119">Possible Causes</span></span>  
 <span data-ttu-id="27566-120">Наиболее вероятная причина заключается в том, что операция добавления файла была выполнена в основной базе данных, но завершилась неуспешно в зеркальной базе данных, так как имена файлов или структуры каталогов на основном и зеркальном серверах отличаются.</span><span class="sxs-lookup"><span data-stu-id="27566-120">The most likely cause is that an add-file operation completed on the principal database but then failed on the mirror database because file names or directory structures differ on the principal server and mirror server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="27566-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="27566-121">User Action</span></span>  
 <span data-ttu-id="27566-122">Просмотрите журнал ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и попытайтесь найти причину этой ошибки.</span><span class="sxs-lookup"><span data-stu-id="27566-122">Look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the cause of this error.</span></span> <span data-ttu-id="27566-123">Попробуйте устранить причину неполадки и возобновите зеркальное отображение базы данных.</span><span class="sxs-lookup"><span data-stu-id="27566-123">Try to resolve the cause and resume mirroring on the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27566-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="27566-124">See Also</span></span>  
 [<span data-ttu-id="27566-125">Диагностика конфигурации зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="27566-125">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
