---
title: Занятие 2. Подготовка папки моментальных снимков | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f286cde9-c0d0-43ef-b7ba-53c3cbb8906c
author: rothja
ms.author: jroth
ms.openlocfilehash: 5d98c7433d0bd50504f20f7f576fcf0b20154c81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739710"
---
# <a name="lesson-2-preparing-the-snapshot-folder"></a><span data-ttu-id="44909-102">Занятие 2. Подготовка папки моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="44909-102">Lesson 2: Preparing the Snapshot Folder</span></span>
  <span data-ttu-id="44909-103">На этом занятии можно научиться настраивать папку моментальных снимков для создания и хранения моментального снимка публикации.</span><span class="sxs-lookup"><span data-stu-id="44909-103">In this lesson, you will learn to configure the snapshot folder that is used to create and store the publication snapshot.</span></span>  
  
### <a name="to-create-a-share-for-the-snapshot-folder-and-assign-permissions"></a><span data-ttu-id="44909-104">Создание ресурса для папки моментальных снимков и настройка разрешений</span><span class="sxs-lookup"><span data-stu-id="44909-104">To create a share for the snapshot folder and assign permissions</span></span>  
  
1.  <span data-ttu-id="44909-105">В проводнике Windows перейдите к папке данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="44909-105">In Windows Explorer, navigate to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data folder.</span></span> <span data-ttu-id="44909-106">Путь по умолчанию — «C:\Program Files\Microsoft SQL Server\MSSQL.X\MSSQL\Data».</span><span class="sxs-lookup"><span data-stu-id="44909-106">The default location is C:\Program Files\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="44909-107">Создайте папку с именем **repldata**.</span><span class="sxs-lookup"><span data-stu-id="44909-107">Create a new folder named **repldata**.</span></span>  
  
3.  <span data-ttu-id="44909-108">Правой кнопкой мыши щелкните эту папку и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="44909-108">Right-click this folder and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="44909-109">В диалоговом окне **Свойства repldata** на вкладке **Общий доступ** щелкните **Открыть общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="44909-109">On the **Sharing** tab in the **repldata Properties** dialog box, click **Share**.</span></span>  
  
5.  <span data-ttu-id="44909-110">В диалоговом окне **Общий доступ к файлу** щелкните **Открыть общий доступ**, а затем — **Готово**.</span><span class="sxs-lookup"><span data-stu-id="44909-110">In the **File Sharing** dialog box, click **Share**, and then click **Done**.</span></span>  
  
6.  <span data-ttu-id="44909-111">На вкладке **Безопасность** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="44909-111">On the **Security** tab, click **Edit**.</span></span>  
  
7.  <span data-ttu-id="44909-112">В диалоговом окне **Разрешения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="44909-112">In the **Permissions** dialog box, click **Add.**</span></span> <span data-ttu-id="44909-113">В текстовом поле **выберите пользователя, компьютеры, учетная запись службы или группы** введите имя учетной записи агент моментальных снимков, созданной на занятии 1, как \<_Machine_Name> _**\ repl_snapshot**, где \<*Machine_Name> \* — имя издателя.</span><span class="sxs-lookup"><span data-stu-id="44909-113">In the **Select User, Computers, Service Account, or Groups** text box, type the name of the Snapshot Agent account created in Lesson 1, as \<_Machine_Name>_**\repl_snapshot**, where \<*Machine_Name>\* is the name of the Publisher.</span></span> <span data-ttu-id="44909-114">Щелкните **Проверить имена**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="44909-114">Click **Check Names**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="44909-115">Повторите предыдущий шаг, чтобы добавить разрешения для агент распространения, как \<_Machine_Name> _ **\ repl_distribution**, а также для агент слияния как \<_Machine_Name> _ **\ repl_merge**.</span><span class="sxs-lookup"><span data-stu-id="44909-115">Repeat the previous step to add permissions for the Distribution Agent, as \<_Machine_Name>_**\repl_distribution**, and for the Merge Agent as \<_Machine_Name>_**\repl_merge**.</span></span>  
  
9. <span data-ttu-id="44909-116">Убедитесь в том, что следующие разрешения допустимы:</span><span class="sxs-lookup"><span data-stu-id="44909-116">Verify the following permissions are allowed:</span></span>  
  
    -   <span data-ttu-id="44909-117">repl_snapshot — «Полный контроль»;</span><span class="sxs-lookup"><span data-stu-id="44909-117">repl_snapshot - Full Control</span></span>  
  
    -   <span data-ttu-id="44909-118">repl_distribution — «Чтение»;</span><span class="sxs-lookup"><span data-stu-id="44909-118">repl_distribution - Read</span></span>  
  
    -   <span data-ttu-id="44909-119">repl_merge — «Чтение».</span><span class="sxs-lookup"><span data-stu-id="44909-119">repl_merge - Read</span></span>  
  
10. <span data-ttu-id="44909-120">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Свойства repldata** , и создайте ресурс repldata.</span><span class="sxs-lookup"><span data-stu-id="44909-120">Click **OK** to close the **repldata Properties** dialog box and create the repldata share.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="44909-121">Next Steps</span><span class="sxs-lookup"><span data-stu-id="44909-121">Next Steps</span></span>  
 <span data-ttu-id="44909-122">Настройка ресурса папки моментальных снимков выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="44909-122">You have successfully configured the share for the snapshot folder.</span></span> <span data-ttu-id="44909-123">Далее предстоит настроить распространение.</span><span class="sxs-lookup"><span data-stu-id="44909-123">Next, you will configure distribution.</span></span> <span data-ttu-id="44909-124">См. [Занятие 3. Настройка распространения](lesson-3-configuring-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="44909-124">See [Lesson 3: Configuring Distribution](lesson-3-configuring-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44909-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="44909-125">See Also</span></span>  
 [<span data-ttu-id="44909-126">Защита папки моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="44909-126">Secure the Snapshot Folder</span></span>](security/secure-the-snapshot-folder.md)  
  
  
