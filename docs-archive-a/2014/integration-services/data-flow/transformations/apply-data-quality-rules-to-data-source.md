---
title: Применение правил качества данных к источнику данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a965e8f2-004d-4ccc-8523-a185b35b26e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d59e6fb5ffb752b3346d40740e0b841bf574344e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728517"
---
# <a name="apply-data-quality-rules-to-data-source"></a><span data-ttu-id="5c820-102">Применение правил качества данных к источнику данных</span><span class="sxs-lookup"><span data-stu-id="5c820-102">Apply Data Quality Rules to Data Source</span></span>
  <span data-ttu-id="5c820-103">Можно использовать службы Data Quality Services (DQS) для корректировки данных в потоке данных пакета, подключив преобразование DQS Cleansing к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="5c820-103">You can use Data Quality Services (DQS) to correct data in the package data flow by connecting the DQS Cleansing transformation to the data source.</span></span> <span data-ttu-id="5c820-104">Дополнительные сведения о языке DQS см. в разделе [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="5c820-104">For more information about DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span> <span data-ttu-id="5c820-105">Дополнительные сведения об этом преобразовании см. в разделе [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="5c820-105">For more information about the transformation, see [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="5c820-106">При обработке данных с помощью преобразования DQS Cleansing, создается проект служб DQS на сервере служб DQS.</span><span class="sxs-lookup"><span data-stu-id="5c820-106">When you process data with the DQS Cleansing transformation, a data quality project is created on the Data Quality Server.</span></span> <span data-ttu-id="5c820-107">Для управления проектом используется клиент DQS.</span><span class="sxs-lookup"><span data-stu-id="5c820-107">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="5c820-108">Дополнительные сведения см. в статье [Управление проектом служб DQS (открытие, разблокировка, переименование и удаление)](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span><span class="sxs-lookup"><span data-stu-id="5c820-108">For more information, see [Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span></span>  
  
### <a name="to-correct-data-in-the-data-flow"></a><span data-ttu-id="5c820-109">Исправление данных в потоке данных</span><span class="sxs-lookup"><span data-stu-id="5c820-109">To correct data in the data flow</span></span>  
  
1.  <span data-ttu-id="5c820-110">Создайте пакет.</span><span class="sxs-lookup"><span data-stu-id="5c820-110">Create a package.</span></span>  
  
2.  <span data-ttu-id="5c820-111">Добавьте и настройте преобразование «Очистка DQS».</span><span class="sxs-lookup"><span data-stu-id="5c820-111">Add and configure the DQS Cleansing transformation.</span></span> <span data-ttu-id="5c820-112">Дополнительные сведения см. в разделе [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="5c820-112">For more information, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="5c820-113">Соедините преобразование «Очистка DQS» с источником данных.</span><span class="sxs-lookup"><span data-stu-id="5c820-113">Connect the DQS Cleansing transformation to a data source.</span></span>  
  
  
