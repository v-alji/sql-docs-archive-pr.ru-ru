---
title: Настройки монитора доставки журналов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.settings.monitor.f1
ms.assetid: 45e2ba7d-b3aa-4643-9451-bcb991572314
author: stevestein
ms.author: sstein
ms.openlocfilehash: 162fdc1b8b0ef850a7e58d1380c533426e16539c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751083"
---
# <a name="log-shipping-monitor-settings"></a><span data-ttu-id="746f9-102">Настройки монитора доставки журналов</span><span class="sxs-lookup"><span data-stu-id="746f9-102">Log Shipping Monitor Settings</span></span>
  <span data-ttu-id="746f9-103">Используйте эту страницу для настройки и изменения параметров монитора доставки журналов на сервере мониторинга.</span><span class="sxs-lookup"><span data-stu-id="746f9-103">Use this page to configure and to modify the properties of the log shipping monitor server.</span></span>  
  
 <span data-ttu-id="746f9-104">Основные сведения о доставке журналов изложены в статье [Сведения о доставке журналов (SQL Server)](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="746f9-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="746f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="746f9-105">Options</span></span>  
 <span data-ttu-id="746f9-106">**Экземпляр сервера мониторинга**</span><span class="sxs-lookup"><span data-stu-id="746f9-106">**Monitor server instance**</span></span>  
 <span data-ttu-id="746f9-107">Отображает имя экземпляра сервера, настроенного в качестве сервера мониторинга для конфигурации доставки журнала.</span><span class="sxs-lookup"><span data-stu-id="746f9-107">Displays the name of the server instance that is currently configured as the monitor server for the log shipping configuration.</span></span>  
  
 <span data-ttu-id="746f9-108">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="746f9-108">**Connect**</span></span>  
 <span data-ttu-id="746f9-109">Выберите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который используется в качестве сервера мониторинга, и соединитесь с ним.</span><span class="sxs-lookup"><span data-stu-id="746f9-109">Choose and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be used as the monitor server.</span></span> <span data-ttu-id="746f9-110">Учетная запись, использованная для подключения, должна быть экземпляром предопределенной роли сервера sysadmin на экземпляре сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="746f9-110">The account used to connect must be a member of the sysadmin fixed server role on the secondary server instance.</span></span>  
  
 <span data-ttu-id="746f9-111">**С помощью олицетворения учетной записи-посредника этого задания**</span><span class="sxs-lookup"><span data-stu-id="746f9-111">**By impersonating the proxy account of the job**</span></span>  
 <span data-ttu-id="746f9-112">Необходимо при доставке журналов олицетворять учетную запись-посредник агента SQL Server при соединении с экземпляром сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="746f9-112">Have log shipping impersonate the SQL Server Agent proxy account when connecting to the monitor server instance.</span></span> <span data-ttu-id="746f9-113">Процессы резервного копирования, копирования и восстановления должны иметь возможность подключения к серверу мониторинга для обновления состояния операций доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="746f9-113">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span>  
  
 <span data-ttu-id="746f9-114">**С использованием следующего имени входа SQL Server**</span><span class="sxs-lookup"><span data-stu-id="746f9-114">**Using the following SQL Server login**</span></span>  
 <span data-ttu-id="746f9-115">Позволяет использовать определенное имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при соединении с экземпляром сервера мониторинга для доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="746f9-115">Allow log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login when connecting to the monitor server instance.</span></span> <span data-ttu-id="746f9-116">Процессы резервного копирования, копирования и восстановления должны иметь возможность подключения к серверу мониторинга для обновления состояния операций доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="746f9-116">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span> <span data-ttu-id="746f9-117">Выберите этот параметр, если для доставки журналов желательно использовать определенное имя входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а затем укажите имя входа и пароль.</span><span class="sxs-lookup"><span data-stu-id="746f9-117">Choose this option if you want log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and then specify the login and password.</span></span>  
  
 <span data-ttu-id="746f9-118">**Удалить журнал после**</span><span class="sxs-lookup"><span data-stu-id="746f9-118">**Delete history after**</span></span>  
 <span data-ttu-id="746f9-119">Укажите интервал времени, в течение которого на сервере мониторинга сохраняются данные о доставке журналов.</span><span class="sxs-lookup"><span data-stu-id="746f9-119">Specify the amount of time to retain log shipping history information on the monitor server before it is deleted.</span></span>  
  
 <span data-ttu-id="746f9-120">**Имя задания**</span><span class="sxs-lookup"><span data-stu-id="746f9-120">**Job name**</span></span>  
 <span data-ttu-id="746f9-121">Указывает имя задания предупреждения агента SQL Server, используемое при доставке журналов, для предупреждения о превышении пороговых значений во время резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="746f9-121">Indicates the name of the SQL Server Agent alert job used by log shipping to raise alerts when backup or restore thresholds have been exceeded.</span></span> <span data-ttu-id="746f9-122">При первом создании этого задания можно изменить имя, введя в текстовом поле новое.</span><span class="sxs-lookup"><span data-stu-id="746f9-122">When first creating this job, you can change the name by typing in the box.</span></span>  
  
 <span data-ttu-id="746f9-123">**Расписание**</span><span class="sxs-lookup"><span data-stu-id="746f9-123">**Schedule**</span></span>  
 <span data-ttu-id="746f9-124">Текущее расписание задания предупреждения агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="746f9-124">Indicates the current schedule of the SQL Server Agent alert job.</span></span>  
  
 <span data-ttu-id="746f9-125">**Edit** (Изменение)</span><span class="sxs-lookup"><span data-stu-id="746f9-125">**Edit**</span></span>  
 <span data-ttu-id="746f9-126">Измените параметры задания предупреждения агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="746f9-126">Modify the SQL Server Agent alert job parameters.</span></span>  
  
 <span data-ttu-id="746f9-127">**Отключить это задание**</span><span class="sxs-lookup"><span data-stu-id="746f9-127">**Disable this job**</span></span>  
 <span data-ttu-id="746f9-128">Приостановите задание предупреждения агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="746f9-128">Suspend the SQL Server Agent alert job.</span></span>  
  
  
