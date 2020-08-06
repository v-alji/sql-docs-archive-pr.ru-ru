---
title: LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c178a308-8d99-47fc-8a49-5a480dc592f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 32ae8ebe102008d08a6059328ed57cd118ece019
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668349"
---
# <a name="localdb_error_instance_folder_path_too_long"></a><span data-ttu-id="62270-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="62270-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>
    
## <a name="details"></a><span data-ttu-id="62270-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="62270-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62270-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="62270-104">Product Name</span></span>|<span data-ttu-id="62270-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="62270-105">SQL Server</span></span>|  
|<span data-ttu-id="62270-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="62270-106">Event ID</span></span>|<span data-ttu-id="62270-107">260</span><span class="sxs-lookup"><span data-stu-id="62270-107">260</span></span>|  
|<span data-ttu-id="62270-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="62270-108">Event Source</span></span>|<span data-ttu-id="62270-109">Среда выполнения локальной базы данных SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="62270-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="62270-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="62270-110">Component</span></span>|<span data-ttu-id="62270-111">API среды выполнения локальной базы данных</span><span class="sxs-lookup"><span data-stu-id="62270-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="62270-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="62270-112">Message Text</span></span>|<span data-ttu-id="62270-113">Длина полного пути к папке экземпляра локальной базы данных превышает MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="62270-113">The full path length of the Local Database instance folder is longer than MAX_PATH.</span></span> <span data-ttu-id="62270-114">Экземпляр должен храниться в папке:%% LOCALAPPDATA%% \ Microsoft\Microsoft SQL Server локальное \\ имя экземпляра дб\инстанцес<\> .</span><span class="sxs-lookup"><span data-stu-id="62270-114">The instance must be stored in folder: %%LOCALAPPDATA%%\Microsoft\Microsoft SQL Server Local DB\Instances\\<instance name\>.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="62270-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="62270-115">Explanation</span></span>  
 <span data-ttu-id="62270-116">Длина пути к месту хранения экземпляра больше MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="62270-116">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="62270-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="62270-117">User Action</span></span>  
 <span data-ttu-id="62270-118">Создайте новый путь, длина которого меньше MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="62270-118">Create a new path that is shorter than MAX_PATH.</span></span>  
  
  
