---
title: Расширение возможностей OLAP с помощью персонализаций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, extensibility
ms.assetid: 348e49fc-4390-43c1-9b6c-61b386ff4373
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93669980e989b1cb11673f45c111de3609bbe920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750292"
---
# <a name="extending-olap-through-personalizations"></a><span data-ttu-id="05031-102">Расширение OLAP через личные настройки</span><span class="sxs-lookup"><span data-stu-id="05031-102">Extending OLAP through personalizations</span></span>
  <span data-ttu-id="05031-103">Службы Microsoft [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] предоставляют множество встроенных функций для использования в языках многомерных выражений (MDX) и расширений интеллектуального анализа данных (DMX).</span><span class="sxs-lookup"><span data-stu-id="05031-103">Microsoft  [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] supplies many intrinsic functions for use with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span> <span data-ttu-id="05031-104">Эти функции спроектированы, чтобы выполнять практически все, от стандартных статистических вычислений до прохода по элементам иерархии.</span><span class="sxs-lookup"><span data-stu-id="05031-104">These functions are designed to accomplish everything from standard statistical calculations to traversing members in a hierarchy.</span></span> <span data-ttu-id="05031-105">Однако, как и в случае с любым другим сложным и надежным продуктом, возникает необходимость в дальнейшем расширении функциональности такого продукта.</span><span class="sxs-lookup"><span data-stu-id="05031-105">However, as with any other complex and robust product, there is always the need to extend the functionality of such a product further.</span></span>  
  
 <span data-ttu-id="05031-106">Поэтому службы Analysis Services предоставляют возможность добавлять сборки и модули персонализации в экземпляр службы, чтобы удовлетворить потребности, не охватываемые стандартной функциональностью.</span><span class="sxs-lookup"><span data-stu-id="05031-106">Therefore, Analysis Services provides you with the ability to add assemblies and personalized extensions to an instance of the service, in order to complete your business needs whenever the standard functionality is not enough.</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="05031-107">Сборки</span><span class="sxs-lookup"><span data-stu-id="05031-107">Assemblies</span></span>  
 <span data-ttu-id="05031-108">Сборки позволяют расширять бизнес-функции многомерных выражений и расширений интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="05031-108">Assemblies enable you to extend the business functionality of MDX and DMX.</span></span> <span data-ttu-id="05031-109">Требуемые функции формируются в виде библиотеки, например динамически подключаемой библиотеки (DLL), которая затем добавляется в качестве сборки к экземпляру служб Analysis Services или к базе данных служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="05031-109">You build the functionality that you want into a library, such as a dynamic link library (DLL), then add the library as an assembly to an instance of Analysis Services or to an Analysis Services database.</span></span> <span data-ttu-id="05031-110">Общие методы в библиотеке затем открываются в виде пользовательских функций для многомерных выражений и выражений расширений интеллектуального анализа данных, их процедур, вычислений, действий и клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="05031-110">The public methods in the library are then exposed as user-defined functions to MDX and DMX expressions, procedures, calculations, actions, and client applications.</span></span>  
  
## <a name="personalized-extensions"></a><span data-ttu-id="05031-111">Модули персонализации</span><span class="sxs-lookup"><span data-stu-id="05031-111">Personalized Extensions</span></span>  
 <span data-ttu-id="05031-112">Модули персонализации служб SQL Server Analysis Services лежат в основе архитектуры подключаемых модулей.</span><span class="sxs-lookup"><span data-stu-id="05031-112">SQL Server Analysis Services personalization extensions are the foundation of the idea of implementing a plug-in architecture.</span></span> <span data-ttu-id="05031-113">Analysis Services расширений персонализации — это простое и элегантное изменение существующей архитектуры управляемой сборки. они доступны во всех Analysis Services объектной модели [Microsoft. AnalysisServices. того объектная AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) , СИНТАКСИСе многомерных выражений и наборах строк схемы.</span><span class="sxs-lookup"><span data-stu-id="05031-113">Analysis Services personalization extensions are a simple and elegant modification to the existing managed assembly architecture and are exposed throughout the Analysis Services [Microsoft.AnalysisServices.AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) object model, Multidimensional Expressions (MDX) syntax, and schema rowsets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05031-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="05031-114">See Also</span></span>  
 <span data-ttu-id="05031-115">[Управление сборками многомерной модели](../multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="05031-115">[Multidimensional Model Assemblies Management](../multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="05031-116">Модули персонализации служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="05031-116">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
  
