---
title: Преобразование отмены свертывания | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottrans.f1
helpviewer_keywords:
- Unpivot transformation
- more normalized data set [Integration Services]
- normalized data [Integration Services]
- datasets [Integration Services], normalized data
ms.assetid: f635c64b-a9c5-4f11-9c40-9cd9d5298c5d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e605dc4827a885b5dc65fbb680cce8a434b89fd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667300"
---
# <a name="unpivot-transformation"></a><span data-ttu-id="4c872-102">Преобразование отмены свертывания</span><span class="sxs-lookup"><span data-stu-id="4c872-102">Unpivot Transformation</span></span>
  <span data-ttu-id="4c872-103">Преобразование «Отмена свертывания» превращает набор ненормализованных данных в более нормализованную версию за счет развертывания значений из нескольких столбцов одной записи в несколько записей с теми же значениями в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="4c872-103">The Unpivot transformation makes an unnormalized dataset into a more normalized version by expanding values from multiple columns in a single record into multiple records with the same values in a single column.</span></span> <span data-ttu-id="4c872-104">Например, набор данных с перечнем имен клиентов имеет одну строку для каждого клиента, при этом купленные товары и их количество отображаются в столбцах строки.</span><span class="sxs-lookup"><span data-stu-id="4c872-104">For example, a dataset that lists customer names has one row for each customer, with the products and the quantity purchased shown in columns in the row.</span></span> <span data-ttu-id="4c872-105">После нормализации с помощью преобразования отмены свертывания набор данных содержит отдельную строку по каждому продукту, приобретенному клиентом.</span><span class="sxs-lookup"><span data-stu-id="4c872-105">After the Unpivot transformation normalizes the data set, the data set contains a different row for each product that the customer purchased.</span></span>  
  
 <span data-ttu-id="4c872-106">На диаграмме ниже показан набор данных до преобразования «Отмена сведения» в столбце Product.</span><span class="sxs-lookup"><span data-stu-id="4c872-106">The following diagram shows a data set before the data is unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="4c872-107">![Набор данных после отмены сведения](../../media/mw-dts-18.gif "Набор данных после отмены сведения")</span><span class="sxs-lookup"><span data-stu-id="4c872-107">![Dataset after it is unpivoted](../../media/mw-dts-18.gif "Dataset after it is unpivoted")</span></span>  
  
 <span data-ttu-id="4c872-108">На диаграмме ниже показан набор данных после преобразования «Отмена сведения» в столбце Product.</span><span class="sxs-lookup"><span data-stu-id="4c872-108">The following diagram shows a data set after it has been unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="4c872-109">![Набор данных до отмены сведения](../../media/mw-dts-17.gif "Набор данных до отмены сведения")</span><span class="sxs-lookup"><span data-stu-id="4c872-109">![Dataset before it is unpivoted](../../media/mw-dts-17.gif "Dataset before it is unpivoted")</span></span>  
  
 <span data-ttu-id="4c872-110">В некоторых случаях результаты преобразования «Отмена свертывания» могут содержать строки с непредвиденными значениями.</span><span class="sxs-lookup"><span data-stu-id="4c872-110">Under some circumstances, the unpivot results may contain rows with unexpected values.</span></span> <span data-ttu-id="4c872-111">Например, если образец данных для отмены свертывания, показанных на диаграмме, содержит для пользователя Фреда во всех столбцах Qty значения NULL, то для Фреда выходные данные будут содержать только одну строку, а не пять.</span><span class="sxs-lookup"><span data-stu-id="4c872-111">For example, if the sample data to unpivot shown in the diagram had null values in all the Qty columns for Fred, then the output would include only one row for Fred, not five.</span></span> <span data-ttu-id="4c872-112">Столбец Qty будет содержать либо значение NULL, либо ноль в зависимости от типа данных столбца.</span><span class="sxs-lookup"><span data-stu-id="4c872-112">The Qty column would contain either null or zero, depending on the column data type.</span></span>  
  
## <a name="configuration-of-the-unpivot-transformation"></a><span data-ttu-id="4c872-113">Настройка преобразования «Отмена сведения»</span><span class="sxs-lookup"><span data-stu-id="4c872-113">Configuration of the Unpivot Transformation</span></span>  
 <span data-ttu-id="4c872-114">Преобразование «Отмена свертывания» включает пользовательское свойство `PivotKeyValue`.</span><span class="sxs-lookup"><span data-stu-id="4c872-114">The Unpivot transformation includes the `PivotKeyValue` custom property.</span></span> <span data-ttu-id="4c872-115">Это свойство может быть обновлено выражением свойства при загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="4c872-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="4c872-116">Дополнительные сведения см. в разделах [Выражения служб Integration Services (SSIS)](../../expressions/integration-services-ssis-expressions.md), [Использование выражений свойств в пакетах](../../expressions/use-property-expressions-in-packages.md) и [Пользовательские свойства преобразований](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4c872-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="4c872-117">Это преобразование имеет один вход и один выход.</span><span class="sxs-lookup"><span data-stu-id="4c872-117">This transformation has one input and one output.</span></span> <span data-ttu-id="4c872-118">Оно не имеет выхода ошибок.</span><span class="sxs-lookup"><span data-stu-id="4c872-118">It has no error output.</span></span>  
  
 <span data-ttu-id="4c872-119">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="4c872-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4c872-120">Дополнительные сведения о свойствах, которые можно задавать в диалоговом окне **Редактор преобразования «Отмена свертывания»** , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4c872-120">For more information about the properties that you can set in the **Unpivot Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="4c872-121">Редактор преобразования «Отмена свертывания»</span><span class="sxs-lookup"><span data-stu-id="4c872-121">Unpivot Transformation Editor</span></span>](../../unpivot-transformation-editor.md)  
  
 <span data-ttu-id="4c872-122">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="4c872-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="4c872-123">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="4c872-123">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="4c872-124">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="4c872-124">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="4c872-125">Дополнительные сведения о настройке свойств см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="4c872-125">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
