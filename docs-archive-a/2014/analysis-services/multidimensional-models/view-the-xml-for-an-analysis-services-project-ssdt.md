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
# <a name="view-the-xml-for-an-analysis-services-project-ssdt"></a>Просмотр XML-кода проекта служб Analysis Services (среда SSDT)
  При работе с базой данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в режиме проекта среда [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] создает определение XML для каждого объекта в папке проекта. В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]можно просмотреть содержимое файла XML для каждого объекта. XML-файл можно редактировать напрямую, однако в большинстве случаев это не рекомендуется, так как может привести к нечитабельности XML-файла в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].  
  
> [!NOTE]  
>  Код XML всего проекта посмотреть нельзя, но можно просмотреть код для каждого объекта, так как для каждого объекта существуют отдельные файлы. Единственный способ просмотреть код для всего проекта — это построить проект и просмотреть код ASSL в \<project name> asdatabase-файле.  
  
### <a name="to-view-the-xml-code-for-an-object"></a>Просмотр XML-кода объекта  
  
1.  Откройте проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].  
  
2.  В обозревателе решений щелкните правой кнопкой мыши объект и выберите пункт **Просмотр кода**.  
  
     XML-код объекта появится в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].  
  
## <a name="see-also"></a>См. также:  
 [Построение проектов служб Analysis Services (среда SSDT)](build-analysis-services-projects-ssdt.md)  
  
  
