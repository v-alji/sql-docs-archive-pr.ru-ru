---
title: MSSQLSERVER_3169 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "3169"
helpviewer_keywords:
- 3169 (Database Engine error)
ms.assetid: 7d4dbed6-bb94-4908-bc03-2040a9cf63bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b13d9c1c17eddb34648bc4a536e2fccf371b99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664241"
---
# <a name="mssqlserver_3169"></a><span data-ttu-id="78dfe-102">MSSQLSERVER_3169</span><span class="sxs-lookup"><span data-stu-id="78dfe-102">MSSQLSERVER_3169</span></span>
    
## <a name="details"></a><span data-ttu-id="78dfe-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="78dfe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78dfe-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="78dfe-104">Product Name</span></span>|<span data-ttu-id="78dfe-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="78dfe-105">SQL Server</span></span>|  
|<span data-ttu-id="78dfe-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="78dfe-106">Event ID</span></span>|<span data-ttu-id="78dfe-107">3169</span><span class="sxs-lookup"><span data-stu-id="78dfe-107">3169</span></span>|  
|<span data-ttu-id="78dfe-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="78dfe-108">Event Source</span></span>|<span data-ttu-id="78dfe-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="78dfe-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="78dfe-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="78dfe-110">Component</span></span>|<span data-ttu-id="78dfe-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="78dfe-111">SQLEngine</span></span>|  
|<span data-ttu-id="78dfe-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="78dfe-112">Symbolic Name</span></span>|<span data-ttu-id="78dfe-113">Н/Д</span><span class="sxs-lookup"><span data-stu-id="78dfe-113">NA</span></span>|  
|<span data-ttu-id="78dfe-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="78dfe-114">Message Text</span></span>|<span data-ttu-id="78dfe-115">Резервная копия базы данных создана на сервере, на котором выполняется версия %ls.</span><span class="sxs-lookup"><span data-stu-id="78dfe-115">The database was backed up on a server running version %ls.</span></span> <span data-ttu-id="78dfe-116">Эта версия несовместима с данным сервером, на котором работает версия %ls.</span><span class="sxs-lookup"><span data-stu-id="78dfe-116">That version is incompatible with this server, which is running version %ls.</span></span> <span data-ttu-id="78dfe-117">Необходимо восстановить базу данных на сервере, который поддерживает эту резервную копию, либо использовать резервную копию, совместимую с данным сервером.</span><span class="sxs-lookup"><span data-stu-id="78dfe-117">Either restore the database on a server that supports the backup, or use a backup that is compatible with this server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="78dfe-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="78dfe-118">Explanation</span></span>  
 <span data-ttu-id="78dfe-119">Некоторые особенности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] влияют на структуру файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="78dfe-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="78dfe-120">При восстановлении базы данных на другом экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файл форматирования может оказаться несовместимым с другой версией компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78dfe-120">When you restore a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="78dfe-121">Например, эта ошибка может возникнуть при использовании формата хранения vardecimal в более поздней версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с последующей попыткой восстановить файлы базы данных в более ранней версии, чем [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 2 (SP2).</span><span class="sxs-lookup"><span data-stu-id="78dfe-121">For example, this error can be caused by using the vardecimalstorage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to restore the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="78dfe-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="78dfe-122">User Action</span></span>  
 <span data-ttu-id="78dfe-123">Определите версию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], запущенную на исходном сервере.</span><span class="sxs-lookup"><span data-stu-id="78dfe-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="78dfe-124">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] либо щелкните правой кнопкой мыши сервер, а затем выберите пункт **свойства** или введите `SELECT @@VERSION` в окне запроса.</span><span class="sxs-lookup"><span data-stu-id="78dfe-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="78dfe-125">Откройте базу данных с помощью исходной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78dfe-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="78dfe-126">Изучите функции, которые включены в исходной базе данных экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78dfe-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="78dfe-127">Измените параметры для работы с версией [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], в которой будет выполняться восстановление базы данных.</span><span class="sxs-lookup"><span data-stu-id="78dfe-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be restored.</span></span>  
  
  
