---
title: Определение обычной связи и свойств обычных связей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- granularity attribute
- relationships [Analysis Services], regular relationships
ms.assetid: 840280d8-20c3-46c0-99ea-62479469c36b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b4f49e219a85d5577fb1acddfe14e7afd3b105d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667917"
---
# <a name="define-a-regular-relationship-and-regular-relationship-properties"></a><span data-ttu-id="309da-102">Определение обычной связи и ее свойств</span><span class="sxs-lookup"><span data-stu-id="309da-102">Define a Regular Relationship and Regular Relationship Properties</span></span>
  <span data-ttu-id="309da-103">При определении нового измерения куба или новой группы мер, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] попытаются определить, существует ли обычная связь, и установить настройку использования измерения в значение `Regular`.</span><span class="sxs-lookup"><span data-stu-id="309da-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a regular relationship exists and then set the dimension usage setting to `Regular`.</span></span> <span data-ttu-id="309da-104">Связь обычного измерения можно просмотреть или отредактировать на вкладке **Использование измерений** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="309da-104">You can view or edit a regular dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span>  
  
 <span data-ttu-id="309da-105">При определении связи измерения куба с группой мер также указывается атрибут гранулярности для этой связи.</span><span class="sxs-lookup"><span data-stu-id="309da-105">When you define the relationship of a cube dimension to a measure group, you also specify the granularity attribute for that relationship.</span></span> <span data-ttu-id="309da-106">Атрибут гранулярности определяет самый низкий уровень детализации, доступный в кубе для измерения, который обычно является ключевым атрибутом для этого измерения.</span><span class="sxs-lookup"><span data-stu-id="309da-106">The granularity attribute defines the lowest level of detail available in the cube for that dimension, which is generally the key attribute for the dimension.</span></span> <span data-ttu-id="309da-107">Однако, в некоторых случаях может быть необходимо изменить размер гранул гранулярности конкретного измерения куба в конкретной группе мер.</span><span class="sxs-lookup"><span data-stu-id="309da-107">However, sometimes you may want to set the granularity of a particular cube dimension in a particular measure group to a different grain.</span></span> <span data-ttu-id="309da-108">Например, может быть необходимо установить атрибут гранулярности для измерения «Время» равным атрибуту «Месяц», а не атрибуту «День», если используется группа мер «Квота на продажу» или «Бюджет».</span><span class="sxs-lookup"><span data-stu-id="309da-108">For example, you may want to set the granularity attribute for the Time dimension to the Month attribute instead of to the Day attribute, if you are using a Sales Quotas or a Budget measure group.</span></span> <span data-ttu-id="309da-109">При указании того, что атрибут гранулярности не является ключевым атрибутом, необходимо гарантировать, что все остальные атрибуты в измерении непосредственно или косвенно связаны с этим другим атрибутом через связи атрибутов.</span><span class="sxs-lookup"><span data-stu-id="309da-109">When you specify the granularity attribute to be an attribute other than the key attribute, you must guarantee that all other attributes in the dimension are directly or indirectly linked to this other attribute through attribute relationships.</span></span> <span data-ttu-id="309da-110">Если это не так, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не смогут корректно выполнить статистическую обработку данных.</span><span class="sxs-lookup"><span data-stu-id="309da-110">If not, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will be unable to aggregate data correctly.</span></span>  
  
  
