---
title: Преобразование "Многоадресная доставка" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multicasttrans.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7b5c0a38c966c89f426a213f302b45c390b77cfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752324"
---
# <a name="multicast-transformation"></a><span data-ttu-id="926eb-102">преобразование «Многоадресная доставка»</span><span class="sxs-lookup"><span data-stu-id="926eb-102">Multicast Transformation</span></span>
  <span data-ttu-id="926eb-103">Преобразование «Многоадресная доставка» распределяет данные на входе на один или более выходов.</span><span class="sxs-lookup"><span data-stu-id="926eb-103">The Multicast transformation distributes its input to one or more outputs.</span></span> <span data-ttu-id="926eb-104">Это преобразование схоже с преобразованием «Условное разбиение».</span><span class="sxs-lookup"><span data-stu-id="926eb-104">This transformation is similar to the Conditional Split transformation.</span></span> <span data-ttu-id="926eb-105">Оба вида преобразований направляют данные на входе на несколько выходов.</span><span class="sxs-lookup"><span data-stu-id="926eb-105">Both transformations direct an input to multiple outputs.</span></span> <span data-ttu-id="926eb-106">Их различие состоит в том, что преобразование «Многоадресная доставка» направляет каждую строку на все выходы, а преобразование «Условное разбиение» направляет одну строку на один выход.</span><span class="sxs-lookup"><span data-stu-id="926eb-106">The difference between the two is that the Multicast transformation directs every row to every output, and the Conditional Split directs a row to a single output.</span></span> <span data-ttu-id="926eb-107">Дополнительные сведения см. в статье [Conditional Split Transformation](conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="926eb-107">For more information, see [Conditional Split Transformation](conditional-split-transformation.md).</span></span>  
  
 <span data-ttu-id="926eb-108">Можно производить настройку преобразования «Многоадресная доставка» путем добавления выходов.</span><span class="sxs-lookup"><span data-stu-id="926eb-108">You configure the Multicast transformation by adding outputs.</span></span>  
  
 <span data-ttu-id="926eb-109">Используя преобразование «Многоадресная доставка», пакет может создавать логические копии данных.</span><span class="sxs-lookup"><span data-stu-id="926eb-109">Using the Multicast transformation, a package can create logical copies of data.</span></span> <span data-ttu-id="926eb-110">Эта возможность полезна, если пакету необходимо применить несколько наборов преобразований к одним и тем же данным.</span><span class="sxs-lookup"><span data-stu-id="926eb-110">This capability is useful when the package needs to apply multiple sets of transformations to the same data.</span></span> <span data-ttu-id="926eb-111">Например, одна копия данных статистически обрабатывается и в назначение загружается только сводная информация, а в другую копию данных перед загрузкой в назначение добавляются значения уточняющего запроса и производные столбцы.</span><span class="sxs-lookup"><span data-stu-id="926eb-111">For example, one copy of the data is aggregated and only the summary information is loaded into its destination, while another copy of the data is extended with lookup values and derived columns before it is loaded into its destination.</span></span>  
  
 <span data-ttu-id="926eb-112">Это преобразование имеет один вход и несколько выходов.</span><span class="sxs-lookup"><span data-stu-id="926eb-112">This transformation has one input and multiple outputs.</span></span> <span data-ttu-id="926eb-113">Вывод ошибок не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="926eb-113">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-multicast-transformation"></a><span data-ttu-id="926eb-114">Настройка преобразования «Многоадресная доставка»</span><span class="sxs-lookup"><span data-stu-id="926eb-114">Configuration of the Multicast Transformation</span></span>  
 <span data-ttu-id="926eb-115">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="926eb-115">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="926eb-116">Сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Многоадресная доставка»** , см. в разделе [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="926eb-116">For information about the properties that you can set in the **Multicast Transformation Editor** dialog box, see [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="926eb-117">Сведения о свойствах, которые можно задать программно, см. в разделе [Common Properties](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="926eb-117">For information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="926eb-118">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="926eb-118">Related Tasks</span></span>  
 <span data-ttu-id="926eb-119">Дополнительные сведения о настройке свойств компонента см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="926eb-119">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="926eb-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="926eb-120">See Also</span></span>  
 <span data-ttu-id="926eb-121">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="926eb-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="926eb-122">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="926eb-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
