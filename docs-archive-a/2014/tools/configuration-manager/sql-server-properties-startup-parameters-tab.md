---
title: Свойства SQL Server (вкладка «Параметры запуска») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 16942624-5374-446c-8de4-ee6ed34d6e94
author: stevestein
ms.author: sstein
ms.openlocfilehash: 66c4b71433face008ba78af93579cf175fb4bed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659047"
---
# <a name="sql-server-properties-startup-parameters-tab"></a><span data-ttu-id="d21d0-102">Свойства SQL Server (вкладка «Параметры запуска»)</span><span class="sxs-lookup"><span data-stu-id="d21d0-102">SQL Server Properties (Startup Parameters Tab)</span></span>
  <span data-ttu-id="d21d0-103">Используйте это диалоговое окно для добавления и удаления параметров запуска для компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d21d0-103">Use this dialog box to add or remove startup parameters for the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="d21d0-104">Параметры запуска могут сильно влиять на производительность компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d21d0-104">Startup parameters can have a large effect on the [!INCLUDE[ssDE](../../includes/ssde-md.md)] performance.</span></span> <span data-ttu-id="d21d0-105">Прежде чем добавлять или изменять параметры запуска, ознакомьтесь с разделом «Использование параметров запуска службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] » в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d21d0-105">Before adding or changing startup parameters, see the topic "Using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Service Startup Options" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d21d0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d21d0-106">Options</span></span>  
 <span data-ttu-id="d21d0-107">**Укажите параметр запуска**</span><span class="sxs-lookup"><span data-stu-id="d21d0-107">**Specify a startup parameter**</span></span>  
 <span data-ttu-id="d21d0-108">Чтобы добавить параметр, введите его и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d21d0-108">To add a parameter, type the parameter, and then click **Add**.</span></span>  
  
 <span data-ttu-id="d21d0-109">Чтобы изменить один из обязательных параметров, выберите этот параметр в поле **Существующие параметры** , измените значения в поле **Укажите параметр запуска** и нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="d21d0-109">To modify one of the required parameters, select the parameter in the **Existing parameters** box, change the values in the **Specify a startup parameter** box, and then click **Update**.</span></span>  
  
 <span data-ttu-id="d21d0-110">**Существующие параметры**</span><span class="sxs-lookup"><span data-stu-id="d21d0-110">**Existing parameters**</span></span>  
 <span data-ttu-id="d21d0-111">Чтобы удалить параметр, выберите его и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d21d0-111">To remove a parameter, select a parameter, and then click **Remove**.</span></span>  
  
## <a name="parameter-format"></a><span data-ttu-id="d21d0-112">Формат параметров</span><span class="sxs-lookup"><span data-stu-id="d21d0-112">Parameter Format</span></span>  
 <span data-ttu-id="d21d0-113">Не вводите разделитель между параметрами.</span><span class="sxs-lookup"><span data-stu-id="d21d0-113">Do not enter a separator between parameters.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d21d0-114">добавит разделитель автоматически.</span><span class="sxs-lookup"><span data-stu-id="d21d0-114">Configuration Manager automatically adds the separator.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d21d0-115">существуют следующие требования к параметрам.</span><span class="sxs-lookup"><span data-stu-id="d21d0-115">Configuration Manager enforces the following parameter requirements.</span></span>  
  
-   <span data-ttu-id="d21d0-116">Начальные и конечные пробелы любого параметра запуска отсекаются.</span><span class="sxs-lookup"><span data-stu-id="d21d0-116">Leading and trailing spaces are trimmed from any startup parameter.</span></span>  
  
-   <span data-ttu-id="d21d0-117">Каждый параметр запуска начинается с символа "—" (тире), вторым символом является буква.</span><span class="sxs-lookup"><span data-stu-id="d21d0-117">All startup parameters start with a - (dash) and the second value is a letter.</span></span>  
  
## <a name="required-parameters"></a><span data-ttu-id="d21d0-118">Необходимые параметры</span><span class="sxs-lookup"><span data-stu-id="d21d0-118">Required Parameters</span></span>  
 <span data-ttu-id="d21d0-119">Следующие параметры обязательны:</span><span class="sxs-lookup"><span data-stu-id="d21d0-119">The following parameters are required.</span></span> <span data-ttu-id="d21d0-120">Их можно изменять, но не удалять.</span><span class="sxs-lookup"><span data-stu-id="d21d0-120">They can be changed but not removed.</span></span>  
  
-   <span data-ttu-id="d21d0-121">-d представляет путь к файлу **master.mdf** (файл данных базы данных master).</span><span class="sxs-lookup"><span data-stu-id="d21d0-121">-d is the path of the **master.mdf** file (the master database data file).</span></span>  
  
-   <span data-ttu-id="d21d0-122">-l представляет путь к файлу **master.ldf** (файл журнала базы данных master).</span><span class="sxs-lookup"><span data-stu-id="d21d0-122">-l is the path of the **master.ldf** file (the master database log file).</span></span>  
  
-   <span data-ttu-id="d21d0-123">-e представляет путь к файлам журнала ошибок [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d21d0-123">-e is the path of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log files.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="d21d0-124">Если параметры пути неверны, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может не запуститься.</span><span class="sxs-lookup"><span data-stu-id="d21d0-124">If the file path parameters are incorrect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might not start.</span></span>  
  
 <span data-ttu-id="d21d0-125">Подробнее о перемещении базы данных master см. в разделе «Перемещение системных баз данных» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d21d0-125">For more information about how to move the master database, see the topic "Moving System Databases" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="optional-parameters"></a><span data-ttu-id="d21d0-126">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="d21d0-126">Optional Parameters</span></span>  
 <span data-ttu-id="d21d0-127">Все поддерживаемые параметры запуска описаны в разделе «Использование параметров запуска службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] » электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d21d0-127">All of the supported startup parameters are described in the topic "Using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Service Startup Options," in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="d21d0-128">Параметр запуска -T*trace#* показывает, что экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен запускаться с указанным флагом трассировки (*trace#* ).</span><span class="sxs-lookup"><span data-stu-id="d21d0-128">A startup parameter of -T*trace#* indicates that an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should be started with a specified trace flag (*trace#*) in effect.</span></span> <span data-ttu-id="d21d0-129">Флаги трассировки используются для запуска сервера в нестандартном режиме.</span><span class="sxs-lookup"><span data-stu-id="d21d0-129">Trace flags are used to start the server with nonstandard behavior.</span></span> <span data-ttu-id="d21d0-130">Подробнее о флагах трассировки см. в разделе "Флаги трассировки ([!INCLUDE[tsql](../../includes/tsql-md.md)])" электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d21d0-130">For more information about trace flags, see the topic "Trace Flags ([!INCLUDE[tsql](../../includes/tsql-md.md)])" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="d21d0-131">Описание некоторых дополнительных недокументированных параметров запуска и флагов трассировки можно найти в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d21d0-131">You might see additional undocumented startup parameters and trace flags described on the Internet.</span></span> <span data-ttu-id="d21d0-132">Недокументированные параметры запуска и флаги трассировки создаются для решения нетиповых задач и создания определенных условий, необходимых для тестирования.</span><span class="sxs-lookup"><span data-stu-id="d21d0-132">Undocumented startup parameters and trace flags are created to address uncommon problems or to force certain conditions required for testing.</span></span> <span data-ttu-id="d21d0-133">Использование недокументированных параметров запуска может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="d21d0-133">Using undocumented startup parameters can have unexpected results.</span></span> <span data-ttu-id="d21d0-134">Используйте недокументированные параметры только по указанию службы поддержки пользователей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d21d0-134">Do not use undocumented parameters unless directed by Microsoft Customer Support Services.</span></span>  
  
 <span data-ttu-id="d21d0-135">В следующем списке описаны самые распространенные необязательные параметры.</span><span class="sxs-lookup"><span data-stu-id="d21d0-135">The following list describes some common optional parameters.</span></span>  
  
|<span data-ttu-id="d21d0-136">Параметр</span><span class="sxs-lookup"><span data-stu-id="d21d0-136">Parameter</span></span>|<span data-ttu-id="d21d0-137">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="d21d0-137">Short description</span></span>|  
|---------------|-----------------------|  
|<span data-ttu-id="d21d0-138">-M</span><span class="sxs-lookup"><span data-stu-id="d21d0-138">-m</span></span>|<span data-ttu-id="d21d0-139">Запускает экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в однопользовательском режиме.</span><span class="sxs-lookup"><span data-stu-id="d21d0-139">Starts an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode.</span></span>|  
|<span data-ttu-id="d21d0-140">-T1204</span><span class="sxs-lookup"><span data-stu-id="d21d0-140">-T1204</span></span>|<span data-ttu-id="d21d0-141">Возвращает ресурсы и типы блокировки, участвующие во взаимоблокировке и текущую команду, на которую влияет взаимоблокировка.</span><span class="sxs-lookup"><span data-stu-id="d21d0-141">Returns the resources and types of locks participating in a deadlock and also the current command affected.</span></span>|  
|<span data-ttu-id="d21d0-142">-T1224</span><span class="sxs-lookup"><span data-stu-id="d21d0-142">-T1224</span></span>|<span data-ttu-id="d21d0-143">Отключает укрупнение блокировок на основе количества блокировок.</span><span class="sxs-lookup"><span data-stu-id="d21d0-143">Disables lock escalation based on the number of locks.</span></span>|  
|<span data-ttu-id="d21d0-144">-T3608</span><span class="sxs-lookup"><span data-stu-id="d21d0-144">-T3608</span></span>|<span data-ttu-id="d21d0-145">Запрещает автоматический запуск [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и восстановление любых баз данных, кроме базы данных master.</span><span class="sxs-lookup"><span data-stu-id="d21d0-145">Prevents [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from automatically starting and recovering any database except the master database.</span></span>|  
|<span data-ttu-id="d21d0-146">-T7806</span><span class="sxs-lookup"><span data-stu-id="d21d0-146">-T7806</span></span>|<span data-ttu-id="d21d0-147">Включает применение выделенных административных соединений (DAC) в [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d21d0-147">Enables a dedicated administrator connection (DAC) on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>|  
  
> [!CAUTION]  
>  <span data-ttu-id="d21d0-148">Некоторые необязательные параметры могут изменить поведение сервера и повлиять на его производительность.</span><span class="sxs-lookup"><span data-stu-id="d21d0-148">Some optional parameters can change server behavior and may affect performance.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="d21d0-149">Разрешения</span><span class="sxs-lookup"><span data-stu-id="d21d0-149">Permissions</span></span>  
 <span data-ttu-id="d21d0-150">Доступ к этой странице имеют только пользователи, уполномоченные изменять соответствующие записи в реестре.</span><span class="sxs-lookup"><span data-stu-id="d21d0-150">Use of this page is restricted to users who can change the related entries in the registry.</span></span> <span data-ttu-id="d21d0-151">Это следующие пользователи.</span><span class="sxs-lookup"><span data-stu-id="d21d0-151">This includes the following users.</span></span>  
  
-   <span data-ttu-id="d21d0-152">Члены локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="d21d0-152">Members of the local administrators group.</span></span>  
  
-   <span data-ttu-id="d21d0-153">Учетная запись домена, используемая [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], если компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] настроен для работы под определенной учетной записью домена.</span><span class="sxs-lookup"><span data-stu-id="d21d0-153">The domain account that is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is configured to run under a domain account.</span></span>  
  
## <a name="books-online-references"></a><span data-ttu-id="d21d0-154">Электронная документация</span><span class="sxs-lookup"><span data-stu-id="d21d0-154">Books Online References</span></span>  
 <span data-ttu-id="d21d0-155">Дополнительные сведения о параметрах запуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в статье "Инструкции. Настройка параметров запуска сервера (диспетчер конфигурации[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] )" в электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d21d0-155">For additional information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup parameters, see "How to: Configure Server Startup Options ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
