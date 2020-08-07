---
title: Сохранение пакета в качестве шаблона пакета | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- reusing packages
- templates [Integration Services]
ms.assetid: efe66cec-3933-4f6e-8d35-fe3d300de66c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 30bddb5a343e7c7aef279bc66c25be30a2cf1a12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730825"
---
# <a name="save-a-package-as-a-package-template"></a><span data-ttu-id="c0891-102">Сохранение пакета в качестве шаблона пакета</span><span class="sxs-lookup"><span data-stu-id="c0891-102">Save a Package as a Package Template</span></span>
  <span data-ttu-id="c0891-103">В этом разделе описано, как обозначить и использовать пользовательские пакеты в виде шаблонов при создании новых пакетов служб Integration Services в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0891-103">This topic describes how to designate and use custom packages as templates when you create new Integration Services packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c0891-104">По умолчанию в службах [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] используется шаблон пакета, который создает пустой пакет при добавлении нового пакета в проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0891-104">By default, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] uses a package template that creates an empty package when you add a new package to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="c0891-105">Этот шаблон по умолчанию заменить нельзя, однако можно добавить новые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="c0891-105">You cannot replace this default template, but you can add new templates.</span></span>  
  
 <span data-ttu-id="c0891-106">Для использования в роли шаблонов можно назначить несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="c0891-106">You can designate multiple packages to use as templates.</span></span> <span data-ttu-id="c0891-107">Прежде чем сделать из пользовательского пакета шаблон, необходимо создать сам пакет.</span><span class="sxs-lookup"><span data-stu-id="c0891-107">Before you can implement custom packages as templates, you must create the packages.</span></span>  
  
 <span data-ttu-id="c0891-108">При создании пакета с помощью пользовательских пакетов в виде шаблонов новые пакеты имеют те же имя и код GUID, что и шаблон.</span><span class="sxs-lookup"><span data-stu-id="c0891-108">When you create package using custom packages as templates, the new packages have the same name and GUID as the template.</span></span> <span data-ttu-id="c0891-109">Чтобы различать пакеты, необходимо обновить значение свойства `Name` и создать новый код GUID для свойства `ID`.</span><span class="sxs-lookup"><span data-stu-id="c0891-109">To differentiate among packages you should update the value of the `Name` property and generate a new GUID for the `ID` property.</span></span> <span data-ttu-id="c0891-110">Дополнительные сведения см. в разделах [Создание пакетов в SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) и [Установка свойства пакета](set-package-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c0891-110">For more information, see [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) and [Set Package Properties](set-package-properties.md).</span></span>  
  
### <a name="to-designate-a-custom-package-as-a-package-template"></a><span data-ttu-id="c0891-111">Обозначение пользовательского пакета как шаблона пакета</span><span class="sxs-lookup"><span data-stu-id="c0891-111">To designate a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="c0891-112">Найдите в файловой системе пакет, который нужно использовать в роли шаблона.</span><span class="sxs-lookup"><span data-stu-id="c0891-112">In the file system, locate the package that you want to use as template.</span></span>  
  
2.  <span data-ttu-id="c0891-113">Скопируйте пакет в папку DataTransformationItems.</span><span class="sxs-lookup"><span data-stu-id="c0891-113">Copy the package to the DataTransformationItems folder.</span></span> <span data-ttu-id="c0891-114">По умолчанию эта папка находится в каталоге «C:\Program Files\Microsoft Visual Studio 9,0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject».</span><span class="sxs-lookup"><span data-stu-id="c0891-114">By default this folder is in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span></span>  
  
3.  <span data-ttu-id="c0891-115">Повторите шаги 1 и 2 для каждого пакета, который нужно использовать в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="c0891-115">Repeat steps 1 and 2 for each package that you want to use as a template.</span></span>  
  
### <a name="to-use-a-custom-package-as-a-package-template"></a><span data-ttu-id="c0891-116">Чтобы использовать пользовательский пакет как шаблон пакета</span><span class="sxs-lookup"><span data-stu-id="c0891-116">To use a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="c0891-117">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , в котором необходимо создать пакет.</span><span class="sxs-lookup"><span data-stu-id="c0891-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you want to create a package.</span></span>  
  
2.  <span data-ttu-id="c0891-118">В обозревателе решений щелкните проект правой кнопкой мыши, укажите **Добавить** и выберите **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="c0891-118">In Solution Explorer, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
3.  <span data-ttu-id="c0891-119">В диалоговом окне **Добавить новый элемент — \<project name>** выберите проект, который нужно использовать в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="c0891-119">In the **Add New Item -\<project name>** dialog box, click the package that you want to use as a template.</span></span>  
  
     <span data-ttu-id="c0891-120">Список шаблонов включает шаблон пакетов по умолчанию с именем «Новый пакет служб SSIS».</span><span class="sxs-lookup"><span data-stu-id="c0891-120">The list of templates includes the default package template named New SSIS Package.</span></span> <span data-ttu-id="c0891-121">Значок пакета определяет шаблоны, которые можно использовать в качестве шаблонов пакетов.</span><span class="sxs-lookup"><span data-stu-id="c0891-121">The package icon identifies templates that can be used as package templates.</span></span>  
  
4.  <span data-ttu-id="c0891-122">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c0891-122">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0891-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0891-123">See Also</span></span>  
 <span data-ttu-id="c0891-124">[Создание пакетов в SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c0891-124">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="c0891-125">Пакеты служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="c0891-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
