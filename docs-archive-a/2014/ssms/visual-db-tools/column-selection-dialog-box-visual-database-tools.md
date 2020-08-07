---
title: Диалоговое окно "Выбор столбцов" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.columnselection
- vdtsql.chm:65548
ms.assetid: 479bae2c-fee0-4215-b424-1ab779a7e5ca
author: stevestein
ms.author: sstein
ms.openlocfilehash: da3effa33704b796dc2597512be7780594706423
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727813"
---
# <a name="column-selection-dialog-box-visual-database-tools"></a><span data-ttu-id="9e532-102">Диалоговое окно «Выбор столбцов» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="9e532-102">Column Selection Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="9e532-103">Позволяет изменить пользовательское представление таблиц в диаграмме базы данных.</span><span class="sxs-lookup"><span data-stu-id="9e532-103">Lets you change the Custom view for tables in the database diagram.</span></span> <span data-ttu-id="9e532-104">В пользовательском представлении отображаются свойства столбцов, указанные пользователем.</span><span class="sxs-lookup"><span data-stu-id="9e532-104">Custom view shows only the column properties identified by the user.</span></span>  
  
 <span data-ttu-id="9e532-105">Чтобы открыть это диалоговое окно, щелкните правой кнопкой мыши и выберите в контекстном меню пункт **Изменить настраиваемое представление** .</span><span class="sxs-lookup"><span data-stu-id="9e532-105">This dialog box appears when you right-click a table and then choose **Modify Custom View** from the shortcut menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9e532-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e532-106">Options</span></span>  
 <span data-ttu-id="9e532-107">**Доступные столбцы**</span><span class="sxs-lookup"><span data-stu-id="9e532-107">**Available columns**</span></span>  
 <span data-ttu-id="9e532-108">Список всех столбцов в таблице выбранной базы данных.</span><span class="sxs-lookup"><span data-stu-id="9e532-108">Lists all columns existing in the selected database table.</span></span> <span data-ttu-id="9e532-109">Перечисленные в списке столбцы зависят от свойств таблицы базы данных и типа базы данных.</span><span class="sxs-lookup"><span data-stu-id="9e532-109">The columns listed here depend on the properties of the database table and the type of database.</span></span> <span data-ttu-id="9e532-110">Выделите требуемый столбец и с помощью кнопок со стрелками переместите столбцы в окно **Выбранные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="9e532-110">Highlight the desired column and use the arrow buttons to move the columns to the **Selected columns** box.</span></span>  
  
 <span data-ttu-id="9e532-111">**Выбранные столбцы**</span><span class="sxs-lookup"><span data-stu-id="9e532-111">**Selected columns**</span></span>  
 <span data-ttu-id="9e532-112">Отображает свойства столбца, определенные для пользовательского представления.</span><span class="sxs-lookup"><span data-stu-id="9e532-112">Displays the column properties currently defined for the Custom view.</span></span> <span data-ttu-id="9e532-113">Для добавления или удаления свойств столбцов в список «Выбранные столбцы» используйте кнопки со стрелками.</span><span class="sxs-lookup"><span data-stu-id="9e532-113">Use the arrow buttons to add and remove column properties to the Selected Columns list.</span></span>  
  
 <span data-ttu-id="9e532-114">**Управление кнопками со стрелками**</span><span class="sxs-lookup"><span data-stu-id="9e532-114">**Arrow controls**</span></span>  
 <span data-ttu-id="9e532-115">Чтобы переместить выделенные столбцы вверх или вниз в списке **Выбранные столбцы** , используйте кнопки со стрелками вверх и вниз.</span><span class="sxs-lookup"><span data-stu-id="9e532-115">Use the up and down arrow buttons to move highlighted columns up or down in the **Selected columns** list.</span></span>  
  
 <span data-ttu-id="9e532-116">Чтобы добавить в пользовательское представление одно или все свойства, используйте кнопки со стрелками > и >>.</span><span class="sxs-lookup"><span data-stu-id="9e532-116">Use the > and >> arrows to add one or all of the properties to the custom view.</span></span>  
  
 <span data-ttu-id="9e532-117">Чтобы удалить из пользовательского представления одно или все свойства, используйте кнопки со стрелками < и <<.</span><span class="sxs-lookup"><span data-stu-id="9e532-117">Use the < and << arrows to remove one or all of the properties from the custom view.</span></span>  
  
 <span data-ttu-id="9e532-118">**Сохранить по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="9e532-118">**Save as default**</span></span>  
 <span data-ttu-id="9e532-119">Заменяет пользовательское представление по умолчанию на столбцы, выбранные в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="9e532-119">Replaces the default Custom view with the columns selected in this dialog box.</span></span> <span data-ttu-id="9e532-120">Если этот параметр не выбран, выбор столбцов, определенных в диалоговом окне, применяется только к таблицам, выбранным в диаграмме базы данных.</span><span class="sxs-lookup"><span data-stu-id="9e532-120">If not selected, the column selection specified in the dialog box will be applied only to the selected table in the database diagram.</span></span>  
  
 <span data-ttu-id="9e532-121">**OK**</span><span class="sxs-lookup"><span data-stu-id="9e532-121">**OK**</span></span>  
 <span data-ttu-id="9e532-122">Сохраняет пользовательское представление.</span><span class="sxs-lookup"><span data-stu-id="9e532-122">Saves the Custom view.</span></span>  
  
 <span data-ttu-id="9e532-123">**Отмена**</span><span class="sxs-lookup"><span data-stu-id="9e532-123">**Cancel**</span></span>  
 <span data-ttu-id="9e532-124">Отменяет изменения пользовательского представления.</span><span class="sxs-lookup"><span data-stu-id="9e532-124">Cancels the modification of Custom view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e532-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e532-125">See Also</span></span>  
 <span data-ttu-id="9e532-126">[Работа с диаграммами баз данных &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9e532-126">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9e532-127">Настройка объема сведений, отображаемых в диаграммах (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="9e532-127">Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;</span></span>](customize-the-amount-of-information-displayed-in-diagrams-visual-database-tools.md)  
  
  
