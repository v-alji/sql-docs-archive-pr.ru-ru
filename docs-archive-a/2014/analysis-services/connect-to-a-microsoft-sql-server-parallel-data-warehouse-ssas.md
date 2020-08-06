---
title: Подключение к Microsoft SQL Server Parallel Data Warehouse (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlparadatawh.f1
ms.assetid: 98c879ee-7257-40c9-bc85-6766bd3b4885
author: minewiskan
ms.author: owend
ms.openlocfilehash: 082d6b34077d1bde11b527d3bfff907073eed16e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656728"
---
# <a name="connect-to-a-microsoft-sql-server-parallel-data-warehouse-ssas"></a><span data-ttu-id="785d0-102">Подключение к параллельному хранилищу данных Microsoft SQL Server (SSAS)</span><span class="sxs-lookup"><span data-stu-id="785d0-102">Connect to a Microsoft SQL Server Parallel Data Warehouse (SSAS)</span></span>
  <span data-ttu-id="785d0-103">Эта страница **мастера импорта таблиц** позволяет указать параметры подключения к Microsoft SQL Server Parallel Data Warehouse (PDW).</span><span class="sxs-lookup"><span data-stu-id="785d0-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server Parallel Data Warehouse (PDW).</span></span> <span data-ttu-id="785d0-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="785d0-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="785d0-105">SQL Server PDW — высокомасштабируемое устройство, которое отличается высокой производительностью при низкой цене благодаря расширенной параллельной обработке.</span><span class="sxs-lookup"><span data-stu-id="785d0-105">SQL Server PDW is a highly scalable appliance that delivers performance at low cost through massively parallel processing.</span></span> <span data-ttu-id="785d0-106">Дополнительные сведения о SQL Server PDW см. на веб-сайте [Параллельное хранилище данных SQL Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=150895).</span><span class="sxs-lookup"><span data-stu-id="785d0-106">For more information about SQL Server PDW, see the web site [SQL Server 2008 R2 Parallel Data Warehouse](https://go.microsoft.com/fwlink/?LinkId=150895).</span></span> <span data-ttu-id="785d0-107">Подключение к хранилищу данных выполняется с помощью проверки подлинности SQL Server.</span><span class="sxs-lookup"><span data-stu-id="785d0-107">You connect to the data warehouse by using SQL Server Authentication.</span></span> <span data-ttu-id="785d0-108">Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="785d0-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="785d0-109">При выборе базы данных на этой странице используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="785d0-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="785d0-110">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="785d0-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="785d0-111">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="785d0-111">UI element list</span></span>  
 <span data-ttu-id="785d0-112">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="785d0-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="785d0-113">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="785d0-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="785d0-114">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="785d0-114">This is a required field.</span></span>  
  
 <span data-ttu-id="785d0-115">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="785d0-115">**Server name**</span></span>  
 <span data-ttu-id="785d0-116">Введите имя или IP-адрес сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="785d0-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="785d0-117">**User name**</span><span class="sxs-lookup"><span data-stu-id="785d0-117">**User name**</span></span>  
 <span data-ttu-id="785d0-118">Укажите имя пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="785d0-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="785d0-119">Это имя пользователя используется при создании строки подключения для источника данных.</span><span class="sxs-lookup"><span data-stu-id="785d0-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="785d0-120">Эти учетные данные также используются при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта.</span><span class="sxs-lookup"><span data-stu-id="785d0-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="785d0-121">Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.</span><span class="sxs-lookup"><span data-stu-id="785d0-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="785d0-122">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="785d0-122">**Password**</span></span>  
 <span data-ttu-id="785d0-123">Укажите пароль для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="785d0-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="785d0-124">**Сохранить мой пароль**</span><span class="sxs-lookup"><span data-stu-id="785d0-124">**Save my password**</span></span>  
 <span data-ttu-id="785d0-125">Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="785d0-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="785d0-126">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="785d0-126">**Database name**</span></span>  
 <span data-ttu-id="785d0-127">Выберите базу данных из списка баз данных.</span><span class="sxs-lookup"><span data-stu-id="785d0-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="785d0-128">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="785d0-128">**Advanced**</span></span>  
 <span data-ttu-id="785d0-129">Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .</span><span class="sxs-lookup"><span data-stu-id="785d0-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="785d0-130">Дополнительные сведения см. в разделе [Установка дополнительных свойств (SSAS)](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="785d0-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="785d0-131">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="785d0-131">**Test Connection**</span></span>  
 <span data-ttu-id="785d0-132">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="785d0-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="785d0-133">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="785d0-133">A message displays and indicates whether the connection is successful.</span></span>  
  
  
