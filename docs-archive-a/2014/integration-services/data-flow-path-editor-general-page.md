---
title: Редактор пути потока данных (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.patheditor.general.f1
helpviewer_keywords:
- Data Flow Path Editor dialog box
ms.assetid: 72a9ff1d-3748-41d1-a9b2-63f4a77bba24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71eca61b1454e2e8cb811bbe450f584191ae77b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729706"
---
# <a name="data-flow-path-editor-general-page"></a><span data-ttu-id="91ae3-102">Редактор пути потока данных (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="91ae3-102">Data Flow Path Editor (General Page)</span></span>
  <span data-ttu-id="91ae3-103">Используйте диалоговое окно **Редактор пути потока данных** , чтобы устанавливать свойства пути, просматривать метаданные столбцов и управлять средствами просмотра данных, прикрепленными к пути.</span><span class="sxs-lookup"><span data-stu-id="91ae3-103">Use the **Data Flow Path Editor** dialog box to set path properties, view column metadata, and manage the data viewers attached to the path.</span></span>  
  
 <span data-ttu-id="91ae3-104">Используйте раздел **Общие** диалогового окна **Редактор пути потока данных** , чтобы задать имя и описание пути, а также указать заметки для пути.</span><span class="sxs-lookup"><span data-stu-id="91ae3-104">Use the **General** node of the **Data Flow Path Editor** dialog box to name and describe the path, and to specify the options for path annotation.</span></span>  
  
## <a name="options"></a><span data-ttu-id="91ae3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="91ae3-105">Options</span></span>  
 <span data-ttu-id="91ae3-106">**имя**;</span><span class="sxs-lookup"><span data-stu-id="91ae3-106">**Name**</span></span>  
 <span data-ttu-id="91ae3-107">Введите уникальное имя пути.</span><span class="sxs-lookup"><span data-stu-id="91ae3-107">Provide a unique name for the path.</span></span>  
  
 <span data-ttu-id="91ae3-108">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="91ae3-108">**ID**</span></span>  
 <span data-ttu-id="91ae3-109">Идентификатор истории данных пути.</span><span class="sxs-lookup"><span data-stu-id="91ae3-109">The lineage identifier of the path.</span></span> <span data-ttu-id="91ae3-110">Это свойство доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="91ae3-110">This property is read-only.</span></span>  
  
 <span data-ttu-id="91ae3-111">**IdentificationString**</span><span class="sxs-lookup"><span data-stu-id="91ae3-111">**IdentificationString**</span></span>  
 <span data-ttu-id="91ae3-112">Строка, идентифицирующая путь.</span><span class="sxs-lookup"><span data-stu-id="91ae3-112">The string that identifies the path.</span></span> <span data-ttu-id="91ae3-113">Автоматически образуется из имени, введенного выше.</span><span class="sxs-lookup"><span data-stu-id="91ae3-113">Automatically generated from the name entered above.</span></span>  
  
 <span data-ttu-id="91ae3-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="91ae3-114">**Description**</span></span>  
 <span data-ttu-id="91ae3-115">Введите описание пути.</span><span class="sxs-lookup"><span data-stu-id="91ae3-115">Describe the path.</span></span>  
  
 <span data-ttu-id="91ae3-116">**PathAnnotation**</span><span class="sxs-lookup"><span data-stu-id="91ae3-116">**PathAnnotation**</span></span>  
 <span data-ttu-id="91ae3-117">Укажите тип заметки, который должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="91ae3-117">Specify the type of annotation to use.</span></span> <span data-ttu-id="91ae3-118">Выберите **Never** , чтобы отключить заметки, **AsNeeded** , чтобы включить заметки по требованию, **SourceName** , чтобы комментирование осуществлялось автоматически с использованием значения параметра **SourceName** и **PathName** , чтобы комментирование осуществлялось автоматически с использованием значения параметра **Name** .</span><span class="sxs-lookup"><span data-stu-id="91ae3-118">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **SourceName** to automatically annotate using the value of the **SourceName** option, and **PathName** to automatically annotate using the value of the **Name** property.</span></span>  
  
 <span data-ttu-id="91ae3-119">**DestinationName**</span><span class="sxs-lookup"><span data-stu-id="91ae3-119">**DestinationName**</span></span>  
 <span data-ttu-id="91ae3-120">Отображает вход, являющийся концом пути.</span><span class="sxs-lookup"><span data-stu-id="91ae3-120">Displays the input that is the end of the path.</span></span>  
  
 <span data-ttu-id="91ae3-121">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="91ae3-121">**SourceName**</span></span>  
 <span data-ttu-id="91ae3-122">Отображает выход, являющийся началом пути.</span><span class="sxs-lookup"><span data-stu-id="91ae3-122">Displays the output that is the start of the path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ae3-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="91ae3-123">See Also</span></span>  
 <span data-ttu-id="91ae3-124">[Редактор пути потока данных &#40;страница метаданных&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span><span class="sxs-lookup"><span data-stu-id="91ae3-124">[Data Flow Path Editor &#40;Metadata Page&#41;](../../2014/integration-services/data-flow-path-editor-metadata-page.md) </span></span>  
 <span data-ttu-id="91ae3-125">[Редактор пути потока данных &#40;страница "средства просмотра данных"&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span><span class="sxs-lookup"><span data-stu-id="91ae3-125">[Data Flow Path Editor &#40;Data Viewers Page&#41;](../../2014/integration-services/data-flow-path-editor-data-viewers-page.md) </span></span>  
 <span data-ttu-id="91ae3-126">[Поток данных](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="91ae3-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="91ae3-127">Использование заметок в пакетах</span><span class="sxs-lookup"><span data-stu-id="91ae3-127">Use Annotations in Packages</span></span>](use-annotations-in-packages.md)  
  
  
