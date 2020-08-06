---
title: Организатор конфигураций пакетов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.packageconfigurationorganizer.f1
helpviewer_keywords:
- Package Configurations Organizer dialog box
ms.assetid: f20ae6cb-9e6a-4d24-88ff-d7a903a4e8d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fdc9ca0faeff57c18fdb6e4d10acca3e9963f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736524"
---
# <a name="package-configurations-organizer"></a><span data-ttu-id="ca7e6-102">Организатор конфигураций пакетов</span><span class="sxs-lookup"><span data-stu-id="ca7e6-102">Package Configurations Organizer</span></span>
  <span data-ttu-id="ca7e6-103">Диалоговое окно **Организатор конфигураций пакетов** используется для включения конфигураций пакетов, просмотра списка конфигураций для текущего пакета, а также для указания порядка, в котором следует загружать конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-103">Use the **Package Configurations Organizer** dialog box to enable package configurations, view a list of configurations for the current package, and specify the preferred order in which the configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca7e6-104">Доступны конфигурации для модели развертывания пакетов.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="ca7e6-105">Для моделей развертывания проектов вместо конфигураций используются параметры.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="ca7e6-106">Модель развертывания проектов позволяет развертывать проекты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сервере служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca7e6-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="ca7e6-107">Дополнительные сведения о моделях развертывания см. в разделе [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="ca7e6-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="ca7e6-108">Если несколько конфигураций обновляют одно и то же свойство, то значения из конфигураций, расположенных в нижней части списка, заменят значения из конфигураций, расположенных в верхней части списка.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-108">If multiple configurations update the same property, values from configurations listed lower in the configuration list will replace values from configurations higher in the list.</span></span> <span data-ttu-id="ca7e6-109">Последнее значение, загружаемое в свойства, является значением, которое используется при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-109">The last value loaded into the property is the value that is used when the package runs.</span></span> <span data-ttu-id="ca7e6-110">Кроме того, если пакет использует сочетание прямой конфигурации, например XML-файла конфигурации, и непрямой конфигурации, например переменной среды, то непрямая конфигурация, указывающая на расположение прямой конфигурации, должна располагаться выше в списке.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-110">Also, if the package uses a combination of direct configuration such as an XML configuration file and an indirect configuration such as an environment variable, the indirect configuration that points to the location of the direct configuration must be higher in the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca7e6-111">При загрузке в указанном порядке конфигурации загружаются с верхней части списка, показанного в диалоговом окне **Организатор конфигураций пакетов** , в нижнюю часть списка.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-111">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="ca7e6-112">Однако во время выполнения конфигурации пакетов могут загружаться в другом порядке.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-112">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="ca7e6-113">В частности, конфигурации родительских пакетов загружаются после всех остальных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-113">In particular, Parent Package Configurations load after configurations of other types.</span></span>  
  
 <span data-ttu-id="ca7e6-114">Конфигурации пакета обновляют значения свойств объектов пакета во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-114">Package configurations update the values of properties of package objects at run time.</span></span> <span data-ttu-id="ca7e6-115">После загрузки пакета значения, полученные из конфигураций, заменяют значения, установленные при разработке пакета.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-115">When a package is loaded, the values from the configurations replace the values that were set when the package was developed.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="ca7e6-116">поддерживают различные типы конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-116">supports different configuration types.</span></span> <span data-ttu-id="ca7e6-117">Например, можно использовать XML-файл, содержащий несколько конфигураций, или переменную среды, содержащую всего одну конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-117">For example, you can use an XML file that can contain multiple configurations, or an environment variable that contains a single configuration.</span></span> <span data-ttu-id="ca7e6-118">Дополнительные сведения см. в статье [Package Configurations](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="ca7e6-118">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ca7e6-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca7e6-119">Options</span></span>  
 <span data-ttu-id="ca7e6-120">**Включить конфигурацию пакетов**</span><span class="sxs-lookup"><span data-stu-id="ca7e6-120">**Enable package configurations**</span></span>  
 <span data-ttu-id="ca7e6-121">Выберите, чтобы использовать конфигурации с пакетом.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-121">Select to use configurations with the package.</span></span>  
  
 <span data-ttu-id="ca7e6-122">**Имя конфигурации**</span><span class="sxs-lookup"><span data-stu-id="ca7e6-122">**Configuration Name**</span></span>  
 <span data-ttu-id="ca7e6-123">Просмотр имени конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-123">View the name of the configuration.</span></span>  
  
 <span data-ttu-id="ca7e6-124">**Тип конфигурации**</span><span class="sxs-lookup"><span data-stu-id="ca7e6-124">**Configuration Type**</span></span>  
 <span data-ttu-id="ca7e6-125">Просмотр типа месторасположения конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-125">View the type of the location where configurations are stored.</span></span>  
  
 <span data-ttu-id="ca7e6-126">**Строка конфигурации**</span><span class="sxs-lookup"><span data-stu-id="ca7e6-126">**Configuration String**</span></span>  
 <span data-ttu-id="ca7e6-127">Просмотр расположения значений конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-127">View the location where the configuration values are stored.</span></span> <span data-ttu-id="ca7e6-128">Расположение может представлять собой путь к файлу, имя переменной среды, имя переменной родительского пакета, раздел реестра или имя таблицы [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca7e6-128">The location can be the path of a file, the name of an environment variable, the name of a parent package variable, a Registry key, or the name of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="ca7e6-129">**Целевой объект**</span><span class="sxs-lookup"><span data-stu-id="ca7e6-129">**Target Object**</span></span>  
 <span data-ttu-id="ca7e6-130">Просмотр имени объекта, обновляемого конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-130">View the name of the object that the configuration updates.</span></span> <span data-ttu-id="ca7e6-131">Если конфигурация является XML-файлом конфигурации или таблицей SQL Server, столбец остается пустым, потому что конфигурация может содержать несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-131">If the configuration is an XML configuration file or a SQL Server table, the column is blank because the configuration can include multiple objects.</span></span>  
  
 <span data-ttu-id="ca7e6-132">**Целевое свойство**</span><span class="sxs-lookup"><span data-stu-id="ca7e6-132">**Target Property**</span></span>  
 <span data-ttu-id="ca7e6-133">Просмотр имени свойства, измененного конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-133">View the name of the property modified by the configuration.</span></span> <span data-ttu-id="ca7e6-134">Этот столбец пустой, если тип конфигурации поддерживает одновременно несколько конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-134">This column is blank if the configuration type supports multiple configurations.</span></span>  
  
 <span data-ttu-id="ca7e6-135">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="ca7e6-135">**Add**</span></span>  
 <span data-ttu-id="ca7e6-136">Добавление конфигурации с помощью мастера настройки пакета.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-136">Add a configuration by using the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="ca7e6-137">**Edit** (Изменение)</span><span class="sxs-lookup"><span data-stu-id="ca7e6-137">**Edit**</span></span>  
 <span data-ttu-id="ca7e6-138">Редактирование существующей конфигурации при помощи перезапуска мастера настройки пакета.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-138">Edit an existing configuration by rerunning the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="ca7e6-139">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="ca7e6-139">**Remove**</span></span>  
 <span data-ttu-id="ca7e6-140">Выберите конфигурацию, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-140">Select a configuration, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="ca7e6-141">**Стрелки**</span><span class="sxs-lookup"><span data-stu-id="ca7e6-141">**Arrows**</span></span>  
 <span data-ttu-id="ca7e6-142">Выберите конфигурацию и, используя стрелки вверх и вниз, переместите ее вверх или вниз в списке.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-142">Select a configuration and use the up and down arrows to move it up or down in the list.</span></span> <span data-ttu-id="ca7e6-143">Конфигурации загружаются в последовательности, указанной в списке.</span><span class="sxs-lookup"><span data-stu-id="ca7e6-143">Configurations are loaded in the sequence in which they appear in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7e6-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca7e6-144">See Also</span></span>  
 [<span data-ttu-id="ca7e6-145">Создание конфигурации пакетов</span><span class="sxs-lookup"><span data-stu-id="ca7e6-145">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
