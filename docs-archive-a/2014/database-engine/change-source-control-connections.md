---
title: Изменить подключения системы управления версиями | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server Management Studio], source controls
- source controls [SQL Server Management Studio], connections
ms.assetid: 538e3beb-f99c-4095-bd65-6413e872d26e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 077a09cdca0c0aff777184f04467ca39592690aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665587"
---
# <a name="change-source-control-connections"></a><span data-ttu-id="0d04b-102">Изменение соединений с системой управления версиями</span><span class="sxs-lookup"><span data-stu-id="0d04b-102">Change Source Control Connections</span></span>
  <span data-ttu-id="0d04b-103">При первом добавлении или открытии решения в системе управления версиями поставщик этой системы создает связь между корневой папкой локального каталога решения и соответствующей папкой на сервере.</span><span class="sxs-lookup"><span data-stu-id="0d04b-103">The first time you add or open a solution from source control, your source control provider creates an association between the root folder of the local solution directory and its corresponding server folder.</span></span>  
  
 <span data-ttu-id="0d04b-104">Корневая папка (называется также унифицированным корнем) находится на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="0d04b-104">The root folder (also called unified root) resides on the client.</span></span> <span data-ttu-id="0d04b-105">Эта папка содержит все файлы, входящие в решение или проект.</span><span class="sxs-lookup"><span data-stu-id="0d04b-105">It is the folder beneath which all the files referenced by a solution or project can be found.</span></span> <span data-ttu-id="0d04b-106">Чтобы найти последнюю версию решения, его журнал и данные о состоянии, найдите серверную папку, расположенную на сервере управления версиями.</span><span class="sxs-lookup"><span data-stu-id="0d04b-106">To find the latest version of a solution, its history, and its status information, locate the server folder, which resides on the source control server.</span></span> <span data-ttu-id="0d04b-107">В [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe серверные папки называются проектами.</span><span class="sxs-lookup"><span data-stu-id="0d04b-107">In [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, server folders are called projects.</span></span>  
  
 <span data-ttu-id="0d04b-108">Во многих ситуациях требуется отменить привязку или отключить решение от его серверной папки.</span><span class="sxs-lookup"><span data-stu-id="0d04b-108">In many situations, you need to unbind or disconnect a solution from its server folder.</span></span> <span data-ttu-id="0d04b-109">Например, если компьютер, на котором находится поставщик управления версиями, недоступен, можно подключиться к резервному компьютеру, повторно привязать решение, подключив его к папке на резервном сервере и продолжить работу в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="0d04b-109">For example, if the computer on which your source control provider resides is unavailable, you can connect to a backup computer, rebind your solution to a backed-up server folder, and resume working normally.</span></span> <span data-ttu-id="0d04b-110">Также, если проект с управляемыми источниками разветвлен, может потребоваться связать решение с серверной папкой, в которой находится новая версия проекта.</span><span class="sxs-lookup"><span data-stu-id="0d04b-110">Also, if a source control project is forked, you may have to bind your solution to the server folder where the new project version resides.</span></span>  
  
 <span data-ttu-id="0d04b-111">С помощью пользовательского интерфейса поставщика управления версиями можно изменить серверную папку, к которой привязано решение.</span><span class="sxs-lookup"><span data-stu-id="0d04b-111">Use the user interface of the source control provider to change the server folder that a solution is bound to.</span></span> <span data-ttu-id="0d04b-112">Пользовательский интерфейс системы управления версиями можно открыть непосредственно из среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d04b-112">You can open the source control user interface from within the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span>  
  
#### <a name="to-open-the-source-control-user-interface-from-the-studio-environment"></a><span data-ttu-id="0d04b-113">Открытие пользовательского интерфейса системы управления версиями из среды Studio</span><span class="sxs-lookup"><span data-stu-id="0d04b-113">To open the source control user interface from the Studio environment</span></span>  
  
1.  <span data-ttu-id="0d04b-114">В меню **файл** укажите пункт **система управления версиями**, а затем выберите пункт **запустить Microsoft Visual SourceSafe**.</span><span class="sxs-lookup"><span data-stu-id="0d04b-114">On the **File** menu, point to **Source Control**, and then click **Launch Microsoft Visual SourceSafe**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d04b-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d04b-115">See Also</span></span>  
 <span data-ttu-id="0d04b-116">[Основы системы управления версиями](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="0d04b-116">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="0d04b-117">[Задание параметров системы управления версиями](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="0d04b-117">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="0d04b-118">Исключить файлы из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="0d04b-118">Exclude Files from Source Control</span></span>](../../2014/database-engine/exclude-files-from-source-control.md)  
  
  
