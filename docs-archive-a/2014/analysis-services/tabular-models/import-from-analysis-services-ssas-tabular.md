---
title: Импорт из Analysis Services (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b9a21b23-3a06-4ef8-bc06-9c79cdc54870
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d6c3d226e46cdb4101bc8db52830046d27b0706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728826"
---
# <a name="import-from-analysis-services-ssas-tabular"></a><span data-ttu-id="892f8-102">Импорт из служб Analysis Services (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="892f8-102">Import from Analysis Services (SSAS Tabular)</span></span>
  <span data-ttu-id="892f8-103">В данном разделе описывается создание нового проекта табличной модели путем импорта метаданных из существующей табличной модели с использованием шаблона проекта «Импорт с сервера» в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="892f8-103">This topic describes how to create a new tabular model project by importing the metadata from an existing tabular model by using the Import from Server project template in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="create-a-new-model-by-importing-metadata-from-an-existing-model-in-analysis-services"></a><span data-ttu-id="892f8-104">Создание новой модели путем импорта метаданных из существующей модели в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="892f8-104">Create a new model by importing metadata from an existing model in Analysis Services</span></span>  
 <span data-ttu-id="892f8-105">Можно использовать шаблон проекта «Импорт с сервера» для создания нового проекта табличной модели с помощью копирования метаданных из существующей табличной модели с сервера служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="892f8-105">You can use the Import from Server project template to create a new tabular model project by copying the metadata from an existing tabular model on an Analysis Services server.</span></span> <span data-ttu-id="892f8-106">Новый проект будет содержать в себе те же соединения с источниками данных, таблицы, связи, меры, ключевые показатели эффективности, роли, иерархии, перспективы и секции, что и модель, используемая для импорта.</span><span class="sxs-lookup"><span data-stu-id="892f8-106">The new project will be created with the same data source connections, tables, relationships, measures, KPIs, roles, hierarchies, perspectives, and partitions as the model it was imported from.</span></span> <span data-ttu-id="892f8-107">Однако данные из существующей модели при этом не копируются в рабочую область новой модели.</span><span class="sxs-lookup"><span data-stu-id="892f8-107">The data, however, is not copied from the existing model to the new model workspace.</span></span> <span data-ttu-id="892f8-108">По завершении импорта, как только будет создан новый проект модели, необходимо запустить полную обработку для загрузки данных из источников данных в базу данных рабочей области нового проекта модели.</span><span class="sxs-lookup"><span data-stu-id="892f8-108">Once the import process has completed, and the new model project created, you must run a Process All to load the data from the data sources into the new model project workspace database.</span></span>  
  
#### <a name="to-create-a-new-model-by-importing-metadata-from-an-existing-model"></a><span data-ttu-id="892f8-109">Создание новой модели путем импорта метаданных из существующей модели</span><span class="sxs-lookup"><span data-stu-id="892f8-109">To create a new model by importing metadata from an existing model</span></span>  
  
1.  <span data-ttu-id="892f8-110">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]в меню **Файл** выберите пункт **Создать**, а затем выберите пункт **Проект**.</span><span class="sxs-lookup"><span data-stu-id="892f8-110">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="892f8-111">В диалоговом окне **Создание проекта** выберите в разделе **Установленные шаблоны**пункт **Бизнес-аналитика**, затем нажмите кнопку **Импортировать с сервера**.</span><span class="sxs-lookup"><span data-stu-id="892f8-111">In the **New Project** dialog box, under **Installed Templates**, click **Business Intelligence**, and then click **Import from Server**.</span></span>  
  
3.  <span data-ttu-id="892f8-112">В поле **Имя**введите имя проекта, укажите расположение и имя решения, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="892f8-112">In **Name**, type a name for the project, then specify a location and solution name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="892f8-113">В диалоговом окне **Импорт из служб Analysis Services** в поле **Имя сервера**введите имя сервера служб Analysis Services, на котором находятся метаданные модели для импорта.</span><span class="sxs-lookup"><span data-stu-id="892f8-113">In the **Import from Analysis Services** dialog box, in **Server Name**, specify the name of the Analysis Services server that contains the model metadata you want to import.</span></span>  
  
5.  <span data-ttu-id="892f8-114">В поле **Имя базы данных**выберите базу данных табличной модели, содержащую метаданные модели для импорта, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="892f8-114">In **Database Name**, select the tabular model database that contains the model metadata you want to import, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="892f8-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="892f8-115">See Also</span></span>  
 [<span data-ttu-id="892f8-116">Свойства проекта (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="892f8-116">Project Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
