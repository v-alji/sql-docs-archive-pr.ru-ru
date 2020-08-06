---
title: Добавление целевого сервера к главному | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- enlisting target servers [SQL Server]
- SQL Server Agent jobs, target servers
- master servers [SQL Server], enlisting target servers
- SQL Server Agent jobs, master servers
- target servers [SQL Server], enlisting
ms.assetid: 7633adb5-d140-4e58-a8f2-5b4b50c2f95b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 256f1a78d298d89a36412ee5689695f3ab3fde8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654731"
---
# <a name="enlist-a-target-server-to-a-master-server"></a><span data-ttu-id="892bb-102">Прикрепление целевого сервера к главному</span><span class="sxs-lookup"><span data-stu-id="892bb-102">Enlist a Target Server to a Master Server</span></span>
  <span data-ttu-id="892bb-103">В этом разделе описывается, как добавить целевые серверы в конфигурацию администрирования нескольких серверов.</span><span class="sxs-lookup"><span data-stu-id="892bb-103">This topic describes how to add target servers to a multiserver administration configuration.</span></span> <span data-ttu-id="892bb-104">Запустите эту процедуру с главного сервера.</span><span class="sxs-lookup"><span data-stu-id="892bb-104">Run this procedure from the master server.</span></span> <span data-ttu-id="892bb-105">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или управляющих объектов SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="892bb-105">in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="892bb-106">Дополнительные сведения о влиянии учетной записи Windows для службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на многосерверную среду см. в разделе [Создание многосерверной среды](create-a-multiserver-environment.md).</span><span class="sxs-lookup"><span data-stu-id="892bb-106">For information about how the Windows account used for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service affects a multiserver environment, see [Create a Multiserver Environment](create-a-multiserver-environment.md).</span></span>  
  
 <span data-ttu-id="892bb-107">По умолчанию полное шифрование SSL и проверка сертификата включены для соединений между главными и целевыми серверами.</span><span class="sxs-lookup"><span data-stu-id="892bb-107">Full Secure Sockets Layer (SSL) encryption and certificate validation is enabled for connections between master servers and target servers by default.</span></span> <span data-ttu-id="892bb-108">Дополнительные сведения см. в статье [Установка параметров шифрования на целевых серверах](set-encryption-options-on-target-servers.md).</span><span class="sxs-lookup"><span data-stu-id="892bb-108">For more information, see [Set Encryption Options on Target Servers](set-encryption-options-on-target-servers.md).</span></span>  
  
 <span data-ttu-id="892bb-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="892bb-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="892bb-110">**Для прикрепления целевого сервера используется:**</span><span class="sxs-lookup"><span data-stu-id="892bb-110">**To enlist a target server, using:**</span></span>  
  
     [<span data-ttu-id="892bb-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="892bb-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="892bb-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="892bb-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="892bb-113">ОБЪЕКТАХ</span><span class="sxs-lookup"><span data-stu-id="892bb-113">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="892bb-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="892bb-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="892bb-115">Прикрепление целевого сервера</span><span class="sxs-lookup"><span data-stu-id="892bb-115">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="892bb-116">В **Обозревателе объектов**разверните главный сервер.</span><span class="sxs-lookup"><span data-stu-id="892bb-116">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="892bb-117">Щелкните правой кнопкой мыши элемент **Агент SQL Server**, укажите пункт **Администрирование нескольких серверов**, а затем выберите пункт **Добавление целевых серверов**.</span><span class="sxs-lookup"><span data-stu-id="892bb-117">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Add Target Servers**.</span></span>  
  
3.  <span data-ttu-id="892bb-118">Завершите работу мастера настройки целевого сервера, который проводит пользователя по этапам процесса.</span><span class="sxs-lookup"><span data-stu-id="892bb-118">Complete the Target Server Wizard, which guides you through the process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="892bb-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="892bb-119">Using Transact-SQL</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="892bb-120">Прикрепление целевого сервера</span><span class="sxs-lookup"><span data-stu-id="892bb-120">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="892bb-121">Используйте хранимую процедуру `sp_msx_enlist`.</span><span class="sxs-lookup"><span data-stu-id="892bb-121">Use the `sp_msx_enlist` stored procedure.</span></span>  <span data-ttu-id="892bb-122">Дополнительные сведения см. в разделе [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="892bb-122">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="892bb-123">Использование управляющие объекты SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="892bb-123">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="892bb-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="892bb-124">See Also</span></span>  
 [<span data-ttu-id="892bb-125">Автоматизация администрирования в масштабах предприятия</span><span class="sxs-lookup"><span data-stu-id="892bb-125">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
