---
title: Использование пользовательских сборок с отчетами | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services]
- assemblies [Reporting Services], custom
- custom assemblies [Reporting Services], about custom assemblies
ms.assetid: 53d141d0-2185-466a-84dc-7b90d284da3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f77b9da44ebb57617bd45e43d1e1e847e9074662
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730221"
---
# <a name="using-custom-assemblies-with-reports"></a><span data-ttu-id="04ade-102">Использование пользовательских сборок с отчетами</span><span class="sxs-lookup"><span data-stu-id="04ade-102">Using Custom Assemblies with Reports</span></span>
  <span data-ttu-id="04ade-103">В службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] можно создавать пользовательский код для значений элементов отчета, стилей и форматирования.</span><span class="sxs-lookup"><span data-stu-id="04ade-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can write custom code for report item values, styles, and formatting.</span></span> <span data-ttu-id="04ade-104">Так, пользовательский код можно использовать для форматирования валют в зависимости от настроек локали, для применения к определенным значениям специальных методов форматирования или для использования других бизнес-правил, установленных в конкретной компании.</span><span class="sxs-lookup"><span data-stu-id="04ade-104">For example, you can use custom code to format currencies based on locale, flag certain values with special formatting, or apply other business rules that are in practice for your company.</span></span> <span data-ttu-id="04ade-105">Одним из способов включения этого кода в отчеты является создание сборки пользовательского кода с помощью [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] коллекции, на которую можно ссылаться из файлов определения отчета.</span><span class="sxs-lookup"><span data-stu-id="04ade-105">One way to include this code in your reports is to create a custom code assembly using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that you can reference from within your report definition files.</span></span> <span data-ttu-id="04ade-106">Сервер вызывает функции пользовательских сборок при выполнении отчета.</span><span class="sxs-lookup"><span data-stu-id="04ade-106">The server calls the functions in your custom assemblies when a report is run.</span></span> <span data-ttu-id="04ade-107">Пользовательские сборки можно применять для получения значений специализированных функций, которые намечено использовать в отчетах.</span><span class="sxs-lookup"><span data-stu-id="04ade-107">Custom assemblies can be used to retrieve specialized functions that you plan to use in your reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04ade-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="04ade-108">In This Section</span></span>  
 [<span data-ttu-id="04ade-109">Ссылки на сборки в RDL-файле</span><span class="sxs-lookup"><span data-stu-id="04ade-109">Referencing Assemblies in an RDL File</span></span>](referencing-assemblies-in-an-rdl-file.md)  
 <span data-ttu-id="04ade-110">Описывает способ создания ссылок на пользовательские сборки в файле языка определения отчета.</span><span class="sxs-lookup"><span data-stu-id="04ade-110">Describes how to reference your custom assemblies in a report definition language file.</span></span>  
  
 [<span data-ttu-id="04ade-111">Развертывание пользовательской сборки</span><span class="sxs-lookup"><span data-stu-id="04ade-111">Deploying a Custom Assembly</span></span>](deploying-a-custom-assembly.md)  
 <span data-ttu-id="04ade-112">Описывает способ развертывания пользовательских сборок в конструкторе отчетов и на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="04ade-112">Describes how to deploy a custom assembly to Report Designer and the report server.</span></span>  
  
 [<span data-ttu-id="04ade-113">Использование пользовательских сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="04ade-113">Using Strong-Named Custom Assemblies</span></span>](using-strong-named-custom-assemblies.md)  
 <span data-ttu-id="04ade-114">Описывает способ применения пользовательских сборок со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="04ade-114">Describes how to use custom assemblies with strong names.</span></span>  
  
 [<span data-ttu-id="04ade-115">Проверка предположений о наличии разрешений в пользовательских сборках</span><span class="sxs-lookup"><span data-stu-id="04ade-115">Asserting Permissions in Custom Assemblies</span></span>](asserting-permissions-in-custom-assemblies.md)  
 <span data-ttu-id="04ade-116">Описывает способ развертывания пользовательских сборок с ограниченными и конкретными разрешениями, а также способ подтверждения этих разрешений в коде.</span><span class="sxs-lookup"><span data-stu-id="04ade-116">Describes how to deploy custom assemblies with limited and specific permissions and how to assert those permissions in code.</span></span>  
  
 [<span data-ttu-id="04ade-117">Доступ к пользовательским сборкам посредством выражений</span><span class="sxs-lookup"><span data-stu-id="04ade-117">Accessing Custom Assemblies Through Expressions</span></span>](accessing-custom-assemblies-through-expressions.md)  
 <span data-ttu-id="04ade-118">Описывает способ вызова методов пользовательских сборок в виде выражений отчетов в определениях отчетов.</span><span class="sxs-lookup"><span data-stu-id="04ade-118">Describes how to call custom assembly methods as report expressions in your report definitions.</span></span>  
  
 [<span data-ttu-id="04ade-119">Инициализация объектов пользовательских сборок</span><span class="sxs-lookup"><span data-stu-id="04ade-119">Initializing Custom Assembly Objects</span></span>](initializing-custom-assembly-objects.md)  
 <span data-ttu-id="04ade-120">Описывает способ инициализации значений для объектов пользовательских сборок, вызываемых из отчета.</span><span class="sxs-lookup"><span data-stu-id="04ade-120">Describes how to initialize values for custom assembly objects called from a report.</span></span>  
  
 [<span data-ttu-id="04ade-121">Руководство. Отладка пользовательских сборок</span><span class="sxs-lookup"><span data-stu-id="04ade-121">How to: Debug Custom Assemblies</span></span>](how-to-debug-custom-assemblies.md)  
 <span data-ttu-id="04ade-122">Описывает способ отладки кода пользовательских сборок.</span><span class="sxs-lookup"><span data-stu-id="04ade-122">Describes how to debug your custom assembly code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ade-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="04ade-123">See Also</span></span>  
 [<span data-ttu-id="04ade-124">Язык определения отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="04ade-124">Report Definition Language &#40;SSRS&#41;</span></span>](../reports/report-definition-language-ssrs.md)  
  
  
