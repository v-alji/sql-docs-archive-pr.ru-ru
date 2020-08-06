---
title: Удаление источника данных в обозреватель решений (многомерные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.deleteobjects.f1
helpviewer_keywords:
- data sources [Analysis Services], deleting
- deleting data sources
- removing data sources
ms.assetid: b45441ef-f909-4736-98b9-cc80d0acac99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6101c8704579894590994d88e0286197148b694
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668472"
---
# <a name="delete-a-data-source-in-solution-explorer-ssas-multidimensional"></a><span data-ttu-id="7a42d-102">Удаление источника данных в обозревателе решений (многомерные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="7a42d-102">Delete a Data Source in Solution Explorer (SSAS Multidimensional)</span></span>
  <span data-ttu-id="7a42d-103">Удалив объект источника данных, можно окончательно исключить его из проекта многомерной модели служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="7a42d-103">You can delete a data source object to permanently remove it from an Analysis Services multidimensional model project.</span></span>  
  
 <span data-ttu-id="7a42d-104">В службах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]источники данных представляют собой основу для построения представлений источников данных, которые в свою очередь используются для определения измерений, кубов и структур интеллектуального анализа данных в проекте или базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a42d-104">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], data sources provide the basis on which data source views are constructed, and data source views are in turn used to define dimensions, cubes, and mining structures in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="7a42d-105">Таким образом, удаление источника данных может сделать недействительными другие объекты служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в проекте служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a42d-105">Therefore, deleting a data source may invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="7a42d-106">Перед тем как удалить объект, необходимо всегда проверять список зависимых объектов, открываемый до удаления.</span><span class="sxs-lookup"><span data-stu-id="7a42d-106">You should always review the list of dependent objects that is provided before deleting the object.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7a42d-107">Источники данных, от которых зависят другие объекты, не могут быть удалены из базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , открытых в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="7a42d-107">Data sources on which other objects depend cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="7a42d-108">Следует удалить все объекты в базе данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , которые зависят от источника данных, до удаления его самого.</span><span class="sxs-lookup"><span data-stu-id="7a42d-108">You must delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that data source before deleting the data source.</span></span> <span data-ttu-id="7a42d-109">Дополнительные сведения о режиме в сети см. в разделе [Connect in Online Mode to an Analysis Services Database](connect-in-online-mode-to-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="7a42d-109">For more information about online mode, see [Connect in Online Mode to an Analysis Services Database](connect-in-online-mode-to-an-analysis-services-database.md).</span></span>  
  
### <a name="to-delete-a-data-source"></a><span data-ttu-id="7a42d-110">Удаление источника данных</span><span class="sxs-lookup"><span data-stu-id="7a42d-110">To delete a data source</span></span>  
  
1.  <span data-ttu-id="7a42d-111">Откройте проект в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]или подключитесь к базе данных, из которой необходимо удалить источник данных.</span><span class="sxs-lookup"><span data-stu-id="7a42d-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database from which you want to delete a data source.</span></span>  
  
2.  <span data-ttu-id="7a42d-112">В **обозревателе решений**откройте папку **Источники данных** .</span><span class="sxs-lookup"><span data-stu-id="7a42d-112">In **Solution Explorer**, expand the **Data Sources** folder.</span></span>  
  
3.  <span data-ttu-id="7a42d-113">Щелкните правой кнопкой мыши источник данных и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7a42d-113">Right-click the data source, and then click **Delete**.</span></span> <span data-ttu-id="7a42d-114">Появится диалоговое окно **Удаление объектов**  со списком объектов, которые станут недействительными при удалении этого источника данных.</span><span class="sxs-lookup"><span data-stu-id="7a42d-114">The **Delete Objects**  dialog box appears, showing the objects that will be invalidated if you delete the data source.</span></span> <span data-ttu-id="7a42d-115">Внимательно просмотрите список, прежде чем нажать кнопку **ОК** и удалить источник данных.</span><span class="sxs-lookup"><span data-stu-id="7a42d-115">Review this list carefully before clicking **OK** to delete the data source.</span></span>  
  
4.  <span data-ttu-id="7a42d-116">Сохраните проект.</span><span class="sxs-lookup"><span data-stu-id="7a42d-116">Save the project.</span></span>  
  
     <span data-ttu-id="7a42d-117">После удаления источника данных из проекта служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] необходимо сохранить в проекте изменения, чтобы не получить сообщение об ошибке при следующем его открытии, так как при обработке XML-файла для удаленного источника данных будет выдана ошибка.</span><span class="sxs-lookup"><span data-stu-id="7a42d-117">After deleting a data source from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you must save the modified project or you will receive an error the next time you open the project because the underlying XML file for the deleted data source will be missing when the project attempts to load the deleted data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a42d-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a42d-118">See Also</span></span>  
 <span data-ttu-id="7a42d-119">[Источники данных в многомерных моделях](data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="7a42d-119">[Data Sources in Multidimensional Models](data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="7a42d-120">Поддерживаемые источники данных &#40;многомерные&#41;SSAS</span><span class="sxs-lookup"><span data-stu-id="7a42d-120">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
