---
title: Создание или развертывание кэша для преобразования "Уточняющий запрос" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- creating cache files for Lookup transformation
- deploying cache files for Lookup transformation
- Lookup transformation cache files
ms.assetid: cedf5cad-2fac-42d0-ad91-9461e117d330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33b00b84f1f1448c2ee80882aedc3a330ba0a5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654414"
---
# <a name="create-and-deploy-a-cache-for-the-lookup-transformation"></a><span data-ttu-id="4e8d3-102">Создание или развертывание кэша для преобразования «Уточняющий запрос»</span><span class="sxs-lookup"><span data-stu-id="4e8d3-102">Create and Deploy a Cache for the Lookup Transformation</span></span>
  <span data-ttu-id="4e8d3-103">Можно создать и развернуть файл кэша (CAW) для преобразования «Уточняющий запрос».</span><span class="sxs-lookup"><span data-stu-id="4e8d3-103">You can create and deploy a cache file (.caw) for the Lookup transformation.</span></span> <span data-ttu-id="4e8d3-104">Эталонный набор данных хранится в файле кэша.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-104">The reference dataset is stored in the cache file.</span></span>  
  
 <span data-ttu-id="4e8d3-105">Преобразование «Уточняющий запрос» выполняет уточняющие запросы, соединяя данные из входных столбцов подключенного источника данных и данные из столбцов в эталонном наборе данных.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference dataset.</span></span>  
  
 <span data-ttu-id="4e8d3-106">Файл кэша создается с помощью диспетчера соединений с кэшем и преобразования «Преобразование кэша».</span><span class="sxs-lookup"><span data-stu-id="4e8d3-106">You create a cache file by using a Cache connection manager and a Cache Transform transformation.</span></span> <span data-ttu-id="4e8d3-107">Дополнительные сведения см. в разделах [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) и [Cache Transform](cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d3-107">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Transform](cache-transform.md).</span></span>  
  
 <span data-ttu-id="4e8d3-108">Дополнительные сведения о преобразовании «Уточняющий запрос» и файлах кэша см. в разделе [Lookup Transformation](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d3-108">To learn more about the Lookup transformation and cache files, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
### <a name="to-create-a-cache-file"></a><span data-ttu-id="4e8d3-109">Создание файла кэша</span><span class="sxs-lookup"><span data-stu-id="4e8d3-109">To create a cache file</span></span>  
  
1.  <span data-ttu-id="4e8d3-110">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]откройте проект [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет, и затем откройте пакет.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-110">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="4e8d3-111">На вкладке **Поток управления** добавьте задачу потока данных.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-111">On the **Control Flow** tab, add a Data Flow task.</span></span>  
  
3.  <span data-ttu-id="4e8d3-112">На вкладке **Поток данных** добавьте преобразование «Преобразование кэша» к потоку данных, а затем подключите преобразование к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-112">On the **Data Flow** tab, add a Cache Transform transformation to the data flow, and then connect the transformation to a data source.</span></span>  
  
     <span data-ttu-id="4e8d3-113">При необходимости настройте источник данных.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-113">Configure the data source as needed.</span></span>  
  
4.  <span data-ttu-id="4e8d3-114">Дважды щелкните "Преобразование кэша", а затем в окне **Редактор преобразований кэша**на странице **Диспетчер соединений** щелкните **Создать** , чтобы создать новый диспетчер соединений с кэшем.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-114">Double-click the Cache Transform, and then in the **Cache Transformation Editor**, on the **Connection Manager** page, click **New** to create a new Cache connection manager.</span></span>  
  
5.  <span data-ttu-id="4e8d3-115">В окне **Редактор диспетчера соединений с кэшем**на вкладке **Общее** настройте конфигурацию диспетчера соединений с кэшем, чтобы сохранить кэш, выбрав следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-115">In the **Cache Connection Manager Editor**, on the **General** tab, configure the Cache connection manager to save the cache by selecting the following options:</span></span>  
  
    1.  <span data-ttu-id="4e8d3-116">Выберите **Использовать кэш файлов**.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-116">Select **Use file cache**.</span></span>  
  
    2.  <span data-ttu-id="4e8d3-117">В поле **Имя файла**введите путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-117">For **File name**, type the file path.</span></span>  
  
     <span data-ttu-id="4e8d3-118">Файл создается системой при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-118">The system creates the file when you run the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4e8d3-119">Уровень защиты пакета не применяется к кэшируемому файлу.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-119">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="4e8d3-120">Если кэшируемый файл содержит важные данные, используйте список управления доступом (ACL), чтобы запретить доступ к расположению или папке, в которой хранится файл.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-120">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="4e8d3-121">Доступ следует разрешать только определенным учетным записям.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-121">You should enable access only to certain accounts.</span></span> <span data-ttu-id="4e8d3-122">Дополнительные сведения см. в разделе [Доступ к файлам, используемым пакетами](../../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d3-122">For more information, see [Access to Files Used by Packages](../../access-to-files-used-by-packages.md).</span></span>  
  
6.  <span data-ttu-id="4e8d3-123">Перейдите на вкладку **Столбцы** , а затем задайте, какие столбцы будут столбцами индекса, с помощью параметра **Позиция индекса** .</span><span class="sxs-lookup"><span data-stu-id="4e8d3-123">Click the **Columns** tab, and then specify which columns are the index columns by using the **Index Position** option.</span></span>  
  
     <span data-ttu-id="4e8d3-124">Для неиндексированных столбцов позиция индекса равна 0.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-124">For non-index columns, the index position is 0.</span></span> <span data-ttu-id="4e8d3-125">Для индексированных столбцов позиция индекса является положительным порядковым номером.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-125">For index columns, the index position is a sequential, positive number.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4e8d3-126">Если преобразование «Уточняющий запрос» настроено для использования диспетчера соединений с кэшем, то только индексированные столбцы в ссылочном наборе данных могут быть сопоставлены с входными столбцами.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-126">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="4e8d3-127">Кроме того, все столбцы индекса должны быть сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-127">Also all index columns must be mapped.</span></span>  
  
     <span data-ttu-id="4e8d3-128">Дополнительные сведения см. в разделе [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d3-128">For more information, see [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
7.  <span data-ttu-id="4e8d3-129">При необходимости настройте преобразование кэша.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-129">Configure the Cache Transform as needed.</span></span>  
  
     <span data-ttu-id="4e8d3-130">Дополнительные сведения см. в разделах [Редактор преобразования "Кэш" (страница "Диспетчер соединений")](../../cache-transformation-editor-connection-manager-page.md) и [Редактор преобразования "Кэш" (страница "Сопоставления")](../../cache-transformation-editor-mappings-page.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d3-130">For more information, see [Cache Transformation Editor &#40;Connection Manager Page&#41;](../../cache-transformation-editor-connection-manager-page.md) and [Cache Transformation Editor &#40;Mappings Page&#41;](../../cache-transformation-editor-mappings-page.md).</span></span>  
  
8.  <span data-ttu-id="4e8d3-131">Запустите пакет.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-131">Run the package.</span></span>  
  
### <a name="to-deploy-a-cache-file"></a><span data-ttu-id="4e8d3-132">Развертывание файла кэша</span><span class="sxs-lookup"><span data-stu-id="4e8d3-132">To deploy a cache file</span></span>  
  
1.  <span data-ttu-id="4e8d3-133">В среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]откройте проект [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет, и затем откройте пакет.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-133">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="4e8d3-134">При необходимости создайте конфигурацию пакета.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-134">Optionally, create a package configuration.</span></span> <span data-ttu-id="4e8d3-135">Дополнительные сведения см. в разделе [Создание конфигурации пакетов](../../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d3-135">For more information, see [Create Package Configurations](../../create-package-configurations.md).</span></span>  
  
3.  <span data-ttu-id="4e8d3-136">Добавьте файл кэша к проекту, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-136">Add the cache file to the project by doing the following:</span></span>  
  
    1.  <span data-ttu-id="4e8d3-137">В обозревателе решений выберите проект, который был открыт в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-137">In Solution Explorer, select the project you opened in step 1.</span></span>  
  
    2.  <span data-ttu-id="4e8d3-138">В меню **Проект** выберите пункт **Добавить существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-138">On the **Project** menu, click **AddExisting Item**.</span></span>  
  
    3.  <span data-ttu-id="4e8d3-139">Выберите файл кэша и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-139">Select the cache file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="4e8d3-140">Файл появится в папке **Разное** в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-140">The file appears in the **Miscellaneous** folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="4e8d3-141">Настройте проект для создания программы развертывания, а затем постройте проект.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-141">Configure the project to create a deployment utility, and then build the project.</span></span> <span data-ttu-id="4e8d3-142">Дополнительные сведения см. в статье [Create a Deployment Utility](../../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d3-142">For more information, see [Create a Deployment Utility](../../create-a-deployment-utility.md).</span></span>  
  
     <span data-ttu-id="4e8d3-143">Создается файл манифеста \<*project name*>.SSISDeploymentManifest.xml, в котором перечисляются различные файлы в проекте, пакеты и конфигурации пакетов.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-143">A manifest file, \<*project name*>.SSISDeploymentManifest.xml, is created that lists the miscellaneous files in the project, the packages, and the package configurations.</span></span>  
  
5.  <span data-ttu-id="4e8d3-144">Развертывание пакета в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="4e8d3-144">Deploy the package to the file system.</span></span> <span data-ttu-id="4e8d3-145">Дополнительные сведения см. в статье [Deploy Packages by Using the Deployment Utility](../../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d3-145">For more information, see [Deploy Packages by Using the Deployment Utility](../../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e8d3-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e8d3-146">See Also</span></span>  
 [<span data-ttu-id="4e8d3-147">Создание программы развертывания</span><span class="sxs-lookup"><span data-stu-id="4e8d3-147">Create a Deployment Utility</span></span>](../../create-a-deployment-utility.md)  
  
  
