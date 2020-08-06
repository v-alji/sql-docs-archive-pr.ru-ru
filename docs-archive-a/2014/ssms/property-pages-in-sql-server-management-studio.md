---
title: Страницы свойств в среде SQL Server Management Studio | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- property pages [SQL Server Management Studio]
ms.assetid: 719282c3-e9cc-4e0e-9a83-7fb8b8b17f67
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3fae6a07fbaa2a259fcca5c3807094b31e0d52d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737412"
---
# <a name="property-pages-in-sql-server-management-studio"></a><span data-ttu-id="b8a45-102">Страницы свойств в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8a45-102">Property Pages in SQL Server Management Studio</span></span>
  <span data-ttu-id="b8a45-103">Во всех диалоговых окнах страниц свойств в среде [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] используется общий формат представления данных с развертыванием и свертыванием категорий.</span><span class="sxs-lookup"><span data-stu-id="b8a45-103">Property page dialog boxes in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] all use a common format displaying information with expanding and collapsing categories.</span></span> <span data-ttu-id="b8a45-104">Состав показываемых полей зависит от конкретного свойства.</span><span class="sxs-lookup"><span data-stu-id="b8a45-104">The fields shown depend on the particular property.</span></span> <span data-ttu-id="b8a45-105">Свойства, выделенные серым цветом, доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b8a45-105">Properties shown in gray are read-only.</span></span> <span data-ttu-id="b8a45-106">В верхней части каждой страницы свойств находятся кнопки «По категориям» и «По алфавиту».</span><span class="sxs-lookup"><span data-stu-id="b8a45-106">Categorized and Alphabetic buttons are near the top of each property page.</span></span>  
  
 <span data-ttu-id="b8a45-107">В следующей таблице описаны общие элементы диалоговых окон страниц свойств среды [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8a45-107">The following table describes the common elements of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] property page dialog boxes.</span></span>  
  
|<span data-ttu-id="b8a45-108">Элемент</span><span class="sxs-lookup"><span data-stu-id="b8a45-108">Element</span></span>|<span data-ttu-id="b8a45-109">Description</span><span class="sxs-lookup"><span data-stu-id="b8a45-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8a45-110">**По категориям**</span><span class="sxs-lookup"><span data-stu-id="b8a45-110">**Categorized**</span></span>|<span data-ttu-id="b8a45-111">Перечисляются все свойства и их значения для выбранного объекта, отсортированные по категориям.</span><span class="sxs-lookup"><span data-stu-id="b8a45-111">Lists all properties and property values for the selected object, sorted by category.</span></span> <span data-ttu-id="b8a45-112">В представлении по категориям можно свернуть ту или иную категорию, чтобы сократить число отображаемых свойств.</span><span class="sxs-lookup"><span data-stu-id="b8a45-112">In category view, you can collapse a category to reduce the number of visible properties.</span></span> <span data-ttu-id="b8a45-113">При раскрытии или свертывании категории слева от ее имени появляется знак «плюс» (+) или «минус» (-).</span><span class="sxs-lookup"><span data-stu-id="b8a45-113">When you expand or collapse a category, you see a plus sign (+) or minus sign (-) to the left of the category name.</span></span> <span data-ttu-id="b8a45-114">Категории перечислены в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="b8a45-114">Categories are listed alphabetically.</span></span>|  
|<span data-ttu-id="b8a45-115">**По алфавиту**</span><span class="sxs-lookup"><span data-stu-id="b8a45-115">**Alphabetic**</span></span>|<span data-ttu-id="b8a45-116">Все свойства и их значения для выбранного объекта перечисляются в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="b8a45-116">Lists all properties and property values for the selected object, sorted alphabetically.</span></span>|  
|<span data-ttu-id="b8a45-117">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="b8a45-117">Property name</span></span>|<span data-ttu-id="b8a45-118">В первом столбце сетки перечислены имена свойств.</span><span class="sxs-lookup"><span data-stu-id="b8a45-118">The first column in the grid lists the property names.</span></span>|  
|<span data-ttu-id="b8a45-119">Свойства</span><span class="sxs-lookup"><span data-stu-id="b8a45-119">Properties</span></span>|<span data-ttu-id="b8a45-120">Во втором столбце сетки перечислены значения свойств.</span><span class="sxs-lookup"><span data-stu-id="b8a45-120">The second column in the grid lists the property values.</span></span>|  
|<span data-ttu-id="b8a45-121">Панель описания</span><span class="sxs-lookup"><span data-stu-id="b8a45-121">Description pane</span></span>|<span data-ttu-id="b8a45-122">Панель описания расположена в нижней части страницы и содержит тип и краткое описание текущего свойства.</span><span class="sxs-lookup"><span data-stu-id="b8a45-122">The description pane appears at the bottom of the page and shows the property type and a short description of the property.</span></span> <span data-ttu-id="b8a45-123">Для включения и отключения описания свойства можно использовать команду **Описание** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="b8a45-123">You can turn the description of the property off and on using the **Description** command on the shortcut menu.</span></span>|  
  
  
