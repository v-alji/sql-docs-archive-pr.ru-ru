---
title: Использование конструктора запросов и представлений с международными данными (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Visual Database Tools [SQL Server], international data
- queries [SQL Server], international data
- languages [SQL Server], Query and View Designer
- international considerations [SQL Server], Query and View Designer
- Criteria pane
- View Designer, international data
- Query Designer [SQL Server], international data
- localized information in Query and View Designer [SQL Server]
- global considerations [SQL Server], Query and View Designer
- SQL pane [Visual Database Tools]
- multiple language support [SQL Server], Query and View Designer
ms.assetid: 4b51c56f-f902-4e72-b919-e36127369b63
author: stevestein
ms.author: sstein
ms.openlocfilehash: 905e4c6909c792b019c11ef95662a7ec1a113bb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734837"
---
# <a name="use-the-query-and-view-designer-with-international-data-visual-database-tools"></a><span data-ttu-id="b79f8-102">Использование конструктора запросов и представлений с международными данными (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="b79f8-102">Use the Query and View Designer with International Data (Visual Database Tools)</span></span>
  <span data-ttu-id="b79f8-103">[Конструктор запросов и представлений](visual-database-tools.md) можно использовать с данными на любом языке и с любой версией операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="b79f8-103">You can use the [Query and View Designer](visual-database-tools.md) with data in any language and in any version of the Windows operating system.</span></span> <span data-ttu-id="b79f8-104">Ниже описаны различия, с которыми можно столкнуться при работе, и предоставлены сведения об управлении данными в международных приложениях.</span><span class="sxs-lookup"><span data-stu-id="b79f8-104">The following guidelines outline the differences you will notice and provide information about managing data in international applications.</span></span>  
  
## <a name="localized-information-in-the-criteria-and-sql-panes"></a><span data-ttu-id="b79f8-105">Локализованные сведения на панелях критериев и «SQL»</span><span class="sxs-lookup"><span data-stu-id="b79f8-105">Localized Information in the Criteria and SQL Panes</span></span>  
 <span data-ttu-id="b79f8-106">Если для создания запроса использовать панель критериев, необходимо ввести данные в формате, соответствующем региональным настройкам Windows компьютера.</span><span class="sxs-lookup"><span data-stu-id="b79f8-106">If you are using the Criteria pane to create your query, you can enter information in the format that corresponds to the Windows Regional Settings for you computer.</span></span> <span data-ttu-id="b79f8-107">Например, для поиска данных нужно ввести данные в столбец критериев с использованием любого привычного формата, за исключением следующих форматов.</span><span class="sxs-lookup"><span data-stu-id="b79f8-107">For example, if you are searching for data, you can enter the data in the Criteria columns using whatever format you are accustomed to using, with these exceptions:</span></span>  
  
-   <span data-ttu-id="b79f8-108">Длинные форматы даты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b79f8-108">Long data formats are not supported.</span></span>  
  
-   <span data-ttu-id="b79f8-109">Символы валют не должны вводиться на панели критериев.</span><span class="sxs-lookup"><span data-stu-id="b79f8-109">Currency symbols should not be entered in the Criteria pane.</span></span>  
  
-   <span data-ttu-id="b79f8-110">Символы валют не отображаются на панели результатов.</span><span class="sxs-lookup"><span data-stu-id="b79f8-110">Currency symbols will not display in the Results pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b79f8-111">На панели результатов можно самостоятельно ввести символ валюты, соответствующий региональным настройкам Windows на компьютере, однако символ будет удален и не отобразится на панели результатов.</span><span class="sxs-lookup"><span data-stu-id="b79f8-111">In the Results pane, you can actually enter the currency symbol that corresponds to the Windows Regional Settings for your computer, but the symbol will be removed and will not display in the Results pane.</span></span>  
  
-   <span data-ttu-id="b79f8-112">Унарный минус всегда появляется на левой стороне (например -1) независимо от параметров региональных настроек.</span><span class="sxs-lookup"><span data-stu-id="b79f8-112">Unary minus always appears on the left side (for example, -1) regardless of the Regional Settings options.</span></span>  
  
 <span data-ttu-id="b79f8-113">Наоборот, данные и ключевые слова на панели «SQL» должны всегда быть в формате ANSI (U.S.).</span><span class="sxs-lookup"><span data-stu-id="b79f8-113">In contrast, data and keywords in the SQL pane must always be in ANSI (U.S.) format.</span></span> <span data-ttu-id="b79f8-114">Например, в процессе построения запроса конструктор запросов и представлений вставляет форму ANSI для всех ключевых слов SQL, таких как SELECT и FROM.</span><span class="sxs-lookup"><span data-stu-id="b79f8-114">For example, as the Query and View Designer builds a query, it inserts the ANSI form of all SQL keywords such as SELECT and FROM.</span></span> <span data-ttu-id="b79f8-115">При добавлении элементов к инструкции на панели «SQL» необходимо убедиться, что для элементов используется стандартная форма ANSI.</span><span class="sxs-lookup"><span data-stu-id="b79f8-115">If you add elements to the statement in the SQL pane, be sure to use the ANSI standard form for the elements.</span></span>  
  
 <span data-ttu-id="b79f8-116">При введении на панель критериев данных с использованием местного формата конструктор запросов и представлений автоматически переводит их в формат ANSI на панель «SQL».</span><span class="sxs-lookup"><span data-stu-id="b79f8-116">When you enter data using local-specific format in the Criteria pane, the Query and View Designer automatically translates it to ANSI format in the SQL pane.</span></span> <span data-ttu-id="b79f8-117">Например, если региональные настройки установлены на стандартный немецкий, то на панели критериев можно вводить данные в следующем формате: «31.12.96».</span><span class="sxs-lookup"><span data-stu-id="b79f8-117">For example, if your Regional Settings are set to Standard German, you can enter data in the Criteria pane in a format such as "31.12.96."</span></span> <span data-ttu-id="b79f8-118">Однако дата появится на панели SQL в формате ANSI для даты-времени как `{ ts '1996-12-31 00:00:00' }.` Если вводить данные непосредственно на панели SQL, следует использовать формат ANSI.</span><span class="sxs-lookup"><span data-stu-id="b79f8-118">However, the date will appear in the SQL pane in ANSI datetime format as `{ ts '1996-12-31 00:00:00' }.` If you enter data directly in the SQL pane, you must enter it in ANSI format.</span></span>  
  
## <a name="sort-order"></a><span data-ttu-id="b79f8-119">Порядок сортировки</span><span class="sxs-lookup"><span data-stu-id="b79f8-119">Sort Order</span></span>  
 <span data-ttu-id="b79f8-120">Порядок сортировки данных в запросе определяется базой данных.</span><span class="sxs-lookup"><span data-stu-id="b79f8-120">The sort order of data in your query is determined by the database.</span></span> <span data-ttu-id="b79f8-121">Параметры, которые указываются в диалоговом окне региональных настроек Windows, не влияют на порядок сортировки запросов.</span><span class="sxs-lookup"><span data-stu-id="b79f8-121">Options that you set in the Windows Regional Settings dialog box do not affect sort order for queries.</span></span> <span data-ttu-id="b79f8-122">Однако в рамках любого конкретного запроса можно запросить возврат строк в определенном порядке.</span><span class="sxs-lookup"><span data-stu-id="b79f8-122">Within any particular query, however, you can request that rows be returned in a particular order.</span></span>  
  
## <a name="using-double-byte-characters"></a><span data-ttu-id="b79f8-123">Использование двухбайтовых символов</span><span class="sxs-lookup"><span data-stu-id="b79f8-123">Using Double-Byte Characters</span></span>  
 <span data-ttu-id="b79f8-124">Можно ввести символы двухбайтовой кодировки DBCS для констант и имен объектов базы данных, таких как имена или псевдонимы таблиц и представлений.</span><span class="sxs-lookup"><span data-stu-id="b79f8-124">You can enter DBCS characters for literals and for database object names such as table and view names or aliases.</span></span> <span data-ttu-id="b79f8-125">Символы двухбайтовой кодировки DBCS также можно использовать для имен параметров и символов-маркеров параметров.</span><span class="sxs-lookup"><span data-stu-id="b79f8-125">You can also use DBCS characters for parameter names and parameter marker characters.</span></span> <span data-ttu-id="b79f8-126">Однако нельзя использовать символы двухбайтовой кодировки DBCS в элементах языка SQL, например в именах функций или ключевых словах SQL.</span><span class="sxs-lookup"><span data-stu-id="b79f8-126">However, you cannot use DBCS characters in SQL language elements such as function names or SQL keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79f8-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="b79f8-127">See Also</span></span>  
 [<span data-ttu-id="b79f8-128">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="b79f8-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
