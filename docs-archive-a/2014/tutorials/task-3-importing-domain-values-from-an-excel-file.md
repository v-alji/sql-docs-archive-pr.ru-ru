---
title: Задача 3. Импорт значений домена из файла Excel | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 242e8309-1195-495b-9cd5-aa127748c185
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 707a3925bb6d0014e2a1248f904123b076024e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656104"
---
# <a name="task-3-importing-domain-values-from-an-excel-file"></a><span data-ttu-id="cf09b-102">Задача 3. Импорт значений домена из файла Excel</span><span class="sxs-lookup"><span data-stu-id="cf09b-102">Task 3: Importing Domain Values from an Excel File</span></span>

  <span data-ttu-id="cf09b-103">При выполнении этой задачи вы импортируете значения для домена **Штат** из листа файла Excel.</span><span class="sxs-lookup"><span data-stu-id="cf09b-103">In this task, you import values for the **State** domain from a worksheet of an Excel file.</span></span>

1.  <span data-ttu-id="cf09b-104">Выберите домен **Штат** в **списке доменов**.</span><span class="sxs-lookup"><span data-stu-id="cf09b-104">Click **State** domain in the **Domain list**.</span></span>

2.  <span data-ttu-id="cf09b-105">Убедитесь, что вкладка **Значения домена** активна в области справа.</span><span class="sxs-lookup"><span data-stu-id="cf09b-105">Ensure that the **Domain Values** tab is active in the right pane.</span></span>

3.  <span data-ttu-id="cf09b-106">В области справа щелкните **стрелку вниз** на панели инструментов рядом с кнопкой **Импортировать значения** и нажмите кнопку **Импорт допустимых значений из Excel**.</span><span class="sxs-lookup"><span data-stu-id="cf09b-106">In the right pane, from the toolbar, click **down arrow** next to the **Import Values** button, and click **Import Valid Values from Excel**.</span></span>

     <span data-ttu-id="cf09b-107">![Импорт допустимых значений из меню Excel](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Импорт допустимых значений из меню Excel")</span><span class="sxs-lookup"><span data-stu-id="cf09b-107">![Import Valid Values from Excel Menu](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Import Valid Values from Excel Menu")</span></span>

4.  <span data-ttu-id="cf09b-108">Нажмите кнопку **Обзор**, выберите файл **Suppliers.xls**и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="cf09b-108">Click **Browse**, select **Suppliers.xls**, and click **Open**.</span></span>

5.  <span data-ttu-id="cf09b-109">Выберите значение **StatesToImport$** для параметра **Лист**.</span><span class="sxs-lookup"><span data-stu-id="cf09b-109">Select **StatesToImport$** for the **Worksheet**.</span></span>

     <span data-ttu-id="cf09b-110">![Диалоговое окно «Импорт значений домена»](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Диалоговое окно «Импорт значений домена»")</span><span class="sxs-lookup"><span data-stu-id="cf09b-110">![Import Domain Values Dialog Box](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Import Domain Values Dialog Box")</span></span>

6.  <span data-ttu-id="cf09b-111">Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Импорт значений домена** .</span><span class="sxs-lookup"><span data-stu-id="cf09b-111">Click **OK** to close the **Import Domain Values** dialog box.</span></span> <span data-ttu-id="cf09b-112">Должны появиться все названия штатов, импортированных в список.</span><span class="sxs-lookup"><span data-stu-id="cf09b-112">You should see all the names of states you imported in the list.</span></span> <span data-ttu-id="cf09b-113">Обратите внимание, что флажок **Показать только новые** после импорта устанавливается автоматически.</span><span class="sxs-lookup"><span data-stu-id="cf09b-113">Notice that **Show Only New** option is automatically selected after importing.</span></span> <span data-ttu-id="cf09b-114">Когда вы импортируете значения и не видите старые значения в списке, это происходит потому, что этот параметр автоматически включается после импорта.</span><span class="sxs-lookup"><span data-stu-id="cf09b-114">When you import values and you don't see the old values in the list, it is because this option is automatically enabled after importing.</span></span> <span data-ttu-id="cf09b-115">Чтобы увидеть все значения, снимите флажок.</span><span class="sxs-lookup"><span data-stu-id="cf09b-115">To see all the values, clear the check box.</span></span> <span data-ttu-id="cf09b-116">При повторном импорте набора значений ни одно из значений не будет импортировано, так как они уже есть в домене.</span><span class="sxs-lookup"><span data-stu-id="cf09b-116">If you import the same set of values again, none of the values are imported as they already exist in the domain.</span></span>

     <span data-ttu-id="cf09b-117">![Флажок «Показывать только новое» в значениях домена](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Флажок «Показывать только новое» в значениях домена")</span><span class="sxs-lookup"><span data-stu-id="cf09b-117">![Show Only New Checkbox on Domain Values](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Show Only New Checkbox on Domain Values")</span></span>

## <a name="next-step"></a><span data-ttu-id="cf09b-118">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="cf09b-118">Next Step</span></span>
 [<span data-ttu-id="cf09b-119">Задача 4. Задание правил домена</span><span class="sxs-lookup"><span data-stu-id="cf09b-119">Task 4: Setting Domain Rules</span></span>](../../2014/tutorials/task-4-setting-domain-rules.md)


