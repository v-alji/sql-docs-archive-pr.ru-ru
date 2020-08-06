---
title: Редактор источника OLE DB (страница «Столбцы») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.columns.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: bfbb0ae1-7759-4d45-8865-31df36ae5b34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 575a5a02198606d2412ff187750963ccb171e338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656471"
---
# <a name="ole-db-source-editor-columns-page"></a><span data-ttu-id="80449-102">Редактор источника «OLE DB» (страница «Столбцы»)</span><span class="sxs-lookup"><span data-stu-id="80449-102">OLE DB Source Editor (Columns Page)</span></span>
  <span data-ttu-id="80449-103">Страница **Столбцы** диалогового окна **Редактор источника "OLE DB"** используется для сопоставления выходного столбца с каждым внешним столбцом (источником).</span><span class="sxs-lookup"><span data-stu-id="80449-103">Use the **Columns** page of the **OLE DB Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="80449-104">Дополнительные сведения об источнике OLE DB см. в разделе [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="80449-104">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="80449-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="80449-105">Options</span></span>  
 <span data-ttu-id="80449-106">**Доступные внешние столбцы**</span><span class="sxs-lookup"><span data-stu-id="80449-106">**Available External Columns**</span></span>  
 <span data-ttu-id="80449-107">Просмотр списка доступных внешних столбцов источника данных.</span><span class="sxs-lookup"><span data-stu-id="80449-107">View the list of available external columns in the data source.</span></span> <span data-ttu-id="80449-108">В этой таблице нельзя добавлять или удалять столбцы.</span><span class="sxs-lookup"><span data-stu-id="80449-108">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="80449-109">**Внешний столбец**</span><span class="sxs-lookup"><span data-stu-id="80449-109">**External Column**</span></span>  
 <span data-ttu-id="80449-110">Просмотрите внешние столбцы (столбцы в источнике) в том порядке, в котором они отображаются при настройке компонентов, получающих данные из этого источника.</span><span class="sxs-lookup"><span data-stu-id="80449-110">View external (source) columns in the order in which you will see them when configuring components that consume data from this source.</span></span> <span data-ttu-id="80449-111">Этот порядок можно изменить, вначале очистив выделенные столбцы в таблице, а затем выбрав в списке внешние столбцы в другом порядке.</span><span class="sxs-lookup"><span data-stu-id="80449-111">You can change this order by first clearing the selected columns in the table, and then selecting external columns from the list in a different order.</span></span>  
  
 <span data-ttu-id="80449-112">**Выходной столбец**</span><span class="sxs-lookup"><span data-stu-id="80449-112">**Output Column**</span></span>  
 <span data-ttu-id="80449-113">Введите уникальное имя для каждого выходного столбца.</span><span class="sxs-lookup"><span data-stu-id="80449-113">Provide a unique name for each output column.</span></span> <span data-ttu-id="80449-114">По умолчанию используется имя выбранного внешнего (исходного) столбца, однако можно выбрать любое уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="80449-114">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="80449-115">Указанное имя будет отображено в конструкторе служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="80449-115">The name provided will be displayed within the SSIS Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80449-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="80449-116">See Also</span></span>  
 <span data-ttu-id="80449-117">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="80449-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="80449-118">[Редактор OLE DBного источника &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="80449-118">[OLE DB Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="80449-119">[Редактор источника OLE DB &#40;странице вывода ошибок&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="80449-119">[OLE DB Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="80449-120">[Извлечение данных с помощью источника OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="80449-120">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="80449-121">Диспетчер соединений OLE DB</span><span class="sxs-lookup"><span data-stu-id="80449-121">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
