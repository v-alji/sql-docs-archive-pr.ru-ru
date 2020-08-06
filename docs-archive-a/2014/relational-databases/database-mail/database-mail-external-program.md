---
title: Внешняя программа компонента Database Mail | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- external programs [Database Mail]
- DatabaseMail90.exe
- Database Mail [SQL Server], external programs
ms.assetid: bc124164-eb6e-4b7f-bf66-98a3113d02f7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 698fc8d97a565b4181552691a0260486c9c43bfd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751167"
---
# <a name="database-mail-external-program"></a><span data-ttu-id="e93b2-102">Внешняя программа компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="e93b2-102">Database Mail External Program</span></span>
  <span data-ttu-id="e93b2-103">Внешним исполняемым файлом компонента Database Mail является файл **DatabaseMail.exe**, находящийся в подкаталоге **MSSQL\Binn** каталога установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e93b2-103">The Database Mail external executable is **DatabaseMail.exe**, located in the **MSSQL\Binn directory** of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="e93b2-104">Компонент Database Mail использует активацию компонента Service Broker для запуска внешней программы, когда нужно выполнить обработку электронных сообщений.</span><span class="sxs-lookup"><span data-stu-id="e93b2-104">Database Mail uses Service Broker activation to start the external program when there are e-mail messages to be processed.</span></span> <span data-ttu-id="e93b2-105">Компонент Database Mail запускает один экземпляр внешней программы.</span><span class="sxs-lookup"><span data-stu-id="e93b2-105">Database Mail starts one instance of the external program.</span></span> <span data-ttu-id="e93b2-106">Внешняя программа выполняется в контексте безопасности учетной записи службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e93b2-106">The external program runs in the security context of the service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e93b2-107">**В этом разделе.**</span><span class="sxs-lookup"><span data-stu-id="e93b2-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="e93b2-108">Основные понятия внешней программы компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="e93b2-108">Database Mail External Program Concepts</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="e93b2-109">Задачи, связанные с настройкой внешней программы компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="e93b2-109">Tasks Related to Configuring Database Mail External Program</span></span>](#RelatedTasks)  
  
##  <a name="database-mail-external-program-concepts"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="e93b2-110">Основные понятия внешней программы компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="e93b2-110">Database Mail External Program Concepts</span></span>  
 <span data-ttu-id="e93b2-111">При запуске внешняя программа подключается к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используя проверку подлинности Windows, и начинает обработку электронных сообщений.</span><span class="sxs-lookup"><span data-stu-id="e93b2-111">When the external program starts, the program connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows Authentication and begins processing e-mail messages.</span></span> <span data-ttu-id="e93b2-112">Если в течение указанного времени ожидания сообщений для отправки нет, программа завершает работу.</span><span class="sxs-lookup"><span data-stu-id="e93b2-112">When there have been no messages to send for the specified time-out period, the program exits.</span></span> <span data-ttu-id="e93b2-113">Период времени, в течение которого программа будет ожидать сообщений до завершения работы, можно настроить или с помощью мастера настройки, или с помощью хранимых процедур компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="e93b2-113">You can configure the amount of time that the program waits before exiting by using either Database Mail Configuration Wizard or the Database Mail stored procedures.</span></span> <span data-ttu-id="e93b2-114">Дополнительные сведения см. в разделе [sysmail_configure_sp (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e93b2-114">For more information, see [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span></span>  
  
 <span data-ttu-id="e93b2-115">Внешняя программа хранит данные в системных таблицах базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="e93b2-115">The external program stores information in system tables in the **msdb** database.</span></span> <span data-ttu-id="e93b2-116">Если внешняя программа не может взаимодействовать с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], она регистрирует ошибки в журнале событий приложений Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="e93b2-116">If the external program cannot communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the program logs errors to the Microsoft Windows application event log.</span></span> <span data-ttu-id="e93b2-117">Дополнительная регистрация сообщений используется, если для уровня ведения журнала в диалоговом окне **Установка системных параметров** **мастера настройки компонента Database Mail** установлено значение **Подробный**.</span><span class="sxs-lookup"><span data-stu-id="e93b2-117">Additional message logging is provided when the logging level is set to **Verbose** in the **Configure System Parameters** dialog box of the **Database Mail Configuration Wizard**.</span></span>  
  
 <span data-ttu-id="e93b2-118">Обратите внимание, что для повышения эффективности внешняя программа кэширует сведения об учетной записи и профиле.</span><span class="sxs-lookup"><span data-stu-id="e93b2-118">Notice that, for efficiency, the external program caches account and profile information.</span></span> <span data-ttu-id="e93b2-119">Поэтому изменения конфигурации учетных записей и профилей могут не отражаться во внешней программе в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="e93b2-119">Therefore, configuration changes to accounts and profiles may not be reflected in the external program for a few minutes.</span></span>  
  
##  <a name="tasks-related-to-configuring-database-mail-external-program"></a><a name="RelatedTasks"></a> <span data-ttu-id="e93b2-120">Задачи, связанные с настройкой внешней программы компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="e93b2-120">Tasks Related to Configuring Database Mail External Program</span></span>  
  
|<span data-ttu-id="e93b2-121">Задача конфигурации</span><span class="sxs-lookup"><span data-stu-id="e93b2-121">Configuration Task</span></span>|<span data-ttu-id="e93b2-122">Ссылка на раздел</span><span class="sxs-lookup"><span data-stu-id="e93b2-122">Topic Link</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="e93b2-123">Указание времени, используемого внешней программой перед выходом.</span><span class="sxs-lookup"><span data-stu-id="e93b2-123">Specify the time that the External Program before exiting.</span></span>|[<span data-ttu-id="e93b2-124">sysmail_configure_sp (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e93b2-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql)|  
  
## <a name="see-also"></a><span data-ttu-id="e93b2-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="e93b2-125">See Also</span></span>  
 <span data-ttu-id="e93b2-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="e93b2-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="e93b2-127">[Ведение журнала и аудит компонента Database Mail](database-mail-log-and-audits.md) </span><span class="sxs-lookup"><span data-stu-id="e93b2-127">[Database Mail Log and Audits](database-mail-log-and-audits.md) </span></span>  
 [<span data-ttu-id="e93b2-128">Database Mail</span><span class="sxs-lookup"><span data-stu-id="e93b2-128">Database Mail</span></span>](database-mail.md)  
  
  
