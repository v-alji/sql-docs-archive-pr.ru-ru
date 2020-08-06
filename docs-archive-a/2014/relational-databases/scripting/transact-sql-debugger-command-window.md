---
title: Окно команд
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Command Window [Transact-SQL]
ms.assetid: e567ebf9-0793-451b-92c7-26193a02d9da
author: rothja
ms.author: jroth
ms.openlocfilehash: c766ed5408de96b6a2305ce377f9031947618a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667671"
---
# <a name="command-window"></a><span data-ttu-id="497bd-102">Окно команд</span><span class="sxs-lookup"><span data-stu-id="497bd-102">Command Window</span></span>
  <span data-ttu-id="497bd-103">Окно **CommandWindow** используется для запуска таких команд, как команды отладки и изменения, для кода, отлаживаемого в настоящее время в окне редактора запросов компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="497bd-103">Use the **CommandWindow** to run commands, such as debug and edit commands, against the code in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor window that is currently being debugged.</span></span> <span data-ttu-id="497bd-104">Чтобы иметь возможность использовать **Окно команд**, необходимо находиться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="497bd-104">You must be in debug mode to use the **Command Window**.</span></span> <span data-ttu-id="497bd-105">Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] поддерживает многие из команд, которые также поддерживаются средой в окне [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Команда**.</span><span class="sxs-lookup"><span data-stu-id="497bd-105">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports many of the commands that are also supported in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Command** window.</span></span> <span data-ttu-id="497bd-106">Дополнительные сведения см. в разделе [Окно команд среды Visual Studio](https://go.microsoft.com/fwlink/?LinkId=112007).</span><span class="sxs-lookup"><span data-stu-id="497bd-106">For more information, see [Visual Studio Command Window](https://go.microsoft.com/fwlink/?LinkId=112007).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="497bd-107">Список задач</span><span class="sxs-lookup"><span data-stu-id="497bd-107">Task List</span></span>  
 <span data-ttu-id="497bd-108">**Доступ к окну команд**</span><span class="sxs-lookup"><span data-stu-id="497bd-108">**To access the Command Window**</span></span>  
  
-   <span data-ttu-id="497bd-109">В меню **Отладка** выберите команду **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="497bd-109">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
 <span data-ttu-id="497bd-110">**Вывод значения переменной**</span><span class="sxs-lookup"><span data-stu-id="497bd-110">**To print the value of a variable**</span></span>  
  
-   <span data-ttu-id="497bd-111">В поле **CommandWindow**введите \*\*Debug. Print \<VariableName> \*\*, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="497bd-111">In the **CommandWindow**, type **Debug.Print \<VariableName>**, and then press ENTER.</span></span>  
  
 <span data-ttu-id="497bd-112">**Получение сведений о текущем потоке**</span><span class="sxs-lookup"><span data-stu-id="497bd-112">**To list information about the current thread**</span></span>  
  
-   <span data-ttu-id="497bd-113">В поле **CommandWindow**введите `Debug.ListThread` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="497bd-113">In the **CommandWindow**, type `Debug.ListThread`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="497bd-114">**Добавление переменной в окно «Быстрая проверка»**</span><span class="sxs-lookup"><span data-stu-id="497bd-114">**To add a variable to the QuickWatch window**</span></span>  
  
-   <span data-ttu-id="497bd-115">В поле **CommandWindow**введите \*\*Debug. Быстрая проверка \<VariableName> \*\*, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="497bd-115">In the **CommandWindow**, type **Debug.QuickWatch \<VariableName>**, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="497bd-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="497bd-116">See Also</span></span>  
 [<span data-ttu-id="497bd-117">Отладчик Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="497bd-117">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
