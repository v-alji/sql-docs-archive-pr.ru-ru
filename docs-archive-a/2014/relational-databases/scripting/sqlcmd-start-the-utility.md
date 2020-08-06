---
title: Запуск программу sqlcmd
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 00d57437-7a29-4da1-b639-ee990db055fb
author: rothja
ms.author: jroth
ms.openlocfilehash: d71e6f140238599b3f22850ee9b63a0ee25d900b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656291"
---
# <a name="start-the-sqlcmd-utility"></a><span data-ttu-id="3760f-102">Запуск программу sqlcmd</span><span class="sxs-lookup"><span data-stu-id="3760f-102">Start the sqlcmd Utility</span></span>
  <span data-ttu-id="3760f-103">Чтобы начать использовать программу `sqlcmd`, требуется запустить ее и подключиться к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3760f-103">To begin using `sqlcmd`, you must first launch the utility and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3760f-104">Можно соединиться или с экземпляром, установленным по умолчанию, или с именованным экземпляром.</span><span class="sxs-lookup"><span data-stu-id="3760f-104">You can connect to either a default or named instance.</span></span> <span data-ttu-id="3760f-105">Первый шаг — запуск программы `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="3760f-105">The first step is to start the `sqlcmd` utility.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3760f-106">По умолчанию в программе `sqlcmd` используется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="3760f-106">Windows Authentication is the default authentication mode for `sqlcmd`.</span></span> <span data-ttu-id="3760f-107">Для использования проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] требуется указать имя пользователя и пароль, применяя параметры **-U** и **-P** .</span><span class="sxs-lookup"><span data-stu-id="3760f-107">To use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must specify a user name and password by using the **-U** and **-P** options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3760f-108">По умолчанию [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] устанавливается как именованный экземпляр с именем **sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="3760f-108">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as the named instance **sqlexpress**.</span></span>  
  
 <span data-ttu-id="3760f-109">Если подключение к этому экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] не было выполнено, то, возможно, потребуется настроить [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на прием соединений.</span><span class="sxs-lookup"><span data-stu-id="3760f-109">If you have not connected to this instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] before, you may have to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-default-instance-of-sql-server"></a><span data-ttu-id="3760f-110">Запуск программы «sqlcmd» и подключение к экземпляру SQL Server по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3760f-110">To start the sqlcmd utility and connect to a default instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="3760f-111">В меню **Пуск** выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3760f-111">On the **Start** menu click **Run**.</span></span> <span data-ttu-id="3760f-112">В поле **Открыть** введите **cmd**, а затем нажмите кнопку **ОК** , чтобы открыть окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="3760f-112">In the **Open** box type **cmd**, and then click **OK** to open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="3760f-113">В командной строке введите `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="3760f-113">At the command prompt, type `sqlcmd`.</span></span>  
  
3.  <span data-ttu-id="3760f-114">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="3760f-114">Press ENTER.</span></span>  
  
     <span data-ttu-id="3760f-115">Теперь установлено доверительное соединение с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию, запущенным на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="3760f-115">You now have a trusted connection to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on your computer.</span></span>  
  
     <span data-ttu-id="3760f-116">**1>** — это `sqlcmd` запрос, указывающий номер строки.</span><span class="sxs-lookup"><span data-stu-id="3760f-116">**1>** is the `sqlcmd` prompt that specifies the line number.</span></span> <span data-ttu-id="3760f-117">При каждом нажатии клавиши ВВОД номер увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="3760f-117">Each time you press ENTER, the number increases by one.</span></span>  
  
4.  <span data-ttu-id="3760f-118">Чтобы завершить `sqlcmd` сеанс, введите `EXIT` в `sqlcmd` командной строке.</span><span class="sxs-lookup"><span data-stu-id="3760f-118">To end the `sqlcmd` session, type `EXIT` at the `sqlcmd` prompt.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-named-instance-of-sql-server"></a><span data-ttu-id="3760f-119">Запуск программы sqlcmd и соединение с именованным экземпляром SQL Server</span><span class="sxs-lookup"><span data-stu-id="3760f-119">To start the sqlcmd utility and connect to a named instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="3760f-120">Откройте окно командной строки и введите `sqlcmd -S` *myServer\instanceName*.</span><span class="sxs-lookup"><span data-stu-id="3760f-120">Open a Command Prompt window, and type `sqlcmd -S`*myServer\instanceName*.</span></span> <span data-ttu-id="3760f-121">Замените *мойСервер\имяЭкземпляра* именем компьютера и экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , с которым нужно соединиться.</span><span class="sxs-lookup"><span data-stu-id="3760f-121">Replace *myServer\instanceName* with the name of the computer and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to.</span></span>  
  
2.  <span data-ttu-id="3760f-122">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="3760f-122">Press ENTER.</span></span>  
  
     <span data-ttu-id="3760f-123">`sqlcmd`Приглашение (1>) указывает, что вы подключены к указанному экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3760f-123">The `sqlcmd` prompt (1>) indicates that you are connected to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3760f-124">Введенные инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] хранятся в буфере.</span><span class="sxs-lookup"><span data-stu-id="3760f-124">Entered [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are stored in a buffer.</span></span> <span data-ttu-id="3760f-125">Они выполняются как пакет при обнаружении команды GO.</span><span class="sxs-lookup"><span data-stu-id="3760f-125">They are executed as a batch when the GO command is encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3760f-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="3760f-126">See Also</span></span>  
 [<span data-ttu-id="3760f-127">Выполнение файлов скрипта Transact-SQL с использованием программы sqlcmd</span><span class="sxs-lookup"><span data-stu-id="3760f-127">Run Transact-SQL Script Files Using sqlcmd</span></span>](sqlcmd-run-transact-sql-script-files.md)  
  
  
