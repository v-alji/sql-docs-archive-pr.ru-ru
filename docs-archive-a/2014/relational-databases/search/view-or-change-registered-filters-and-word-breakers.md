---
title: Просмотр или изменение зарегистрированных фильтров и средств разбиения текста на слова | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text search [SQL Server], word breakers
- full-text search [SQL Server], filters
- filters [full-text search]
- word breakers [full-text search]
ms.assetid: f88c54df-b1aa-4701-807f-dc92c32363fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79ad7f1f7df15fed21a132bbe253adc7185d8c06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730414"
---
# <a name="view-or-change-registered-filters-and-word-breakers"></a><span data-ttu-id="7fd59-102">Просмотр или изменение зарегистрированных фильтры и разделители слов</span><span class="sxs-lookup"><span data-stu-id="7fd59-102">View or Change Registered Filters and Word Breakers</span></span>
  <span data-ttu-id="7fd59-103">После того как в системе была произведена установка или удаление средств разбиения по словам или фильтров, автоматического внесения изменений на экземплярах сервера не происходит.</span><span class="sxs-lookup"><span data-stu-id="7fd59-103">After any word breakers or filters are installed or uninstalled on a system, the changes do not automatically take effect on server instances.</span></span> <span data-ttu-id="7fd59-104">В данном разделе описано, как можно просмотреть зарегистрированные в данный момент средства разбиения по словам и фильтры, а также как зарегистрировать недавно установленные средства разбиения по словам и фильтры на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fd59-104">This topic describes how to view the currently registered word breaker or filters and how to register newly installed word breakers and filters on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-a-list-of-languages-whose-word-breakers-are-currently-registered"></a><span data-ttu-id="7fd59-105">Просмотр списка языков, для которых установлены зарегистрированные в данный момент средства разбиения по словам</span><span class="sxs-lookup"><span data-stu-id="7fd59-105">To view a list of languages whose word breakers are currently registered</span></span>  
  
1.  <span data-ttu-id="7fd59-106">Используйте представление каталога [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7fd59-106">Use the [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) catalog view, as follows:</span></span>  
  
    ```  
    SELECT * FROM sys.fulltext_languages;   
    ```  
  
### <a name="to-view-a-list-of-the-filters-that-are-currently-registered"></a><span data-ttu-id="7fd59-107">Просмотр списка зарегистрированных в данный момент фильтров</span><span class="sxs-lookup"><span data-stu-id="7fd59-107">To view a list of the filters that are currently registered</span></span>  
  
1.  <span data-ttu-id="7fd59-108">Используйте системную хранимую процедуру [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7fd59-108">Use the [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) system stored procedure, as follows:</span></span>  
  
    ```  
    EXEC sp_help_fulltext_system_components 'filter';    
    ```  
  
### <a name="to-register-newly-installed-word-breakers-and-filters"></a><span data-ttu-id="7fd59-109">Регистрация недавно установленных средств разбиения по словам и фильтров</span><span class="sxs-lookup"><span data-stu-id="7fd59-109">To register newly installed word breakers and filters</span></span>  
  
1.  <span data-ttu-id="7fd59-110">Используйте системную хранимую процедуру [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) для обновления списка языков следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7fd59-110">Use the [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) system stored procedure to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages';   
    ```  
  
### <a name="to-unregister-uninstalled-word-breakers-and-filters"></a><span data-ttu-id="7fd59-111">Отмена регистрации удаленных средств разбиения по словам и фильтров</span><span class="sxs-lookup"><span data-stu-id="7fd59-111">To unregister uninstalled word breakers and filters</span></span>  
  
1.  <span data-ttu-id="7fd59-112">Используйте **sp_fulltext_service** для обновления списка языков следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7fd59-112">Use the **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages'  
    ```  
  
2.  <span data-ttu-id="7fd59-113">Используйте **sp_fulltext_service** для перезапуска процессов узла управляющей программы фильтрации (fdhost.exe) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7fd59-113">Use the **sp_fulltext_service** to restart the filter daemon host processes (fdhost.exe), as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'restart_all_fdhosts';  
    ```  
  
### <a name="to-replace-existing-word-breakers-or-filters-when-installing-new-ones"></a><span data-ttu-id="7fd59-114">Замена существующих средств разбиения по словам или фильтров при установке новых</span><span class="sxs-lookup"><span data-stu-id="7fd59-114">To replace existing word breakers or filters when installing new ones</span></span>  
  
1.  <span data-ttu-id="7fd59-115">При подготовке к установке DLL-файла, содержащего новые средства разбиения по словам или фильтры, следует убедиться, что его имя отличается от имен существующих DLL-файлов, установленных на экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="7fd59-115">When preparing to install a DLL file that contains new word breakers or filters, verify that it has a different filename from any of the existing DLL files installed on your server instance.</span></span>  
  
2.  <span data-ttu-id="7fd59-116">Скопируйте новый DLL-файл в каталог, содержащий стандартные DLL-файлы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="7fd59-116">Copy the new DLL file into the directory containing the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files for the server instance.</span></span> <span data-ttu-id="7fd59-117">Расположение по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="7fd59-117">The default location is:</span></span>  
  
     <span data-ttu-id="7fd59-118">C:\Program Files\Microsoft SQL Server\MSSQL.*имя_экземпляра*\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="7fd59-118">C:\Program Files\Microsoft SQL Server\MSSQL.*instance_name*\MSSQL\Binn</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7fd59-119">Рекомендуется загружать только подписанные и проверенные компоненты.</span><span class="sxs-lookup"><span data-stu-id="7fd59-119">We highly recommend that you load only signed and verified components.</span></span> <span data-ttu-id="7fd59-120">Кроме того, службу FDHOST Launcher (MSSQLFDLauncher) рекомендуется запускать с наименьшими возможными правами доступа.</span><span class="sxs-lookup"><span data-stu-id="7fd59-120">Also, we recommend that you run the FDHOST Launcher (MSSQLFDLauncher) Service with the least possible privileges.</span></span>  
  
3.  <span data-ttu-id="7fd59-121">Установите новые средства разбиения по словам или фильтры.</span><span class="sxs-lookup"><span data-stu-id="7fd59-121">Install the new word breaker or filters.</span></span>  
  
     <span data-ttu-id="7fd59-122">**Установка и загрузка фильтров IFilter из пакета фильтров (Майкрософт)**</span><span class="sxs-lookup"><span data-stu-id="7fd59-122">**To install and load Microsoft Filter Pack IFilters**</span></span>  
  
    -   [<span data-ttu-id="7fd59-123">Как зарегистрировать пакет дополнительных фильтров Microsoft IFilters в SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fd59-123">How to register Microsoft Filter Pack IFilters with SQL Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=130439)  
  
4.  <span data-ttu-id="7fd59-124">Загрузите вновь установленные средства разбиения по словам и фильтры на экземпляр сервера с помощью хранимой процедуры **sp_fulltext_service** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7fd59-124">Use **sp_fulltext_service** to load newly installed word breakers and filters in the server instance, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service @action='load_os_resources', @value=1;  
    ```  
  
5.  <span data-ttu-id="7fd59-125">Обновите список языков с помощью хранимой процедуры **sp_fulltext_service** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7fd59-125">Use **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'update_languages';  
    ```  
  
6.  <span data-ttu-id="7fd59-126">Перезапустите процессы узла управляющей программы фильтрации (fdhost.exe) с помощью хранимой процедуры **sp_fulltext_service** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7fd59-126">Restart the filter daemon host processes (fdhost.exe), using **sp_fulltext_service** as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'restart_all_fdhosts';   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7fd59-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="7fd59-127">See Also</span></span>  
 <span data-ttu-id="7fd59-128">[Настройка учетной записи службы средства запуска управляющей программы полнотекстовой фильтрации](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="7fd59-128">[Set the Service Account for the Full-text Filter Daemon Launcher](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="7fd59-129">[Настройка и управление фильтрами для поиска](configure-and-manage-filters-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="7fd59-129">[Configure and Manage Filters for Search](configure-and-manage-filters-for-search.md) </span></span>  
 [<span data-ttu-id="7fd59-130">Настройка и управление средством разбиения на слова и парадигматические модули для поиска</span><span class="sxs-lookup"><span data-stu-id="7fd59-130">Configure and Manage Word Breakers and Stemmers for Search</span></span>](configure-and-manage-word-breakers-and-stemmers-for-search.md)  
  
  
