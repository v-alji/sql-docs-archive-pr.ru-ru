---
title: Копирование таблиц из одной диаграммы базы данных в другую (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- duplicating tables
ms.assetid: 155a4f09-9321-4887-a7d4-aa2ce6b51277
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7e90c8f324e80f7c59674def06a77e93a5bf0cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727770"
---
# <a name="copy-tables-from-one-database-diagrams-to-another-visual-database-tools"></a><span data-ttu-id="ce0db-102">Копирование таблиц из одних диаграмм базы данных в другие (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="ce0db-102">Copy Tables from One Database Diagrams to Another (Visual Database Tools)</span></span>
  <span data-ttu-id="ce0db-103">Можно скопировать таблицу из одной диаграммы базы данных в другую в той же самой базе данных.</span><span class="sxs-lookup"><span data-stu-id="ce0db-103">You can copy a table from one database diagram to another in the same database.</span></span>  
  
 <span data-ttu-id="ce0db-104">Копирование таблицы из одной диаграммы базы данных в другую диаграмму добавляет ссылку на таблицу во второй диаграмме.</span><span class="sxs-lookup"><span data-stu-id="ce0db-104">Copying a table from one database diagram to another diagram adds a reference to the table in the second diagram.</span></span> <span data-ttu-id="ce0db-105">Таблица не будет продублирована в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ce0db-105">The table is not duplicated in your database.</span></span> <span data-ttu-id="ce0db-106">Например, при копировании таблицы `authors` из одной диаграммы базы данных в другую каждая диаграмма будет ссылаться на одну и ту же таблицу `authors` в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ce0db-106">For example, if you copy the `authors` table from one database diagram to another, each diagram references the same `authors` table in the database.</span></span>  
  
### <a name="to-copy-a-table-from-another-database-diagram"></a><span data-ttu-id="ce0db-107">Копирование таблицы из диаграммы другой базы данных</span><span class="sxs-lookup"><span data-stu-id="ce0db-107">To copy a table from another database diagram</span></span>  
  
1.  <span data-ttu-id="ce0db-108">Убедитесь в наличии соединения с базой данных, таблицу которой необходимо скопировать.</span><span class="sxs-lookup"><span data-stu-id="ce0db-108">Make sure you are connected to the database whose table you want to copy.</span></span>  
  
2.  <span data-ttu-id="ce0db-109">Откройте исходные и целевые диаграммы базы данных и в исходной диаграмме выберите таблицу, которую необходимо скопировать в целевую схему.</span><span class="sxs-lookup"><span data-stu-id="ce0db-109">Open the source and target database diagrams and within the source diagram, select the table that you want to copy to the target diagram.</span></span>  
  
3.  <span data-ttu-id="ce0db-110">Нажмите кнопку **Копировать** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="ce0db-110">Click the **Copy** button on the toolbar.</span></span> <span data-ttu-id="ce0db-111">Это действие помещает выбранное определение таблицы в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="ce0db-111">This action places the selected table definition on the Clipboard.</span></span>  
  
4.  <span data-ttu-id="ce0db-112">Переключитесь на целевую диаграмму.</span><span class="sxs-lookup"><span data-stu-id="ce0db-112">Switch to the target diagram.</span></span> <span data-ttu-id="ce0db-113">Эта диаграмма должна быть в той же самой базе данных, где и исходная диаграмма.</span><span class="sxs-lookup"><span data-stu-id="ce0db-113">This diagram must be in the same database as the source diagram.</span></span>  
  
5.  <span data-ttu-id="ce0db-114">Нажмите кнопку **Вставить** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="ce0db-114">Click the **Paste** button on the toolbar.</span></span> <span data-ttu-id="ce0db-115">Содержимое буфера обмена появится в новом месте и останется выделенным до тех пор, пока не будет выполнен щелчок где-либо в другом месте.</span><span class="sxs-lookup"><span data-stu-id="ce0db-115">The Clipboard contents appear at the new location and remain highlighted until you click elsewhere.</span></span> <span data-ttu-id="ce0db-116">Если существуют связи между выбранными таблицами и другими таблицами в целевой диаграмме, линии связи будут нарисованы автоматически.</span><span class="sxs-lookup"><span data-stu-id="ce0db-116">If relationships exist between the selected tables and other tables in the target diagram, relationship lines are automatically drawn.</span></span>  
  
 <span data-ttu-id="ce0db-117">При изменении таблицы в любой из диаграмм изменения будут отражены в обеих.</span><span class="sxs-lookup"><span data-stu-id="ce0db-117">When you edit the table in either diagram, your changes are reflected in both diagrams.</span></span> <span data-ttu-id="ce0db-118">Точно так же при сохранении таблицы в любой диаграмме таблица больше не считается измененной в любой диаграмме.</span><span class="sxs-lookup"><span data-stu-id="ce0db-118">Similarly, once you save the table in either diagram, the table is no longer considered "modified" in either diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce0db-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce0db-119">See Also</span></span>  
 <span data-ttu-id="ce0db-120">[Работа с диаграммами баз данных &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ce0db-120">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ce0db-121">Добавление таблиц в диаграммы (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="ce0db-121">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-tables-to-diagrams-visual-database-tools.md)  
  
  
