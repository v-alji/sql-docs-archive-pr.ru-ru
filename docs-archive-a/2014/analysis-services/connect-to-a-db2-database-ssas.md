---
title: Подключение к базе данных DB2 (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndb2db.f1
ms.assetid: eeef3697-a4fd-4263-ba7e-f86afa1f46cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: f36a583956c1fe75bb0a6acd827d083a6c7562f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656741"
---
# <a name="connect-to-a-db2-database-ssas"></a><span data-ttu-id="f3c26-102">Соединение с базой данных DB2 (SSAS)</span><span class="sxs-lookup"><span data-stu-id="f3c26-102">Connect to a DB2 Database (SSAS)</span></span>
  <span data-ttu-id="f3c26-103">Эта страница **Мастера импорта таблиц** используется для задания параметров подключения к базе данных DB2.</span><span class="sxs-lookup"><span data-stu-id="f3c26-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a DB2 database.</span></span> <span data-ttu-id="f3c26-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="f3c26-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="f3c26-105">Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="f3c26-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3c26-106">При выборе базы данных на этой странице используются учетные данные указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f3c26-106">When selecting a database in this page, the credentials of the user specified are used.</span></span> <span data-ttu-id="f3c26-107">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="f3c26-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f3c26-108">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="f3c26-108">UI element list</span></span>  
 <span data-ttu-id="f3c26-109">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="f3c26-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="f3c26-110">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="f3c26-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="f3c26-111">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="f3c26-111">This is a required field.</span></span>  
  
 <span data-ttu-id="f3c26-112">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="f3c26-112">**Server name**</span></span>  
 <span data-ttu-id="f3c26-113">Введите или выберите экземпляр сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="f3c26-113">Type or select the server instance to connect to.</span></span>  
  
 <span data-ttu-id="f3c26-114">**User name**</span><span class="sxs-lookup"><span data-stu-id="f3c26-114">**User name**</span></span>  
 <span data-ttu-id="f3c26-115">Укажите имя пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="f3c26-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="f3c26-116">Это имя пользователя используется при создании строки подключения для источника данных.</span><span class="sxs-lookup"><span data-stu-id="f3c26-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="f3c26-117">Эти учетные данные также используются при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта.</span><span class="sxs-lookup"><span data-stu-id="f3c26-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="f3c26-118">Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.</span><span class="sxs-lookup"><span data-stu-id="f3c26-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="f3c26-119">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="f3c26-119">**Password**</span></span>  
 <span data-ttu-id="f3c26-120">Укажите пароль для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="f3c26-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="f3c26-121">**Сохранить мой пароль**</span><span class="sxs-lookup"><span data-stu-id="f3c26-121">**Save my password**</span></span>  
 <span data-ttu-id="f3c26-122">Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="f3c26-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="f3c26-123">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="f3c26-123">**Database name**</span></span>  
 <span data-ttu-id="f3c26-124">Выберите базу данных из списка баз данных.</span><span class="sxs-lookup"><span data-stu-id="f3c26-124">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="f3c26-125">**Коллекция пакетов**</span><span class="sxs-lookup"><span data-stu-id="f3c26-125">**Package Collection**</span></span>  
 <span data-ttu-id="f3c26-126">Укажите имя коллекции для пакетов DB2.</span><span class="sxs-lookup"><span data-stu-id="f3c26-126">Specify the name of the collection for the DB2 packages.</span></span> <span data-ttu-id="f3c26-127">Поставщик использует пакеты для выполнения инструкций SQL и вызова хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="f3c26-127">A provider uses packages to issue SQL statements and call stored procedures.</span></span>  
  
 <span data-ttu-id="f3c26-128">**Схема по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="f3c26-128">**Default Schema**</span></span>  
 <span data-ttu-id="f3c26-129">Укажите имя схемы по умолчанию для выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="f3c26-129">Specify the name of the default schema for the selected database.</span></span>  
  
 <span data-ttu-id="f3c26-130">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="f3c26-130">**Advanced**</span></span>  
 <span data-ttu-id="f3c26-131">Задание дополнительных свойств соединения с помощью диалогового окна « **Задание дополнительных свойств** ».</span><span class="sxs-lookup"><span data-stu-id="f3c26-131">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="f3c26-132">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="f3c26-132">**Test Connection**</span></span>  
 <span data-ttu-id="f3c26-133">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="f3c26-133">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="f3c26-134">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="f3c26-134">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
