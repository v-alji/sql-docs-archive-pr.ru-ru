---
title: Параметр состояния (средство администрирования распределенного воспроизведения) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: ea89386e-1598-4412-8b37-680d14b2a5b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ce3d07bc357c5f3788fb6f995a43399021b3553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727681"
---
# <a name="status-option-distributed-replay-administration-tool"></a><span data-ttu-id="0688e-102">Параметр состояния (средство администрирования распределенного воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="0688e-102">Status Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="0688e-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Средство администрирования распределенное воспроизведение `DReplay.exe` — это средство командной строки, которое можно использовать для взаимодействия с контроллером распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="0688e-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="0688e-104">В этой статье описан параметр командной строки **status** и соответствующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0688e-104">This topic describes the **status** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="0688e-105">Параметр **status** опрашивает контроллер и отображает его текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="0688e-105">The **status** option queries the controller and displays the current status.</span></span>

 <span data-ttu-id="0688e-106">![Значок ссылки на раздел](../../database-engine/media/topic-link.gif "Значок ссылки на раздел") Дополнительные сведения о синтаксических обозначениях, используемых в синтаксисе средства администрирования, см. в разделе [Синтаксические обозначения в Transact-SQL (Transact-SQL)](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0688e-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="0688e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0688e-107">Syntax</span></span>

```

dreplay status [-mcontroller] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="0688e-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="0688e-108">Parameters</span></span>
 <span data-ttu-id="0688e-109">*контроллер* **-m** указывает имя компьютера контроллера.</span><span class="sxs-lookup"><span data-stu-id="0688e-109">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="0688e-110">Локальный компьютер можно указать как «`localhost`» или «`.`».</span><span class="sxs-lookup"><span data-stu-id="0688e-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="0688e-111">Если параметр **-m** не задан, то используется локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="0688e-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="0688e-112">**-f** *status_interval* указывает частоту (в секундах) вывода состояния.</span><span class="sxs-lookup"><span data-stu-id="0688e-112">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="0688e-113">Если параметр **-f** не задан, то интервал по умолчанию составляет 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="0688e-113">If the **-f** parameter is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="0688e-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="0688e-114">Examples</span></span>
 <span data-ttu-id="0688e-115">В следующем примере текущий статус отображается каждые 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="0688e-115">In the following example, the current status is displayed every 60 seconds.</span></span> <span data-ttu-id="0688e-116">Значение `localhost` указывает, что служба контроллера запущена на том же компьютере, что и средство администрирования.</span><span class="sxs-lookup"><span data-stu-id="0688e-116">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay status -m localhost -f 60
```

## <a name="permissions"></a><span data-ttu-id="0688e-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="0688e-117">Permissions</span></span>
 <span data-ttu-id="0688e-118">Средство администрирования должно запускаться как интерактивный пользователь, с учетной записью локального пользователя или пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="0688e-118">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="0688e-119">Для использования учетной записи локального пользователя средство администрирования и контроллер должны быть запущены на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0688e-119">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="0688e-120">Дополнительные сведения см. в статье [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="0688e-120">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0688e-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="0688e-121">See Also</span></span>
 <span data-ttu-id="0688e-122">[Отладчик Transact-SQL](../../relational-databases/scripting/transact-sql-debugger.md) [SQL Server распределенное воспроизведение](sql-server-distributed-replay.md)</span><span class="sxs-lookup"><span data-stu-id="0688e-122">[SQL Server Distributed Replay](sql-server-distributed-replay.md) [Transact-SQL Debugger](../../relational-databases/scripting/transact-sql-debugger.md)</span></span>


