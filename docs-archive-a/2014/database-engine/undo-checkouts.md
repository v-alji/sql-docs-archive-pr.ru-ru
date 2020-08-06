---
title: Отменить извлечение | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourcControl.UndoCheckDialog
helpviewer_keywords:
- checking out files
- checkout source controls [SQL Server]
- undoing checkouts
ms.assetid: a6596b20-3aa5-4dc4-a4c5-3649f1f5a20e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ff6e6041b59caa75bf7f8530d915db48e0379338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655313"
---
# <a name="undo-checkouts"></a><span data-ttu-id="a21bb-102">Отмена извлечения</span><span class="sxs-lookup"><span data-stu-id="a21bb-102">Undo Checkouts</span></span>
  <span data-ttu-id="a21bb-103">Чтобы отменить существующее извлечение, следует использовать команду **Отмена извлечения** .</span><span class="sxs-lookup"><span data-stu-id="a21bb-103">You can use the **Undo Checkout** command to cancel an existing checkout.</span></span> <span data-ttu-id="a21bb-104">Она особенно удобна, если необходимо выполнить откат изменений после сохранения их в файле.</span><span class="sxs-lookup"><span data-stu-id="a21bb-104">This is particularly useful when you have modified and saved a file, and then later need to roll back your changes.</span></span>  
  
 <span data-ttu-id="a21bb-105">В зависимости от параметров, установленных в диалоговом окне **Дополнительные параметры отмены извлечений** , среда Studio либо оставляет работающую копию элемента на диске, либо заменяет ее последней версией из системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="a21bb-105">Depending on the options you set in the **Undo Checkout Advanced Options** dialog box, the Studio environment either leaves the working copy of the item on your local disk or replaces it with the latest source-controlled version.</span></span> <span data-ttu-id="a21bb-106">Если изменения элемента были произведены вне контекста системы управления версиями, полученная версия может оказаться не последней.</span><span class="sxs-lookup"><span data-stu-id="a21bb-106">If someone has modified the item outside the context of the source control system, the retrieved version may not be the latest one.</span></span>  
  
### <a name="to-undo-a-checkout"></a><span data-ttu-id="a21bb-107">Отмена извлечения</span><span class="sxs-lookup"><span data-stu-id="a21bb-107">To undo a checkout</span></span>  
  
1.  <span data-ttu-id="a21bb-108">Выберите проект в Обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="a21bb-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="a21bb-109">В меню **Файл** укажите пункт **Управление версиями**, затем выберите **Отменить извлечение**.</span><span class="sxs-lookup"><span data-stu-id="a21bb-109">On the **File** menu, point to **Source Control**, and then click **Undo Checkout**.</span></span>  
  
3.  <span data-ttu-id="a21bb-110">В диалоговом окне **Отмена извлечения** выберите соответствующие параметры и нажмите кнопку **Отменить извлечение** .</span><span class="sxs-lookup"><span data-stu-id="a21bb-110">In the **Undo Checkout** dialog box, select the appropriate options, and then click the **Undo Checkout** button.</span></span>  
  
     <span data-ttu-id="a21bb-111">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="a21bb-111">**Columns**</span></span>  
     <span data-ttu-id="a21bb-112">Определите отображаемые столбцы и порядок, в котором они будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="a21bb-112">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="a21bb-113">**Плоское представление**</span><span class="sxs-lookup"><span data-stu-id="a21bb-113">**Flat View**</span></span>  
     <span data-ttu-id="a21bb-114">Позволяет отобразить элементы в виде плоских списков внутри соответствующего подключения к системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="a21bb-114">Display the items as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="a21bb-115">**имя**;</span><span class="sxs-lookup"><span data-stu-id="a21bb-115">**Name**</span></span>  
     <span data-ttu-id="a21bb-116">Отображает имена элементов, для которых нужно отменить извлечение.</span><span class="sxs-lookup"><span data-stu-id="a21bb-116">Displays the names of the items for which to undo the checkout.</span></span> <span data-ttu-id="a21bb-117">Напротив элементов отображаются флажки, которые установлены.</span><span class="sxs-lookup"><span data-stu-id="a21bb-117">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="a21bb-118">Если не требуется отменять извлечение какого-либо элемента, снимите соответствующий флажок.</span><span class="sxs-lookup"><span data-stu-id="a21bb-118">If you do not want to undo the checkout of an item, clear its check box.</span></span>  
  
     <span data-ttu-id="a21bb-119">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="a21bb-119">**Options**</span></span>  
     <span data-ttu-id="a21bb-120">При нажатии стрелки справа от кнопки отображаются параметры отмены извлечения, специфические для конкретного модуля управления версиями.</span><span class="sxs-lookup"><span data-stu-id="a21bb-120">Displays source control plug-in-specific undo checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="a21bb-121">**Sort**</span><span class="sxs-lookup"><span data-stu-id="a21bb-121">**Sort**</span></span>  
     <span data-ttu-id="a21bb-122">Отсортируйте порядок отображаемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="a21bb-122">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="a21bb-123">**Представление в виде дерева**</span><span class="sxs-lookup"><span data-stu-id="a21bb-123">**Tree View**</span></span>  
     <span data-ttu-id="a21bb-124">Отображает иерархию папок и элементов для элементов, извлечение которых отменяется.</span><span class="sxs-lookup"><span data-stu-id="a21bb-124">Display the folder and item hierarchy for items on which you are reversing the checkout.</span></span>  
  
     <span data-ttu-id="a21bb-125">**Отмена извлечения**</span><span class="sxs-lookup"><span data-stu-id="a21bb-125">**Undo Checkout**</span></span>  
     <span data-ttu-id="a21bb-126">Позволяет отменить извлечение, при этом отменяются какие-либо изменения в извлекаемом файле.</span><span class="sxs-lookup"><span data-stu-id="a21bb-126">Revert the checkout, discarding any changes to the checked-out file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a21bb-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="a21bb-127">See Also</span></span>  
 <span data-ttu-id="a21bb-128">[Извлечение файлов](../../2014/database-engine/check-out-files.md) </span><span class="sxs-lookup"><span data-stu-id="a21bb-128">[Check Out Files](../../2014/database-engine/check-out-files.md) </span></span>  
 [<span data-ttu-id="a21bb-129">Управление извлечениями</span><span class="sxs-lookup"><span data-stu-id="a21bb-129">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
