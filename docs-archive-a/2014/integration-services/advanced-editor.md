---
title: Расширенный редактор | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.advancededitor.columnmappings.f1
- sql12.dts.designer.advancededitor.inputcolumns.f1
- sql12.dts.designer.advancededitor.columnproperties.f1
- sql12.dts.designer.advancededitor.componentproperties.f1
- sql12.dts.designer.advancededitor.connections.f1
ms.assetid: 5ad0ac71-fa8b-4c26-bd42-e6ef00c87571
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4897f2589acdeb93efecbdf9aacde07d21ca42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657247"
---
# <a name="advanced-editor"></a><span data-ttu-id="3fd61-102">Расширенный редактор</span><span class="sxs-lookup"><span data-stu-id="3fd61-102">Advanced Editor</span></span>
  <span data-ttu-id="3fd61-103">Используйте диалоговое окно **Расширенный редактор** для настройки свойств компонентов для выбранного объекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3fd61-103">Use the **Advanced Editor** dialog box to configure to configure properties for the selected [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="3fd61-104">**Расширенный редактор** доступен для большинства объектов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] с настраиваемыми свойствами.</span><span class="sxs-lookup"><span data-stu-id="3fd61-104">The **Advanced Editor** is available for most [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects that have configurable properties.</span></span> <span data-ttu-id="3fd61-105">Это единственный редактор, доступный для объектов, не показывающих настраиваемый пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="3fd61-105">It is the only editor available for those objects that do not expose a custom user interface.</span></span>  
  
 <span data-ttu-id="3fd61-106">Объекты потока данных [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] обладают свойствами, которые могут быть заданы на уровне компонентов, на уровне ввода и вывода и на уровне входных и выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="3fd61-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] data flow objects have properties that can be set at the component level, the input and output level, and the input and output column level.</span></span> <span data-ttu-id="3fd61-107">**Расширенный редактор** перечисляет все общие и пользовательские свойства выбранного объекта и показывает их на одной-четырех вкладках из пяти следующих вкладок:</span><span class="sxs-lookup"><span data-stu-id="3fd61-107">The **Advanced Editor** enumerates all the common and custom properties of the selected object and displays them on up to four of the following five tabs as applicable:</span></span>  
  
-   <span data-ttu-id="3fd61-108">**Диспетчеры соединений** — эта вкладка используется для настройки свойств подключения.</span><span class="sxs-lookup"><span data-stu-id="3fd61-108">**Connection Managers** -- use this tab to set connection properties</span></span>  
  
-   <span data-ttu-id="3fd61-109">**Свойства компонентов** — эта вкладка используется для настройки свойств уровня компонентов.</span><span class="sxs-lookup"><span data-stu-id="3fd61-109">**Component Properties** -- use this tab to set component-level properties</span></span>  
  
-   <span data-ttu-id="3fd61-110">**Сопоставления столбцов** — эта вкладка используется для сопоставления доступных столбцов в качестве выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="3fd61-110">**Column Mappings** -- use this tab to map available columns as output columns</span></span>  
  
-   <span data-ttu-id="3fd61-111">**Входные столбцы** — эта вкладка используется для выбора входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="3fd61-111">**Input Columns** -- use this tab to select input columns</span></span>  
  
-   <span data-ttu-id="3fd61-112">**Входные и выходные свойства** — эта вкладка используется для настройки входных и выходных свойств, добавления и удаления выходов, выбора или удаления столбцов для входов и выходов, а также задания свойств для входов и выходов.</span><span class="sxs-lookup"><span data-stu-id="3fd61-112">**Input and Output Properties** -- use this tab to set input and output properties; and to add and remove outputs, select or remove columns for inputs and outputs, and set properties for inputs and outputs</span></span>  
  
 <span data-ttu-id="3fd61-113">Отображаемые свойства зависят от компонента.</span><span class="sxs-lookup"><span data-stu-id="3fd61-113">The properties displayed vary by component.</span></span> <span data-ttu-id="3fd61-114">Дополнительные сведения о свойствах, которые могут отображаться в компоненте **Расширенный редактор**, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3fd61-114">For more information on the properties that may be displayed in the **Advanced Editor**, see the following topics:</span></span>  
  
-   [<span data-ttu-id="3fd61-115">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="3fd61-115">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
-   [<span data-ttu-id="3fd61-116">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="3fd61-116">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
-   [<span data-ttu-id="3fd61-117">Свойства пути</span><span class="sxs-lookup"><span data-stu-id="3fd61-117">Path Properties</span></span>](../../2014/integration-services/path-properties.md)  
  
 <span data-ttu-id="3fd61-118">Дополнительные сведения о конкретном изменяемом компоненте см. в описании компонента в разделе «Элементы потока данных» документации «Объекты и основные понятия для служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ».</span><span class="sxs-lookup"><span data-stu-id="3fd61-118">For more information about the specific component that you are editing, see the description of the component in the Data Flow Elements section of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Objects and Concepts documentation:</span></span>  
  
-   [<span data-ttu-id="3fd61-119">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="3fd61-119">Integration Services Transformations</span></span>](data-flow/transformations/integration-services-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="3fd61-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="3fd61-120">See Also</span></span>  
 [<span data-ttu-id="3fd61-121">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="3fd61-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
