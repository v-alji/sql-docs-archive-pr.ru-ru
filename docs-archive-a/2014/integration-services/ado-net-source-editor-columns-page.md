---
title: Редактор источника «ADO NET» (страница «Столбцы») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.columns.f1
ms.assetid: fbc205b9-2001-4737-a76b-1ba777344bd9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d89f8c926761b9149f19269bc2519c12bcf130e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664453"
---
# <a name="ado-net-source-editor-columns-page"></a><span data-ttu-id="012dc-102">Редактор источника «ADO.NET» (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="012dc-102">ADO NET Source Editor (Columns Page)</span></span>
  <span data-ttu-id="012dc-103">Страница **Столбцы** диалогового окна **Редактор источника "ADO.NET"** используется для сопоставления выходного столбца с каждым внешним (исходным) столбцом.</span><span class="sxs-lookup"><span data-stu-id="012dc-103">Use the **Columns** page of the **ADO NET Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="012dc-104">Дополнительные сведения об источниках данных «ADO.NET» см. в разделе [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="012dc-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="012dc-105">**Открытие страницы «Столбцы»**</span><span class="sxs-lookup"><span data-stu-id="012dc-105">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="012dc-106">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий источник данных «ADO.NET».</span><span class="sxs-lookup"><span data-stu-id="012dc-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="012dc-107">На вкладке **Поток данных** дважды щелкните источник данных "ADO.NET".</span><span class="sxs-lookup"><span data-stu-id="012dc-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="012dc-108">В окне **Редактор источника «ADO.NET»** нажмите кнопку **Столбцы**.</span><span class="sxs-lookup"><span data-stu-id="012dc-108">In the **ADO NET Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="012dc-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="012dc-109">Options</span></span>  
 <span data-ttu-id="012dc-110">**Доступные внешние столбцы**</span><span class="sxs-lookup"><span data-stu-id="012dc-110">**Available External Columns**</span></span>  
 <span data-ttu-id="012dc-111">Просмотр списка доступных внешних столбцов источника данных.</span><span class="sxs-lookup"><span data-stu-id="012dc-111">View the list of available external columns in the data source.</span></span> <span data-ttu-id="012dc-112">В этой таблице нельзя добавлять или удалять столбцы.</span><span class="sxs-lookup"><span data-stu-id="012dc-112">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="012dc-113">**Внешний столбец**</span><span class="sxs-lookup"><span data-stu-id="012dc-113">**External Column**</span></span>  
 <span data-ttu-id="012dc-114">Просмотрите внешние столбцы (столбцы в источнике) в том порядке, в котором они отображаются при настройке компонентов, получающих данные из этого источника.</span><span class="sxs-lookup"><span data-stu-id="012dc-114">View external (source) columns in the order in which you will see them when configuring components that consume data from this source.</span></span>  
  
 <span data-ttu-id="012dc-115">**Выходной столбец**</span><span class="sxs-lookup"><span data-stu-id="012dc-115">**Output Column**</span></span>  
 <span data-ttu-id="012dc-116">Введите уникальное имя для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="012dc-116">Provide a unique name for each output column.</span></span> <span data-ttu-id="012dc-117">По умолчанию используется имя выбранного внешнего (исходного) столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="012dc-117">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="012dc-118">Это имя будет отображаться в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="012dc-118">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012dc-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="012dc-119">See Also</span></span>  
 <span data-ttu-id="012dc-120">[Редактор источника «ADO NET» &#40;«диспетчер соединений»&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="012dc-120">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="012dc-121">[Редактор источника ADO NET &#40;страница вывода ошибок&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="012dc-121">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="012dc-122">Диспетчер подключений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="012dc-122">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
