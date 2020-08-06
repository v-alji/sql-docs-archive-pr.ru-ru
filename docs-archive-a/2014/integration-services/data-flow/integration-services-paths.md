---
title: Пути служб Integration Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- paths [Integration Services], about paths
- data flow [Integration Services], paths
- paths [Integration Services]
- destinations [Integration Services], paths
- sources [Integration Services], paths
ms.assetid: 6c4629a9-2ede-4011-9101-3b342249640e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c52bbd06974311a7fc94b3058309399d70df0034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731954"
---
# <a name="integration-services-paths"></a><span data-ttu-id="9a604-102">Пути служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="9a604-102">Integration Services Paths</span></span>
  <span data-ttu-id="9a604-103">Путь связывает два компонента в потоке данных при помощи соединения выхода одного компонента потока данных с входом другого.</span><span class="sxs-lookup"><span data-stu-id="9a604-103">A path connects two components in a data flow by connecting the output of one data flow component to the input of another component.</span></span> <span data-ttu-id="9a604-104">У пути есть источник и целевой объект.</span><span class="sxs-lookup"><span data-stu-id="9a604-104">A path has a source and a destination.</span></span> <span data-ttu-id="9a604-105">Например, если путь соединяет источник OLE DB и преобразование «Сортировка», то источник OLE DB является источником пути, а целевым объектом пути будет преобразование «Сортировка».</span><span class="sxs-lookup"><span data-stu-id="9a604-105">For example, if a path connects an OLE DB source and a Sort transformation, the OLE DB source is the source of the path, and the Sort transformation is the destination of the path.</span></span> <span data-ttu-id="9a604-106">Источником является начало пути, а целевым объектом — его конец.</span><span class="sxs-lookup"><span data-stu-id="9a604-106">The source is the component where the path starts, and the destination is the component where the path ends.</span></span>  
  
 <span data-ttu-id="9a604-107">Если пакет запускается в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , то данные в потоке данных можно просмотреть путем присоединения средств просмотра данных к пути.</span><span class="sxs-lookup"><span data-stu-id="9a604-107">If you run a package in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can view the data in a data flow by attaching data viewers to a path.</span></span> <span data-ttu-id="9a604-108">Средство просмотра данных может отображать данные в виде сетки.</span><span class="sxs-lookup"><span data-stu-id="9a604-108">A data viewer can be configured to display data in a grid.</span></span> <span data-ttu-id="9a604-109">Средство просмотра данных — это эффективное средство отладки.</span><span class="sxs-lookup"><span data-stu-id="9a604-109">A data viewer is a useful debugging tool.</span></span> <span data-ttu-id="9a604-110">Дополнительные сведения см. в статье [Отладка потока данных](../troubleshooting/debugging-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="9a604-110">For more information, see [Debugging Data Flow](../troubleshooting/debugging-data-flow.md).</span></span>  
  
## <a name="configuration-of-the-path"></a><span data-ttu-id="9a604-111">Настройка пути</span><span class="sxs-lookup"><span data-stu-id="9a604-111">Configuration of the Path</span></span>  
 <span data-ttu-id="9a604-112">Конструктор [!INCLUDE[ssIS](../../includes/ssis-md.md)] содержит диалоговое окно **Редактор пути потока данных** для установки свойств пути, просмотра метаданных столбцов данных, которые проходят через путь, и для настройки средств просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="9a604-112">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides the **Data Flow Path Editor** dialog box for setting path properties, viewing the metadata of the data columns that pass through the path, and configuring data viewers.</span></span>  
  
 <span data-ttu-id="9a604-113">Настраиваемые свойства пути — это имя, описание и аннотация пути.</span><span class="sxs-lookup"><span data-stu-id="9a604-113">The configurable path properties include the name, description, and annotation of the path.</span></span> <span data-ttu-id="9a604-114">Пути также можно настраивать программно.</span><span class="sxs-lookup"><span data-stu-id="9a604-114">You can also configure paths programmatically.</span></span> <span data-ttu-id="9a604-115">Дополнительные сведения см. в статье [Программное соединение компонентов потока данных](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="9a604-115">For more information, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
 <span data-ttu-id="9a604-116">Аннотация пути показывает имя источника пути или имя пути в области конструктора вкладки **Поток данных** в конструкторе [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a604-116">A path annotation displays the name of the path source or the path name on the design surface of the **Data Flow** tab in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="9a604-117">Аннотации пути похожи на аннотации, которые можно добавлять к потокам данных, потокам управления и обработчикам событий.</span><span class="sxs-lookup"><span data-stu-id="9a604-117">Path annotations are similar to the annotations you can add to data flows, control flows, and event handlers.</span></span> <span data-ttu-id="9a604-118">Единственная разница заключается в том, что аннотация пути прикреплена к этому пути, тогда как другие аннотации появляются на вкладках **Поток данных**, **Поток управления**и **Обработчики событий**в конструкторе [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a604-118">The only difference is that a path annotation is attached to a path, whereas other annotations appear on the **Data Flow**, **Control Flow**, and **Event Handle**r tabs of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="9a604-119">Метаданные показывают имя, тип данных, точность, масштаб, длину, кодовую страницу и компонент-источник для каждого выходного столбца предыдущего компонента.</span><span class="sxs-lookup"><span data-stu-id="9a604-119">The metadata shows the name, data type, precision, scale, length, code page, and source component of each column in the output of the previous component.</span></span> <span data-ttu-id="9a604-120">Компонент-источник потока является компонентом-источником данных, создавшим этот столбец.</span><span class="sxs-lookup"><span data-stu-id="9a604-120">The source component is the data flow component that created the column.</span></span> <span data-ttu-id="9a604-121">Он не обязательно должен быть первым компонентом потока данных.</span><span class="sxs-lookup"><span data-stu-id="9a604-121">This may or may not be the first component in the data flow.</span></span> <span data-ttu-id="9a604-122">Например, преобразования «Объединить все» и «Сортировка» создают свои собственные столбцы, и они являются источниками для выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="9a604-122">For example, the Union All and Sort transformations create their own columns, and they are the sources of their output columns.</span></span> <span data-ttu-id="9a604-123">Преобразование «Копирование столбца», напротив, может проходить по столбцам, не изменяя их, или может создавать новые столбцы путем копирования входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="9a604-123">In contrast, a Copy Column transformation can pass through columns without changing them or can create new columns by copying input columns.</span></span> <span data-ttu-id="9a604-124">Преобразование «Копирование столбца» является компонентом-источником только для новых столбцов.</span><span class="sxs-lookup"><span data-stu-id="9a604-124">The Copy Column transformation is the source component only of the new columns.</span></span>  
  
 <span data-ttu-id="9a604-125">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="9a604-125">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="9a604-126">Дополнительные сведения о свойствах, которые могут быть заданы в диалоговом окне **Редактор пути потока данных** , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9a604-126">For more information about the properties that you can set in the **Data Flow Path Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="9a604-127">Редактор пути потока данных &#40;общие&#41;страницы</span><span class="sxs-lookup"><span data-stu-id="9a604-127">Data Flow Path Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="9a604-128">Редактор пути потока данных &#40;страница метаданных&#41;</span><span class="sxs-lookup"><span data-stu-id="9a604-128">Data Flow Path Editor &#40;Metadata Page&#41;</span></span>](../data-flow-path-editor-metadata-page.md)  
  
-   [<span data-ttu-id="9a604-129">Редактор пути потока данных &#40;страница "средства просмотра данных"&#41;</span><span class="sxs-lookup"><span data-stu-id="9a604-129">Data Flow Path Editor &#40;Data Viewers Page&#41;</span></span>](../data-flow-path-editor-data-viewers-page.md)  
  
 <span data-ttu-id="9a604-130">Дополнительные сведения о свойствах, которые можно задать программно, см. в разделе [Path Properties](../path-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9a604-130">For more information about the properties that you can set programmatically, see [Path Properties](../path-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="9a604-131">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9a604-131">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9a604-132">Просмотр метаданных пути в редакторе пути потока данных</span><span class="sxs-lookup"><span data-stu-id="9a604-132">View Path Metadata in the Data Flow Path Editor</span></span>](../view-path-metadata-in-the-data-flow-path-editor.md)  
  
-   [<span data-ttu-id="9a604-133">Соединение компонентов в потоке данных</span><span class="sxs-lookup"><span data-stu-id="9a604-133">Connect Components in a Data Flow</span></span>](connect-components-in-a-data-flow.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a604-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a604-134">See Also</span></span>  
 [<span data-ttu-id="9a604-135">Поток данных</span><span class="sxs-lookup"><span data-stu-id="9a604-135">Data Flow</span></span>](data-flow.md)  
  
  
