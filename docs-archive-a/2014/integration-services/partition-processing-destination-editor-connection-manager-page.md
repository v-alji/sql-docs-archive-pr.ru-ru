---
title: Редактор назначения обработки секций (страница «Диспетчер соединений») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.connection.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 7add6f82-eed1-47fc-a5d7-7b91f3f24d34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a0f79dfcc9c0d98d871a49618f4dabfb8a3bbac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658875"
---
# <a name="partition-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="515e2-102">Редактор назначения обработки секций (страница «Диспетчер соединений»)</span><span class="sxs-lookup"><span data-stu-id="515e2-102">Partition Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="515e2-103">Используйте страницу **Диспетчер соединений** диалогового окна **Редактор назначения обработки секций**, чтобы определить соединение с проектом служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] или экземпляром служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="515e2-103">Use the **Connection Manager** page of the **Partition Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="515e2-104">Дополнительные сведения о назначении «Обработка секций» см. в разделе [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="515e2-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="515e2-105">Описанные здесь задачи не применимы к табличным моделям служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="515e2-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="515e2-106">Нельзя связать входные столбцы со столбцами секционирования для табличных моделей.</span><span class="sxs-lookup"><span data-stu-id="515e2-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="515e2-107">Вместо этого для обработки секции следует использовать задачу выполнения DDL [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="515e2-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="515e2-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="515e2-108">Options</span></span>  
 <span data-ttu-id="515e2-109">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="515e2-109">**Connection manager**</span></span>  
 <span data-ttu-id="515e2-110">Выберите из списка существующий диспетчер соединений или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="515e2-110">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="515e2-111">**Создать**</span><span class="sxs-lookup"><span data-stu-id="515e2-111">**New**</span></span>  
 <span data-ttu-id="515e2-112">Создайте новое соединение, воспользовавшись диалоговым окном **Добавление диспетчера соединений со службами Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="515e2-112">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="515e2-113">**Список доступных секций**</span><span class="sxs-lookup"><span data-stu-id="515e2-113">**List of available partitions**</span></span>  
 <span data-ttu-id="515e2-114">Выберите секцию для обработки.</span><span class="sxs-lookup"><span data-stu-id="515e2-114">Select the partition to process.</span></span>  
  
 <span data-ttu-id="515e2-115">**Метод обработки**</span><span class="sxs-lookup"><span data-stu-id="515e2-115">**Processing method**</span></span>  
 <span data-ttu-id="515e2-116">Выберите метод обработки.</span><span class="sxs-lookup"><span data-stu-id="515e2-116">Select the processing method.</span></span> <span data-ttu-id="515e2-117">Значение этого параметра по умолчанию — **Полная**.</span><span class="sxs-lookup"><span data-stu-id="515e2-117">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="515e2-118">Значение</span><span class="sxs-lookup"><span data-stu-id="515e2-118">Value</span></span>|<span data-ttu-id="515e2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="515e2-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="515e2-120">Добавление (дополнительное)</span><span class="sxs-lookup"><span data-stu-id="515e2-120">Add (incremental)</span></span>|<span data-ttu-id="515e2-121">Выполнить дополнительную обработку секции.</span><span class="sxs-lookup"><span data-stu-id="515e2-121">Perform an incremental processing of the partition.</span></span>|  
|<span data-ttu-id="515e2-122">Полное</span><span class="sxs-lookup"><span data-stu-id="515e2-122">Full</span></span>|<span data-ttu-id="515e2-123">Выполнить полную обработку секции.</span><span class="sxs-lookup"><span data-stu-id="515e2-123">Perform full processing of the partition.</span></span>|  
|<span data-ttu-id="515e2-124">Только данные</span><span class="sxs-lookup"><span data-stu-id="515e2-124">Data only</span></span>|<span data-ttu-id="515e2-125">Выполнить обработку обновления секции.</span><span class="sxs-lookup"><span data-stu-id="515e2-125">Perform an update processing of the partition.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="515e2-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="515e2-126">See Also</span></span>  
 <span data-ttu-id="515e2-127">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="515e2-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="515e2-128">[Редактор назначения "Обработка секций" &#40;"сопоставления"&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="515e2-128">[Partition Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="515e2-129">Редактор назначения "Обработка секций" (страница "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="515e2-129">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
