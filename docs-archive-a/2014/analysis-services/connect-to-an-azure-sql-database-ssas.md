---
title: Подключение к базе данных SQL Azure (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlazure.f1
ms.assetid: 4e0344e9-1822-4698-ad22-05f1f341ced7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91ae6f0f5ab95d3013b6348bd43ddb746fff1c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656725"
---
# <a name="connect-to-an-azure-sql-database-ssas"></a><span data-ttu-id="0595e-102">Подключение к базе данных SQL Azure (SSAS)</span><span class="sxs-lookup"><span data-stu-id="0595e-102">Connect to an Azure SQL Database (SSAS)</span></span>
  <span data-ttu-id="0595e-103">Эта страница **мастера импорта таблиц** позволяет установить соединение с [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0595e-103">This page of the **Table Import Wizard** enables you to connect to a [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="0595e-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="0595e-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0595e-105">При подключении к набору данных Azure DataMarket см. раздел [Соединение с отчетом или веб-каналом данных (SSAS)](connect-to-a-report-or-data-feed-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="0595e-105">If you are connecting to an Azure DataMarket dataset, see [Connect to a Report or Data Feed &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span></span>  
  
 <span data-ttu-id="0595e-106">[!INCLUDE[ssSDS](../includes/sssds-md.md)] — это размещаемая реляционная база данных, соединение с которой устанавливается с проверкой подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0595e-106">The [!INCLUDE[ssSDS](../includes/sssds-md.md)] is a hosted, relational database that you connect to by using SQL Server Authentication.</span></span> <span data-ttu-id="0595e-107">Дополнительные сведения о [!INCLUDE[ssSDS](../includes/sssds-md.md)]см. на веб-сайте [SQL Database](https://go.microsoft.com/fwlink/?LinkID=157856).</span><span class="sxs-lookup"><span data-stu-id="0595e-107">For more information about [!INCLUDE[ssSDS](../includes/sssds-md.md)], see the web site [SQL Database](https://go.microsoft.com/fwlink/?LinkID=157856).</span></span> <span data-ttu-id="0595e-108">Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="0595e-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0595e-109">При выборе базы данных на этой странице используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="0595e-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="0595e-110">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="0595e-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="0595e-111">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0595e-111">UI element list</span></span>  
 <span data-ttu-id="0595e-112">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="0595e-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="0595e-113">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="0595e-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="0595e-114">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="0595e-114">This is a required field.</span></span>  
  
 <span data-ttu-id="0595e-115">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="0595e-115">**Server name**</span></span>  
 <span data-ttu-id="0595e-116">Введите имя или IP-адрес сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="0595e-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="0595e-117">**User name**</span><span class="sxs-lookup"><span data-stu-id="0595e-117">**User name**</span></span>  
 <span data-ttu-id="0595e-118">Укажите имя пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="0595e-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="0595e-119">Это имя пользователя используется при создании строки подключения для источника данных.</span><span class="sxs-lookup"><span data-stu-id="0595e-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="0595e-120">Эти учетные данные также используются при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта.</span><span class="sxs-lookup"><span data-stu-id="0595e-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="0595e-121">Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.</span><span class="sxs-lookup"><span data-stu-id="0595e-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="0595e-122">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="0595e-122">**Password**</span></span>  
 <span data-ttu-id="0595e-123">Укажите пароль для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="0595e-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="0595e-124">**Сохранить мой пароль**</span><span class="sxs-lookup"><span data-stu-id="0595e-124">**Save my password**</span></span>  
 <span data-ttu-id="0595e-125">Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="0595e-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="0595e-126">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="0595e-126">**Database name**</span></span>  
 <span data-ttu-id="0595e-127">Выберите базу данных из списка баз данных.</span><span class="sxs-lookup"><span data-stu-id="0595e-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="0595e-128">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="0595e-128">**Advanced**</span></span>  
 <span data-ttu-id="0595e-129">Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .</span><span class="sxs-lookup"><span data-stu-id="0595e-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="0595e-130">Дополнительные сведения см. в разделе [Установка дополнительных свойств (SSAS)](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="0595e-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="0595e-131">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="0595e-131">**Test Connection**</span></span>  
 <span data-ttu-id="0595e-132">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="0595e-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="0595e-133">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="0595e-133">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
