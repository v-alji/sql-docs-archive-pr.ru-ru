---
title: Диалоговое окно "Параметризация" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.parameter.f1
ms.assetid: fac02b6d-d247-447a-8940-e8700c7ac350
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db19844132402740aec092d6e88f3c9e3864d58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664301"
---
# <a name="parameterize-dialog-box"></a><span data-ttu-id="043c2-102">Parameterize Dialog Box</span><span class="sxs-lookup"><span data-stu-id="043c2-102">Parameterize Dialog Box</span></span>
  <span data-ttu-id="043c2-103">Диалоговое окно **Параметризация** позволяет связать новый или существующий параметр со свойством задачи.</span><span class="sxs-lookup"><span data-stu-id="043c2-103">The **Parameterize** dialog box enables you to associate a new or an existing parameter with a property of a task.</span></span> <span data-ttu-id="043c2-104">Чтобы открыть это диалоговое окно, щелкните правой кнопкой мыши задачу или вкладку «Поток управления» в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] и выберите команду **Параметризация**.</span><span class="sxs-lookup"><span data-stu-id="043c2-104">You open the dialog box by right-clicking a task or the Control Flow tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and then by clicking **Parameterize**.</span></span> <span data-ttu-id="043c2-105">Следующий список описывает элементы пользовательского интерфейса в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="043c2-105">The following list describes UI elements in the dialog box.</span></span> <span data-ttu-id="043c2-106">Дополнительные сведения о параметрах см. в разделе [Параметры служб Integration Services (SSIS)](integration-services-ssis-package-and-project-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="043c2-106">For more information about parameters, see [Integration Services &#40;SSIS&#41; Parameters](integration-services-ssis-package-and-project-parameters.md).</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="043c2-107">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="043c2-107">UI element list</span></span>  
 <span data-ttu-id="043c2-108">**Свойство**</span><span class="sxs-lookup"><span data-stu-id="043c2-108">**Property**</span></span>  
 <span data-ttu-id="043c2-109">Выберите свойство задачи, которую нужно связать с параметром.</span><span class="sxs-lookup"><span data-stu-id="043c2-109">Select the property of the task that you want to associate with a parameter.</span></span> <span data-ttu-id="043c2-110">Этот список заполняется всеми свойствами, которые могут быть параметризированы.</span><span class="sxs-lookup"><span data-stu-id="043c2-110">This list is populated with all the properties that can be parameterized.</span></span>  
  
 <span data-ttu-id="043c2-111">**Используйте существующий параметр**</span><span class="sxs-lookup"><span data-stu-id="043c2-111">**Use existing parameter**</span></span>  
 <span data-ttu-id="043c2-112">Выберите этот параметр для связывания свойства задачи с существующим параметром, а затем выберите параметр из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="043c2-112">Select this option to associate the property of task with an existing parameter and then select the parameter from drop-down list.</span></span>  
  
 <span data-ttu-id="043c2-113">**Не используйте параметр**</span><span class="sxs-lookup"><span data-stu-id="043c2-113">**Do not use parameter**</span></span>  
 <span data-ttu-id="043c2-114">Выберите этот параметр для удаления ссылки на параметр.</span><span class="sxs-lookup"><span data-stu-id="043c2-114">Select this option to remove a reference to a parameter.</span></span> <span data-ttu-id="043c2-115">Параметр не удаляется.</span><span class="sxs-lookup"><span data-stu-id="043c2-115">The parameter is not deleted.</span></span>  
  
 <span data-ttu-id="043c2-116">**Создание нового параметра**</span><span class="sxs-lookup"><span data-stu-id="043c2-116">**Create new parameter**</span></span>  
 <span data-ttu-id="043c2-117">Выберите этот параметр для создания нового параметра, который необходимо связать со свойством задачи.</span><span class="sxs-lookup"><span data-stu-id="043c2-117">Select this option to create a new parameter that you want to associate with the property of the task.</span></span>  
  
 <span data-ttu-id="043c2-118">**имя**;</span><span class="sxs-lookup"><span data-stu-id="043c2-118">**Name**</span></span>  
 <span data-ttu-id="043c2-119">Задайте имя создаваемого параметра.</span><span class="sxs-lookup"><span data-stu-id="043c2-119">Specify the name of the parameter you want to create.</span></span>  
  
 <span data-ttu-id="043c2-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="043c2-120">**Description**</span></span>  
 <span data-ttu-id="043c2-121">Задайте описание параметра.</span><span class="sxs-lookup"><span data-stu-id="043c2-121">Specify the description for parameter.</span></span>  
  
 <span data-ttu-id="043c2-122">**Значение**</span><span class="sxs-lookup"><span data-stu-id="043c2-122">**Value**</span></span>  
 <span data-ttu-id="043c2-123">Задайте значение параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="043c2-123">Specify the default value for the parameter.</span></span> <span data-ttu-id="043c2-124">Оно также называется значением по умолчанию проекта, которое может быть переопределено позднее во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="043c2-124">This is also known as the design default, which can be overridden later at the deployment time.</span></span>  
  
 <span data-ttu-id="043c2-125">**Область**</span><span class="sxs-lookup"><span data-stu-id="043c2-125">**Scope**</span></span>  
 <span data-ttu-id="043c2-126">Укажите область действия параметра, выбрав или параметр **Проект** , или параметр **Пакет** .</span><span class="sxs-lookup"><span data-stu-id="043c2-126">Specify the scope of the parameter by selecting either **Project** or **Package** option.</span></span> <span data-ttu-id="043c2-127">Параметры проекта используются для предоставления любых внешних данных, получаемых проектом, одному пакету в проекте или более.</span><span class="sxs-lookup"><span data-stu-id="043c2-127">Project parameters are used to supply any external input the project receives to one or more packages in the project.</span></span> <span data-ttu-id="043c2-128">Параметры пакета позволяют изменить выполнение пакета. При этом изменять пакет и развертывать его повторно не придется.</span><span class="sxs-lookup"><span data-stu-id="043c2-128">Package parameters allow you to modify package execution without having to edit and redeploy the package.</span></span>  
  
 <span data-ttu-id="043c2-129">**Регистр**</span><span class="sxs-lookup"><span data-stu-id="043c2-129">**Sensitive**</span></span>  
 <span data-ttu-id="043c2-130">Установив или сняв флажок, определите конфиденциальность параметра.</span><span class="sxs-lookup"><span data-stu-id="043c2-130">Specify whether the parameter is a sensitive by checking or clearing the check box.</span></span> <span data-ttu-id="043c2-131">Конфиденциальные значения параметров шифруются в каталоге и при просмотре с помощью Transact-SQL или в среде SQL Server Management Studio отображаются как значения NULL.</span><span class="sxs-lookup"><span data-stu-id="043c2-131">Sensitive parameter values are encrypted in the catalog and appear as a NULL value when viewed with Transact-SQL or SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="043c2-132">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="043c2-132">**Required**</span></span>  
 <span data-ttu-id="043c2-133">Укажите, необходимо ли задавать параметру значение, отличное от значения по умолчанию проекта, перед выполнением пакета.</span><span class="sxs-lookup"><span data-stu-id="043c2-133">Specify whether the parameter requires that a value, other than the design default, is specified before the package can execute.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="043c2-134">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="043c2-134">UI element list</span></span>  
  
