---
title: Просмотр XML-кода для Analysis Services проекта (SSDT) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Analysis Services], viewing XML
ms.assetid: dd1a4bc6-57b5-47df-8619-09f921aa6351
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1c320145be2073c741498bed0f10732ac8d528e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740511"
---
# <a name="view-the-xml-for-an-analysis-services-project-ssdt"></a><span data-ttu-id="63230-102">Просмотр XML-кода проекта служб Analysis Services (среда SSDT)</span><span class="sxs-lookup"><span data-stu-id="63230-102">View the XML for an Analysis Services Project (SSDT)</span></span>
  <span data-ttu-id="63230-103">При работе с базой данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в режиме проекта среда [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] создает определение XML для каждого объекта в папке проекта.</span><span class="sxs-lookup"><span data-stu-id="63230-103">When you are working with an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in project mode, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates an XML definition for each object within the project folder.</span></span> <span data-ttu-id="63230-104">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]можно просмотреть содержимое файла XML для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="63230-104">You can view the contents of the XML file for each object within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="63230-105">XML-файл можно редактировать напрямую, однако в большинстве случаев это не рекомендуется, так как может привести к нечитабельности XML-файла в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63230-105">You can also edit the XML file directly; however, this is not recommended in most circumstances as you may make changes that make the XML unreadable by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63230-106">Код XML всего проекта посмотреть нельзя, но можно просмотреть код для каждого объекта, так как для каждого объекта существуют отдельные файлы.</span><span class="sxs-lookup"><span data-stu-id="63230-106">You cannot view the xml code for an entire project, but rather you view the code for each object because a separate file exists for each object.</span></span> <span data-ttu-id="63230-107">Единственный способ просмотреть код для всего проекта — это построить проект и просмотреть код ASSL в \<project name> asdatabase-файле.</span><span class="sxs-lookup"><span data-stu-id="63230-107">The only way to view the code for an entire project is to build the project and view the ASSL code in the \<project name>.asdatabase file.</span></span>  
  
### <a name="to-view-the-xml-code-for-an-object"></a><span data-ttu-id="63230-108">Просмотр XML-кода объекта</span><span class="sxs-lookup"><span data-stu-id="63230-108">To view the XML code for an object</span></span>  
  
1.  <span data-ttu-id="63230-109">Откройте проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63230-109">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="63230-110">В обозревателе решений щелкните правой кнопкой мыши объект и выберите пункт **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="63230-110">Right-click the object in Solution Explorer and then click **View Code**.</span></span>  
  
     <span data-ttu-id="63230-111">XML-код объекта появится в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63230-111">The XML code for the object appears in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63230-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="63230-112">See Also</span></span>  
 [<span data-ttu-id="63230-113">Построение проектов служб Analysis Services (среда SSDT)</span><span class="sxs-lookup"><span data-stu-id="63230-113">Build Analysis Services Projects &#40;SSDT&#41;</span></span>](build-analysis-services-projects-ssdt.md)  
  
  
