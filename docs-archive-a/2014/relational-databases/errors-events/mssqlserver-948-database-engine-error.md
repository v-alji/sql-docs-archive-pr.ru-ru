---
title: MSSQLSERVER_948 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "948"
helpviewer_keywords:
- 948 (Database Engine error)
ms.assetid: 95c4ad45-a518-4165-a5c4-6e6b932b0570
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8461069a3fceb7bdca318b82a522f7f51af83d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658750"
---
# <a name="mssqlserver_948"></a><span data-ttu-id="c9037-102">MSSQLSERVER_948</span><span class="sxs-lookup"><span data-stu-id="c9037-102">MSSQLSERVER_948</span></span>
    
## <a name="details"></a><span data-ttu-id="c9037-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="c9037-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9037-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c9037-104">Product Name</span></span>|<span data-ttu-id="c9037-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9037-105">SQL Server</span></span>|  
|<span data-ttu-id="c9037-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c9037-106">Event ID</span></span>|<span data-ttu-id="c9037-107">948</span><span class="sxs-lookup"><span data-stu-id="c9037-107">948</span></span>|  
|<span data-ttu-id="c9037-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c9037-108">Event Source</span></span>|<span data-ttu-id="c9037-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c9037-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c9037-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c9037-110">Component</span></span>|<span data-ttu-id="c9037-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c9037-111">SQLEngine</span></span>|  
|<span data-ttu-id="c9037-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c9037-112">Symbolic Name</span></span>|<span data-ttu-id="c9037-113">Н/Д</span><span class="sxs-lookup"><span data-stu-id="c9037-113">NA</span></span>|  
|<span data-ttu-id="c9037-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c9037-114">Message Text</span></span>|<span data-ttu-id="c9037-115">Не удалось открыть базу данных «%.\*ls», поскольку она имеет версию %d.</span><span class="sxs-lookup"><span data-stu-id="c9037-115">The database '%.\*ls' cannot be opened because it is version %d.</span></span> <span data-ttu-id="c9037-116">Данный сервер поддерживает версию %d и более ранние.</span><span class="sxs-lookup"><span data-stu-id="c9037-116">This server supports version %d and earlier.</span></span> <span data-ttu-id="c9037-117">Переход на предыдущую версию не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c9037-117">A downgrade path is not supported.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9037-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c9037-118">Explanation</span></span>  
 <span data-ttu-id="c9037-119">Некоторые особенности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] влияют на структуру файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="c9037-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="c9037-120">При добавлении базы данных на другой экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файл форматирования может оказаться несовместимым с другой версией компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9037-120">When you attach a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="c9037-121">Например, эта ошибка может возникнуть при использовании формата хранения vardecimal в более поздней версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и при последующей попытке добавить файлы базы данных в версию более раннюю, чем [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] с пакетом обновления 2 (SP2).</span><span class="sxs-lookup"><span data-stu-id="c9037-121">For example, this error can be caused by using the vardecimal storage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to attach the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9037-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c9037-122">User Action</span></span>  
 <span data-ttu-id="c9037-123">Определите версию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], запущенную на исходном сервере.</span><span class="sxs-lookup"><span data-stu-id="c9037-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="c9037-124">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] либо щелкните правой кнопкой мыши сервер, а затем выберите пункт **свойства** или введите `SELECT @@VERSION` в окне запроса.</span><span class="sxs-lookup"><span data-stu-id="c9037-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="c9037-125">Откройте базу данных с помощью исходной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9037-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c9037-126">Изучите функции, которые включены в исходной базе данных экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9037-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c9037-127">Измените параметры для работы с версией [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], в которой будет выполняться добавление базы данных.</span><span class="sxs-lookup"><span data-stu-id="c9037-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be attached.</span></span>  
  
  
