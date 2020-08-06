---
title: Свойства объектов (столбцов) с табличными значениями (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.designers.properties.QueryViewColumn
ms.assetid: 212d9bcd-aded-4313-a6b9-d7e2270e5954
author: stevestein
ms.author: sstein
ms.openlocfilehash: a2837851c50f770820eb5059e61f196890e2c23e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735762"
---
# <a name="table-valued-object-column-properties-visual-database-tools"></a><span data-ttu-id="cfc9f-102">Свойства табличного объекта (столбца) (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="cfc9f-102">Table-Valued Object (Column) Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="cfc9f-103">Эти свойства отображаются при выборе столбца в табличном объекте на панели **Диаграмма** конструктора запросов и представлений.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-103">These properties appear when you select a column in a table-valued object in the **Diagram** pane of Query and View Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfc9f-104">Свойства в данном разделе сгруппированы по категориям, а не по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-104">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfc9f-105">В зависимости от установок или выпуска сервера доступные диалоговые окна и команды меню могут отличаться от описанных в справке.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cfc9f-106">Чтобы изменить параметры, выберите **Импорт и экспорт параметров** в меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="cfc9f-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="cfc9f-107">**Категория «Идентификатор»**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-107">**Identity Category**</span></span>  
 <span data-ttu-id="cfc9f-108">Разверните для отображения свойства **Имя** .</span><span class="sxs-lookup"><span data-stu-id="cfc9f-108">Expands to show the **Name** property.</span></span>  
  
 <span data-ttu-id="cfc9f-109">**Название**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-109">**Name**</span></span>  
 <span data-ttu-id="cfc9f-110">Отображает имя выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-110">Shows the name of the selected column.</span></span>  
  
 <span data-ttu-id="cfc9f-111">**Категория конструктора запросов**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-111">**Query DesignerCategory**</span></span>  
 <span data-ttu-id="cfc9f-112">Разворачивается и отображает свойства **Разрешить значения NULL**, **Параметры сортировки**, **Тип данных**, **Длина**, **Точность**, **Масштаб**и **Размер**.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-112">Expands to show properties for **Allow Nulls**, **Collation**, **Datatype**, **Length**, **Precision**, **Scale**, and **Size**.</span></span>  
  
 <span data-ttu-id="cfc9f-113">**Разрешить значения NULL**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-113">**Allow Nulls**</span></span>  
 <span data-ttu-id="cfc9f-114">Указывает, разрешены ли в столбце данного типа значения NULL.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-114">Shows whether or not the column's data type allows null values.</span></span>  
  
 <span data-ttu-id="cfc9f-115">**Параметры сортировки**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-115">**Collation**</span></span>  
 <span data-ttu-id="cfc9f-116">Отображает установку параметров сортировки для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-116">Shows the collation setting for the selected column.</span></span> <span data-ttu-id="cfc9f-117">Параметры сортировки могут быть заданы во вкладке «Свойства столбца» в конструкторе таблиц.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-117">The collation can be set in the Column Properties tab of Table Designer.</span></span>  
  
 <span data-ttu-id="cfc9f-118">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-118">**Data Type**</span></span>  
 <span data-ttu-id="cfc9f-119">Отображает тип данных выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-119">Shows the data type of the selected column.</span></span>  
  
 <span data-ttu-id="cfc9f-120">**Длина**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-120">**Length**</span></span>  
 <span data-ttu-id="cfc9f-121">Показывает число символов или цифр, допустимых выбранным типом данных этого столбца.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-121">Shows the number of characters or digits allowed by the selected column's data type.</span></span> <span data-ttu-id="cfc9f-122">Данное свойство доступно только для символьных типов данных.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-122">This property is only available for character-based data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfc9f-123">Размер в байтах см. в свойстве **Размер** ниже.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-123">For the size in bytes, see the **Size** property below.</span></span>  
  
 <span data-ttu-id="cfc9f-124">**Точность**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-124">**Precision**</span></span>  
 <span data-ttu-id="cfc9f-125">Указывает максимальное число разрядов, допустимых для числовых типов данных.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-125">Shows the maximum number of digits allowed for numeric data types.</span></span> <span data-ttu-id="cfc9f-126">Для нечисловых типов данных в этом свойстве отображается **0** .</span><span class="sxs-lookup"><span data-stu-id="cfc9f-126">This property shows **0** for nonnumeric data types.</span></span>  
  
 <span data-ttu-id="cfc9f-127">**Масштабирование**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-127">**Scale**</span></span>  
 <span data-ttu-id="cfc9f-128">Указывает максимальное количество цифр справа от запятой в числовых типах данных.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-128">Shows the maximum number of digits that can appear to the right of the decimal point for numeric data types.</span></span> <span data-ttu-id="cfc9f-129">Это значение должно быть меньше или равно указанной точности.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-129">This value must be less than or equal to the precision.</span></span> <span data-ttu-id="cfc9f-130">Для нечисловых типов данных в этом свойстве отображается **0** .</span><span class="sxs-lookup"><span data-stu-id="cfc9f-130">This property shows **0** for nonnumeric data types.</span></span>  
  
 <span data-ttu-id="cfc9f-131">**Размер**</span><span class="sxs-lookup"><span data-stu-id="cfc9f-131">**Size**</span></span>  
 <span data-ttu-id="cfc9f-132">Показывает размер в байтах, допустимых типом данных этого столбца.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-132">Shows the size in bytes allowed by the column's data type.</span></span> <span data-ttu-id="cfc9f-133">Например, тип данных nchar может иметь длину 10 (количество символов), однако для работы с кодировкой Юникод его длина будет равняться 20.</span><span class="sxs-lookup"><span data-stu-id="cfc9f-133">For example, a nchar data type may have a length of 10 (the number of characters) but it would have a size of 20 to account for Unicode character sets.</span></span>  
  
  
