---
title: Подключение к базе данных Informix (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conninformixdb.f1
ms.assetid: b01d537c-1c04-4d7d-9146-051c249b08e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 35c7263ce9b0432802cd24b6df9165151b279d83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656729"
---
# <a name="connect-to-an-informix-database-ssas"></a><span data-ttu-id="ee46f-102">Соединени с базой данных Informix (SSAS)</span><span class="sxs-lookup"><span data-stu-id="ee46f-102">Connect to an Informix Database (SSAS)</span></span>
  <span data-ttu-id="ee46f-103">Эта страница **мастера импорта таблиц** используется для задания параметров для соединения с базой данных Informix.</span><span class="sxs-lookup"><span data-stu-id="ee46f-103">This page of the **Table Import Wizard** enables you to specify settings to connect to an Informix database.</span></span> <span data-ttu-id="ee46f-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="ee46f-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="ee46f-105">Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="ee46f-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee46f-106">При выборе базы данных на этой странице используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="ee46f-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="ee46f-107">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="ee46f-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ee46f-108">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="ee46f-108">UI element list</span></span>  
 <span data-ttu-id="ee46f-109">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="ee46f-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="ee46f-110">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="ee46f-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="ee46f-111">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ee46f-111">This is a required field.</span></span>  
  
 <span data-ttu-id="ee46f-112">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="ee46f-112">**Server name**</span></span>  
 <span data-ttu-id="ee46f-113">Введите или выберите имя экземпляра сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="ee46f-113">Type or select the name of the server instance to connect to.</span></span>  
  
 <span data-ttu-id="ee46f-114">**User name**</span><span class="sxs-lookup"><span data-stu-id="ee46f-114">**User name**</span></span>  
 <span data-ttu-id="ee46f-115">Укажите имя пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="ee46f-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="ee46f-116">Это имя пользователя используется при создании строки подключения для источника данных.</span><span class="sxs-lookup"><span data-stu-id="ee46f-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="ee46f-117">Эти учетные данные также используются при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта.</span><span class="sxs-lookup"><span data-stu-id="ee46f-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="ee46f-118">Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.</span><span class="sxs-lookup"><span data-stu-id="ee46f-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="ee46f-119">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="ee46f-119">**Password**</span></span>  
 <span data-ttu-id="ee46f-120">Укажите пароль для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="ee46f-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="ee46f-121">**Сохранить мой пароль**</span><span class="sxs-lookup"><span data-stu-id="ee46f-121">**Save my password**</span></span>  
 <span data-ttu-id="ee46f-122">Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="ee46f-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="ee46f-123">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="ee46f-123">**Advanced**</span></span>  
 <span data-ttu-id="ee46f-124">Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .</span><span class="sxs-lookup"><span data-stu-id="ee46f-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="ee46f-125">Дополнительные сведения см. в разделе [Установка дополнительных свойств (SSAS)](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="ee46f-125">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="ee46f-126">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="ee46f-126">**Test Connection**</span></span>  
 <span data-ttu-id="ee46f-127">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="ee46f-127">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="ee46f-128">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="ee46f-128">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
