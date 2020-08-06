---
title: Архитектура пользовательских элементов отчета | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, architecture
ms.assetid: 2a88ea46-c9f8-4dd7-aad1-16de11da4f06
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a053eb55547da9030eebe9036667cca2e14606f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654919"
---
# <a name="custom-report-item-architecture"></a><span data-ttu-id="9f7e1-102">Архитектура пользовательских элементов отчета</span><span class="sxs-lookup"><span data-stu-id="9f7e1-102">Custom Report Item Architecture</span></span>
  <span data-ttu-id="9f7e1-103">Пользовательский элемент отчета является расширением языка определения отчетов (RDL), позволяющим разработчикам добавлять функции, изначально не поддерживаемые в RDL, или расширять функциональные возможности существующих элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-103">A custom report item is an extension to the Report Definition Language (RDL) that allows developers to add functionality that's not natively supported in RDL or extend the functionality of existing controls.</span></span> <span data-ttu-id="9f7e1-104">Существует два основных компонента пользовательского элемента отчета: компонент времени выполнения и компонент времени разработки.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-104">There are two main components to a custom report item: the run-time component and the design-time component.</span></span> <span data-ttu-id="9f7e1-105">Эти компоненты реализованы как сборки платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] и могут быть записаны на любом соответствующем CLS языке.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-105">These components are implemented as [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assemblies, and can be written in any CLS-compliant language.</span></span>  
  
## <a name="the-run-time-component"></a><span data-ttu-id="9f7e1-106">Компонент времени выполнения</span><span class="sxs-lookup"><span data-stu-id="9f7e1-106">The Run-Time Component</span></span>  
 <span data-ttu-id="9f7e1-107">Компонент времени выполнения для пользовательского элемента отчета вызывается обработчиком отчетов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-107">The run-time component for a custom report item is called by the report processor at run time.</span></span> <span data-ttu-id="9f7e1-108">Компонент времени выполнения принимает данные, переданные обработчиком отчетов во время выполнения, обрабатывает эти данные и возвращает изображение, содержащее отображаемый пользовательский элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-108">The run-time component accepts data passed by the report processor at run time, processes this data, and returns an image containing the rendered custom report item.</span></span>  
  
 <span data-ttu-id="9f7e1-109">![Пользовательский элемент отчета (компонент времени выполнения)](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Пользовательский элемент отчета (компонент времени выполнения)")</span><span class="sxs-lookup"><span data-stu-id="9f7e1-109">![Custom report item run-time component](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Custom report item run-time component")</span></span>  
  
## <a name="the-design-time-component"></a><span data-ttu-id="9f7e1-110">Компонент времени разработки</span><span class="sxs-lookup"><span data-stu-id="9f7e1-110">The Design-Time Component</span></span>  
 <span data-ttu-id="9f7e1-111">Компонент времени разработки позволяет определять пользовательский элемент отчета и управлять этим элементом в интерфейсе конструктора отчетов в [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f7e1-111">The design-time component allows the custom report item to be defined and manipulated in the Report Designer interface in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="9f7e1-112">Компонент времени разработки состоит из нескольких вложенных элементов управления, которые контролируют внешний вид и свойства пользовательского элемента отчета в среде проектирования.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-112">The design-time component consists of several sub-controls that control the appearance and properties of the custom report item in the design environment.</span></span>  
  
 <span data-ttu-id="9f7e1-113">![Пользовательский элемент отчета (компонент времени разработки)](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Пользовательский элемент отчета (компонент времени разработки)")</span><span class="sxs-lookup"><span data-stu-id="9f7e1-113">![Custom report item design-time component](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Custom report item design-time component")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f7e1-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f7e1-114">See Also</span></span>  
 <span data-ttu-id="9f7e1-115">[Создание компонента времени выполнения пользовательского элемента отчета](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="9f7e1-115">[Creating a Custom Report Item Run-Time Component](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="9f7e1-116">[Создание компонента времени разработки пользовательского элемента отчета](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="9f7e1-116">[Creating a Custom Report Item Design-Time Component](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span></span>  
 [<span data-ttu-id="9f7e1-117">Руководство. развернуть пользовательский элемент отчета</span><span class="sxs-lookup"><span data-stu-id="9f7e1-117">How to: Deploy a Custom Report Item</span></span>](../custom-report-items/how-to-deploy-a-custom-report-item.md)  
  
  
