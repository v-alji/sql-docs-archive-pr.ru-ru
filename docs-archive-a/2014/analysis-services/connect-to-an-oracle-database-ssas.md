---
title: Подключение к Oracle Database (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connoracledb.f1
ms.assetid: 9bd177fb-8539-46cd-bf96-189ade52c2a1
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0260983f5060ecba7f618975e805ff63c507d5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656716"
---
# <a name="connect-to-an-oracle-database-ssas"></a><span data-ttu-id="072a1-102">Соединение с базой данных Oracle (SSAS)</span><span class="sxs-lookup"><span data-stu-id="072a1-102">Connect to an Oracle Database (SSAS)</span></span>
  <span data-ttu-id="072a1-103">Эта страница **мастера импорта таблиц** используется для задания параметров для соединения с базой данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="072a1-103">This page of the **Table Import Wizard** enables you to specify settings to connect to an Oracle database.</span></span> <span data-ttu-id="072a1-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="072a1-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="072a1-105">Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.</span><span class="sxs-lookup"><span data-stu-id="072a1-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="072a1-106">При выборе базы данных на этой странице используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="072a1-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="072a1-107">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="072a1-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="072a1-108">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="072a1-108">UI element list</span></span>  
 <span data-ttu-id="072a1-109">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="072a1-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="072a1-110">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="072a1-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="072a1-111">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="072a1-111">This is a required field.</span></span>  
  
 <span data-ttu-id="072a1-112">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="072a1-112">**Server name**</span></span>  
 <span data-ttu-id="072a1-113">Введите или выберите имя экземпляра сервера для подключения.</span><span class="sxs-lookup"><span data-stu-id="072a1-113">Type or select the name of the server instance to connect to.</span></span>  
  
 <span data-ttu-id="072a1-114">**User name**</span><span class="sxs-lookup"><span data-stu-id="072a1-114">**User name**</span></span>  
 <span data-ttu-id="072a1-115">Укажите имя пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="072a1-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="072a1-116">Это имя пользователя используется при создании строки подключения для источника данных.</span><span class="sxs-lookup"><span data-stu-id="072a1-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="072a1-117">Эти учетные данные также используются при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта.</span><span class="sxs-lookup"><span data-stu-id="072a1-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="072a1-118">Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.</span><span class="sxs-lookup"><span data-stu-id="072a1-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="072a1-119">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="072a1-119">**Password**</span></span>  
 <span data-ttu-id="072a1-120">Укажите пароль для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="072a1-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="072a1-121">**Сохранить мой пароль**</span><span class="sxs-lookup"><span data-stu-id="072a1-121">**Save my password**</span></span>  
 <span data-ttu-id="072a1-122">Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="072a1-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="072a1-123">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="072a1-123">**Advanced**</span></span>  
 <span data-ttu-id="072a1-124">Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .</span><span class="sxs-lookup"><span data-stu-id="072a1-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="072a1-125">Дополнительные сведения см. в разделе [Установка дополнительных свойств (SSAS)](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="072a1-125">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="072a1-126">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="072a1-126">**Test Connection**</span></span>  
 <span data-ttu-id="072a1-127">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="072a1-127">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="072a1-128">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="072a1-128">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
