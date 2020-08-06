---
title: Назначение "Неструктурированный файл" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledest.f1
helpviewer_keywords:
- flat files
- Flat File destination
- text file writing [Integration Services]
- destinations [Integration Services], Flat File
ms.assetid: e0d6e356-8db4-48aa-ba66-029397f98f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a961b7528b13a4eaa3297343e91f1deaf2fa3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751316"
---
# <a name="flat-file-destination"></a><span data-ttu-id="d751c-102">назначение «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="d751c-102">Flat File Destination</span></span>
  <span data-ttu-id="d751c-103">Назначение «Неструктурированный файл» записывает данные в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="d751c-103">The Flat File destination writes data to a text file.</span></span> <span data-ttu-id="d751c-104">Текстовый файл может быть в следующих форматах: с разделителями, фиксированной ширины, фиксированной ширины с разделителем строки и без выравнивания текста справа.</span><span class="sxs-lookup"><span data-stu-id="d751c-104">The text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="d751c-105">Можно настроить назначение «Неструктурированный файл» следующими способами:</span><span class="sxs-lookup"><span data-stu-id="d751c-105">You can configure the Flat File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="d751c-106">Предоставить блок текста, который вставлен в файл, прежде чем какие-либо данные будут записаны.</span><span class="sxs-lookup"><span data-stu-id="d751c-106">Provide a block of text that is inserted in the file before any data is written.</span></span> <span data-ttu-id="d751c-107">Текст может предоставить необходимые сведения, такие как заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="d751c-107">The text can provide information such as column headings.</span></span>  
  
-   <span data-ttu-id="d751c-108">Указать, нужно ли перезаписывать данные в файле назначения, имеющем то же имя.</span><span class="sxs-lookup"><span data-stu-id="d751c-108">Specify whether to overwrite a data in a destination file that has the same name.</span></span>  
  
 <span data-ttu-id="d751c-109">Назначение использует диспетчер соединений с неструктурированными файлами для доступа к текстовым файлам.</span><span class="sxs-lookup"><span data-stu-id="d751c-109">This destination uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="d751c-110">Путем установки свойств в диспетчере соединений с неструктурированными файлами, который использует назначение «Неструктурированный файл», можно определить способ, которым назначение «Неструктурированный файл» форматирует и записывает текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="d751c-110">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="d751c-111">При настройке диспетчера соединений с неструктурированными файлами указываются сведения о файле и о каждом столбце в файле.</span><span class="sxs-lookup"><span data-stu-id="d751c-111">When you configure the Flat File connection manager, you specify information about the file and about each column in the file.</span></span> <span data-ttu-id="d751c-112">Например, указываются символы-разделители для столбцов и строк в файле, а также тип данных и длина каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="d751c-112">For example, you specify the characters that delimit columns and rows in the file, and you specify the data type and the length of each column.</span></span> <span data-ttu-id="d751c-113">Дополнительные сведения см. в статье [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d751c-113">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="d751c-114">Назначение "Неструктурированный файл" включает пользовательское свойство Header.</span><span class="sxs-lookup"><span data-stu-id="d751c-114">The Flat File destination includes the Header custom property.</span></span> <span data-ttu-id="d751c-115">Это свойство может быть обновлено выражением свойства при загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="d751c-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="d751c-116">Дополнительные сведения см. в разделах [Выражения служб Integration Services (SSIS)](../expressions/integration-services-ssis-expressions.md), [Использование выражений свойств в пакетах](../expressions/use-property-expressions-in-packages.md) и [Пользовательские свойства неструктурированного файла](flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d751c-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [Flat File Custom Properties](flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="d751c-117">Этот назначение имеет один выход.</span><span class="sxs-lookup"><span data-stu-id="d751c-117">This destination has one output.</span></span> <span data-ttu-id="d751c-118">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d751c-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-destination"></a><span data-ttu-id="d751c-119">Настройка назначения «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="d751c-119">Configuration of the Flat File Destination</span></span>  
 <span data-ttu-id="d751c-120">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="d751c-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d751c-121">Дополнительные сведения о свойствах, которые можно задать в диалоговом окне **Редактор источника «Неструктурированный файл»** , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d751c-121">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d751c-122">Редактор назначения "Неструктурированный файл" (страница "Диспетчер соединений")</span><span class="sxs-lookup"><span data-stu-id="d751c-122">Flat File Destination Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="d751c-123">Редактор назначения "Неструктурированный файл" (страница "Сопоставления")</span><span class="sxs-lookup"><span data-stu-id="d751c-123">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../flat-file-destination-editor-mappings-page.md)  
  
 <span data-ttu-id="d751c-124">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="d751c-124">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="d751c-125">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d751c-125">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d751c-126">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="d751c-126">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="d751c-127">Пользовательские свойства неструктурированного файла</span><span class="sxs-lookup"><span data-stu-id="d751c-127">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="d751c-128">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d751c-128">Related Tasks</span></span>  
 <span data-ttu-id="d751c-129">Дополнительные сведения о настройке свойств для компонента потока данных см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d751c-129">For information about how to set the properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d751c-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="d751c-130">See Also</span></span>  
 <span data-ttu-id="d751c-131">[Источник «Неструктурированный файл»](flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="d751c-131">[Flat File Source](flat-file-source.md) </span></span>  
 [<span data-ttu-id="d751c-132">Поток данных</span><span class="sxs-lookup"><span data-stu-id="d751c-132">Data Flow</span></span>](data-flow.md)  
  
  
