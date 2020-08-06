---
title: Просмотр метаданных пути в редакторе пути потока данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- metadata [Integration Services]
- paths [Integration Services], metadata
ms.assetid: 25cf8bdd-8691-4caa-96b6-3081b2f37dea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d84e14c2bc42ac4b831a4d1a3321d3e8b4acf6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654396"
---
# <a name="view-path-metadata-in-the-data-flow-path-editor"></a><span data-ttu-id="d811d-102">Просмотр метаданных пути в редакторе пути потока данных</span><span class="sxs-lookup"><span data-stu-id="d811d-102">View Path Metadata in the Data Flow Path Editor</span></span>
  <span data-ttu-id="d811d-103">Пути соединяют два компонента потока данных.</span><span class="sxs-lookup"><span data-stu-id="d811d-103">Paths connect two data flow components.</span></span> <span data-ttu-id="d811d-104">Чтобы просмотреть пути метаданных, поток данных должен содержать по крайней мере два соединенных компонента потока данных.</span><span class="sxs-lookup"><span data-stu-id="d811d-104">Before you can view path metadata, the data flow must contain at least two connected data flow components.</span></span> <span data-ttu-id="d811d-105">Дополнительные сведения см. в разделах [Добавление или удаление компонента в потоке данных](data-flow/add-or-delete-a-component-in-a-data-flow.md) и [Соединение компонентов в потоке данных](data-flow/connect-components-in-a-data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="d811d-105">For more information, see [Add or Delete a Component in a Data Flow](data-flow/add-or-delete-a-component-in-a-data-flow.md) and [Connect Components in a Data Flow](data-flow/connect-components-in-a-data-flow.md).</span></span>  
  
### <a name="to-view-path-metadata"></a><span data-ttu-id="d811d-106">Просмотр метаданных пути</span><span class="sxs-lookup"><span data-stu-id="d811d-106">To view path metadata</span></span>  
  
1.  <span data-ttu-id="d811d-107">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="d811d-107">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d811d-108">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="d811d-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d811d-109">Выберите вкладку **Поток данных** и дважды щелкните путь.</span><span class="sxs-lookup"><span data-stu-id="d811d-109">Click the **Data Flow** tab and double-click a path.</span></span>  
  
4.  <span data-ttu-id="d811d-110">В диалоговом окне **Редактор пути потока данных** нажмите кнопку **Метаданные**.</span><span class="sxs-lookup"><span data-stu-id="d811d-110">In **Data Flow Path Editor** dialog box, click **Metadata**.</span></span>  
  
5.  <span data-ttu-id="d811d-111">Просмотрите метаданные пути, включая имена столбцов, тип данных, точность, масштаб, длину, кодовую страницу, а также имя исходного компонента каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="d811d-111">View path metadata, including the column names, data type, precision, scale, length, code page, and the name of the source component of each column.</span></span>  
  
6.  <span data-ttu-id="d811d-112">Чтобы скопировать метаданные, нажмите кнопку **Копировать в буфер обмена**.</span><span class="sxs-lookup"><span data-stu-id="d811d-112">To copy the metadata, click **Copy to Clipboard**.</span></span>  
  
7.  <span data-ttu-id="d811d-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d811d-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d811d-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="d811d-114">See Also</span></span>  
 <span data-ttu-id="d811d-115">[Пути служб Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="d811d-115">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 [<span data-ttu-id="d811d-116">Поток данных</span><span class="sxs-lookup"><span data-stu-id="d811d-116">Data Flow</span></span>](data-flow/data-flow.md)  
  
  
