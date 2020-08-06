---
title: Подключение к Analysis Services Microsoft SQL Server (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserveras.f1
ms.assetid: 7f3244ee-b690-471c-893d-68e361c2d416
author: minewiskan
ms.author: owend
ms.openlocfilehash: 984979480e3ea54c86c986fa6dd9771aaf879cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656712"
---
# <a name="connect-to-microsoft-sql-server-analysis-services-ssas"></a><span data-ttu-id="d94db-102">Соединение со службами Microsoft SQL Server Analysis Services (SSAS)</span><span class="sxs-lookup"><span data-stu-id="d94db-102">Connect to Microsoft SQL Server Analysis Services (SSAS)</span></span>
  <span data-ttu-id="d94db-103">На этой странице **мастера импорта таблиц** можно указать параметры импорта данных из Microsoft SQL Server Analysis Services куба или книги PowerPivot, размещенной в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d94db-103">This page of the **Table Import Wizard** enables you to specify settings to import data from a Microsoft SQL Server Analysis Services cube or a PowerPivot workbook that is hosted on SharePoint.</span></span> <span data-ttu-id="d94db-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="d94db-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="d94db-105">Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="d94db-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d94db-106">При выборе базы данных на этой странице используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="d94db-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="d94db-107">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="d94db-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d94db-108">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="d94db-108">UI element list</span></span>  
 <span data-ttu-id="d94db-109">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="d94db-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="d94db-110">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="d94db-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="d94db-111">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d94db-111">This is a required field.</span></span>  
  
 <span data-ttu-id="d94db-112">**Сервер или имя файла**</span><span class="sxs-lookup"><span data-stu-id="d94db-112">**Server or File Name**</span></span>  
 <span data-ttu-id="d94db-113">Введите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="d94db-113">Enter one of the following:</span></span>  
  
-   <span data-ttu-id="d94db-114">Введите имя или IP-адрес сервера служб SQL Server Analysis Services, с которым необходимо установить соединение.</span><span class="sxs-lookup"><span data-stu-id="d94db-114">Type the name or IP address of the SQL Server Analysis Services server to connect to.</span></span>  
  
     <span data-ttu-id="d94db-115">Для указания локального сервера можно использовать точку (.), (local) или localhost.</span><span class="sxs-lookup"><span data-stu-id="d94db-115">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
-   <span data-ttu-id="d94db-116">Введите URL-адрес книги PowerPivot, опубликованной на сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d94db-116">Type the URL of a PowerPivot workbook that is published to SharePoint.</span></span>  
  
 <span data-ttu-id="d94db-117">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="d94db-117">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="d94db-118">Укажите, следует ли использовать проверку подлинности Windows для подключения к серверу служб SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d94db-118">Specify whether Windows Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="d94db-119">Режим проверки подлинности Windows позволяет подключаться с учетной записью Windows.</span><span class="sxs-lookup"><span data-stu-id="d94db-119">Windows Authentication mode enables a user to connect through a Windows user account.</span></span> <span data-ttu-id="d94db-120">При возможности используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d94db-120">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="d94db-121">При использовании проверки подлинности Windows учетные данные текущего пользователя задействованы при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта.</span><span class="sxs-lookup"><span data-stu-id="d94db-121">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="d94db-122">Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.</span><span class="sxs-lookup"><span data-stu-id="d94db-122">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="d94db-123">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d94db-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="d94db-124">Укажите, следует ли использовать проверку подлинности SQL Server для подключения к серверу служб SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d94db-124">Specify whether SQL Server Authentication is used to connect to a SQL Server Analysis Services server.</span></span>  
  
 <span data-ttu-id="d94db-125">При проверке подлинности SQL Server последний проверяет существование учетной записи входа SQL Server и совпадение указанного пароля с ранее сохраненным паролем.</span><span class="sxs-lookup"><span data-stu-id="d94db-125">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="d94db-126">Проверка подлинности SQL Server используется для создания строки подключения для источника данных.</span><span class="sxs-lookup"><span data-stu-id="d94db-126">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="d94db-127">Эти учетные данные также используются при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта.</span><span class="sxs-lookup"><span data-stu-id="d94db-127">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="d94db-128">Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.</span><span class="sxs-lookup"><span data-stu-id="d94db-128">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="d94db-129">**User name**</span><span class="sxs-lookup"><span data-stu-id="d94db-129">**User name**</span></span>  
 <span data-ttu-id="d94db-130">Укажите имя пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="d94db-130">Specify a user name for the database connection.</span></span> <span data-ttu-id="d94db-131">Этот параметр доступен только при соединении с использованием метода проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d94db-131">This option is only available if you have selected to connect using Windows Authentication.</span></span>  
  
 <span data-ttu-id="d94db-132">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="d94db-132">**Password**</span></span>  
 <span data-ttu-id="d94db-133">Укажите пароль для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="d94db-133">Specify a password for the database connection.</span></span> <span data-ttu-id="d94db-134">Этот параметр доступен для редактирования только при подключении с использованием проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d94db-134">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="d94db-135">**Сохранить мой пароль**</span><span class="sxs-lookup"><span data-stu-id="d94db-135">**Save my password**</span></span>  
 <span data-ttu-id="d94db-136">Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="d94db-136">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="d94db-137">Этот параметр доступен только при выборе проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d94db-137">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="d94db-138">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="d94db-138">**Database name**</span></span>  
 <span data-ttu-id="d94db-139">Выберите базу данных из списка баз данных.</span><span class="sxs-lookup"><span data-stu-id="d94db-139">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="d94db-140">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="d94db-140">**Advanced**</span></span>  
 <span data-ttu-id="d94db-141">Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .</span><span class="sxs-lookup"><span data-stu-id="d94db-141">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="d94db-142">Дополнительные сведения см. в разделе [Установка дополнительных свойств (SSAS)](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="d94db-142">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="d94db-143">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="d94db-143">**Test Connection**</span></span>  
 <span data-ttu-id="d94db-144">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="d94db-144">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="d94db-145">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="d94db-145">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
