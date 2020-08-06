---
title: Редактор назначения «Обработка измерений» (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.connection.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 44aab631-d62d-4895-8fc7-7f1f3b1b68ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 50ba42292c1f48c9b1cdf2ba00c709dacd2f9675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668449"
---
# <a name="dimension-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="c1414-102">Редактор назначения обработки измерений (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="c1414-102">Dimension Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="c1414-103">Страница **Диспетчер соединений** в диалоговом окне **Редактор назначения обработки измерений** позволяет указать соединение с проектом служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или с экземпляром служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1414-103">Use the **Connection Manager** page of the **Dimension Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c1414-104">Дополнительные сведения о назначении обработки измерений см. в разделе [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c1414-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c1414-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1414-105">Options</span></span>  
 <span data-ttu-id="c1414-106">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="c1414-106">**Connection manager**</span></span>  
 <span data-ttu-id="c1414-107">Выберите из списка существующий диспетчер соединений или нажмите кнопку **Создать** , чтобы создать диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="c1414-107">Select an existing connection manager from the list, or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="c1414-108">**Создать**</span><span class="sxs-lookup"><span data-stu-id="c1414-108">**New**</span></span>  
 <span data-ttu-id="c1414-109">Создайте новое соединение, воспользовавшись диалоговым окном **Добавление диспетчера соединений со службами Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="c1414-109">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="c1414-110">**Список доступных измерений**</span><span class="sxs-lookup"><span data-stu-id="c1414-110">**List of available dimensions**</span></span>  
 <span data-ttu-id="c1414-111">Выберите измерение для обработки.</span><span class="sxs-lookup"><span data-stu-id="c1414-111">Select the dimension to process.</span></span>  
  
 <span data-ttu-id="c1414-112">**Метод обработки**</span><span class="sxs-lookup"><span data-stu-id="c1414-112">**Processing method**</span></span>  
 <span data-ttu-id="c1414-113">Выберите метод обработки, применяемый к выбранному в списке измерению.</span><span class="sxs-lookup"><span data-stu-id="c1414-113">Select the processing method to apply to the dimension selected in the list.</span></span> <span data-ttu-id="c1414-114">Значение этого параметра по умолчанию — **Полная**.</span><span class="sxs-lookup"><span data-stu-id="c1414-114">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="c1414-115">Значение</span><span class="sxs-lookup"><span data-stu-id="c1414-115">Value</span></span>|<span data-ttu-id="c1414-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c1414-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c1414-117">**Добавление (дополнительное)**</span><span class="sxs-lookup"><span data-stu-id="c1414-117">**Add (incremental)**</span></span>|<span data-ttu-id="c1414-118">Выполнить добавочную обработку измерения.</span><span class="sxs-lookup"><span data-stu-id="c1414-118">Perform an incremental processing of the dimension.</span></span>|  
|<span data-ttu-id="c1414-119">**Полное**</span><span class="sxs-lookup"><span data-stu-id="c1414-119">**Full**</span></span>|<span data-ttu-id="c1414-120">Выполнить полную обработку измерения.</span><span class="sxs-lookup"><span data-stu-id="c1414-120">Perform full processing of the dimension.</span></span>|  
|<span data-ttu-id="c1414-121">**Обновление**</span><span class="sxs-lookup"><span data-stu-id="c1414-121">**Update**</span></span>|<span data-ttu-id="c1414-122">Выполнить обновление обработки измерения.</span><span class="sxs-lookup"><span data-stu-id="c1414-122">Perform an update processing of the dimension.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1414-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="c1414-123">See Also</span></span>  
 <span data-ttu-id="c1414-124">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c1414-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c1414-125">[Редактор назначения «Обработка измерений» &#40;«сопоставления»&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="c1414-125">[Dimension Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="c1414-126">Редактор назначения "Обработка измерения" (страница "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="c1414-126">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-advanced-page.md)  
  
  
