---
title: Редактор назначения «Обработка секций» (страница «сопоставления») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.mapping.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: e75b766c-85ba-453e-9576-4a1a34f91ecc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3855b15c7ebf1f6fa95c941931869064d552680e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667794"
---
# <a name="partition-processing-destination-editor-mappings-page"></a><span data-ttu-id="a0c09-102">Редактор назначения «Обработка секций» (страница «Сопоставления»)</span><span class="sxs-lookup"><span data-stu-id="a0c09-102">Partition Processing Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="a0c09-103">Страница **Сопоставления** диалогового окна **Редактор назначения обработки секций** используется для сопоставления входных столбцов со столбцами секционирования.</span><span class="sxs-lookup"><span data-stu-id="a0c09-103">Use the **Mappings** page of the **Partition Processing Destination Editor** dialog box to map input columns to partition columns.</span></span>  
  
 <span data-ttu-id="a0c09-104">Дополнительные сведения о назначении «Обработка секций» см. в разделе [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a0c09-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0c09-105">Описанные здесь задачи не применимы к табличным моделям служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a0c09-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="a0c09-106">Нельзя связать входные столбцы со столбцами секционирования для табличных моделей.</span><span class="sxs-lookup"><span data-stu-id="a0c09-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="a0c09-107">Вместо этого для обработки секции следует использовать задачу выполнения DDL [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a0c09-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a0c09-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0c09-108">Options</span></span>  
 <span data-ttu-id="a0c09-109">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="a0c09-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="a0c09-110">Просмотрите список доступных входных столбцов.</span><span class="sxs-lookup"><span data-stu-id="a0c09-110">View the list of available input columns.</span></span> <span data-ttu-id="a0c09-111">Для сопоставления доступных входных столбцов с целевыми столбцами используется операция перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="a0c09-111">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="a0c09-112">**Доступные целевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="a0c09-112">**Available Destination Columns**</span></span>  
 <span data-ttu-id="a0c09-113">Просмотрите список доступных целевых столбцов.</span><span class="sxs-lookup"><span data-stu-id="a0c09-113">View the list of available destination columns.</span></span> <span data-ttu-id="a0c09-114">Чтобы сопоставить доступные целевые столбцы с входными столбцами, воспользуйтесь операцией перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="a0c09-114">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="a0c09-115">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="a0c09-115">**Input Column**</span></span>  
 <span data-ttu-id="a0c09-116">Просмотрите выбранные входные столбцы из вышеприведенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="a0c09-116">View input columns selected from the table above.</span></span> <span data-ttu-id="a0c09-117">Сопоставления можно изменить с помощью списка **Доступные входные столбцы**.</span><span class="sxs-lookup"><span data-stu-id="a0c09-117">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="a0c09-118">**Целевой столбец**</span><span class="sxs-lookup"><span data-stu-id="a0c09-118">**Destination Column**</span></span>  
 <span data-ttu-id="a0c09-119">Просмотреть все доступные целевые столбцы независимо от того, сопоставлены они с входными столбцами или нет.</span><span class="sxs-lookup"><span data-stu-id="a0c09-119">View each available destination column, whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c09-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0c09-120">See Also</span></span>  
 <span data-ttu-id="a0c09-121">[Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a0c09-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a0c09-122">[Редактор назначения "Обработка секций" &#40;страница "Диспетчер соединений"&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a0c09-122">[Partition Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="a0c09-123">Редактор назначения "Обработка секций" (страница "Дополнительно")</span><span class="sxs-lookup"><span data-stu-id="a0c09-123">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
