---
title: Редактор источника «ADO NET» (страница «вывод ошибок») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.erroroutput.f1
ms.assetid: 4dd9d129-a95c-4d3a-bbbf-e84a39089950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9ee480caa8764d70b52b25a416f200f353d30c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740256"
---
# <a name="ado-net-source-editor-error-output-page"></a><span data-ttu-id="b6c9f-102">Редактор источника данных «ADO.NET» (страница «Вывод ошибок»)</span><span class="sxs-lookup"><span data-stu-id="b6c9f-102">ADO NET Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="b6c9f-103">Страница **Вывод ошибок** диалогового окна **Редактор источника «ADO.NET»** используется для выбора параметров обработки ошибок, а также для установки свойств выходных столбцов ошибок.</span><span class="sxs-lookup"><span data-stu-id="b6c9f-103">Use the **Error Output** page of the **ADO NET Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="b6c9f-104">Дополнительные сведения об источниках данных «ADO.NET» см. в разделе [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="b6c9f-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="b6c9f-105">**Открытие страницы «Вывод ошибок»**</span><span class="sxs-lookup"><span data-stu-id="b6c9f-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="b6c9f-106">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте пакет [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий источник данных «ADO.NET».</span><span class="sxs-lookup"><span data-stu-id="b6c9f-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="b6c9f-107">На вкладке **Поток данных** дважды щелкните источник данных "ADO.NET".</span><span class="sxs-lookup"><span data-stu-id="b6c9f-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="b6c9f-108">В окне **Редактор источника «ADO.NET»** нажмите кнопку **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="b6c9f-108">In the **ADO NET Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b6c9f-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6c9f-109">Options</span></span>  
 <span data-ttu-id="b6c9f-110">**Ввод-вывод**</span><span class="sxs-lookup"><span data-stu-id="b6c9f-110">**Input/Output**</span></span>  
 <span data-ttu-id="b6c9f-111">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="b6c9f-111">View the name of the data source.</span></span>  
  
 <span data-ttu-id="b6c9f-112">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="b6c9f-112">**Column**</span></span>  
 <span data-ttu-id="b6c9f-113">Просмотрите внешние (исходные) столбцы, выбранные на странице **Диспетчер подключений** диалогового окна **Редактор источника "ADO.NET"** .</span><span class="sxs-lookup"><span data-stu-id="b6c9f-113">View the external (source) columns that you selected on the **Connection Manager** page of the **ADO NET Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="b6c9f-114">**Error**</span><span class="sxs-lookup"><span data-stu-id="b6c9f-114">**Error**</span></span>  
 <span data-ttu-id="b6c9f-115">Задайте действие, которое необходимо выполнить при возникновении ошибки: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="b6c9f-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="b6c9f-116">**См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="b6c9f-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="b6c9f-117">**Усечение**</span><span class="sxs-lookup"><span data-stu-id="b6c9f-117">**Truncation**</span></span>  
 <span data-ttu-id="b6c9f-118">Укажите, что нужно сделать при усечении: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="b6c9f-118">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="b6c9f-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b6c9f-119">**Description**</span></span>  
 <span data-ttu-id="b6c9f-120">Просмотреть описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6c9f-120">View the description of the error.</span></span>  
  
 <span data-ttu-id="b6c9f-121">**Присвоить указанное значение выбранным ячейкам**</span><span class="sxs-lookup"><span data-stu-id="b6c9f-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="b6c9f-122">Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения: пропустить ошибку, перенаправить строку или вызвать сбой компонента.</span><span class="sxs-lookup"><span data-stu-id="b6c9f-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="b6c9f-123">**Применить**</span><span class="sxs-lookup"><span data-stu-id="b6c9f-123">**Apply**</span></span>  
 <span data-ttu-id="b6c9f-124">Применить параметр обработки ошибок к выбранным ячейкам.</span><span class="sxs-lookup"><span data-stu-id="b6c9f-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c9f-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="b6c9f-125">See Also</span></span>  
 <span data-ttu-id="b6c9f-126">[Редактор источника «ADO NET» &#40;«диспетчер соединений»&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="b6c9f-126">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="b6c9f-127">[Редактор источника «ADO NET» &#40;столбцы&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="b6c9f-127">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="b6c9f-128">Диспетчер подключений ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b6c9f-128">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
