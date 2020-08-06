---
title: Диалоговое окно "Предупреждения проверки" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65556
- vdt.dlgbox.validationwarnings
ms.assetid: fc76e234-ec9c-4a19-a65b-cb558ec8268e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4f94c3ae91e077af853db949847bc8448f6a4753
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665182"
---
# <a name="validation-warnings-dialog-box-visual-database-tools"></a><span data-ttu-id="08555-102">Диалоговое окно «Предупреждения проверки» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="08555-102">Validation Warnings Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="08555-103">Это диалоговое окно появляется при попытке сохранить изменения с потенциально опасными побочными эффектами или в случае вероятной неудачи операции фиксации базы данных.</span><span class="sxs-lookup"><span data-stu-id="08555-103">This dialog box appears if you attempt to save modifications with potentially damaging side effects, or if the database commit operation is likely to fail.</span></span> <span data-ttu-id="08555-104">Это диалоговое окно указывает возможные побочные эффекты или возможные причины неудачи операции фиксации.</span><span class="sxs-lookup"><span data-stu-id="08555-104">This dialog box indicates what those side effects might be or why the commit operation might fail.</span></span> <span data-ttu-id="08555-105">Диалоговое окно предоставляет возможность продолжить действие или отменить его.</span><span class="sxs-lookup"><span data-stu-id="08555-105">It gives you the chance to continue with the modification or cancel the operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08555-106">Это диалоговое окно выводится при попытке передачи изменений в базу данных или при сохранении скрипта изменения.</span><span class="sxs-lookup"><span data-stu-id="08555-106">This dialog box appears when you attempt to transmit your modifications to the database or when you save a change script.</span></span>  
  
 <span data-ttu-id="08555-107">Появление диалогового окна может быть вызвано любой из следующих причин:</span><span class="sxs-lookup"><span data-stu-id="08555-107">The dialog box can appear for any of these reasons:</span></span>  
  
-   <span data-ttu-id="08555-108">Возможно, отсутствуют разрешения базы данных на фиксацию всех изменений.</span><span class="sxs-lookup"><span data-stu-id="08555-108">You might not have database permissions to commit all the modifications.</span></span>  
  
-   <span data-ttu-id="08555-109">Внесение изменений может привести к неправильному формированию производных столбцов, ограничений по умолчанию или проверочных ограничений.</span><span class="sxs-lookup"><span data-stu-id="08555-109">Your modifications would result in improperly formed derived columns, default constraints, or check constraints.</span></span>  
  
-   <span data-ttu-id="08555-110">Изменение типа данных столбца может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="08555-110">A modification to a column's data type might cause data loss.</span></span>  
  
-   <span data-ttu-id="08555-111">Изменение может привести к тому, что размер индекса будет более 900 байт.</span><span class="sxs-lookup"><span data-stu-id="08555-111">A modification would result in an index greater than 900 bytes.</span></span>  
  
-   <span data-ttu-id="08555-112">Изменение может изменить таблицу или столбец, являющиеся источниками для связанного со схемой представления или определяемой пользователем функции.</span><span class="sxs-lookup"><span data-stu-id="08555-112">A modification would change a table or column contributing to a schema-bound view or user-defined function.</span></span>  
  
-   <span data-ttu-id="08555-113">Изменение приведет к воссозданию таблицы, которая имеет один или более зашифрованных триггеров; триггеры будут удалены.</span><span class="sxs-lookup"><span data-stu-id="08555-113">A modification would result in the re-creation of a table that has one or more encrypted triggers; the triggers will be dropped.</span></span>  
  
-   <span data-ttu-id="08555-114">Изменения приведут к установке особых параметров настройки ANSI_NULLS или ANSI_PADDING (или обоих) для столбцов одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="08555-114">Your modifications will yield noteworthy settings of ANSI_NULLS or ANSI_PADDING or both for the columns within one table.</span></span>  
  
## <a name="options"></a><span data-ttu-id="08555-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="08555-115">Options</span></span>  
 <span data-ttu-id="08555-116">**Да**</span><span class="sxs-lookup"><span data-stu-id="08555-116">**Yes**</span></span>  
 <span data-ttu-id="08555-117">Продолжите операцию и создайте скрипт изменения или передайте изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="08555-117">Proceed with the operation and generate the change script or transmit the modifications to the database.</span></span> <span data-ttu-id="08555-118">Операции фиксации могут быть неудачными, если отсутствуют права на изменение базы данных, если изменения приведут к тому, что размер индекса будет более 900 байт; или если изменения приведут к неправильному формированию вычисляемого столбца, ограничения по умолчанию или проверочных ограничений.</span><span class="sxs-lookup"><span data-stu-id="08555-118">The commit operation can still fail if you do not have privileges to modify the database, if your modifications will result in an index greater than 900 bytes, or if your modifications will result in an improperly formed computed column, default constraint, or check constraint.</span></span>  
  
 <span data-ttu-id="08555-119">**Нет**</span><span class="sxs-lookup"><span data-stu-id="08555-119">**No**</span></span>  
 <span data-ttu-id="08555-120">Отменить сохранение.</span><span class="sxs-lookup"><span data-stu-id="08555-120">Cancel the save action.</span></span>  
  
 <span data-ttu-id="08555-121">**Сохранить текстовый файл**</span><span class="sxs-lookup"><span data-stu-id="08555-121">**Save Text File**</span></span>  
 <span data-ttu-id="08555-122">Отображает диалоговое окно **Сохранить как** , которое позволит указать местоположение текстового файла, содержащего список предупреждений.</span><span class="sxs-lookup"><span data-stu-id="08555-122">Display the **Save As** dialog box, where you can specify a location for a text file containing a list of the warnings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08555-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="08555-123">See Also</span></span>  
 <span data-ttu-id="08555-124">[Разработка таблиц &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="08555-124">[Design Tables &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="08555-125">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="08555-125">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
