---
title: Выбор элементов инструментария (страница "Задачи обслуживания") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vs.chooseitems.maintenance_tasks
- VS.ToolboxPages.Maintenance_Tasks
helpviewer_keywords:
- Customize Toolbox dialog box
ms.assetid: b92c9054-7479-45d8-a54c-c1bb6699bdb3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28c90cd0abc76a7ae721ff0580aa119c3c5639b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733450"
---
# <a name="choose-toolbox-items-maintenance-tasks-page"></a><span data-ttu-id="1e246-102">Выбор элементов инструментария (страница «Задачи обслуживания»)</span><span class="sxs-lookup"><span data-stu-id="1e246-102">Choose Toolbox Items (Maintenance Tasks Page)</span></span>
  <span data-ttu-id="1e246-103">На этой вкладке диалогового окна **Настройка области элементов** выводится список всех компонентов задачи обслуживания, зарегистрированных на компьютере, и предоставляется возможность изменять компоненты, отображаемые на панели элементов.</span><span class="sxs-lookup"><span data-stu-id="1e246-103">This tab of the **Customize Toolbox** dialog box displays a list of all maintenancetask components registered on your computer and makes it possible for you to change the ones that are displayed in the Toolbox.</span></span> <span data-ttu-id="1e246-104">Диалоговое окно **Настройка области элементов** можно открыть из меню **Сервис** .</span><span class="sxs-lookup"><span data-stu-id="1e246-104">You can open the **Customize Toolbox** dialog box from the **Tools** menu.</span></span> <span data-ttu-id="1e246-105">Для сортировки списка компонентов выберите любой заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="1e246-105">To sort the list of components, select any column heading.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e246-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e246-106">Options</span></span>  
 <span data-ttu-id="1e246-107">Вкладка **Задачи обслуживания** содержит указанные ниже столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="1e246-107">The **Maintenance Tasks** tab includes the following columns of information.</span></span>  
  
 <span data-ttu-id="1e246-108">**Название**</span><span class="sxs-lookup"><span data-stu-id="1e246-108">**Name**</span></span>  
 <span data-ttu-id="1e246-109">Отображает имена доступных компонентов.</span><span class="sxs-lookup"><span data-stu-id="1e246-109">Displays the names of available components.</span></span> <span data-ttu-id="1e246-110">Перед каждым именем находится флажок.</span><span class="sxs-lookup"><span data-stu-id="1e246-110">Preceding each name is a check box.</span></span> <span data-ttu-id="1e246-111">Установленный флажок указывает на то, что среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] нашла запись для компонента в реестре компьютера.</span><span class="sxs-lookup"><span data-stu-id="1e246-111">If selected, a check box indicates that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] has found an entry for the component in your computer's registry.</span></span> <span data-ttu-id="1e246-112">Компонент уже отображается на активной вкладке **Область элементов** или будет добавлен на нее при нажатии кнопки **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e246-112">The component is either already displayed on the active **Toolbox** tab, or it will be added to it when you click **OK**.</span></span> <span data-ttu-id="1e246-113">Снятый флажок указывает на то, что компонент в текущий момент не отображается в **области элементов**или будет удален из **области элементов** при нажатии кнопки **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1e246-113">If cleared, a check box indicates that the component is not currently displayed in the **Toolbox**, or that it will be removed from the **Toolbox** when you click **OK**.</span></span>  
  
 <span data-ttu-id="1e246-114">**Путь**</span><span class="sxs-lookup"><span data-stu-id="1e246-114">**Path**</span></span>  
 <span data-ttu-id="1e246-115">Отображается полный путь к компоненту.</span><span class="sxs-lookup"><span data-stu-id="1e246-115">Displays the full path to the component.</span></span> <span data-ttu-id="1e246-116">Для идентификации компонентов по умолчанию, поставленных вместе с продуктом, отсортируйте этот столбец, а затем перейдите к компонентам, хранящимся в пути установки среды [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1e246-116">To identify the default components that shipped with the product, sort on this column and then locate those stored on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio installation path.</span></span>  
  
 <span data-ttu-id="1e246-117">**Изменено**</span><span class="sxs-lookup"><span data-stu-id="1e246-117">**Last Modified**</span></span>  
 <span data-ttu-id="1e246-118">Отображается дата последнего изменения компонента.</span><span class="sxs-lookup"><span data-stu-id="1e246-118">Displays the date when the component was last modified.</span></span>  
  
 <span data-ttu-id="1e246-119">Щелкните имя, чтобы вывести атрибуты компонента в полях **Язык** и **Версия** вместе со значком.</span><span class="sxs-lookup"><span data-stu-id="1e246-119">Click on a name to show the attributes of the component in the **Language** and **Version** boxes, along with the icon.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1e246-120">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e246-120">Options</span></span>  
 <span data-ttu-id="1e246-121">**Язык**</span><span class="sxs-lookup"><span data-stu-id="1e246-121">**Language**</span></span>  
 <span data-ttu-id="1e246-122">Язык компонента.</span><span class="sxs-lookup"><span data-stu-id="1e246-122">The language of the component.</span></span>  
  
 <span data-ttu-id="1e246-123">**Версия**</span><span class="sxs-lookup"><span data-stu-id="1e246-123">**Version**</span></span>  
 <span data-ttu-id="1e246-124">Версия компонента.</span><span class="sxs-lookup"><span data-stu-id="1e246-124">The version of the component.</span></span>  
  
  
