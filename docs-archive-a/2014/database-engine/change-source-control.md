---
title: Изменить систему управления версиями | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- IDD_SCC_CONNECTION_DIALOG
helpviewer_keywords:
- Change Source Control dialog box
ms.assetid: e6a5d83c-5809-4c56-907a-73d0c7ccdd7a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 55831529243608e8c71972a31009e5672fb0234f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665585"
---
# <a name="change-source-control"></a><span data-ttu-id="5177f-102">Изменение систем управления версиями</span><span class="sxs-lookup"><span data-stu-id="5177f-102">Change Source Control</span></span>
  <span data-ttu-id="5177f-103">Создает и управляет соединениями и привязками, которые связывают локально хранимые решения или проект с папкой базы данных системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5177f-103">Creates and manages the connections and bindings that link a locally saved solution or project to a source control database folder.</span></span>  
  
## <a name="dialog-box-access"></a><span data-ttu-id="5177f-104">Доступ к диалоговому окну</span><span class="sxs-lookup"><span data-stu-id="5177f-104">Dialog Box Access</span></span>  
 <span data-ttu-id="5177f-105">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]выберите элемент в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="5177f-105">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], select an item in Solution Explorer.</span></span> <span data-ttu-id="5177f-106">В меню **Файл** выберите **Система управления версиями**, а затем **Изменение системы управления версиями**.</span><span class="sxs-lookup"><span data-stu-id="5177f-106">On the **File** menu, click **Source Control**, and then **Change Source Control**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5177f-107">Вызвать это диалоговое окно также можно, щелкнув правой кнопкой мыши элемент в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="5177f-107">This dialog box is also available by right-clicking the item in Solution Explorer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5177f-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="5177f-108">Options</span></span>  
 <span data-ttu-id="5177f-109">**Выполняется**</span><span class="sxs-lookup"><span data-stu-id="5177f-109">**Bind**</span></span>  
 <span data-ttu-id="5177f-110">Связывает выбранный элемент с расположением заданного сервера системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5177f-110">Associate selected items with a specified source control server location.</span></span> <span data-ttu-id="5177f-111">Например, эту кнопку можно использовать для привязки к последней используемой папке сервера системы управления версиями и базой данных.</span><span class="sxs-lookup"><span data-stu-id="5177f-111">For example, you can use this button to bind to the last known source control server folder and database.</span></span> <span data-ttu-id="5177f-112">Если использованная в предыдущий раз папка сервера или база данных не может быть найдена, появится запрос для задания другого расположения.</span><span class="sxs-lookup"><span data-stu-id="5177f-112">If a recent server folder or database cannot be found, you are prompted to specify another.</span></span>  
  
 <span data-ttu-id="5177f-113">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="5177f-113">**Browse**</span></span>  
 <span data-ttu-id="5177f-114">Переместитесь к новому расположению сервера системы управления версиями для заданного элемента.</span><span class="sxs-lookup"><span data-stu-id="5177f-114">Navigate to a new source control server location for the specified item.</span></span>  
  
 <span data-ttu-id="5177f-115">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="5177f-115">**Columns**</span></span>  
 <span data-ttu-id="5177f-116">Обозначьте столбцы для отображения и порядок, в котором они будут выводиться.</span><span class="sxs-lookup"><span data-stu-id="5177f-116">Identify columns to display and the order in which they are displayed.</span></span>  
  
 <span data-ttu-id="5177f-117">**Подключить**</span><span class="sxs-lookup"><span data-stu-id="5177f-117">**Connect**</span></span>  
 <span data-ttu-id="5177f-118">Создается соединение между выбранным элементом и сервером системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5177f-118">Create a connection between selected items and the source control server.</span></span>  
  
 <span data-ttu-id="5177f-119">**Подключен**</span><span class="sxs-lookup"><span data-stu-id="5177f-119">**Connected**</span></span>  
 <span data-ttu-id="5177f-120">Отображает состояние соединения выбранного решения или проекта.</span><span class="sxs-lookup"><span data-stu-id="5177f-120">Displays the connection status of a selected solution or project.</span></span>  
  
 <span data-ttu-id="5177f-121">**Отключение**</span><span class="sxs-lookup"><span data-stu-id="5177f-121">**Disconnect**</span></span>  
 <span data-ttu-id="5177f-122">Отключает локальную копию решения или проекта на компьютере от ее главной копии в базе данных.</span><span class="sxs-lookup"><span data-stu-id="5177f-122">Disconnect the local copy of a solution or project on your computer from its master copy in the database.</span></span> <span data-ttu-id="5177f-123">Используйте эту команду перед отсоединением компьютера от сервера системы управления версиями. Например, при завершении работы переносного компьютера.</span><span class="sxs-lookup"><span data-stu-id="5177f-123">Use this command before disconnecting your computer from the source control server, for example, when working offline on your laptop.</span></span>  
  
 <span data-ttu-id="5177f-124">**OK**</span><span class="sxs-lookup"><span data-stu-id="5177f-124">**OK**</span></span>  
 <span data-ttu-id="5177f-125">Принятие изменений, выполненных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="5177f-125">Accept changes made in the dialog box.</span></span>  
  
 <span data-ttu-id="5177f-126">**Поставщик**</span><span class="sxs-lookup"><span data-stu-id="5177f-126">**Provider**</span></span>  
 <span data-ttu-id="5177f-127">Отображает имя вспомогательной программы системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5177f-127">Displays the name of your source control plug-in.</span></span>  
  
 <span data-ttu-id="5177f-128">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="5177f-128">**Refresh**</span></span>  
 <span data-ttu-id="5177f-129">Обновляет сведения о соединении для всех проектов, перечисленных в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="5177f-129">Refreshes the connection information for all projects listed in this dialog box.</span></span>  
  
 <span data-ttu-id="5177f-130">**Привязка сервера**</span><span class="sxs-lookup"><span data-stu-id="5177f-130">**Server Binding**</span></span>  
 <span data-ttu-id="5177f-131">Отображает привязку элементов к серверу системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5177f-131">Indicates the item's binding to a source control server.</span></span>  
  
 <span data-ttu-id="5177f-132">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="5177f-132">**Server Name**</span></span>  
 <span data-ttu-id="5177f-133">Отображает имя сервера системы управления версиями, к которому привязаны соответствующее решение или проект.</span><span class="sxs-lookup"><span data-stu-id="5177f-133">Displays the name of the source control server to which the corresponding solution or project is bound.</span></span>  
  
 <span data-ttu-id="5177f-134">**Решение/Проект**</span><span class="sxs-lookup"><span data-stu-id="5177f-134">**Solution/Project**</span></span>  
 <span data-ttu-id="5177f-135">Отображает имя каждого решения или проекта для текущего выбора.</span><span class="sxs-lookup"><span data-stu-id="5177f-135">Displays the name of each solution and project in the current selection.</span></span>  
  
 <span data-ttu-id="5177f-136">**Sort**</span><span class="sxs-lookup"><span data-stu-id="5177f-136">**Sort**</span></span>  
 <span data-ttu-id="5177f-137">Сортировать порядок отображаемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="5177f-137">Sort the order of displayed columns.</span></span>  
  
 <span data-ttu-id="5177f-138">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="5177f-138">**Status**</span></span>  
 <span data-ttu-id="5177f-139">Определяет состояние привязки и соединения элемента.</span><span class="sxs-lookup"><span data-stu-id="5177f-139">Identifies the binding and connection status of an item.</span></span> <span data-ttu-id="5177f-140">Возможные параметры:</span><span class="sxs-lookup"><span data-stu-id="5177f-140">Possible options are:</span></span>  
  
|<span data-ttu-id="5177f-141">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="5177f-141">**Option**</span></span>|<span data-ttu-id="5177f-142">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5177f-142">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="5177f-143">Допустимо</span><span class="sxs-lookup"><span data-stu-id="5177f-143">Valid</span></span>|<span data-ttu-id="5177f-144">Элемент корректно привязан и подсоединен к папке сервера, к которой он принадлежит.</span><span class="sxs-lookup"><span data-stu-id="5177f-144">The item is correctly bound and connected to the server folder to which it belongs.</span></span>|  
|<span data-ttu-id="5177f-145">Недопустимо</span><span class="sxs-lookup"><span data-stu-id="5177f-145">Invalid</span></span>|<span data-ttu-id="5177f-146">Элемент некорректно привязан или отсоединен от папки сервера, к которой он принадлежит.</span><span class="sxs-lookup"><span data-stu-id="5177f-146">The item is incorrectly bound to or disconnected from the folder to which it belongs.</span></span> <span data-ttu-id="5177f-147">Используйте команду **Добавить к системе управления версиями** вместо **Привязать** для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="5177f-147">Use the **Add to Source Control** command instead of **Bind** for this item.</span></span>|  
|<span data-ttu-id="5177f-148">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="5177f-148">Unknown</span></span>|<span data-ttu-id="5177f-149">Состояние элемента в системе управления версиями еще не было определено.</span><span class="sxs-lookup"><span data-stu-id="5177f-149">The status of the item under source control has not yet been determined.</span></span>|  
|<span data-ttu-id="5177f-150">Не управляется</span><span class="sxs-lookup"><span data-stu-id="5177f-150">Not Controlled</span></span>|<span data-ttu-id="5177f-151">Элемент не был включен в систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5177f-151">The item has not been placed under source control.</span></span>|  
  
 <span data-ttu-id="5177f-152">**Отменить привязку**</span><span class="sxs-lookup"><span data-stu-id="5177f-152">**Unbind**</span></span>  
 <span data-ttu-id="5177f-153">Отображает диалоговое окно **Система управления версиями** , с помощью которого можно удалить выбранные элементы из системы управления версиями и разорвать связи этих элементов с соответствующими папками.</span><span class="sxs-lookup"><span data-stu-id="5177f-153">Display the **Source Control** dialog box to allow you to remove selected items from source control and permanently disassociate the items from their present folders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5177f-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="5177f-154">See Also</span></span>  
 [<span data-ttu-id="5177f-155">Обозреватель решений для системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="5177f-155">Solution Explorer Source Control</span></span>](../../2014/database-engine/solution-explorer-source-control.md)  
  
  
