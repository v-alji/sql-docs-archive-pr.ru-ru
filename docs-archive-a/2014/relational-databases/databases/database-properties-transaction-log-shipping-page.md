---
title: Свойства базы данных (страница "Доставка журналов транзакций") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.f1
ms.assetid: 72c4e539-fe11-4d57-b977-65b418d5916f
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd36b3bc56bcd48c53871c9bc1e334d72c80ac78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751124"
---
# <a name="database-properties-transaction-log-shipping-page"></a><span data-ttu-id="4dded-102">Свойства базы данных (страница «Доставка журналов транзакций»)</span><span class="sxs-lookup"><span data-stu-id="4dded-102">Database Properties (Transaction Log Shipping Page)</span></span>
  <span data-ttu-id="4dded-103">Используйте эту страницу, чтобы настроить и изменить свойства доставки журналов базы данных.</span><span class="sxs-lookup"><span data-stu-id="4dded-103">Use this page to configure and modify the properties of log shipping for a database.</span></span>  
  
 <span data-ttu-id="4dded-104">Основные сведения о доставке журналов изложены в статье [Сведения о доставке журналов (SQL Server)](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dded-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4dded-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4dded-105">Options</span></span>  
 <span data-ttu-id="4dded-106">**Включить эту базу данных в качестве источника в конфигурацию доставки журналов**</span><span class="sxs-lookup"><span data-stu-id="4dded-106">**Enable this as a primary database in a log shipping configuration**</span></span>  
 <span data-ttu-id="4dded-107">Включает эту базу данных в качестве источника для доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="4dded-107">Enables this database as a log shipping primary database.</span></span> <span data-ttu-id="4dded-108">Выберите этот пункт и затем настройте остальные параметры на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4dded-108">Select it and then configure the remaining options on this page.</span></span> <span data-ttu-id="4dded-109">Если снять этот флажок, конфигурация доставки журналов для этой базы данных будет сброшена.</span><span class="sxs-lookup"><span data-stu-id="4dded-109">If you clear this check box, the log shipping configuration will be dropped for this database.</span></span>  
  
 <span data-ttu-id="4dded-110">**Параметры копирования**</span><span class="sxs-lookup"><span data-stu-id="4dded-110">**Backup Settings**</span></span>  
 <span data-ttu-id="4dded-111">Нажмите кнопку **Параметры копирования** , чтобы настроить параметры расписания резервного копирования, расположения, предупреждений и архивирования.</span><span class="sxs-lookup"><span data-stu-id="4dded-111">Click **Backup Settings** to configure backup schedule, location, alert, and archiving parameters.</span></span>  
  
 <span data-ttu-id="4dded-112">**Расписание копирования**</span><span class="sxs-lookup"><span data-stu-id="4dded-112">**Backup schedule**</span></span>  
 <span data-ttu-id="4dded-113">Показывает выбранное в настоящий момент расписание резервного копирования для базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="4dded-113">Shows the currently selected backup schedule for the primary database.</span></span> <span data-ttu-id="4dded-114">Нажмите кнопку **Параметры копирования** , чтобы изменить эти настройки.</span><span class="sxs-lookup"><span data-stu-id="4dded-114">Click **Backup Settings** to modify these settings.</span></span>  
  
 <span data-ttu-id="4dded-115">**Последняя резервная копия создана**</span><span class="sxs-lookup"><span data-stu-id="4dded-115">**Last backup created**</span></span>  
 <span data-ttu-id="4dded-116">Указывает время и дату создания последней резервной копии журнала транзакций базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="4dded-116">Indicates the time and date of the last transaction log backup of the primary database.</span></span>  
  
 <span data-ttu-id="4dded-117">**Экземпляры сервера-получателя и базы данных**</span><span class="sxs-lookup"><span data-stu-id="4dded-117">**Secondary server instances and databases**</span></span>  
 <span data-ttu-id="4dded-118">Перечисляет настроенные в настоящий момент серверы-получатели и базы данных-получатели для этой базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="4dded-118">Lists the currently configured secondary servers and databases for this primary database.</span></span> <span data-ttu-id="4dded-119">Выделите базу данных, а затем нажмите кнопку вызова диалогового окна, обозначенную многоточием **...** , чтобы изменить параметры, связанные с этой базой данных-получателем.</span><span class="sxs-lookup"><span data-stu-id="4dded-119">Highlight a database, and then click **...** to modify the parameters associated with that secondary database.</span></span>  
  
 <span data-ttu-id="4dded-120">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="4dded-120">**Add**</span></span>  
 <span data-ttu-id="4dded-121">Нажмите кнопку **Добавить** , чтобы добавить базу данных-получатель в конфигурацию доставки журналов для этой базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="4dded-121">Click **Add** to add a secondary database to the log shipping configuration for this primary database.</span></span>  
  
 <span data-ttu-id="4dded-122">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="4dded-122">**Remove**</span></span>  
 <span data-ttu-id="4dded-123">Удаляет выбранную базу данных из этой конфигурации доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="4dded-123">Removes a selected database from this log shipping configuration.</span></span> <span data-ttu-id="4dded-124">Сначала выберите базу данных, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4dded-124">Select the database first and then click **Remove**.</span></span>  
  
 <span data-ttu-id="4dded-125">**Использовать экземпляр сервера мониторинга**</span><span class="sxs-lookup"><span data-stu-id="4dded-125">**Use a monitor server instance**</span></span>  
 <span data-ttu-id="4dded-126">Устанавливает экземпляр сервера мониторинга для этой конфигурации доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="4dded-126">Sets up a monitor server instance for this log shipping configuration.</span></span> <span data-ttu-id="4dded-127">Установите флажок **Использовать экземпляр сервера мониторинга** , затем выберите пункт **Настройки** , чтобы указать экземпляр сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4dded-127">Select the **Use a monitor server instance** check box and then click **Settings** to specify the monitor server instance.</span></span>  
  
 <span data-ttu-id="4dded-128">**Экземпляр сервера мониторинга**</span><span class="sxs-lookup"><span data-stu-id="4dded-128">**Monitor server instance**</span></span>  
 <span data-ttu-id="4dded-129">Указывает настроенный в настоящий момент экземпляр сервера мониторинга для этой конфигурации доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="4dded-129">Indicates the currently configured monitor server instance for this log shipping configuration.</span></span>  
  
 <span data-ttu-id="4dded-130">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="4dded-130">**Settings**</span></span>  
 <span data-ttu-id="4dded-131">Настраивает экземпляр сервера мониторинга для конфигурации доставки журналов.</span><span class="sxs-lookup"><span data-stu-id="4dded-131">Configures the monitor server instance for a log shipping configuration.</span></span> <span data-ttu-id="4dded-132">Выберите пункт **Настройки** , чтобы настроить экземпляр сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4dded-132">Click **Settings** to configure this monitor server instance.</span></span>  
  
 <span data-ttu-id="4dded-133">**Скрипт конфигурации**</span><span class="sxs-lookup"><span data-stu-id="4dded-133">**Script Configuration**</span></span>  
 <span data-ttu-id="4dded-134">Создает скрипт для настройки доставки журналов с выбранными параметрами.</span><span class="sxs-lookup"><span data-stu-id="4dded-134">Generates a script for configuring log shipping with the parameters you have selected.</span></span> <span data-ttu-id="4dded-135">Нажмите кнопку **Скрипт конфигурации**, а затем выберите выходное назначение для скрипта.</span><span class="sxs-lookup"><span data-stu-id="4dded-135">Click **Script Configuration**, and then choose an output destination for the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4dded-136">До создания сценария настройки для базы данных-получателя необходимо вызвать диалоговое окно **Настройки базы данных-получателя** .</span><span class="sxs-lookup"><span data-stu-id="4dded-136">Before scripting settings for a secondary database, you must invoke the **Secondary Database Settings** dialog box.</span></span> <span data-ttu-id="4dded-137">При вызове этого диалогового окна выполняется подключение к серверу-получателю и получение текущих настроек базы данных-получателя, необходимых для создания скрипта.</span><span class="sxs-lookup"><span data-stu-id="4dded-137">Invoking this dialog box connects you to the secondary server and retrieves the current settings of the secondary database that are needed to generate the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dded-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="4dded-138">See Also</span></span>  
 <span data-ttu-id="4dded-139">[Хранимые процедуры доставки журналов (Transact-SQL)](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4dded-139">[Log Shipping Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="4dded-140">Таблицы доставки журналов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4dded-140">Log Shipping Tables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/log-shipping-tables-transact-sql)  
  
  
