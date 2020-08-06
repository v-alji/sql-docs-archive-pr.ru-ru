---
title: Подключение к базе данных Microsoft SQL Server (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserverdb.f1
ms.assetid: 6ebfe029-dbba-4f0d-a556-328e79ef629f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 64267cd65836cf8e6c8d8b26a177de595894b601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656735"
---
# <a name="connect-to-a-microsoft-sql-server-database-ssas"></a><span data-ttu-id="8bc87-102">Соединение с базой данных Microsoft SQL Server (SSAS)</span><span class="sxs-lookup"><span data-stu-id="8bc87-102">Connect to a Microsoft SQL Server Database (SSAS)</span></span>
  <span data-ttu-id="8bc87-103">Эта страница **мастера импорта таблиц** используется для задания параметров подключения к базе данных Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bc87-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server database.</span></span> <span data-ttu-id="8bc87-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="8bc87-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="8bc87-105">Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="8bc87-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8bc87-106">При выборе базы данных на этой странице используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="8bc87-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="8bc87-107">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="8bc87-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="8bc87-108">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="8bc87-108">UI element list</span></span>  
 <span data-ttu-id="8bc87-109">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="8bc87-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="8bc87-110">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="8bc87-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="8bc87-111">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="8bc87-111">This is a required field.</span></span>  
  
 <span data-ttu-id="8bc87-112">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="8bc87-112">**Server name**</span></span>  
 <span data-ttu-id="8bc87-113">Выберите имя или введите имя или IP-адрес экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , к которому необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="8bc87-113">Select the name, or type the name or IP address, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to.</span></span>  
  
 <span data-ttu-id="8bc87-114">Для указания локального сервера можно использовать точку (.), (local) или localhost.</span><span class="sxs-lookup"><span data-stu-id="8bc87-114">You can use a period (.), (local), or localhost to indicate the local server.</span></span>  
  
 <span data-ttu-id="8bc87-115">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="8bc87-115">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="8bc87-116">Укажите, следует ли использовать проверку подлинности Windows для подключения к экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bc87-116">Specify whether Windows Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8bc87-117">Режим проверки подлинности Windows позволяет подключаться с учетной записью пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="8bc87-117">Windows Authentication mode enables a user to connect by using a Windows user account.</span></span> <span data-ttu-id="8bc87-118">При возможности используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="8bc87-118">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="8bc87-119">При использовании проверки подлинности Windows учетные данные текущего пользователя задействованы при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта.</span><span class="sxs-lookup"><span data-stu-id="8bc87-119">When Windows Authentication is used, the credentials of the current user are used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="8bc87-120">Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.</span><span class="sxs-lookup"><span data-stu-id="8bc87-120">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation information page are used instead.</span></span>  
  
 <span data-ttu-id="8bc87-121">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8bc87-121">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="8bc87-122">Укажите, следует ли использовать проверку подлинности SQL Server для подключения к экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bc87-122">Specify whether SQL Server Authentication is used to connect to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8bc87-123">При проверке подлинности SQL Server последний проверяет существование учетной записи входа SQL Server и совпадение указанного пароля с ранее сохраненным паролем.</span><span class="sxs-lookup"><span data-stu-id="8bc87-123">With SQL Server Authentication, SQL Server performs the authentication itself by checking to see if a SQL Server login account has been set up and if the specified password matches the one previously recorded.</span></span>  
  
 <span data-ttu-id="8bc87-124">Проверка подлинности SQL Server используется для создания строки подключения для источника данных.</span><span class="sxs-lookup"><span data-stu-id="8bc87-124">SQL Server Authentication is used to construct the connection string for the data source.</span></span> <span data-ttu-id="8bc87-125">Эти учетные данные также используются при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта.</span><span class="sxs-lookup"><span data-stu-id="8bc87-125">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="8bc87-126">Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.</span><span class="sxs-lookup"><span data-stu-id="8bc87-126">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="8bc87-127">**User name**</span><span class="sxs-lookup"><span data-stu-id="8bc87-127">**User name**</span></span>  
 <span data-ttu-id="8bc87-128">Укажите имя пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="8bc87-128">Specify a user name for the database connection.</span></span> <span data-ttu-id="8bc87-129">Этот параметр доступен только при выборе проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bc87-129">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="8bc87-130">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="8bc87-130">**Password**</span></span>  
 <span data-ttu-id="8bc87-131">Укажите пароль для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="8bc87-131">Specify a password for the database connection.</span></span> <span data-ttu-id="8bc87-132">Этот параметр доступен для редактирования только при подключении с использованием проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bc87-132">This option is only editable if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="8bc87-133">**Сохранить мой пароль**</span><span class="sxs-lookup"><span data-stu-id="8bc87-133">**Save my password**</span></span>  
 <span data-ttu-id="8bc87-134">Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="8bc87-134">Specify whether the password you have entered in the **Password** box is stored.</span></span> <span data-ttu-id="8bc87-135">Этот параметр доступен только при выборе проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bc87-135">This option is only available if you have selected to connect using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="8bc87-136">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="8bc87-136">**Database name**</span></span>  
 <span data-ttu-id="8bc87-137">Выберите базу данных из списка баз данных.</span><span class="sxs-lookup"><span data-stu-id="8bc87-137">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="8bc87-138">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="8bc87-138">**Advanced**</span></span>  
 <span data-ttu-id="8bc87-139">Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .</span><span class="sxs-lookup"><span data-stu-id="8bc87-139">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="8bc87-140">Дополнительные сведения см. в разделе [Установка дополнительных свойств (SSAS)](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="8bc87-140">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="8bc87-141">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="8bc87-141">**Test Connection**</span></span>  
 <span data-ttu-id="8bc87-142">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="8bc87-142">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="8bc87-143">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="8bc87-143">A message is displayed indicating whether the connection was successful.</span></span>  
  
  
