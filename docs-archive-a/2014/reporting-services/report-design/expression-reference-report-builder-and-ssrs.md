---
title: Справочник выражений (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: bb16e4ab-b13f-48f2-8cfe-1851656875ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7854aa2cc256d63fe93ddb049486e782bfaa0e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658119"
---
# <a name="expression-reference-report-builder-and-ssrs"></a><span data-ttu-id="d3aef-102">Справочник выражений (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-102">Expression Reference (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d3aef-103">Выражения отчета поддерживают различные ссылки на встроенные функции и встроенные коллекции.</span><span class="sxs-lookup"><span data-stu-id="d3aef-103">Report expressions support a variety of references to built-in functions and built-in collections.</span></span> <span data-ttu-id="d3aef-104">Чтобы отчет можно было опубликовать или обработать, выражения должны иметь допустимый синтаксис [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3aef-104">Expressions must have valid [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] syntax before a report can be published or processed.</span></span>  
  
 <span data-ttu-id="d3aef-105">Для разработки сложных выражений или выражений, использующих пользовательский код или пользовательские сборки, рекомендуется использовать конструктор отчетов среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3aef-105">To develop complex expressions or expressions that use custom code or custom assemblies, we recommend that you use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d3aef-106">Дополнительные сведения см. в разделе [Пользовательский код и ссылки на сборки в выражениях в конструкторе отчетов (службы SSRS)](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d3aef-106">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="d3aef-107">Этот раздел предназначен для помощи в написании простых выражений в отчете.</span><span class="sxs-lookup"><span data-stu-id="d3aef-107">Use the topics in this section to help write simple expressions in a report.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3aef-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d3aef-108">In This Section</span></span>  
 [<span data-ttu-id="d3aef-109">Типы данных в выражениях (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-109">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="d3aef-110">Константы в выражениях (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-110">Constants in Expressions &#40;Report Builder and SSRS&#41;</span></span>](constants-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="d3aef-111">Операторы в выражениях (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-111">Operators in Expressions &#40;Report Builder and SSRS&#41;</span></span>](operators-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="d3aef-112">Встроенные коллекции в выражениях (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-112">Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-in-expressions-report-builder.md)  
  
 [<span data-ttu-id="d3aef-113">Встроенные глобальные значения и ссылки на пользовательские поля (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-113">Built-in Globals and Users References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-built-in-globals-and-users-references-report-builder.md)  
  
 [<span data-ttu-id="d3aef-114">Ссылки на коллекцию параметров (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-114">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
 [<span data-ttu-id="d3aef-115">Ссылки на коллекцию полей набора данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-115">Dataset Fields Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-dataset-fields-collection-references-report-builder.md)  
  
 [<span data-ttu-id="d3aef-116">Ссылки на коллекции DataSources и DataSets (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-116">DataSources and DataSets Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-datasources-and-datasets-references-report-builder.md)  
  
 [<span data-ttu-id="d3aef-117">Ссылки на коллекции переменных отчета и группы (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-117">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  
  
 [<span data-ttu-id="d3aef-118">Ссылки на коллекцию ReportItems (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-118">ReportItems Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-reportitems-collection-references-report-builder.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3aef-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3aef-119">See Also</span></span>  
 [<span data-ttu-id="d3aef-120">Выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d3aef-120">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
