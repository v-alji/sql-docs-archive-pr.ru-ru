---
title: Включение и отключение диалогового окна "обратная запись" (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitiondesigner.writebackenabledisable.f1
ms.assetid: 2d254393-3f0d-4b70-8b98-87159f9f3639
author: minewiskan
ms.author: owend
ms.openlocfilehash: 54ee4597ee78f45682730bd0e8d7119d204eaf2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669146"
---
# <a name="enable-disable-writeback-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="4088b-102">Диалоговое окно «Включение-отключение обратной записи» (Analysis Services-многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="4088b-102">Enable-Disable Writeback Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="4088b-103">Диалоговое окно **Включение или отключение обратной записи** включает или отключает обратную запись для группы мер в кубе.</span><span class="sxs-lookup"><span data-stu-id="4088b-103">The **Enable/Disable Writeback** dialog box enables or disables writeback for a measure group in a cube.</span></span> <span data-ttu-id="4088b-104">Включение обратной записи в группе мер определяет секцию обратной записи и создает таблицу обратной записи для этой группы мер.</span><span class="sxs-lookup"><span data-stu-id="4088b-104">Enabling writeback on a measure group defines a writeback partition and creates a writeback table for that measure group.</span></span> <span data-ttu-id="4088b-105">Отключение обратной записи в группе мер удаляет секцию обратной записи, но сохраняет таблицу обратной записи, чтобы избежать непредвиденной потери данных.</span><span class="sxs-lookup"><span data-stu-id="4088b-105">Disabling writeback on a measure group removes the writeback partition but does not delete the writeback table, to avoid unanticipated data loss.</span></span> <span data-ttu-id="4088b-106">Диалоговое окно **Включение/отключение обратной записи** отображается следующими способами:</span><span class="sxs-lookup"><span data-stu-id="4088b-106">The **Enable/Disable Writeback** dialog box is displayed by:</span></span>  
  
-   <span data-ttu-id="4088b-107">Нажмите **Настройки обратной записи** на панели **Группы мер** вкладки **Секции** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="4088b-107">Clicking **Writeback Settings** in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="4088b-108">Щелкните правой кнопкой мыши секцию в сетке **Секции** панели **Группы мер** вкладки **Секции** конструктора кубов и выберите пункт **Настройки обратной записи** из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="4088b-108">Right-clicking a partition in the **Partitions** grid in the **Measure Groups** pane on the **Partitions** tab in Cube Designer and selecting **Writeback Settings** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4088b-109">Варианты</span><span class="sxs-lookup"><span data-stu-id="4088b-109">Options</span></span>  
 <span data-ttu-id="4088b-110">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="4088b-110">**Table name**</span></span>  
 <span data-ttu-id="4088b-111">Введите имя таблицы обратной записи, создаваемой для выбранной секции.</span><span class="sxs-lookup"><span data-stu-id="4088b-111">Type the name of the writeback table to create for the selected partition.</span></span> <span data-ttu-id="4088b-112">В таблицу обратной записи сохраняются изменения в группе мер из клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="4088b-112">The writeback table stores the changes made to the measure group from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4088b-113">Если обратная запись не включена, этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="4088b-113">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="4088b-114">**Источник данных**</span><span class="sxs-lookup"><span data-stu-id="4088b-114">**Data source**</span></span>  
 <span data-ttu-id="4088b-115">Выберите источник данных, содержащий таблицу обратной записи.</span><span class="sxs-lookup"><span data-stu-id="4088b-115">Select the data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4088b-116">Если обратная запись не включена, этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="4088b-116">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="4088b-117">**Создать**</span><span class="sxs-lookup"><span data-stu-id="4088b-117">**New**</span></span>  
 <span data-ttu-id="4088b-118">Нажмите, чтобы открыть диалоговое окно **Диспетчер соединений** и задать новый источник данных, содержащий таблицу обратной записи.</span><span class="sxs-lookup"><span data-stu-id="4088b-118">Click to display the **Connection Manager** dialog box and define a new data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4088b-119">Если обратная запись не включена, этот параметр недоступен.</span><span class="sxs-lookup"><span data-stu-id="4088b-119">This option is disabled if writeback is not enabled.</span></span>  
  
  
