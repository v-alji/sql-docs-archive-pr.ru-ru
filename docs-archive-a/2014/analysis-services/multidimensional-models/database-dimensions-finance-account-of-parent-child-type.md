---
title: Создание финансовой учетной записи измерения типа "родители-потомки" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], account
- account dimensions [Analysis Services]
- adding account intelligence
- account intelligence [Analysis Services]
ms.assetid: 2ba74e81-5b4b-407e-acdf-deb2f6accf0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ba10e642425628426d9183be2b8d2c4ff751c3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731001"
---
# <a name="create-a-finance-account-of-parent-child-type-dimension"></a><span data-ttu-id="6e719-102">Создание учетной записи Finance с измерением типа «родитель-потомок»</span><span class="sxs-lookup"><span data-stu-id="6e719-102">Create a Finance Account of parent-child type Dimension</span></span>
  <span data-ttu-id="6e719-103">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] службах измерение типа «счет» — это измерение, атрибуты которого представляют диаграмму счетов для целей финансовой отчетности.</span><span class="sxs-lookup"><span data-stu-id="6e719-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], an account type dimension is a dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="6e719-104">Измерение счетов позволяет выборочно управлять поведением статистической обработки счетов во времени.</span><span class="sxs-lookup"><span data-stu-id="6e719-104">An account dimension lets you selectively manage aggregation behavior across accounts over time.</span></span> <span data-ttu-id="6e719-105">Измерение счетов также позволяет использовать стандартный механизм разрешения большинства нестандартных проблем, связанных со статистическими выражениями, которые часто возникают в решениях бизнес-аналитики, обрабатывающих финансовые данные.</span><span class="sxs-lookup"><span data-stu-id="6e719-105">An account dimension also lets use a standard mechanism to resolve most of the nonstandard aggregation issues typically encountered in business intelligence solutions that handle financial data.</span></span> <span data-ttu-id="6e719-106">Если такого стандартного механизма нет, то для решения нестандартных проблем, связанных со статистической обработкой, потребуются пользовательские формулы свертки, вычисляемые элементы или скрипты многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="6e719-106">If you did not have such a standard mechanism, resolving these nonstandard aggregation issues would require custom rollup formulas, calculated members, or Multidimensional Expressions (MDX) scripts.</span></span>  
  
 <span data-ttu-id="6e719-107">Чтобы сделать измерение измерением счетов, установите для свойства `Type` этого измерения значение `Accounts`.</span><span class="sxs-lookup"><span data-stu-id="6e719-107">To identify a dimension as an account dimension, set the `Type` property of the dimension to `Accounts`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="6e719-108">Структура измерения</span><span class="sxs-lookup"><span data-stu-id="6e719-108">Dimension Structure</span></span>  
 <span data-ttu-id="6e719-109">Измерения счетов содержат не менее двух атрибутов:</span><span class="sxs-lookup"><span data-stu-id="6e719-109">An account dimension contains, at least, two attributes:</span></span>  
  
-   <span data-ttu-id="6e719-110">Ключевой атрибут — атрибут, определяющий отдельные учетные записи в таблице измерения для измерения счетов.</span><span class="sxs-lookup"><span data-stu-id="6e719-110">A key attribute-an attribute that identifies individual accounts in the dimension table for the account dimension.</span></span>  
  
-   <span data-ttu-id="6e719-111">Атрибут Account — родительский атрибут, описывающий, как учетные записи иерархически упорядочиваются в измерении счетов.</span><span class="sxs-lookup"><span data-stu-id="6e719-111">An account attribute-a parent attribute that describes how accounts are hierarchically arranged in the account dimension.</span></span>  
  
     <span data-ttu-id="6e719-112">Чтобы сделать атрибут атрибутом счета, присвойте свойству `Type` атрибута значение `Account`, а свойству `Usage` — значение `Parent`.</span><span class="sxs-lookup"><span data-stu-id="6e719-112">To identify an attribute as an account attribute, set the `Type` property of the attribute to `Account` and the `Usage` property to `Parent`.</span></span>  
  
 <span data-ttu-id="6e719-113">Измерения счетов могут содержать следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="6e719-113">Account dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="6e719-114">Атрибут типа Account — атрибут, определяющий тип счета для каждой учетной записи в измерении.</span><span class="sxs-lookup"><span data-stu-id="6e719-114">An account type attribute-an attribute that defines the account type for each account in the dimension.</span></span> <span data-ttu-id="6e719-115">Имена элементов атрибутов счета сопоставляются с типами счетов, которые определены для проекта или базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , и обозначают статистическую функцию, применяемую службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для этих счетов.</span><span class="sxs-lookup"><span data-stu-id="6e719-115">The member names of the account type attribute map to the account types defined for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project, and indicate the aggregation function used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for those accounts.</span></span> <span data-ttu-id="6e719-116">Для определения поведения статистических вычислений атрибутов счетов можно использовать унарные операторы и формулы пользовательской свертки, однако типы счетов позволяют легко добиться согласованного поведения диаграммы счетов без изменения исходной реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="6e719-116">You can also use unary operators or custom rollup formulas to determine aggregation behavior for account attributes, but account types let you to easily apply consistent behavior to a chart of accounts without requiring changes to the underlying relational database.</span></span>  
  
     <span data-ttu-id="6e719-117">Чтобы определить атрибут счета, установите для свойства `Type` этого атрибута значение `AccountType`;</span><span class="sxs-lookup"><span data-stu-id="6e719-117">To identify an account type attribute, set the `Type` property of the attribute to `AccountType`.</span></span>  
  
-   <span data-ttu-id="6e719-118">Атрибут имени учетной записи — атрибут, используемый для создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="6e719-118">An account name attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="6e719-119">Чтобы определить атрибут имени счета, установите для свойства `Type` этого атрибута значение `AccountName`;</span><span class="sxs-lookup"><span data-stu-id="6e719-119">You identify an account name attribute by setting the `Type` property of the attribute to `AccountName`.</span></span>  
  
-   <span data-ttu-id="6e719-120">Атрибут номера счета — атрибут, используемый для создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="6e719-120">An account number attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="6e719-121">Чтобы определить атрибут номера счета, установите для свойства `Type` этого атрибута значение `AccountNumber`.</span><span class="sxs-lookup"><span data-stu-id="6e719-121">You identify an account number attribute by setting the `Type` property of the attribute to `AccountNumber`.</span></span>  
  
 <span data-ttu-id="6e719-122">Дополнительные сведения о типах атрибутов см. в разделе [Настройка типов атрибутов](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="6e719-122">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="adding-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="6e719-123">Добавление логики операций со счетами при помощи мастера бизнес-аналитики</span><span class="sxs-lookup"><span data-stu-id="6e719-123">Adding Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="6e719-124">После определения измерения счетов и добавления измерения в куб можно добавить логику операций со счетами, например определение и сопоставление типов счетов, в измерение при помощи мастера бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="6e719-124">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to adding account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="6e719-125">Дополнительные сведения см. в разделе [Добавление логики операций со счетами к измерению](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="6e719-125">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e719-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e719-126">See Also</span></span>  
 <span data-ttu-id="6e719-127">[Атрибуты и иерархии атрибутов](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="6e719-127">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="6e719-128">[Справка F1 мастера бизнес-аналитики](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="6e719-128">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="6e719-129">Типы измерений</span><span class="sxs-lookup"><span data-stu-id="6e719-129">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
