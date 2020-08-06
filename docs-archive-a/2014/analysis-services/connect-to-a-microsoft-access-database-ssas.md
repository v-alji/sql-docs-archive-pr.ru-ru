---
title: Подключение к базе данных Microsoft Access (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connaccessdb.f1
ms.assetid: 9fa81839-dd8b-41d3-915e-c774a707ed53
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb180a754b6bc276d588997117eb84fd1a5a873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656736"
---
# <a name="connect-to-a-microsoft-access-database-ssas"></a><span data-ttu-id="79ce2-102">Соединение с базой данных Microsoft Access (SSAS)</span><span class="sxs-lookup"><span data-stu-id="79ce2-102">Connect to a Microsoft Access Database (SSAS)</span></span>
  <span data-ttu-id="79ce2-103">Эта страница **мастера импорта таблиц** позволяет задать параметры для соединения с базой данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="79ce2-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft Access database.</span></span> <span data-ttu-id="79ce2-104">Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.</span><span class="sxs-lookup"><span data-stu-id="79ce2-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="79ce2-105">Для соединения с базой данных Microsoft Access необходимо, чтобы на компьютере был установлен поставщик ACE.</span><span class="sxs-lookup"><span data-stu-id="79ce2-105">To connect to a Microsoft Access database, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="79ce2-106">Дополнительные сведения см. в разделе [Поддерживаемые источники данных (табличные службы SSAS)](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="79ce2-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79ce2-107">При выборе файла на этой странице используются учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="79ce2-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="79ce2-108">Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранного файла.</span><span class="sxs-lookup"><span data-stu-id="79ce2-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="79ce2-109">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="79ce2-109">UI element list</span></span>  
 <span data-ttu-id="79ce2-110">**Понятное имя соединения**</span><span class="sxs-lookup"><span data-stu-id="79ce2-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="79ce2-111">Введите уникальное имя для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="79ce2-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="79ce2-112">Это поле является обязательным.</span><span class="sxs-lookup"><span data-stu-id="79ce2-112">This is a required field.</span></span>  
  
 <span data-ttu-id="79ce2-113">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="79ce2-113">**Database name**</span></span>  
 <span data-ttu-id="79ce2-114">Укажите полный путь к файлу базы данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="79ce2-114">Specify the full path for a Microsoft Access database file.</span></span>  
  
 <span data-ttu-id="79ce2-115">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="79ce2-115">**Browse**</span></span>  
 <span data-ttu-id="79ce2-116">Перейдите к расположению, в котором доступен файл базы данных Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="79ce2-116">Navigate to a location where a Microsoft Access database file is available.</span></span>  
  
 <span data-ttu-id="79ce2-117">**User name**</span><span class="sxs-lookup"><span data-stu-id="79ce2-117">**User name**</span></span>  
 <span data-ttu-id="79ce2-118">Укажите имя пользователя для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="79ce2-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="79ce2-119">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="79ce2-119">**Password**</span></span>  
 <span data-ttu-id="79ce2-120">Укажите пароль для подключения к базе данных.</span><span class="sxs-lookup"><span data-stu-id="79ce2-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="79ce2-121">**Сохранить мой пароль**</span><span class="sxs-lookup"><span data-stu-id="79ce2-121">**Save my password**</span></span>  
 <span data-ttu-id="79ce2-122">Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="79ce2-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="79ce2-123">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="79ce2-123">**Advanced**</span></span>  
 <span data-ttu-id="79ce2-124">Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** .</span><span class="sxs-lookup"><span data-stu-id="79ce2-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="79ce2-125">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="79ce2-125">**Test Connection**</span></span>  
 <span data-ttu-id="79ce2-126">Установите соединение с источником данных с использованием текущих параметров.</span><span class="sxs-lookup"><span data-stu-id="79ce2-126">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="79ce2-127">Появится сообщение об успешном или неуспешном соединении.</span><span class="sxs-lookup"><span data-stu-id="79ce2-127">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
