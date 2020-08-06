---
title: Открытие монитора активности (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server], setting the refresh interval
- refresh interval for Activity Monitor
- Activity Monitor [SQL Server], opening
- opening Activity Monitor
ms.assetid: 0a6eeb16-f02b-479d-9a60-543e40ebf46b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea74122ad18a0a1ede5eef1e09684606ca0ce073
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739734"
---
# <a name="open-activity-monitor-sql-server-management-studio"></a><span data-ttu-id="170f1-102">Открытие монитора активности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="170f1-102">Open Activity Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="170f1-103">В этом разделе описано, как можно открыть монитор активности, который позволяет получить сведения о процессах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и о том, как эти процессы влияют на текущий экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="170f1-103">This topic describes how to open the Activity Monitor to obtain information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="170f1-104">Кроме того, он описывает, как можно задать интервал обновления для монитора активности.</span><span class="sxs-lookup"><span data-stu-id="170f1-104">It also describes how to set the refresh interval of the Activity Monitor.</span></span>  
  
 <span data-ttu-id="170f1-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="170f1-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="170f1-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="170f1-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="170f1-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="170f1-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="170f1-108">**Открытие монитора активности с помощью:**</span><span class="sxs-lookup"><span data-stu-id="170f1-108">**To open the Activity Monitor using:**</span></span>  
  
     [<span data-ttu-id="170f1-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="170f1-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="170f1-110">**Установка интервала обновления с помощью:**  [Среда SQL Server Management Studio](#Refresh)</span><span class="sxs-lookup"><span data-stu-id="170f1-110">**To set the refresh interval using:**  [SQL Server Management Studio](#Refresh)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="170f1-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="170f1-111">Before You Begin</span></span>  
 <span data-ttu-id="170f1-112">Монитор активности выполняет запросы в отслеживаемом экземпляре, чтобы получать данные для панелей отображения монитора активности.</span><span class="sxs-lookup"><span data-stu-id="170f1-112">Activity Monitor runs queries on the monitored instance to obtain information for the Activity Monitor display panes.</span></span> <span data-ttu-id="170f1-113">Если установлен интервал обновления менее 10 секунд, то время, затрачиваемое на выполнение этих запросов, может повлиять на производительность сервера.</span><span class="sxs-lookup"><span data-stu-id="170f1-113">When the refresh interval is set to less than 10 seconds, the time that is used to run these queries can affect server performance</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="170f1-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="170f1-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="170f1-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="170f1-115">Permissions</span></span>  
 <span data-ttu-id="170f1-116">Для просмотра монитора активности у пользователя должно быть разрешение VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="170f1-116">To view the Activity Monitor, a user must have VIEW SERVER STATE permission.</span></span> <span data-ttu-id="170f1-117">Для просмотра раздела ввода-вывода в файл данных монитора активности, кроме разрешения на VIEW SERVER STATE, необходимо иметь также разрешения на CREATE DATABASE, ALTER ANY DATABASE или VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="170f1-117">To view the Data File I/O section of Activity Monitor, you must have CREATE DATABASE, ALTER ANY DATABASE, or VIEW ANY DEFINITION permission in addition to VIEW SERVER STATE.</span></span>  
  
 <span data-ttu-id="170f1-118">Для вызова инструкции KILL для процесса пользователь должен быть членом предопределенных ролей сервера sysadmin или processadmin.</span><span class="sxs-lookup"><span data-stu-id="170f1-118">To KILL a process, a user must be a member of the sysadmin or processadmin fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="170f1-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="170f1-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-open-activity-monitor-in-sql-server-management-studio"></a><span data-ttu-id="170f1-120">Открытие монитора активности в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="170f1-120">To open Activity Monitor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="170f1-121">На стандартной панели инструментов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] щелкните **Монитор активности**.</span><span class="sxs-lookup"><span data-stu-id="170f1-121">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] standard toolbar, click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="170f1-122">В диалоговом окне **Подключение к серверу** выберите имя сервера и режим проверки подлинности, а затем нажмите кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="170f1-122">In the **Connect to Server** dialog box, select the server name and authentication mode, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="170f1-123">Открыть монитор активности можно также в любое время, нажав сочетание CTRL+ALT A.</span><span class="sxs-lookup"><span data-stu-id="170f1-123">You can also open Activity Monitor at any time by pressing CTRL+ALT A.</span></span>  
  
#### <a name="to-open-activity-monitor-in-object-explorer"></a><span data-ttu-id="170f1-124">Открытие монитора активности в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="170f1-124">To open Activity Monitor in Object Explorer</span></span>  
  
-   <span data-ttu-id="170f1-125">В обозревателе объектов щелкните правой кнопкой мыши имя экземпляра и выберите пункт **Монитор активности**.</span><span class="sxs-lookup"><span data-stu-id="170f1-125">In Object Explorer, right-click the instance name, and then select **Activity Monitor**.</span></span>  
  
#### <a name="to-open-activity-monitor-when-opening-sql-server-management-studio"></a><span data-ttu-id="170f1-126">Открытие монитора активности при открытии среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="170f1-126">To open Activity Monitor when opening SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="170f1-127">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="170f1-127">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="170f1-128">В диалоговом окне **Параметры** последовательно раскройте элементы **Среда**, а затем щелкните **Общие**.</span><span class="sxs-lookup"><span data-stu-id="170f1-128">In the **Options** dialog box, expand **Environment**, and then select **General**.</span></span>  
  
3.  <span data-ttu-id="170f1-129">В области **При запуске** выберите **Открыть обозреватель объектов и монитор активности**.</span><span class="sxs-lookup"><span data-stu-id="170f1-129">In the **At startup** box, select **Open Object Explorer and Activity Monitor**.</span></span>  
  
4.  <span data-ttu-id="170f1-130">Чтобы изменения вступили в силу, закройте и снова откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="170f1-130">To activate the changes, close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-set-the-activity-monitor-refresh-interval"></a><a name="Refresh"></a><span data-ttu-id="170f1-131">Настройка интервала обновления монитора активности</span><span class="sxs-lookup"><span data-stu-id="170f1-131">To Set the Activity Monitor Refresh Interval</span></span>  
  
-   <span data-ttu-id="170f1-132">Откройте монитор активности.</span><span class="sxs-lookup"><span data-stu-id="170f1-132">Open the Activity Monitor.</span></span>  
  
-   <span data-ttu-id="170f1-133">Щелкните правой кнопкой мыши пункт **Обзор**, выберите пункт **Интервал обновления**, а затем — интервал, в котором монитор активности будет получать новые данные экземпляра.</span><span class="sxs-lookup"><span data-stu-id="170f1-133">Right-click **Overview**, select **Refresh Interval**, and then select the interval in which Activity Monitor should obtain new instance information.</span></span>  
  
  
