---
title: Пользовательские элементы отчета | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- extending Reporting Services
- Reporting Services, extending
- custom report items
ms.assetid: 64dcaf2c-1af5-4937-8ff7-98f1ec3b367e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 86b819cb4d305e537a52a2e7f25cdfa3aefa5f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750532"
---
# <a name="custom-report-items"></a><span data-ttu-id="37a8a-102">Пользовательские элементы отчета</span><span class="sxs-lookup"><span data-stu-id="37a8a-102">Custom Report Items</span></span>
  <span data-ttu-id="37a8a-103">Службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] предлагают широкий выбор средств для построения и публикации отчетов предприятия, управления безопасностью и подписками. Эти средства позволяют расширить функциональные возможности по созданию отчетов через всеобъемлющий API-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="37a8a-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] provides a rich set of tools for building and publishing enterprise reports, managing security and subscriptions, and extending the reporting functionality through a comprehensive API.</span></span> <span data-ttu-id="37a8a-104">Отчеты определяются с помощью языка, основанного на языке XML, называемого языком определения отчетов Report Definition Language (RDL).</span><span class="sxs-lookup"><span data-stu-id="37a8a-104">Reports are defined using an XML-based language called Report Definition Language (RDL).</span></span> <span data-ttu-id="37a8a-105">Язык определения отчетов предоставляет ясный набор инструкций, описывающих макет, сведения о запросах и типы элементов для отчетов.</span><span class="sxs-lookup"><span data-stu-id="37a8a-105">RDL provides a set of instructions that describe layout, query information, and item types for a report.</span></span> <span data-ttu-id="37a8a-106">Язык определения отчетов возможно расширить, создав пользовательские элементы отчетов.</span><span class="sxs-lookup"><span data-stu-id="37a8a-106">It is possible to extend RDL by writing a custom report item.</span></span> <span data-ttu-id="37a8a-107">Пользовательский элемент отчета состоит из исполняемого компонента, который вызывается обработчиком отчетов во время выполнения, и компонента времени разработки, который делает пользовательский элемент отчета доступным в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="37a8a-107">The custom report item consists of a run-time component, which is called by the report processor at run time, and a design-time component, which allows the custom report item to be available in Report Designer.</span></span>  
  
 <span data-ttu-id="37a8a-108">Образец полностью реализованного пользовательского элемента отчета см. на странице [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="37a8a-108">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-scenarios"></a><span data-ttu-id="37a8a-109">Сценарии применения пользовательских элементов отчета</span><span class="sxs-lookup"><span data-stu-id="37a8a-109">Custom Report Item Scenarios</span></span>  
 <span data-ttu-id="37a8a-110">Разработчикам, желающим интегрировать службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в собственные приложения, могут потребоваться функциональные возможности, не поддерживаемые языком определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="37a8a-110">Developers who need to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into their applications may require functionality that is not natively supported in RDL.</span></span> <span data-ttu-id="37a8a-111">В их число могут входить следующие элементы: карты, горизонтальные списки, списки в столбцах и матрицы с возможностью сведения.</span><span class="sxs-lookup"><span data-stu-id="37a8a-111">This may include items such as: map controls, horizontal lists, columnar lists, and repivotable matrixes.</span></span> <span data-ttu-id="37a8a-112">Можно разработать пользовательский элемент отчета времени выполнения, а затем распространить его через приложение, которое удовлетворит потребности разработчиков.</span><span class="sxs-lookup"><span data-stu-id="37a8a-112">A run-time custom report item component can be developed and distributed with an application to fill this need.</span></span>  
  
 <span data-ttu-id="37a8a-113">В дополнение к предоставлению возможностей, которые изначально не поддерживались, некоторые разработчики могут захотеть расширить функциональные возможности, создав альтернативные версии элементов управления, изначально присутствовавших в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37a8a-113">In addition to providing functionality that isn't natively supported, some developers may want to extend existing functionality with alternative versions of controls that are already included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="37a8a-114">В данном сценарии разработчик может предоставить три компонента: компонент времени выполнения, компонент времени разработки и компонент преобразования элемента отчета времени разработки, по запросу преобразующий существующий элемент отчета в пользовательский элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="37a8a-114">In this scenario, a developer could provide three components: a run-time component, a design-time component, and a design-time report item conversion component that converts an existing report item into a custom report item on demand.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37a8a-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="37a8a-115">In This Section</span></span>  
 [<span data-ttu-id="37a8a-116">Архитектура пользовательских элементов отчета</span><span class="sxs-lookup"><span data-stu-id="37a8a-116">Custom Report Item Architecture</span></span>](custom-report-item-architecture.md)  
 <span data-ttu-id="37a8a-117">Описывает компоненты, из которых состоит пользовательский элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="37a8a-117">Describes the components that make up a custom report item.</span></span>  
  
 [<span data-ttu-id="37a8a-118">Требования к реализации пользовательских элементов отчета</span><span class="sxs-lookup"><span data-stu-id="37a8a-118">Custom Report Item Implementation Requirements</span></span>](custom-report-item-implementation-requirements.md)  
 <span data-ttu-id="37a8a-119">Описывает предварительные условия для создания пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="37a8a-119">Describes prerequisites for creating a custom report item.</span></span>  
  
 [<span data-ttu-id="37a8a-120">Создание компонента времени выполнения пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="37a8a-120">Creating a Custom Report Item Run-Time Component</span></span>](creating-a-custom-report-item-run-time-component.md)  
 <span data-ttu-id="37a8a-121">Описывает процесс создания компонента времени выполнения пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="37a8a-121">Describes how to create a custom report item run-time component.</span></span>  
  
 [<span data-ttu-id="37a8a-122">Создание компонента времени разработки пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="37a8a-122">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
 <span data-ttu-id="37a8a-123">Описывает процесс создания компонента времени разработки пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="37a8a-123">Describes how to create a custom report item design-time component.</span></span>  
  
 [<span data-ttu-id="37a8a-124">Руководство. развернуть пользовательский элемент отчета</span><span class="sxs-lookup"><span data-stu-id="37a8a-124">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
 <span data-ttu-id="37a8a-125">Описывает процесс развертывания пользовательского элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="37a8a-125">Describes how to deploy a custom report item.</span></span>  
  
 [<span data-ttu-id="37a8a-126">Библиотеки классов пользовательского элемента отчета</span><span class="sxs-lookup"><span data-stu-id="37a8a-126">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
 <span data-ttu-id="37a8a-127">Описывает классы инфраструктуры пользовательского элемента отчета и управляемые классы-оболочки в пространстве имен `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="37a8a-127">Describes the custom report item infrastructure classes and managed wrapper classes in the `Microsoft.ReportDesigner` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a8a-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="37a8a-128">See Also</span></span>  
 [<span data-ttu-id="37a8a-129">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="37a8a-129">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
