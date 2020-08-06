---
title: Добавление, удаление и изменение области определяемой пользователем переменной в пакете | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], adding
ms.assetid: cbf40c7f-3c8a-48cd-aefa-8b37faf8b40e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7e5980fc7f730c69ef886e4e80760cfbdc9e4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658966"
---
# <a name="add-delete-change-scope-of-user-defined-variable-in-a-package"></a><span data-ttu-id="83044-102">Добавление, удаление и изменение области определяемой пользователем переменной в пакете</span><span class="sxs-lookup"><span data-stu-id="83044-102">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>
  <span data-ttu-id="83044-103">Эти процедуры описывают добавление, удаление и изменение области видимости определенной пользователем переменной в пакете с помощью окна **Переменные** .</span><span class="sxs-lookup"><span data-stu-id="83044-103">These procedures describe how to add, delete, and change the scope of a user-defined variable in a package by using the **Variables** window.</span></span>  
  
 <span data-ttu-id="83044-104">Дополнительные сведения об области переменной см. в разделе [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="83044-104">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="83044-105">Службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] также предоставляют системные переменные, позволяющие получить системную информацию во время выполнения. Эти переменные могут использоваться в контейнерах, например в пакетах и обработчиках событий.</span><span class="sxs-lookup"><span data-stu-id="83044-105">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] also provides system variables that make system information available at run time and can be used in containers such as packages and event handlers.</span></span> <span data-ttu-id="83044-106">Системные переменные нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="83044-106">You cannot delete system variables.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="83044-107">Добавление переменной</span><span class="sxs-lookup"><span data-stu-id="83044-107">To add a variable</span></span>  
  
1.  <span data-ttu-id="83044-108">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте необходимый пакет служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83044-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="83044-109">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="83044-109">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="83044-110">Для определения области переменной в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="83044-110">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="83044-111">Чтобы установить в качестве области область пакета, щелкните в любом месте области конструктора на вкладке **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="83044-111">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="83044-112">Чтобы установить в качестве области область обработчика события, выберите исполняемый объект и обработчик событий в области конструктора на вкладке **Обработчик событий** .</span><span class="sxs-lookup"><span data-stu-id="83044-112">To set the scope to an event handler, select an executable and an event handler on the design surface of the **Event Handler** tab.</span></span>  
  
    -   <span data-ttu-id="83044-113">Чтобы установить в качестве области область задачи или контейнера, щелкните задачу или контейнер в области конструктора на вкладке **Поток управления** или вкладке **Обработчик события** .</span><span class="sxs-lookup"><span data-stu-id="83044-113">To set the scope to a task or container, on the design surface of the **Control Flow** tab or the **Event Handler** tab, click a task or container.</span></span>  
  
4.  <span data-ttu-id="83044-114">В меню **Службы SSIS** щелкните **Переменные**.</span><span class="sxs-lookup"><span data-stu-id="83044-114">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="83044-115">При необходимости окно **Переменные** можно открыть, назначив команде View.Variables нужное сочетание клавиш на странице **Клавиатура** диалогового окна **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="83044-115">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
5.  <span data-ttu-id="83044-116">В окне **Переменные** щелкните значок **Добавить переменную** .</span><span class="sxs-lookup"><span data-stu-id="83044-116">In the **Variables** window, click the **Add Variable** icon.</span></span> <span data-ttu-id="83044-117">Новая переменная будет добавлена в список.</span><span class="sxs-lookup"><span data-stu-id="83044-117">The new variable is added to the list.</span></span>  
  
6.  <span data-ttu-id="83044-118">Также можно щелкнуть значок **Параметры сетки** , выбрать дополнительные столбцы для отображения в диалоговом окне **Параметры сетки переменных** и нажать кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="83044-118">Optionally, click the **Grid Options** icon, select additional columns to show in the **Variables Grid Options** dialog box, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="83044-119">Если необходимо, установите свойства переменной.</span><span class="sxs-lookup"><span data-stu-id="83044-119">Optionally, set the variable properties.</span></span> <span data-ttu-id="83044-120">Дополнительные сведения см. в разделе [Установка свойств определяемой пользователем переменной](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span><span class="sxs-lookup"><span data-stu-id="83044-120">For more information, see [Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span></span>  
  
8.  <span data-ttu-id="83044-121">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="83044-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-variable"></a><span data-ttu-id="83044-122">Удаление переменной</span><span class="sxs-lookup"><span data-stu-id="83044-122">To delete a variable</span></span>  
  
1.  <span data-ttu-id="83044-123">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="83044-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="83044-124">В окне обозревателя решений щелкните пакет правой кнопкой мыши для его открытия.</span><span class="sxs-lookup"><span data-stu-id="83044-124">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="83044-125">В меню **Службы SSIS** щелкните **Переменные**.</span><span class="sxs-lookup"><span data-stu-id="83044-125">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="83044-126">При необходимости окно **Переменные** можно открыть, назначив команде View.Variables нужное сочетание клавиш на странице **Клавиатура** диалогового окна **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="83044-126">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="83044-127">Выберите удаляемую переменную и нажмите кнопку **Удалить переменную**.</span><span class="sxs-lookup"><span data-stu-id="83044-127">Select the variable to delete, and then click **Delete Variable**.</span></span>  
  
     <span data-ttu-id="83044-128">Если переменная не отображается в окне Переменные, щелкните **Параметры сетки** , а затем выберите **Показать переменные всех областей**.</span><span class="sxs-lookup"><span data-stu-id="83044-128">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="83044-129">Если открывается диалоговое окно **Подтверждение удаления переменных** , для подтверждения нажмите кнопку **Да** .</span><span class="sxs-lookup"><span data-stu-id="83044-129">If the **Confirm Deletion of Variables** dialog box opens, click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="83044-130">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="83044-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-change-the-scope-of-a-variable"></a><span data-ttu-id="83044-131">Изменение области видимости переменной</span><span class="sxs-lookup"><span data-stu-id="83044-131">To change the scope of a variable</span></span>  
  
1.  <span data-ttu-id="83044-132">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="83044-132">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="83044-133">В окне обозревателя решений щелкните пакет правой кнопкой мыши для его открытия.</span><span class="sxs-lookup"><span data-stu-id="83044-133">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="83044-134">В меню **Службы SSIS** щелкните **Переменные**.</span><span class="sxs-lookup"><span data-stu-id="83044-134">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="83044-135">При необходимости окно **Переменные** можно открыть, назначив команде View.Variables нужное сочетание клавиш на странице **Клавиатура** диалогового окна **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="83044-135">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="83044-136">Выберите переменную и нажмите кнопку **Переместить переменную**.</span><span class="sxs-lookup"><span data-stu-id="83044-136">Select the variable and then click **Move Variable**.</span></span>  
  
     <span data-ttu-id="83044-137">Если переменная не отображается в окне Переменные, щелкните **Параметры сетки** , а затем выберите **Показать переменные всех областей**.</span><span class="sxs-lookup"><span data-stu-id="83044-137">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="83044-138">В диалоговом окне **Выбор новой области** выберите пакет, контейнер, задачу или обработчик событий в пакете, чтобы изменить область переменной.</span><span class="sxs-lookup"><span data-stu-id="83044-138">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
6.  <span data-ttu-id="83044-139">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="83044-139">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83044-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="83044-140">See Also</span></span>  
 <span data-ttu-id="83044-141">[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="83044-141">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="83044-142">[Использование переменных в пакетах](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="83044-142">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="83044-143">[Задание свойств определяемой пользователем переменной](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span><span class="sxs-lookup"><span data-stu-id="83044-143">[Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span></span>  
 [<span data-ttu-id="83044-144">Использование значений переменных и параметров в дочернем пакете</span><span class="sxs-lookup"><span data-stu-id="83044-144">Use the Values of Variables and Parameters in a Child Package</span></span>](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md)  
  
  
