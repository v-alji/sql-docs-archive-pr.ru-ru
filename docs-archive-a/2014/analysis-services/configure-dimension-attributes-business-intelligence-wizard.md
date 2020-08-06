---
title: Настройка атрибутов измерения (мастер бизнес-аналитики) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.selectattributes.f1
ms.assetid: 3d046e63-bcb1-4ab1-9c37-652463fa68c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1d2e9bc83b7a6d83b6d2808b472d67169266ff07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656758"
---
# <a name="configure-dimension-attributes-business-intelligence-wizard"></a><span data-ttu-id="cb3e7-102">Настройка атрибутов измерения (мастер бизнес-аналитики)</span><span class="sxs-lookup"><span data-stu-id="cb3e7-102">Configure Dimension Attributes (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="cb3e7-103">Страница **Настройка атрибутов измерения** используется для сопоставления атрибутов измерения с типами атрибутов, используемыми службами [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] для идентификации атрибутов для измерений счетов.</span><span class="sxs-lookup"><span data-stu-id="cb3e7-103">Use the **Configure Dimension Attributes** page to map the dimension attributes to the attribute types that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to identify attributes for account dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cb3e7-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="cb3e7-104">Options</span></span>  
 <span data-ttu-id="cb3e7-105">**Тип измерения**</span><span class="sxs-lookup"><span data-stu-id="cb3e7-105">**Dimension type**</span></span>  
 <span data-ttu-id="cb3e7-106">Отображает выбранный тип измерения.</span><span class="sxs-lookup"><span data-stu-id="cb3e7-106">Displays the selected dimension type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb3e7-107">Этот параметр недоступен, так как `Type` свойство измерения не может быть изменено на значение, отличное от *Account* для измерений счетов.</span><span class="sxs-lookup"><span data-stu-id="cb3e7-107">This option is not available because the `Type` property of the dimension cannot be changed to a value other than *Account* for account dimensions.</span></span>  
  
 <span data-ttu-id="cb3e7-108">**Атрибуты измерения**</span><span class="sxs-lookup"><span data-stu-id="cb3e7-108">**Dimension attributes**</span></span>  
 <span data-ttu-id="cb3e7-109">Отображает допустимые типы атрибутов, которые можно сопоставить с существующими атрибутами измерений в измерении.</span><span class="sxs-lookup"><span data-stu-id="cb3e7-109">Displays the valid attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="cb3e7-110">**Относится**</span><span class="sxs-lookup"><span data-stu-id="cb3e7-110">**Include**</span></span>  
 <span data-ttu-id="cb3e7-111">Установите флажок для включения соответствующего типа атрибута в измерение.</span><span class="sxs-lookup"><span data-stu-id="cb3e7-111">Select a check box to include the corresponding attribute type in the dimension.</span></span>  
  
 <span data-ttu-id="cb3e7-112">**Тип атрибута**</span><span class="sxs-lookup"><span data-stu-id="cb3e7-112">**Attribute Type**</span></span>  
 <span data-ttu-id="cb3e7-113">Отображает список типов атрибутов, которые можно сопоставить с существующими атрибутами измерений в измерении.</span><span class="sxs-lookup"><span data-stu-id="cb3e7-113">Lists the attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="cb3e7-114">**Атрибут измерения**</span><span class="sxs-lookup"><span data-stu-id="cb3e7-114">**Dimension Attribute**</span></span>  
 <span data-ttu-id="cb3e7-115">Выберите атрибут измерения, который необходимо сопоставить с нужным типом атрибутов.</span><span class="sxs-lookup"><span data-stu-id="cb3e7-115">Select the dimension attribute that should be mapped to the corresponding attribute type.</span></span>  
  
 <span data-ttu-id="cb3e7-116">**Установить полуаддитивные меры в соответствии с типом счета**</span><span class="sxs-lookup"><span data-stu-id="cb3e7-116">**Set measures to be semiadditive based on account type**</span></span>  
 <span data-ttu-id="cb3e7-117">Выберите, чтобы каждая мера, связанная с данным измерением, агрегировалась по типу счета.</span><span class="sxs-lookup"><span data-stu-id="cb3e7-117">Select to change every measure associated with this dimension to be aggregated by account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb3e7-118">Этот параметр не отображается, если мастер бизнес-аналитики был запущен из конструктора измерений, а также при щелчке правой кнопкой мыши по измерению в обозревателе решений в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb3e7-118">This option does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3e7-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="cb3e7-119">See Also</span></span>  
 <span data-ttu-id="cb3e7-120">[Справка F1 мастера бизнес-аналитики](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="cb3e7-120">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="cb3e7-121">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="cb3e7-121">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="cb3e7-122">Конструктор измерений &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="cb3e7-122">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
