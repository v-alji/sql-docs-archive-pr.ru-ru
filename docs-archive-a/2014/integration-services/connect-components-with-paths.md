---
title: Соединить компоненты с путями | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], connections
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 05633e4c-1370-4b05-802b-f36b07dd71c8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e11955601406406abe48b53197e95c8224762fee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738621"
---
# <a name="connect-components-with-paths"></a><span data-ttu-id="fea57-102">Соединение компонентов с путями</span><span class="sxs-lookup"><span data-stu-id="fea57-102">Connect Components with Paths</span></span>
  <span data-ttu-id="fea57-103">Поток данных пакета проектируется в области конструктора на вкладке **Поток данных** конструктора служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fea57-103">You construct the data flow in a package on the design surface of the **Data Flow** tab in the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="fea57-104">Если поток данных содержит два компонента потока данных, можно соединить их, подключив выход источника или преобразования ко входу преобразования или назначения.</span><span class="sxs-lookup"><span data-stu-id="fea57-104">If a data flow contains two data flow components, you can connect them by connecting the output of a source or transformation to the input of a transformation or destination.</span></span> <span data-ttu-id="fea57-105">Соединитель компонентов потока данных называется путем.</span><span class="sxs-lookup"><span data-stu-id="fea57-105">The connector between two data flow components is called a path.</span></span>

 <span data-ttu-id="fea57-106">На следующей диаграмме показан простой поток данных с компонентом источника, двумя преобразованиями, целевым компонентом и путями, которые их соединяют.</span><span class="sxs-lookup"><span data-stu-id="fea57-106">The following diagram shows a simple data flow with a source component, two transformations, a destination component, and the paths that connect them.</span></span>

 <span data-ttu-id="fea57-107">![Поток данных](media/mw-dts-08.gif "Поток данных")</span><span class="sxs-lookup"><span data-stu-id="fea57-107">![Data flow](media/mw-dts-08.gif "Data flow")</span></span>

 <span data-ttu-id="fea57-108">После соединения двух компонентов можно просматривать метаданные тех данных, которые перемещаются по пути, и свойства пути в **Редакторе пути потока данных**.</span><span class="sxs-lookup"><span data-stu-id="fea57-108">After two components are connected, you can view the metadata of the data that moves through the path and the properties of the path in **Data Flow Path Editor**.</span></span> <span data-ttu-id="fea57-109">Дополнительные сведения см. в статье [Integration Services Paths](data-flow/integration-services-paths.md).</span><span class="sxs-lookup"><span data-stu-id="fea57-109">For more information, see [Integration Services Paths](data-flow/integration-services-paths.md).</span></span>

 <span data-ttu-id="fea57-110">Также можно добавлять к путям средства просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="fea57-110">You can also add data viewers to paths.</span></span> <span data-ttu-id="fea57-111">Средство просмотра данных дает возможность просматривать данные, перемещающиеся между компонентами потока данных во время выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="fea57-111">A data viewer makes it possible to view data moving between data flow components when the package is run.</span></span>

### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="fea57-112">Соединение компонентов в потоке данных</span><span class="sxs-lookup"><span data-stu-id="fea57-112">To connect components in a data flow</span></span>

-   [<span data-ttu-id="fea57-113">Соединение компонентов в потоке данных</span><span class="sxs-lookup"><span data-stu-id="fea57-113">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)

### <a name="to-set-path-properties"></a><span data-ttu-id="fea57-114">Задание свойств пути</span><span class="sxs-lookup"><span data-stu-id="fea57-114">To set path properties</span></span>

-   [<span data-ttu-id="fea57-115">Задание свойств пути с помощью редактора пути потока данных</span><span class="sxs-lookup"><span data-stu-id="fea57-115">Set the Properties of a Path by Using the Data Flow Path Editor</span></span>](../../2014/integration-services/set-the-properties-of-a-path-by-using-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="fea57-116">Просмотр метаданных пути</span><span class="sxs-lookup"><span data-stu-id="fea57-116">To view path metadata</span></span>

-   [<span data-ttu-id="fea57-117">Просмотр метаданных пути в редакторе пути потока данных</span><span class="sxs-lookup"><span data-stu-id="fea57-117">View Path Metadata in the Data Flow Path Editor</span></span>](../../2014/integration-services/view-path-metadata-in-the-data-flow-path-editor.md)

### <a name="to-view-path-metadata"></a><span data-ttu-id="fea57-118">Просмотр метаданных пути</span><span class="sxs-lookup"><span data-stu-id="fea57-118">To view path metadata</span></span>

-   [<span data-ttu-id="fea57-119">Добавление средства просмотра данных к потоку данных</span><span class="sxs-lookup"><span data-stu-id="fea57-119">Add a Data Viewer to a Data Flow</span></span>](../../2014/integration-services/add-a-data-viewer-to-a-data-flow.md)

## <a name="see-also"></a><span data-ttu-id="fea57-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="fea57-120">See Also</span></span>
 <span data-ttu-id="fea57-121">[Поток](data-flow/data-flow.md) данных [задачи потока](control-flow/data-flow-task.md) данных [Преобразование данных с помощью](data-flow/transformations/transform-data-with-transformations.md) преобразований [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="fea57-121">[Data Flow Task](control-flow/data-flow-task.md) [Data Flow](data-flow/data-flow.md) [Transform Data with Transformations](data-flow/transformations/transform-data-with-transformations.md) [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>


