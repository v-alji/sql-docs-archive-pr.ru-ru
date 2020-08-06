---
title: Свойства объектов с табличными значениями (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.designers.properties.TVO
ms.assetid: eaf06cbf-8242-4483-894f-80ae02a4840e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f1c1e6414d0059dfd1d43bbbb40eabdfc9470b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735766"
---
# <a name="table-valued-object-properties-visual-database-tools"></a><span data-ttu-id="d8d73-102">Свойства объектов с табличными значениями (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="d8d73-102">Table-Valued Object Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="d8d73-103">Эти свойства отображаются в окне свойств при выборе табличного объекта в **конструкторе запросов и представлений**.</span><span class="sxs-lookup"><span data-stu-id="d8d73-103">These properties appear in the Properties window when you select a table-valued object in **Query and View Designer**.</span></span> <span data-ttu-id="d8d73-104">Табличный объект может быть представлением, синонимом, производной таблицей или возвращающей табличное значение функцией.</span><span class="sxs-lookup"><span data-stu-id="d8d73-104">The table-valued object could be a view, synonym, derived table, or table-valued function.</span></span> <span data-ttu-id="d8d73-105">Если не указано иное, в окне **Свойства** эти свойства отображаются только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d8d73-105">Unless otherwise noted, these properties are read-only in the **Properties** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8d73-106">Свойства в данном разделе сгруппированы по категориям, а не по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="d8d73-106">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8d73-107">В зависимости от установок или выпуска сервера доступные диалоговые окна и команды меню могут отличаться от описанных в справке.</span><span class="sxs-lookup"><span data-stu-id="d8d73-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d8d73-108">Чтобы изменить параметры, выберите **Импорт и экспорт параметров** в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="d8d73-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="d8d73-109">**Категория «Идентификатор»**</span><span class="sxs-lookup"><span data-stu-id="d8d73-109">**Identity Category**</span></span>  
 <span data-ttu-id="d8d73-110">При открытии отображает свойства **Имя** и **Тип объекта, возвращающего табличное значение** .</span><span class="sxs-lookup"><span data-stu-id="d8d73-110">Expands to show the **Name** and **TVO Type** properties.</span></span>  
  
 <span data-ttu-id="d8d73-111">**Название**</span><span class="sxs-lookup"><span data-stu-id="d8d73-111">**Name**</span></span>  
 <span data-ttu-id="d8d73-112">Отображает имя указанного табличного объекта.</span><span class="sxs-lookup"><span data-stu-id="d8d73-112">Shows the name of the selected table-valued object.</span></span>  
  
 <span data-ttu-id="d8d73-113">**Тип объекта, возвращающего табличное значение**</span><span class="sxs-lookup"><span data-stu-id="d8d73-113">**TVO Type**</span></span>  
 <span data-ttu-id="d8d73-114">Показывает, к какому типу относится объект TVO.</span><span class="sxs-lookup"><span data-stu-id="d8d73-114">Shows which type of table-valued object.</span></span> <span data-ttu-id="d8d73-115">Это может быть базовая таблица, представление, возвращающая табличное значение функция или производная таблица.</span><span class="sxs-lookup"><span data-stu-id="d8d73-115">It can be either a base table, view, table-valued function, or a derived table.</span></span>  
  
 <span data-ttu-id="d8d73-116">**Категория конструктора запросов**</span><span class="sxs-lookup"><span data-stu-id="d8d73-116">**Query DesignerCategory**</span></span>  
 <span data-ttu-id="d8d73-117">При открытии отображает свойства **Псевдоним**, **Список столбцов**, **Полное имя**и **Список параметров**.</span><span class="sxs-lookup"><span data-stu-id="d8d73-117">Expands to show properties for **Alias**, **Column List**, **Full Name**, and **Parameter List**.</span></span>  
  
 <span data-ttu-id="d8d73-118">**Псевдоним**</span><span class="sxs-lookup"><span data-stu-id="d8d73-118">**Alias**</span></span>  
 <span data-ttu-id="d8d73-119">Отображает псевдоним указанного табличного объекта.</span><span class="sxs-lookup"><span data-stu-id="d8d73-119">Shows the alias for the selected table-valued object.</span></span> <span data-ttu-id="d8d73-120">Чтобы создать или изменить псевдоним, введите его в поле ввода.</span><span class="sxs-lookup"><span data-stu-id="d8d73-120">To add or change an alias, type it into the field.</span></span>  
  
 <span data-ttu-id="d8d73-121">**Список столбцов**</span><span class="sxs-lookup"><span data-stu-id="d8d73-121">**Column List**</span></span>  
 <span data-ttu-id="d8d73-122">Отображает столбцы, входящие в указанный табличный объект.</span><span class="sxs-lookup"><span data-stu-id="d8d73-122">Shows the columns included in the selected table-valued object.</span></span> <span data-ttu-id="d8d73-123">Чтобы увидеть их в отдельном окне, щелкните "Список столбцов", а затем — многоточие (…) справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="d8d73-123">To see them in a separate window, click Column List and then click the ellipses (...) to the right of the property.</span></span>  
  
 <span data-ttu-id="d8d73-124">**Полное имя**</span><span class="sxs-lookup"><span data-stu-id="d8d73-124">**Full Name**</span></span>  
 <span data-ttu-id="d8d73-125">Отображает полное имя выбранного табличного объекта, включая дополнительную информацию, такую, как схема или источник данных объекта.</span><span class="sxs-lookup"><span data-stu-id="d8d73-125">Shows the name of the selected table-valued object, including additional information such as the schema or data source of the object.</span></span>  
  
 <span data-ttu-id="d8d73-126">**Список параметров**</span><span class="sxs-lookup"><span data-stu-id="d8d73-126">**Parameter List**</span></span>  
 <span data-ttu-id="d8d73-127">Отображает параметры, определенные для выбранной возвращающей табличное значение функции.</span><span class="sxs-lookup"><span data-stu-id="d8d73-127">Shows the parameters defined for selected table-valued function.</span></span> <span data-ttu-id="d8d73-128">Чтобы определить значения параметров, щелкните "Список параметров", а затем — многоточие (…) справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="d8d73-128">To define a value for the parameters, click Parameter List and then click the ellipses (...) to the right of the property.</span></span> <span data-ttu-id="d8d73-129">В диалоговом окне «Параметры функции» введите значения.</span><span class="sxs-lookup"><span data-stu-id="d8d73-129">In the Function Parameters dialog box, type in values.</span></span> <span data-ttu-id="d8d73-130">Это свойство доступно лишь тогда, когда выбрана возвращающая табличное значение функция.</span><span class="sxs-lookup"><span data-stu-id="d8d73-130">This property is only available when a table-valued function is selected.</span></span>  
  
  
