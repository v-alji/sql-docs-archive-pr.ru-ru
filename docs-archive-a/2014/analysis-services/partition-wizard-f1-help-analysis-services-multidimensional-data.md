---
title: Справка F1 мастера секционирования (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Partition Wizard
ms.assetid: 3b6d7053-aeef-4d9e-af70-f5b40256e859
author: minewiskan
ms.author: owend
ms.openlocfilehash: fa8c0e94c2b18ffbd1228752bd7cb4ad4f684acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657358"
---
# <a name="partition-wizard-f1-help-analysis-services---multidimensional-data"></a><span data-ttu-id="60e32-102">Справка F1 мастера секционирования (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="60e32-102">Partition Wizard F1 Help (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="60e32-103">Мастер секционирования можно использовать для определения секций для группы мер в кубе.</span><span class="sxs-lookup"><span data-stu-id="60e32-103">You can use the Partition Wizard to define partitions for a measure group in a cube.</span></span> <span data-ttu-id="60e32-104">По умолчанию для каждой группы мер в кубе определяется одна секция.</span><span class="sxs-lookup"><span data-stu-id="60e32-104">By default, a single partition is defined for each measure group in a cube.</span></span> <span data-ttu-id="60e32-105">Для крупных секций, однако, могут снизиться меры доступа и производительности обработки.</span><span class="sxs-lookup"><span data-stu-id="60e32-105">Access and processing performance, however, can degrade for large partitions.</span></span> <span data-ttu-id="60e32-106">Создавая несколько секций, каждая из которых содержит часть данных для группы мер, можно улучшить показатели доступа и производительности обработки для данной группы мер.</span><span class="sxs-lookup"><span data-stu-id="60e32-106">By creating multiple partitions, each containing a portion of the data for a measure group, you can improve the access and processing performance for that measure group.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="60e32-107">Можно создать секции, которые будут содержать неверные данные, включив повторяющиеся строки на страницах **Определение исходных сведений** или **Ограничение на строки** .</span><span class="sxs-lookup"><span data-stu-id="60e32-107">It is possible to create partitions that may contain incorrect data by including duplicate rows in the **Specify Source Information** or **Restrict Rows** pages.</span></span>  
  
 <span data-ttu-id="60e32-108">Мастер секционирования проводит пользователя через следующую последовательность шагов.</span><span class="sxs-lookup"><span data-stu-id="60e32-108">The Partition Wizard guides you through the following steps:</span></span>  
  
-   <span data-ttu-id="60e32-109">Выбор представления источников данных для секции.</span><span class="sxs-lookup"><span data-stu-id="60e32-109">Selecting the data source view for the partition.</span></span>  
  
-   <span data-ttu-id="60e32-110">Создание фильтра для записей, включенных в секцию.</span><span class="sxs-lookup"><span data-stu-id="60e32-110">Creating a filter for the records included in the partition.</span></span>  
  
-   <span data-ttu-id="60e32-111">Настройка расположения обработки и хранения.</span><span class="sxs-lookup"><span data-stu-id="60e32-111">Setting the processing and storage locations.</span></span>  
  
-   <span data-ttu-id="60e32-112">Присвоение имени и сохранение секции.</span><span class="sxs-lookup"><span data-stu-id="60e32-112">Naming and saving the partition.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60e32-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="60e32-113">In This Section</span></span>  
  
-   [<span data-ttu-id="60e32-114">Мастер определения источника &#40;секций&#41;</span><span class="sxs-lookup"><span data-stu-id="60e32-114">Specify Source Information &#40;Partition Wizard&#41;</span></span>](specify-source-information-partition-wizard.md)  
  
-   [<span data-ttu-id="60e32-115">Мастер секционирования ограничений строк &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="60e32-115">Restrict Rows &#40;Partition Wizard&#41;</span></span>](restrict-rows-partition-wizard.md)  
  
-   [<span data-ttu-id="60e32-116">Мастер создания секций и места хранения &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="60e32-116">Processing and Storage Locations &#40;Partition Wizard&#41;</span></span>](processing-and-storage-locations-partition-wizard.md)  
  
-   [<span data-ttu-id="60e32-117">Завершение мастера создания разделов &#40;мастера&#41;</span><span class="sxs-lookup"><span data-stu-id="60e32-117">Completing the Wizard &#40;Partition Wizard&#41;</span></span>](completing-the-wizard-partition-wizard.md)  
  
-   [<span data-ttu-id="60e32-118">Диалоговое окно «Выбор удаленной папки» &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="60e32-118">Browse for Remote Folder Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browse-for-remote-folder-dialog-box-analysis-services-multidimensional-data.md)  
  
## <a name="see-also"></a><span data-ttu-id="60e32-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="60e32-119">See Also</span></span>  
 [<span data-ttu-id="60e32-120">Секции (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="60e32-120">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
