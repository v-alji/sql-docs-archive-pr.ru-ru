---
title: Диалоговое окно «Получение» (система управления версиями) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.GetVersionDialog
helpviewer_keywords:
- Get dialog box
ms.assetid: 048564d3-6c58-405b-8b57-b690fbfdbe9e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 6d949a649a35ee3c5a6521223d45975b7c372aff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669052"
---
# <a name="get-dialog-box-source-control"></a><span data-ttu-id="85c4d-102">Диалоговое окно «Получить» (система управления версиями)</span><span class="sxs-lookup"><span data-stu-id="85c4d-102">Get Dialog Box (Source Control)</span></span>
  <span data-ttu-id="85c4d-103">Получает доступную только для чтения копию выбранного элемента из базы данных системы управления версиями, помещая ее в вашу рабочую папку или в другую указанную папку.</span><span class="sxs-lookup"><span data-stu-id="85c4d-103">Retrieves a read-only copy of the selected item from the source control database to your working folder, or another folder that you specify.</span></span>  
  
## <a name="dialog-box-access"></a><span data-ttu-id="85c4d-104">Доступ к диалоговому окну</span><span class="sxs-lookup"><span data-stu-id="85c4d-104">Dialog Box Access</span></span>  
 <span data-ttu-id="85c4d-105">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]выберите элемент в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="85c4d-105">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], select an item in Solution Explorer.</span></span> <span data-ttu-id="85c4d-106">В меню **Файл** выберите пункт **Система управления версиями** , затем — **Получить**.</span><span class="sxs-lookup"><span data-stu-id="85c4d-106">On the **File** menu, click **Source Control,** then click **Get**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85c4d-107">Вызвать это диалоговое окно также можно, щелкнув правой кнопкой мыши элемент в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="85c4d-107">This dialog box is also available by right-clicking the item in Solution Explorer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="85c4d-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="85c4d-108">Options</span></span>  
 <span data-ttu-id="85c4d-109">**Действие**</span><span class="sxs-lookup"><span data-stu-id="85c4d-109">**Action**</span></span>  
 <span data-ttu-id="85c4d-110">Указывает действие, выполняемое для элементов при их получении.</span><span class="sxs-lookup"><span data-stu-id="85c4d-110">Specifies the action being performed on the items to retrieve.</span></span>  
  
 <span data-ttu-id="85c4d-111">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="85c4d-111">**Columns**</span></span>  
 <span data-ttu-id="85c4d-112">Определяет столбцы для вывода и порядок, в котором они будут выводиться.</span><span class="sxs-lookup"><span data-stu-id="85c4d-112">Identifies columns to display and the order in which they are displayed.</span></span>  
  
 <span data-ttu-id="85c4d-113">**Плоское представление**</span><span class="sxs-lookup"><span data-stu-id="85c4d-113">**Flat View**</span></span>  
 <span data-ttu-id="85c4d-114">Выводит получаемые файлы как плоские списки под их соединениями системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="85c4d-114">Display the files you are retrieving as flat lists under their source control connection.</span></span>  
  
 <span data-ttu-id="85c4d-115">**Время изменения**</span><span class="sxs-lookup"><span data-stu-id="85c4d-115">**Modified Time**</span></span>  
 <span data-ttu-id="85c4d-116">Выводит время последнего изменения данного элемента.</span><span class="sxs-lookup"><span data-stu-id="85c4d-116">Displays the time when an item was last modified.</span></span>  
  
 <span data-ttu-id="85c4d-117">**имя**;</span><span class="sxs-lookup"><span data-stu-id="85c4d-117">**Name**</span></span>  
 <span data-ttu-id="85c4d-118">Выводит имена получаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="85c4d-118">Display the names of the items to retrieve.</span></span> <span data-ttu-id="85c4d-119">Напротив элементов отображаются флажки, которые установлены.</span><span class="sxs-lookup"><span data-stu-id="85c4d-119">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="85c4d-120">Если какой-либо элемент получать не нужно, снимите его флажок.</span><span class="sxs-lookup"><span data-stu-id="85c4d-120">If you do not want to retrieve a particular item, clear its check box.</span></span>  
  
 <span data-ttu-id="85c4d-121">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="85c4d-121">**Options**</span></span>  
 <span data-ttu-id="85c4d-122">Выводит параметры получения, специфичные для подключаемых модулей, если щелкнуть стрелку справа от данной кнопки.</span><span class="sxs-lookup"><span data-stu-id="85c4d-122">Displays source safe plug-in-specific get options when the arrow to the right of the button is clicked.</span></span>  
  
 <span data-ttu-id="85c4d-123">**Sort**</span><span class="sxs-lookup"><span data-stu-id="85c4d-123">**Sort**</span></span>  
 <span data-ttu-id="85c4d-124">Сортировка порядка отображаемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="85c4d-124">Sort the order of the displayed columns.</span></span>  
  
 <span data-ttu-id="85c4d-125">**Представление в виде дерева**</span><span class="sxs-lookup"><span data-stu-id="85c4d-125">**Tree View**</span></span>  
 <span data-ttu-id="85c4d-126">Выводит иерархию папок и файлов для получаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="85c4d-126">Display the folder and file hierarchy for the items you are retrieving.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c4d-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="85c4d-127">See Also</span></span>  
 <span data-ttu-id="85c4d-128">[Получение файлов](../../2014/database-engine/retrieve-files.md) </span><span class="sxs-lookup"><span data-stu-id="85c4d-128">[Retrieve Files](../../2014/database-engine/retrieve-files.md) </span></span>  
 [<span data-ttu-id="85c4d-129">Обозреватель решений для системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="85c4d-129">Solution Explorer Source Control</span></span>](../../2014/database-engine/solution-explorer-source-control.md)  
  
  
