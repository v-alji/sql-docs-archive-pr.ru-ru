---
title: Добавление, перемещение или удаление текстового поля (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f042cf81-d933-4ac7-9287-c074a46bde98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd85415fd2f0bac2a37b3fbda06795e10f351b19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739350"
---
# <a name="add-move-or-delete-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="03689-102">Добавление, перемещение или удаление текстового поля (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="03689-102">Add, Move, or Delete a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="03689-103">Текстовые поля — это наиболее часто используемые элементы отчета.</span><span class="sxs-lookup"><span data-stu-id="03689-103">Text boxes are the most commonly used report item in reports.</span></span> <span data-ttu-id="03689-104">В текст отчета можно добавить текстовое поле, в котором будут отображаться такие сведения, как заголовки, выбранные значения параметров, встроенные поля и даты.</span><span class="sxs-lookup"><span data-stu-id="03689-104">You can add a text box to the report body to display information such as titles, parameter choices, built-in fields, and dates.</span></span>  
  
 <span data-ttu-id="03689-105">Каждая ячейка в таблице или матрице представляет собой текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="03689-105">Every cell in a table or matrix is really a text box.</span></span> <span data-ttu-id="03689-106">Почти все данные, отображаемые в отчете с таблицами и матрицами, являются результатом оценки обработчиком отчетов содержимого всех текстовых полей в отчете.</span><span class="sxs-lookup"><span data-stu-id="03689-106">Almost all report data displayed in a report with tables and matrices is the result of the report processor evaluating the contents of each text box in the report.</span></span> <span data-ttu-id="03689-107">Поэтому ячейки можно форматировать аналогично другим текстовым полям вне области данных.</span><span class="sxs-lookup"><span data-stu-id="03689-107">As such, you can format cells in the same way you would format other text boxes outside the data region.</span></span>  
  
 <span data-ttu-id="03689-108">Чтобы включить текстовое поле в область данных списка, необходимо сначала создать текстовое поле, а затем перетащить его в список.</span><span class="sxs-lookup"><span data-stu-id="03689-108">To add a text box to a list data region, you must first add the text box and then drag it into the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="03689-109">Щелкнув текстовое поле, можно изменить текст, расположенный в нем.</span><span class="sxs-lookup"><span data-stu-id="03689-109">When you click a text box, you're immediately editing the text in the text box.</span></span> <span data-ttu-id="03689-110">Для выбора самого текстового поля, а не текста в нем, нажмите клавишу ESC.</span><span class="sxs-lookup"><span data-stu-id="03689-110">To select the text box itself, not the text in it, press ESC.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-text-box"></a><span data-ttu-id="03689-111">Добавление текстового поля</span><span class="sxs-lookup"><span data-stu-id="03689-111">To add a text box</span></span>  
  
1.  <span data-ttu-id="03689-112">На вкладке **Вставка** в представлении конструктора щелкните **Текстовое поле**.</span><span class="sxs-lookup"><span data-stu-id="03689-112">On the **Insert** tab in Design view, click **Text Box**.</span></span>  
  
2.  <span data-ttu-id="03689-113">В области конструктора щелкните и перетащите указатель мыши, чтобы получилось текстовое поле нужного размера.</span><span class="sxs-lookup"><span data-stu-id="03689-113">On the design surface, click and then drag a box to the desired size of the text box.</span></span> <span data-ttu-id="03689-114">В качестве альтернативы можно щелкнуть область конструктора, чтобы создать текстовое поле с размером по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="03689-114">Alternatively, click the design surface to create a text box of default size.</span></span>  
  
### <a name="to-add-a-text-box-in-a-list"></a><span data-ttu-id="03689-115">Добавление текстового поля в список</span><span class="sxs-lookup"><span data-stu-id="03689-115">To add a text box in a list</span></span>  
  
1.  <span data-ttu-id="03689-116">На вкладке **Вставка** в режиме конструктора отчетов щелкните **Список**.</span><span class="sxs-lookup"><span data-stu-id="03689-116">On the **Insert** tab in report design view, click **List**.</span></span>  
  
2.  <span data-ttu-id="03689-117">В области конструктора щелкните и перетащите указатель мыши, чтобы получился список нужного размера.</span><span class="sxs-lookup"><span data-stu-id="03689-117">On the design surface, click and then drag a box to the desired size of the list.</span></span> <span data-ttu-id="03689-118">Или щелкните область конструктора, чтобы создать список с размером по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="03689-118">Alternatively, click the design surface to create a list of default size.</span></span>  
  
3.  <span data-ttu-id="03689-119">На вкладке **Вставка** щелкните **Текстовое поле**.</span><span class="sxs-lookup"><span data-stu-id="03689-119">On the **Insert** tab, click **Text Box**.</span></span>  
  
4.  <span data-ttu-id="03689-120">Щелкните в области конструктора в пределах списка, добавленного на шаге 1, и перетащите указатель мыши, чтобы получилось текстовое поле нужного размера.</span><span class="sxs-lookup"><span data-stu-id="03689-120">On the design surface, click and then drag a box to the desired size of the text box inside the list you added in step 1.</span></span> <span data-ttu-id="03689-121">Также можно щелкнуть область конструктора в пределах списка, чтобы создать текстовое поле с размером по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="03689-121">Alternatively, click the design surface inside the list to create a text box of default size.</span></span>  
  
5.  <span data-ttu-id="03689-122">Чтобы удостовериться, что текстовое поле было помещено в список, выберите текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="03689-122">To confirm the text box is correctly nested inside the list, select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03689-123">Если щелкнуть текстовое поле в режиме редактирования, то для выбора этого текстового поля необходимо нажать клавишу ESC.</span><span class="sxs-lookup"><span data-stu-id="03689-123">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
6.  <span data-ttu-id="03689-124">В панели свойств проверьте, что его свойство **Родитель** указывает на прямоугольник, который был автоматически добавлен в область данных списка.</span><span class="sxs-lookup"><span data-stu-id="03689-124">In the Properties pane, verify that the **Parent** property is the rectangle that was automatically added to the list data region.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03689-125">Если панель свойств не появилась, проверьте **Свойства** на вкладке **Вид** .</span><span class="sxs-lookup"><span data-stu-id="03689-125">If the Properties pane is not visible, check **Properties** on the **View** tab.</span></span>  
  
### <a name="to-move-a-text-box"></a><span data-ttu-id="03689-126">Перемещение текстового поля</span><span class="sxs-lookup"><span data-stu-id="03689-126">To move a text box</span></span>  
  
1.  <span data-ttu-id="03689-127">В режиме конструктора отчетов щелкните пустое пространство внутри текстового поля, чтобы выделить это поле.</span><span class="sxs-lookup"><span data-stu-id="03689-127">In report design view, click any empty space within the text box to select the text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03689-128">Если щелкнуть текстовое поле в режиме редактирования, то для выбора этого текстового поля необходимо нажать клавишу ESC.</span><span class="sxs-lookup"><span data-stu-id="03689-128">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
2.  <span data-ttu-id="03689-129">Щелкните маркер текстового поля и перетащите текстовое поле в новое место.</span><span class="sxs-lookup"><span data-stu-id="03689-129">Click the text box handle and drag the text box to the new location.</span></span> <span data-ttu-id="03689-130">Для вертикального или горизонтального перемещения текстового поля можно использовать кнопки со стрелками.</span><span class="sxs-lookup"><span data-stu-id="03689-130">Alternatively, you can use the arrow keys to move a selected text box horizontally or vertically.</span></span> <span data-ttu-id="03689-131">Для перемещения текстового поля по области конструктора с более мелким шагом используйте кнопки со стрелками, удерживая клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="03689-131">To move the text box in smaller increments on the design surface, hold down CTRL plus the arrow keys.</span></span>  
  
### <a name="to-delete-a-text-box"></a><span data-ttu-id="03689-132">Удаление текстового поля</span><span class="sxs-lookup"><span data-stu-id="03689-132">To delete a text box</span></span>  
  
1.  <span data-ttu-id="03689-133">В режиме конструктора отчетов щелкните правой кнопкой мыши в пустом месте текстового поля, чтобы его выбрать, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="03689-133">In report design view, right-click any empty space within the text box to select it, and then click **Delete**.</span></span> <span data-ttu-id="03689-134">Также можно щелкнуть пустое пространство внутри текстового поля и нажать клавишу DEL.</span><span class="sxs-lookup"><span data-stu-id="03689-134">Alternatively, click any empty space within the text box, and then press DELETE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03689-135">Если щелкнуть текстовое поле в режиме редактирования, то для выбора этого текстового поля необходимо нажать клавишу ESC.</span><span class="sxs-lookup"><span data-stu-id="03689-135">If you click in the text box and are in edit mode, press ESC to select the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03689-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="03689-136">See Also</span></span>  
 <span data-ttu-id="03689-137">[Текстовые поля &#40;построитель отчетов и службы SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03689-137">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="03689-138">[Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="03689-138">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="03689-139">Сочетания клавиш (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="03689-139">Keyboard Shortcuts &#40;Report Builder&#41;</span></span>](../report-builder/keyboard-shortcuts-report-builder.md)  
  
  
