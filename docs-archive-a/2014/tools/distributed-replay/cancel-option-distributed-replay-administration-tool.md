---
title: Параметр отмены (средство администрирования распределенного воспроизведения) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: fea376de-307a-4b45-b7e2-37df88f3681a
author: stevestein
ms.author: sstein
ms.openlocfilehash: d132fbf5ce541a2bdab82e44dc55e6fc92df536d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665176"
---
# <a name="cancel-option-distributed-replay-administration-tool"></a><span data-ttu-id="725e5-102">Параметр отмены (средство администрирования распределенного воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="725e5-102">Cancel Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="725e5-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Средство администрирования распределенное воспроизведение `DReplay.exe` — это средство командной строки, которое можно использовать для взаимодействия с контроллером распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="725e5-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="725e5-104">В этом разделе описывается параметр командной строки **cancel** и соответствующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="725e5-104">This topic describes the **cancel** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="725e5-105">Параметр **cancel** отменяет текущую операцию, выполняемую на контроллере.</span><span class="sxs-lookup"><span data-stu-id="725e5-105">The **cancel** option cancels the current operation that is running on the controller.</span></span>

 <span data-ttu-id="725e5-106">![Значок ссылки на раздел](../../database-engine/media/topic-link.gif "Значок ссылки на раздел") Дополнительные сведения о синтаксических обозначениях, используемых в синтаксисе средства администрирования, см. в разделе [Синтаксические обозначения в Transact-SQL (Transact-SQL)](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="725e5-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="725e5-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="725e5-107">Syntax</span></span>

```

dreplay cancel [-mcontroller] [-q] 
```

#### <a name="parameters"></a><span data-ttu-id="725e5-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="725e5-108">Parameters</span></span>
 <span data-ttu-id="725e5-109">**-m** *контроллер* имя компьютера контроллера.</span><span class="sxs-lookup"><span data-stu-id="725e5-109">**-m** *controller* The computer name of the controller.</span></span> <span data-ttu-id="725e5-110">Локальный компьютер можно указать как «`localhost`» или «`.`».</span><span class="sxs-lookup"><span data-stu-id="725e5-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="725e5-111">Если параметр **-m** не задан, то используется локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="725e5-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="725e5-112">**-q** Тихий режим.</span><span class="sxs-lookup"><span data-stu-id="725e5-112">**-q** Quiet mode.</span></span> <span data-ttu-id="725e5-113">Не запрашивает подтверждения.</span><span class="sxs-lookup"><span data-stu-id="725e5-113">Does not prompt for confirmation.</span></span>

 <span data-ttu-id="725e5-114">Параметр **-q** необязателен.</span><span class="sxs-lookup"><span data-stu-id="725e5-114">The **-q** parameter is optional.</span></span>

## <a name="examples"></a><span data-ttu-id="725e5-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="725e5-115">Examples</span></span>
 <span data-ttu-id="725e5-116">В следующем примере запрос отмены передается в тихом режиме.</span><span class="sxs-lookup"><span data-stu-id="725e5-116">In the following example, a cancel request is submitted in quiet mode.</span></span> <span data-ttu-id="725e5-117">Значение `localhost` указывает, что служба контроллера запущена на том же компьютере, что и средство администрирования.</span><span class="sxs-lookup"><span data-stu-id="725e5-117">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay cancel -m localhost -q
```

## <a name="permissions"></a><span data-ttu-id="725e5-118">Разрешения</span><span class="sxs-lookup"><span data-stu-id="725e5-118">Permissions</span></span>
 <span data-ttu-id="725e5-119">Средство администрирования должно запускаться как интерактивный пользователь, с учетной записью локального пользователя или пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="725e5-119">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="725e5-120">Для использования учетной записи локального пользователя средство администрирования и контроллер должны быть запущены на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="725e5-120">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="725e5-121">Дополнительные сведения см. в статье [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="725e5-121">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="725e5-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="725e5-122">See Also</span></span>
 [<span data-ttu-id="725e5-123">Распределенное воспроизведение SQL Server</span><span class="sxs-lookup"><span data-stu-id="725e5-123">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)


