---
title: Служебная программа SqlLocalDB | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- SqlLocalDB utility [SQL Server]
- local database runtime utility
- LocalDB, SqlLocalDB Utility
ms.assetid: d785cdb7-1ea0-4871-bde9-1ae7881190f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfb95cea4365d56c296d14fcc09046cd7eddc0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727557"
---
# <a name="sqllocaldb-utility"></a><span data-ttu-id="8f6e2-102">Программа SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="8f6e2-102">SqlLocalDB Utility</span></span>
  <span data-ttu-id="8f6e2-103">Используйте `SqlLocalDB` программу для создания экземпляра [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)] **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-103">Use the `SqlLocalDB` utility to create an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)]**LocalDB**.</span></span> <span data-ttu-id="8f6e2-104">`SqlLocalDB`Программа (SqlLocalDB.exe) — это простое средство командной строки, которое позволяет пользователям и разработчикам создавать и администрировать экземпляр [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-104">The `SqlLocalDB` utility (SqlLocalDB.exe) is a simple command line tool to enable users and developers to create and manage an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="8f6e2-105">Сведения об использовании **LocalDB**см. в разделе [SQL Server 2014 Express LocalDB](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span><span class="sxs-lookup"><span data-stu-id="8f6e2-105">For information about how to use **LocalDB**, see [SQL Server 2014 Express LocalDB](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f6e2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f6e2-106">Syntax</span></span>  
  
```  
SqlLocalDB.exe   
{  
      [ create   | c ] <instance-name><instance-version> [-s ]  
    | [ delete   | d ] <instance-name>  
    | [ start    | s ] <instance-name>  
    | [ stop     | p ] <instance-name>  [ -i ] [ -k ]  
    | [ share    | h ] ["<user_SID>" | "<user_account>" ] "<private-name>""<shared-name>"  
    | [ unshare  | u ] "<shared-name>"  
    | [ info     | i ] <instance-name>  
    | [ versions | v ]  
    | [ trace    | t ] [ on | off ]  
    | [ help     | -? ]  
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="8f6e2-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8f6e2-107">Arguments</span></span>  
 <span data-ttu-id="8f6e2-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [ **-s** ]</span><span class="sxs-lookup"><span data-stu-id="8f6e2-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [**-s** ]</span></span>  
 <span data-ttu-id="8f6e2-109">Создает новый экземпляр [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-109">Creates a new of instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="8f6e2-110">`SqlLocalDB`использует версию [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] двоичных файлов, заданную *\<instance-version>* аргументом.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-110">`SqlLocalDB` uses the version of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] binaries specified by *\<instance-version>* argument.</span></span> <span data-ttu-id="8f6e2-111">Номер версии задается в числовом формате и содержит хотя бы один знак после разделителя.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-111">The version number is specified in numeric format with at least one decimal.</span></span> <span data-ttu-id="8f6e2-112">Дополнительные номера версии (пакеты обновления) являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-112">The minor version numbers (service packs) are optional.</span></span> <span data-ttu-id="8f6e2-113">Например, можно указать следующие номера версий: 11.0 или 11.0.1186.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-113">For example the following two version numbers are both acceptable: 11.0, or 11.0.1186.</span></span> <span data-ttu-id="8f6e2-114">Указываемая версия должна быть установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-114">The specified version must be installed on the computer.</span></span> <span data-ttu-id="8f6e2-115">Если значение не указано, по умолчанию используется версия `SqlLocalDB` программы.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-115">If not specified, the version number defaults to the version of the `SqlLocalDB` utility.</span></span> <span data-ttu-id="8f6e2-116">В случае добавления параметра **-s** запускается новый экземпляр **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-116">Adding **-s** starts the new instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="8f6e2-117">[ **share** | **h** ]</span><span class="sxs-lookup"><span data-stu-id="8f6e2-117">[ **share** | **h** ]</span></span>  
 <span data-ttu-id="8f6e2-118">Делает указанный частный экземпляр **LocalDB** общим, используя указанное общее имя.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-118">Shares the specified private instance of **LocalDB** using the specified shared name.</span></span> <span data-ttu-id="8f6e2-119">Если идентификатор безопасности пользователя или имя учетной записи не указаны, используется значение по умолчанию — имя текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-119">If the user SID or account name is omitted, it defaults to the current user.</span></span>  
  
 <span data-ttu-id="8f6e2-120">[ **unshared** | **u** ]</span><span class="sxs-lookup"><span data-stu-id="8f6e2-120">[ **unshared** | **u** ]</span></span>  
 <span data-ttu-id="8f6e2-121">Отменяет общий доступ к указанному экземпляру **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-121">Stops the sharing of the specified shared instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="8f6e2-122">[ **delete** | **d** ] *\<instance-name>*</span><span class="sxs-lookup"><span data-stu-id="8f6e2-122">[ **delete** | **d** ] *\<instance-name>*</span></span>  
 <span data-ttu-id="8f6e2-123">Удаляет указанный экземпляр [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-123">Deletes the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span>  
  
 <span data-ttu-id="8f6e2-124">[ **start** | **s** ] " *\<instance-name>* "</span><span class="sxs-lookup"><span data-stu-id="8f6e2-124">[ **start** | **s** ] "*\<instance-name>*"</span></span>  
 <span data-ttu-id="8f6e2-125">Запускает указанный экземпляр [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-125">Starts the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="8f6e2-126">В случае успешного завершения инструкция возвращает адрес именованного канала **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-126">When successful the statement returns the named pipe address of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="8f6e2-127">[ **stop** | **p** ] *\<instance-name>* [ **-i** ] [ **-k** ]</span><span class="sxs-lookup"><span data-stu-id="8f6e2-127">[ **stop** | **p** ] *\<instance-name>* [**-i** ] [**-k** ]</span></span>  
 <span data-ttu-id="8f6e2-128">Останавливает указанный экземпляр [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-128">Stops the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="8f6e2-129">Добавление **-i** запрашивает завершение работы экземпляра с `NOWAIT` параметром.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-129">Adding **-i** requests the instance shutdown with the `NOWAIT` option.</span></span> <span data-ttu-id="8f6e2-130">В случае добавления параметра **-k** процесс экземпляра завершается без обращения к нему.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-130">Adding **-k** kills the instance process without contacting it.</span></span>  
  
 <span data-ttu-id="8f6e2-131">[ **info** | **i** ] [ *\<instance-name>* ]</span><span class="sxs-lookup"><span data-stu-id="8f6e2-131">[ **info** | **i** ] [ *\<instance-name>* ]</span></span>  
 <span data-ttu-id="8f6e2-132">Перечисляет все экземпляры [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** , принадлежащие текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-132">Lists all instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** owned by the current user.</span></span>  
  
 <span data-ttu-id="8f6e2-133">*\<instance-name>* возвращает имя, версию, состояние (выполняется или остановлено), время последнего запуска для указанного экземпляра [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] **LocalDB** и имя локального канала для **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-133">*\<instance-name>* returns the name, version, state (Running or Stopped), last start time for the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**, and the local pipe name of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="8f6e2-134">[ **trace** | **t** ] **on** | **off**</span><span class="sxs-lookup"><span data-stu-id="8f6e2-134">[ **trace** | **t** ] **on** | **off**</span></span>  
 <span data-ttu-id="8f6e2-135">**Trace on** включает трассировку `SqlLocalDB` вызовов API для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-135">**trace on** enables tracing for the `SqlLocalDB` API calls for the current user.</span></span> <span data-ttu-id="8f6e2-136">Параметр**trace off** отключает трассировку.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-136">**trace off** disables tracing.</span></span>  
  
 <span data-ttu-id="8f6e2-137">**-?**</span><span class="sxs-lookup"><span data-stu-id="8f6e2-137">**-?**</span></span>  
 <span data-ttu-id="8f6e2-138">Возвращает краткое описание каждого `SqlLocalDB` параметра.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-138">Returns brief descriptions of each `SqlLocalDB` option.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f6e2-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="8f6e2-139">Remarks</span></span>  
 <span data-ttu-id="8f6e2-140">В аргументе *имя-экземпляра* должны соблюдаться правила для идентификаторов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] . В противном случае он должен заключаться в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-140">The *instance name* argument must follow the rules for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers or it must be enclosed in double quotes.</span></span>  
  
 <span data-ttu-id="8f6e2-141">При выполнении SqlLocalDB без аргументов возвращается текст справки.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-141">Executing SqlLocalDB without arguments returns the help text.</span></span>  
  
 <span data-ttu-id="8f6e2-142">Любые операции, за исключением запуска, могут выполняться только с экземпляром, принадлежащим текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-142">Operations other than start can only be performed on an instance belonging to currently logged in user.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8f6e2-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="8f6e2-143">Examples</span></span>  
  
### <a name="a-creating-an-instance-of-localdb"></a><span data-ttu-id="8f6e2-144">A.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-144">A.</span></span> <span data-ttu-id="8f6e2-145">Создание экземпляра LocalDB</span><span class="sxs-lookup"><span data-stu-id="8f6e2-145">Creating an Instance of LocalDB</span></span>  
 <span data-ttu-id="8f6e2-146">В следующем примере экземпляр [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** с именем `DEPARTMENT` создается с помощью двоичных файлов [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] , а затем запускается.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-146">The following example creates an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** named `DEPARTMENT` using the [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] binaries and starts the instance.</span></span>  
  
```  
SqlLocalDB.exe create "DEPARTMENT" 12.0 -s  
```  
  
### <a name="b-working-with-a-shared-instance-of-localdb"></a><span data-ttu-id="8f6e2-147">Б.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-147">B.</span></span> <span data-ttu-id="8f6e2-148">Работа с общим экземпляром LocalDB</span><span class="sxs-lookup"><span data-stu-id="8f6e2-148">Working with a Shared Instance of LocalDB</span></span>  
 <span data-ttu-id="8f6e2-149">Откройте командную строку с правами доступа администратора.</span><span class="sxs-lookup"><span data-stu-id="8f6e2-149">Open a command prompt using Administrator privileges.</span></span>  
  
```  
SqlLocalDB.exe create "DeptLocalDB"  
SqlLocalDB.exe share "DeptLocalDB" "DeptSharedLocalDB"  
SqlLocalDB.exe start "DeptLocalDB"  
SqlLocalDB.exe info "DeptLocalDB"  
REM The previous statement outputs the Instance pipe name for the next step  
sqlcmd -S np:\\.\pipe\LOCALDB#<use your pipe name>\tsql\query  
CREATE LOGIN NewLogin WITH PASSWORD = 'Passw0rd!!@52';   
GO  
CREATE USER NewLogin;  
GO  
EXIT  
```  
  
 <span data-ttu-id="8f6e2-150">Выполните следующий код, чтобы подключиться к общему экземпляру **LocalDB** с использованием имени входа `NewLogin` .</span><span class="sxs-lookup"><span data-stu-id="8f6e2-150">Execute the following code to connect to the shared instance of **LocalDB** using the `NewLogin` login.</span></span>  
  
```  
sqlcmd -S (localdb)\.\DeptSharedLocalDB -U NewLogin -P Passw0rd!!@52  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f6e2-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="8f6e2-151">See Also</span></span>  
 [<span data-ttu-id="8f6e2-152">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="8f6e2-152">SQL Server 2014 Express LocalDB</span></span>](../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
  
