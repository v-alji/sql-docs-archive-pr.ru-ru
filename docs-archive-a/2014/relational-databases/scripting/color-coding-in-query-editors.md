---
title: Выделение цветом в редакторах запросов
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], color coding
- color coding [Query Editor]
ms.assetid: 802882dc-c997-4e3f-8a01-994bb43169ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f23b37cec051b52082cdb310a134a4603423b8c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658162"
---
# <a name="color-coding-in-query-editors"></a><span data-ttu-id="25d1c-102">Выделение цветом в редакторах запросов</span><span class="sxs-lookup"><span data-stu-id="25d1c-102">Color Coding in Query Editors</span></span>
  <span data-ttu-id="25d1c-103">Тексту, который вводится в редакторах кода, присваивается категория. Каждая категория идентифицируется по цвету.</span><span class="sxs-lookup"><span data-stu-id="25d1c-103">The text entered in the code editors is assigned a category; each category is identified by a color.</span></span> <span data-ttu-id="25d1c-104">Цвета помогают быстро находить текст в коде.</span><span class="sxs-lookup"><span data-stu-id="25d1c-104">The colors help you quickly find text in your code.</span></span> <span data-ttu-id="25d1c-105">Например, комментарии выделены темно-зеленым.</span><span class="sxs-lookup"><span data-stu-id="25d1c-105">For example, comments stand out in dark green.</span></span> <span data-ttu-id="25d1c-106">В следующей таблице приведены наиболее часто применяемые цвета.</span><span class="sxs-lookup"><span data-stu-id="25d1c-106">The following table lists the most common colors.</span></span> <span data-ttu-id="25d1c-107">Чтобы просмотреть полный список цветов и их категорий, а также настроить пользовательскую цветовую схему, в меню **Сервис**выберите пункт **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="25d1c-107">You can view the whole list of colors and their categories, and configure a custom color scheme by using the **Tools**, **Options** menu.</span></span> <span data-ttu-id="25d1c-108">Дополнительные сведения об изменении цветов по умолчанию см. в разделе [Change Font Color, Size, and Style](change-font-color-size-and-style.md).</span><span class="sxs-lookup"><span data-stu-id="25d1c-108">For more information about how to change the default colors, see [Change Font Color, Size, and Style](change-font-color-size-and-style.md).</span></span>  
  
## <a name="default-code-colors"></a><span data-ttu-id="25d1c-109">Цвета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="25d1c-109">Default Code Colors</span></span>  
  
|<span data-ttu-id="25d1c-110">Color</span><span class="sxs-lookup"><span data-stu-id="25d1c-110">Color</span></span>|<span data-ttu-id="25d1c-111">Категория</span><span class="sxs-lookup"><span data-stu-id="25d1c-111">Category</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="25d1c-112">Красный</span><span class="sxs-lookup"><span data-stu-id="25d1c-112">Red</span></span>|<span data-ttu-id="25d1c-113">Строка SQL</span><span class="sxs-lookup"><span data-stu-id="25d1c-113">SQL string</span></span>|  
|<span data-ttu-id="25d1c-114">Темно-зеленый</span><span class="sxs-lookup"><span data-stu-id="25d1c-114">Dark green</span></span>|<span data-ttu-id="25d1c-115">Комментарий</span><span class="sxs-lookup"><span data-stu-id="25d1c-115">Comment</span></span>|  
|<span data-ttu-id="25d1c-116">Черный на серебристом фоне</span><span class="sxs-lookup"><span data-stu-id="25d1c-116">Black on silver background</span></span>|<span data-ttu-id="25d1c-117">Инструкция SQLCMD</span><span class="sxs-lookup"><span data-stu-id="25d1c-117">SQLCMD command</span></span>|  
|<span data-ttu-id="25d1c-118">Пурпурный</span><span class="sxs-lookup"><span data-stu-id="25d1c-118">Magenta</span></span>|<span data-ttu-id="25d1c-119">Системная функция</span><span class="sxs-lookup"><span data-stu-id="25d1c-119">System function</span></span>|  
|<span data-ttu-id="25d1c-120">Зеленый</span><span class="sxs-lookup"><span data-stu-id="25d1c-120">Green</span></span>|<span data-ttu-id="25d1c-121">Системная таблица, представление или функция с табличным значением.</span><span class="sxs-lookup"><span data-stu-id="25d1c-121">System table, view, or table-valued function.</span></span> <span data-ttu-id="25d1c-122">А также системные схемы sys и INFORMATION_SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="25d1c-122">Also, the system schemas sys and INFORMATION_SCHEMA.</span></span>|  
|<span data-ttu-id="25d1c-123">Синий</span><span class="sxs-lookup"><span data-stu-id="25d1c-123">Blue</span></span>|<span data-ttu-id="25d1c-124">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="25d1c-124">Keyword</span></span>|  
|<span data-ttu-id="25d1c-125">Бирюзовый</span><span class="sxs-lookup"><span data-stu-id="25d1c-125">Teal</span></span>|<span data-ttu-id="25d1c-126">Номера строк или параметр шаблона</span><span class="sxs-lookup"><span data-stu-id="25d1c-126">Line numbers or template parameter</span></span>|  
|<span data-ttu-id="25d1c-127">Каштановый</span><span class="sxs-lookup"><span data-stu-id="25d1c-127">Maroon</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="25d1c-128">хранимая процедура</span><span class="sxs-lookup"><span data-stu-id="25d1c-128">stored procedure</span></span>|  
|<span data-ttu-id="25d1c-129">Темно-серый</span><span class="sxs-lookup"><span data-stu-id="25d1c-129">Dark gray</span></span>|<span data-ttu-id="25d1c-130">Операторы</span><span class="sxs-lookup"><span data-stu-id="25d1c-130">Operators</span></span>|  
  
## <a name="status-bar"></a><span data-ttu-id="25d1c-131">Строка состояния</span><span class="sxs-lookup"><span data-stu-id="25d1c-131">Status Bar</span></span>  
 <span data-ttu-id="25d1c-132">Можно назначить зарегистрированным серверам или серверам компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] в обозревателе объектов различные цвета в строке состояния редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25d1c-132">You can configure registered servers or [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers in Object Explorer to have different colors in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor status bar.</span></span> <span data-ttu-id="25d1c-133">Это поможет идентифицировать, к какому серверу подключено каждое из окон редактора, когда одновременно открыто много окон.</span><span class="sxs-lookup"><span data-stu-id="25d1c-133">This helps you identify which server each editor window is connected to when you have many windows open at the same time.</span></span> <span data-ttu-id="25d1c-134">Дополнительные сведения о настройке цветов строки состояния см. в статье [Строка состояния (редактор запросов компонента Database Engine)](status-bar-database-engine-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="25d1c-134">For more information about setting status bar colors, see [Status Bar &#40;Database Engine Query Editor&#41;](status-bar-database-engine-query-editor.md).</span></span>  
  
 <span data-ttu-id="25d1c-135">В некоторых редакторах строка состояния не отображается, либо не поддерживается несколько цветов.</span><span class="sxs-lookup"><span data-stu-id="25d1c-135">Some types of editors do not display the status bar, or do not support multiple colors.</span></span>  
  
  
