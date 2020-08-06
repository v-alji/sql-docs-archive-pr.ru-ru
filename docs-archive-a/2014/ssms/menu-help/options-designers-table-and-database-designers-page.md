---
title: Параметры (конструкторы — страница «Конструкторы таблиц и баз данных») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Designers.Table_Designer
ms.assetid: b43f4b97-17b9-4004-a824-f77b9e145741
author: stevestein
ms.author: sstein
ms.openlocfilehash: d8a1218b4ea1ae9c6f9cf734bb33a2a4bebcb167
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666321"
---
# <a name="options-designers-table-and-database-designers-page"></a><span data-ttu-id="83d03-102">Параметры (конструкторы — страница «Конструкторы таблиц и баз данных»)</span><span class="sxs-lookup"><span data-stu-id="83d03-102">Options (Designers-Table and Database Designers Page)</span></span>
  <span data-ttu-id="83d03-103">Эта страница используется для определения поведения конструктора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83d03-103">Use this page to determine the default behavior of the designer.</span></span> <span data-ttu-id="83d03-104">Для доступа к параметрам в меню **Сервис** выберите **Параметры**, откройте папку **Конструкторы** и щелкните **Конструктор таблиц**.</span><span class="sxs-lookup"><span data-stu-id="83d03-104">To access the settings, on the **Tools** menu, click **Options**, expand the **Designers** folder, and click **Table Designer**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="83d03-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="83d03-105">UI element list</span></span>  
 <span data-ttu-id="83d03-106">**Переопределить интервал ожидания в строке подключения для обновлений конструктора таблиц**</span><span class="sxs-lookup"><span data-stu-id="83d03-106">**Override connection string time-out value for table designer updates**</span></span>  
 <span data-ttu-id="83d03-107">Позволяет устанавливать новое значение времени ожидания для действий конструктора таблиц.</span><span class="sxs-lookup"><span data-stu-id="83d03-107">Permits a new time-out value to be set for the actions of the table designer.</span></span> <span data-ttu-id="83d03-108">Это может быть полезным, если конструктор таблиц обрабатывает большие таблицы и для изменения таблицы ему необходимо дополнительное время.</span><span class="sxs-lookup"><span data-stu-id="83d03-108">This can be useful when the table designer affects a large table and requires extra time to complete the table modification.</span></span>  
  
 <span data-ttu-id="83d03-109">**Интервал ожидания транзакции**</span><span class="sxs-lookup"><span data-stu-id="83d03-109">**Transaction time-out after**</span></span>  
 <span data-ttu-id="83d03-110">Устанавливает значение времени ожидания для конструктора таблиц.</span><span class="sxs-lookup"><span data-stu-id="83d03-110">Sets a time-out value for the table designer.</span></span>  
  
 <span data-ttu-id="83d03-111">**Автоматическое создание скриптов завершения**</span><span class="sxs-lookup"><span data-stu-id="83d03-111">**Auto generate change scripts**</span></span>  
 <span data-ttu-id="83d03-112">Автоматически создает скрипт для реализации изменений, определенных в конструкторе таблиц.</span><span class="sxs-lookup"><span data-stu-id="83d03-112">Automatically creates a script to implement the changes defined in the table designer.</span></span>  
  
 <span data-ttu-id="83d03-113">**Предупреждать о первичных ключах со значением NULL**</span><span class="sxs-lookup"><span data-stu-id="83d03-113">**Warn on null primary keys**</span></span>  
 <span data-ttu-id="83d03-114">Выводится диалоговое окно предупреждения, если поле, выбранное для первичного ключа, может содержать значения NULL.</span><span class="sxs-lookup"><span data-stu-id="83d03-114">Provides a warning dialog box when a field that is selected for a primary key can contain null values.</span></span>  
  
 <span data-ttu-id="83d03-115">**Предупреждать об обнаружении различий**</span><span class="sxs-lookup"><span data-stu-id="83d03-115">**Warn about difference detection**</span></span>  
 <span data-ttu-id="83d03-116">Если этот флажок установлен, при сохранении изменений в окне сообщения будут перечислены конфликты, возникшие между изменениями, сделанными текущим пользователем, и изменениями, сделанными другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="83d03-116">If you check this box, when you save the changes, a message box will list any conflicts between your changes and changes that were made by another user.</span></span>  
  
 <span data-ttu-id="83d03-117">**Предупреждать о затронутых таблицах**</span><span class="sxs-lookup"><span data-stu-id="83d03-117">**Warn about tables affected**</span></span>  
 <span data-ttu-id="83d03-118">Выводится диалоговое окно предупреждения, содержащее таблицы, которые будут затронуты действием, и запрашивающее подтверждение.</span><span class="sxs-lookup"><span data-stu-id="83d03-118">Provides a warning dialog box that lists the tables to be affected by the action and prompts for confirmation.</span></span>  
  
 <span data-ttu-id="83d03-119">**Запретить сохранение изменений, требующих повторного создания таблицы**</span><span class="sxs-lookup"><span data-stu-id="83d03-119">**Prevent saving changes that require table re-creation**</span></span>  
 <span data-ttu-id="83d03-120">Запрещает пользователю совершать изменения, требующие повторного создания таблицы.</span><span class="sxs-lookup"><span data-stu-id="83d03-120">Prevents a user from making changes that require re-creating the table.</span></span> <span data-ttu-id="83d03-121">Повторное создание таблицы может понадобиться для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="83d03-121">The following actions might require a table to be re-created:</span></span>  
  
-   <span data-ttu-id="83d03-122">добавление нового столбца в середину таблицы;</span><span class="sxs-lookup"><span data-stu-id="83d03-122">Adding a new column to the middle of the table</span></span>  
  
-   <span data-ttu-id="83d03-123">удаление столбца;</span><span class="sxs-lookup"><span data-stu-id="83d03-123">Dropping a column</span></span>  
  
-   <span data-ttu-id="83d03-124">изменение допустимости значения NULL для столбца;</span><span class="sxs-lookup"><span data-stu-id="83d03-124">Changing column nullability</span></span>  
  
-   <span data-ttu-id="83d03-125">изменение порядка столбцов;</span><span class="sxs-lookup"><span data-stu-id="83d03-125">Changing the order of the columns</span></span>  
  
-   <span data-ttu-id="83d03-126">изменение типа данных столбца.</span><span class="sxs-lookup"><span data-stu-id="83d03-126">Changing the data type of a column</span></span>  
  
 <span data-ttu-id="83d03-127">**Представление таблицы по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="83d03-127">**Default table view**</span></span>  
 <span data-ttu-id="83d03-128">Выбор способа отображения таблиц в конструкторах.</span><span class="sxs-lookup"><span data-stu-id="83d03-128">Select the way you want to see tables in the designers:</span></span>  
  
-   <span data-ttu-id="83d03-129">**Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="83d03-129">**Standard**</span></span>  
  
     <span data-ttu-id="83d03-130">Отображается заголовок таблицы, имена всех столбцов, типы данных и установка разрешения значений NULL.</span><span class="sxs-lookup"><span data-stu-id="83d03-130">Shows the table header, all column names, data types, and the Allow Nulls setting.</span></span>  
  
-   <span data-ttu-id="83d03-131">**Имена столбцов**</span><span class="sxs-lookup"><span data-stu-id="83d03-131">**Column Names**</span></span>  
  
     <span data-ttu-id="83d03-132">Отображаются имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="83d03-132">Shows the column names.</span></span>  
  
-   <span data-ttu-id="83d03-133">**Key**</span><span class="sxs-lookup"><span data-stu-id="83d03-133">**Key**</span></span>  
  
     <span data-ttu-id="83d03-134">Отображается заголовок таблицы и первичные ключевые столбцы.</span><span class="sxs-lookup"><span data-stu-id="83d03-134">Shows the table header and the primary key columns.</span></span>  
  
-   <span data-ttu-id="83d03-135">**Только имя**</span><span class="sxs-lookup"><span data-stu-id="83d03-135">**Name Only**</span></span>  
  
     <span data-ttu-id="83d03-136">Отображается только заголовок таблицы с его именем.</span><span class="sxs-lookup"><span data-stu-id="83d03-136">Shows only the table header with it's name.</span></span>  
  
-   <span data-ttu-id="83d03-137">**Custom**</span><span class="sxs-lookup"><span data-stu-id="83d03-137">**Custom**</span></span>  
  
     <span data-ttu-id="83d03-138">Возможен выбор столбцов для отображения.</span><span class="sxs-lookup"><span data-stu-id="83d03-138">Allows you to choose which columns to view.</span></span>  
  
 <span data-ttu-id="83d03-139">**Открывать диалоговое окно «Добавления таблицы» при создании диаграммы**</span><span class="sxs-lookup"><span data-stu-id="83d03-139">**Launch add table dialog on new diagram**</span></span>  
 <span data-ttu-id="83d03-140">При открытии конструкторов автоматически открывается диалоговое окно **Добавление таблицы** .</span><span class="sxs-lookup"><span data-stu-id="83d03-140">Automatically opens the **Add Table** dialog box when the designers open.</span></span>  
  
  
