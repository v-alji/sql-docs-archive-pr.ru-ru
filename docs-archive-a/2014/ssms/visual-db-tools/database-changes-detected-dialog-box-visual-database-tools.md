---
title: Диалоговое окно "Обнаружены изменения базы данных" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.schema.databasechangesdetected
- vdtsql.chm:65543
- vdtsql.chm:65554
ms.assetid: 91f13086-371f-46a2-9f46-804c1415f3ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91d58e812b93f207d592d245d094b0fbeddcce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731253"
---
# <a name="database-changes-detected-dialog-box-visual-database-tools"></a><span data-ttu-id="e1878-102">Диалоговое окно «Обнаружены изменения базы данных» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e1878-102">Database Changes Detected Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="e1878-103">Это диалоговое окно появляется при попытке сохранить диаграмму базы данных или выбранных таблиц, но при этом некоторые объекты базы данных, на которых распространяется действие сохранения, являются устаревшими по сравнению с базой данных.</span><span class="sxs-lookup"><span data-stu-id="e1878-103">This dialog appears if you attempt to save a database diagram or selected tables but some of the database objects that will be affected by the save action are out of date with the database.</span></span> <span data-ttu-id="e1878-104">Принятие изменений, показанных в диалоговом окне, обновит базу данных до соответствия с диаграммой и перезапишет изменения, сделанные другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="e1878-104">Accepting the changes shown in this dialog box updates the database to match your diagram and overwrites other users' changes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1878-105">Несмотря на то что изменения, произведенные с таблицей или диаграммой базы данных, нельзя отменить, они не будут сохранены в базе данных до тех пор, пока не будет сохранена таблица или диаграмма.</span><span class="sxs-lookup"><span data-stu-id="e1878-105">Although you cannot undo changes made to a table or database diagram, the changes are not saved to the database until you save the table or diagram.</span></span> <span data-ttu-id="e1878-106">Можно отказаться от любых несохраненных изменений, выбрав **Нет** и закрыв все открытые диаграммы без сохранения.</span><span class="sxs-lookup"><span data-stu-id="e1878-106">You can discard any unsaved changes by choosing **No** and closing all open diagrams without saving them.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e1878-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1878-107">Options</span></span>  
 <span data-ttu-id="e1878-108">**Предупреждать об обнаружении различий**</span><span class="sxs-lookup"><span data-stu-id="e1878-108">**Warn about difference detection**</span></span>  
 <span data-ttu-id="e1878-109">Укажите, выводить ли это диалоговое окно при следующей попытке сохранить диаграмму базы данных или выбранные таблицы.</span><span class="sxs-lookup"><span data-stu-id="e1878-109">Specify whether this dialog box appears the next time you attempt to save a database diagram or selected tables.</span></span> <span data-ttu-id="e1878-110">Установленный флажок означает, что диалоговое окно будет появляться каждый раз при попытке сохранить диаграмму, являющуюся устаревшей по отношению к базе данных.</span><span class="sxs-lookup"><span data-stu-id="e1878-110">Checked means that the dialog box continues to appear each time you save a diagram or table that is out of date with the database.</span></span> <span data-ttu-id="e1878-111">Отсутствие флажка означает, что диалоговое окно не будет появляться.</span><span class="sxs-lookup"><span data-stu-id="e1878-111">Unchecked means that the dialog box does not appear.</span></span> <span data-ttu-id="e1878-112">По умолчанию этот флажок установлен.</span><span class="sxs-lookup"><span data-stu-id="e1878-112">By default, this box is checked.</span></span> <span data-ttu-id="e1878-113">Если флажок был снят, его можно установить заново в диалоговом окне **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="e1878-113">If you uncheck this option, you can recheck it in the **Options** dialog box.</span></span>  
  
 <span data-ttu-id="e1878-114">**Да**</span><span class="sxs-lookup"><span data-stu-id="e1878-114">**Yes**</span></span>  
 <span data-ttu-id="e1878-115">Обновить базу данных, применив все показанное в списке.</span><span class="sxs-lookup"><span data-stu-id="e1878-115">Update the database with all the changes shown in the list.</span></span>  
  
 <span data-ttu-id="e1878-116">**Нет**</span><span class="sxs-lookup"><span data-stu-id="e1878-116">**No**</span></span>  
 <span data-ttu-id="e1878-117">Отменить сохранение.</span><span class="sxs-lookup"><span data-stu-id="e1878-117">Cancel the save action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1878-118">Чтобы обновить диаграмму до соответствия с базой данных, закройте ее без сохранения изменений, щелкните правой кнопкой мыши на обозревателе серверов и выберите «Обновить», затем снова откройте диаграмму.</span><span class="sxs-lookup"><span data-stu-id="e1878-118">To refresh your diagram to match the database, close it without saving changes, right-click the diagram in Server Explorer and click Refresh, and then reopen the diagram.</span></span>  
  
 <span data-ttu-id="e1878-119">**Сохранить текстовый файл**</span><span class="sxs-lookup"><span data-stu-id="e1878-119">**Save Text File**</span></span>  
 <span data-ttu-id="e1878-120">Отображает диалоговое окно **Сохранить как** , которое позволяет указать расположение текстового файла, содержащего список изменений в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e1878-120">Display the **Save As** dialog box, letting you specify a location for a text file containing a list of the database changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1878-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1878-121">See Also</span></span>  
 <span data-ttu-id="e1878-122">[Выверка диаграммы базы данных с измененной базой данных &#40;визуальные инструменты для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e1878-122">[Reconcile a Database Diagram with a Modified Database &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="e1878-123">Многопользовательские среды (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="e1878-123">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
