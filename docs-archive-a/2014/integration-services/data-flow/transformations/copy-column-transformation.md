---
title: Преобразование "Копирование столбца" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copycolumntrans.f1
helpviewer_keywords:
- columns [Integration Services], copying
- copying columns
- Copy Column transformation
ms.assetid: 1c72a313-9026-46bc-a57f-c6b3f47346f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fd2745070a92ab71e89f3bfa9edd8673b676632b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665457"
---
# <a name="copy-column-transformation"></a><span data-ttu-id="72e52-102">преобразование «Копирование столбца»</span><span class="sxs-lookup"><span data-stu-id="72e52-102">Copy Column Transformation</span></span>
  <span data-ttu-id="72e52-103">Преобразование «Копирование столбца» позволяет создавать новые столбцы путем копирования входных столбцов и добавления новых к выходу преобразования.</span><span class="sxs-lookup"><span data-stu-id="72e52-103">The Copy Column transformation creates new columns by copying input columns and adding the new columns to the transformation output.</span></span> <span data-ttu-id="72e52-104">На более поздних этапах потока данных к копиям столбцов могут применяться различные преобразования.</span><span class="sxs-lookup"><span data-stu-id="72e52-104">Later in the data flow, different transformations can be applied to the column copies.</span></span> <span data-ttu-id="72e52-105">Например, преобразование «Копирование столбца» можно использовать для создания копии столбца и дальнейшего перевода символов скопированных данных в верхний регистр с помощью преобразования «Таблица символов» или для статистической обработки нового столбца с помощью преобразования «Агрегатная обработка».</span><span class="sxs-lookup"><span data-stu-id="72e52-105">For example, you can use the Copy Column transformation to create a copy of a column and then convert the copied data to uppercase characters by using the Character Map transformation, or apply aggregations to the new column by using the Aggregate transformation.</span></span>  
  
## <a name="configuration-of-the-copy-column-transformation"></a><span data-ttu-id="72e52-106">Настройка преобразования «Копирование столбца»</span><span class="sxs-lookup"><span data-stu-id="72e52-106">Configuration of the Copy Column Transformation</span></span>  
 <span data-ttu-id="72e52-107">Преобразование «Копирование столбца» настраивается путем определения входных столбцов, которые необходимо скопировать.</span><span class="sxs-lookup"><span data-stu-id="72e52-107">You configure the Copy Column transformation by specifying the input columns to copy.</span></span> <span data-ttu-id="72e52-108">Можно создать несколько копий столбца или же копии нескольких столбцов в одной операции.</span><span class="sxs-lookup"><span data-stu-id="72e52-108">You can create multiple copies of a column, or create copies of multiple columns in one operation.</span></span>  
  
 <span data-ttu-id="72e52-109">Это преобразование имеет один вход и один выход.</span><span class="sxs-lookup"><span data-stu-id="72e52-109">This transformation has one input and one output.</span></span> <span data-ttu-id="72e52-110">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72e52-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="72e52-111">Свойства могут устанавливаться через конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="72e52-111">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="72e52-112">Дополнительные сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Копирование столбцов»** , см. в разделе [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="72e52-112">For more information about the properties that you can set in the **Copy Column Transformation Editor** dialog box, see [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="72e52-113">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="72e52-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="72e52-114">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="72e52-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="72e52-115">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="72e52-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="72e52-116">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="72e52-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="72e52-117">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="72e52-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e52-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="72e52-118">See Also</span></span>  
 <span data-ttu-id="72e52-119">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="72e52-119">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="72e52-120">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="72e52-120">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
