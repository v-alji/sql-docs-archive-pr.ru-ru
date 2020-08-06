---
title: Разработка с использованием языкового скрипта Analysis Services (ASSL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services Scripting Language
- ASSL
ms.assetid: ce9aca4d-b7ad-451e-bb7f-20c2b0c03f29
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb64c120e67d5b4ac12e7bd77f0e0c4e5736757
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664574"
---
# <a name="developing-with-analysis-services-scripting-language-assl"></a><span data-ttu-id="a7c9d-102">Разработка на языке ASSL (язык ASSL)</span><span class="sxs-lookup"><span data-stu-id="a7c9d-102">Developing with Analysis Services Scripting Language (ASSL)</span></span>
  <span data-ttu-id="a7c9d-103">Язык ASSL является расширением XML для аналитики, в котором добавлен язык определения объектов и командный язык для создания структур служб Analysis Services и управления этими структурами непосредственно на сервере.</span><span class="sxs-lookup"><span data-stu-id="a7c9d-103">Analysis Services Scripting Language (ASSL) is an extension to XMLA that adds an object definition language and command language for creating and managing Analysis Services structures directly on the server.</span></span> <span data-ttu-id="a7c9d-104">Язык ASSL можно применять в пользовательском приложении для обмена данными со службами Analysis Services по протоколу XMLA.</span><span class="sxs-lookup"><span data-stu-id="a7c9d-104">You can use ASSL in custom application to communicate with Analysis Services over the XMLA protocol.</span></span> <span data-ttu-id="a7c9d-105">Язык ASSL состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="a7c9d-105">ASSL is made up of two parts:</span></span>  
  
-   <span data-ttu-id="a7c9d-106">Язык описания данных DDL, или язык определения объектов, который определяет и описывает экземпляр служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], а также базы данных и объекты баз данных, находящихся в этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="a7c9d-106">A Data Definition Language (DDL), or object definition language, defines and describes an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], as well as the databases and database objects that the instance contains.</span></span>  
  
-   <span data-ttu-id="a7c9d-107">Командный язык, предназначенный для отправки экземпляру служб Analysis Services команд-действий, например `Create`, `Alter` или `Process`.</span><span class="sxs-lookup"><span data-stu-id="a7c9d-107">A command language that sends action commands, such as `Create`, `Alter`, or `Process`, to an instance of Analysis Services.</span></span> <span data-ttu-id="a7c9d-108">Этот язык команд рассматривается в [справочнике по XML для аналитики &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="a7c9d-108">This command language is discussed in the [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="a7c9d-109">Чтобы просмотреть код ASSL, описывающий многомерное решение в среде [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], можно использовать команду «Показать код» на уровне проекта.</span><span class="sxs-lookup"><span data-stu-id="a7c9d-109">To view the ASSL that describes a multidimensional solution in [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], you can use the View Code command at the project level.</span></span> <span data-ttu-id="a7c9d-110">Также можно создать или изменить скрипт языка ASSL в среде [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] с помощью редактора запросов XMLA.</span><span class="sxs-lookup"><span data-stu-id="a7c9d-110">You can also create or edit ASSL script in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] using the XMLA query editor.</span></span> <span data-ttu-id="a7c9d-111">Построенные скрипты можно использовать для управления объектами и выполнения команд на сервере.</span><span class="sxs-lookup"><span data-stu-id="a7c9d-111">The scripts you build can be used to manage objects or run commands on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c9d-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7c9d-112">See Also</span></span>  
 <span data-ttu-id="a7c9d-113">[Объекты и характеристики объектов ASSL](assl-objects-and-object-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="a7c9d-113">[ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md) </span></span>  
 <span data-ttu-id="a7c9d-114">[XML-соглашения ASSL](assl-xml-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="a7c9d-114">[ASSL XML Conventions](assl-xml-conventions.md) </span></span>  
 [<span data-ttu-id="a7c9d-115">Источники данных и привязки (многомерные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="a7c9d-115">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](../data-sources-and-bindings-ssas-multidimensional.md)  
  
  
