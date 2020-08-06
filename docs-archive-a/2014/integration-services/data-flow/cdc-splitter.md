---
title: Разделитель CDC | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsplitter.f1
ms.assetid: 167bc5c6-fa36-439d-987c-b20acd1a77e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45dd16602625b28d2ca7e16f2fa6b0d62294fe81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665464"
---
# <a name="cdc-splitter"></a><span data-ttu-id="70744-102">Разделитель CDC</span><span class="sxs-lookup"><span data-stu-id="70744-102">CDC Splitter</span></span>
  <span data-ttu-id="70744-103">Разделитель CDC разбивает один поток строк изменений из потока исходных данных CDC на различные потоки данных, относящиеся к операциям Insert, Update и Delete.</span><span class="sxs-lookup"><span data-stu-id="70744-103">The CDC splitter splits a single flow of change rows from a CDC source data flow into different data flows for Insert, Update and Delete operations.</span></span> <span data-ttu-id="70744-104">Разбиение потока данных осуществляется на основе обязательного столбца `__$operation` и его стандартных значений в таблицах изменений [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="70744-104">The data flow is split based on the required column `__$operation` and its standard values in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables.</span></span>  
  
|<span data-ttu-id="70744-105">Значение операции</span><span class="sxs-lookup"><span data-stu-id="70744-105">Value of Operation</span></span>|<span data-ttu-id="70744-106">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="70744-106">Output</span></span>|<span data-ttu-id="70744-107">Description</span><span class="sxs-lookup"><span data-stu-id="70744-107">Description</span></span>|  
|------------------------|------------|-----------------|  
|<span data-ttu-id="70744-108">1</span><span class="sxs-lookup"><span data-stu-id="70744-108">1</span></span>|<span data-ttu-id="70744-109">DELETE</span><span class="sxs-lookup"><span data-stu-id="70744-109">Delete</span></span>|<span data-ttu-id="70744-110">Удаленная строка</span><span class="sxs-lookup"><span data-stu-id="70744-110">Deleted Row</span></span>|  
|<span data-ttu-id="70744-111">2</span><span class="sxs-lookup"><span data-stu-id="70744-111">2</span></span>|<span data-ttu-id="70744-112">Вставить</span><span class="sxs-lookup"><span data-stu-id="70744-112">Insert</span></span>|<span data-ttu-id="70744-113">Вставленная строка (недоступно при использовании режима CDC **Суммарные со слиянием** )</span><span class="sxs-lookup"><span data-stu-id="70744-113">Inserted row (not available when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="70744-114">3</span><span class="sxs-lookup"><span data-stu-id="70744-114">3</span></span>|<span data-ttu-id="70744-115">Update</span><span class="sxs-lookup"><span data-stu-id="70744-115">Update</span></span>|<span data-ttu-id="70744-116">Строка перед обновлением (доступно только при использовании режима CDC **Все со старыми значениями** )</span><span class="sxs-lookup"><span data-stu-id="70744-116">Before-update row (available only when using **All with Old Values** CDC mode)</span></span>|  
|<span data-ttu-id="70744-117">4</span><span class="sxs-lookup"><span data-stu-id="70744-117">4</span></span>|<span data-ttu-id="70744-118">Update</span><span class="sxs-lookup"><span data-stu-id="70744-118">Update</span></span>|<span data-ttu-id="70744-119">Строка после обновления (следует за строкой, которая имела место перед обновлением)</span><span class="sxs-lookup"><span data-stu-id="70744-119">After-update row (follows the Before-update)</span></span>|  
|<span data-ttu-id="70744-120">5</span><span class="sxs-lookup"><span data-stu-id="70744-120">5</span></span>|<span data-ttu-id="70744-121">Update</span><span class="sxs-lookup"><span data-stu-id="70744-121">Update</span></span>|<span data-ttu-id="70744-122">Строка слияния (доступно только при использовании режима CDC **Суммарные со слиянием** )</span><span class="sxs-lookup"><span data-stu-id="70744-122">Merge row (available only when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="70744-123">Другие</span><span class="sxs-lookup"><span data-stu-id="70744-123">Other</span></span>|<span data-ttu-id="70744-124">Ошибка</span><span class="sxs-lookup"><span data-stu-id="70744-124">Error</span></span>||  
  
 <span data-ttu-id="70744-125">Разделитель вы можете использовать для подключения к стандартным выводам INSERT, DELETE и UPDATE в целях дальнейшей обработки.</span><span class="sxs-lookup"><span data-stu-id="70744-125">You can use the splitter to connect to pre-defined INSERT, DELETE, and UPDATE outputs for further processing.</span></span>  
  
 <span data-ttu-id="70744-126">Преобразование «Разделитель CDC» имеет один обычный ввод и один вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="70744-126">The CDC Splitter transformation has one regular input and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="70744-127">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="70744-127">Error Handling</span></span>  
 <span data-ttu-id="70744-128">Преобразование «Разделитель CDC» имеет вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="70744-128">The CDC Splitter transformation has an error output.</span></span> <span data-ttu-id="70744-129">Входные строки с недопустимым значением в столбце $operation рассматриваются как ошибочные и обрабатываются в соответствии со свойством ввода **ErrorRowDisposition** .</span><span class="sxs-lookup"><span data-stu-id="70744-129">Input rows with an invalid value of the $operation column are considered erroneous and are handled according to the **ErrorRowDisposition** property of the input.</span></span>  
  
 <span data-ttu-id="70744-130">Вывод ошибок компонента включает следующие выходные столбцы.</span><span class="sxs-lookup"><span data-stu-id="70744-130">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="70744-131">**Код ошибки**. Задан равным 1.</span><span class="sxs-lookup"><span data-stu-id="70744-131">**Error Code**: Set to 1.</span></span>  
  
-   <span data-ttu-id="70744-132">**Столбец с ошибкой**. Входной столбец, вызывающий ошибку (это относится к ошибкам преобразования).</span><span class="sxs-lookup"><span data-stu-id="70744-132">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="70744-133">**Столбцы строки с ошибкой**. Входные столбцы строки, которая вызвала ошибку.</span><span class="sxs-lookup"><span data-stu-id="70744-133">**Error Row Columns**: The input columns of the row that caused the error.</span></span>  
  
## <a name="configuring-the-cdc-splitter"></a><span data-ttu-id="70744-134">Настройка разделителя CDC</span><span class="sxs-lookup"><span data-stu-id="70744-134">Configuring the CDC Splitter</span></span>  
 <span data-ttu-id="70744-135">Какие-либо настраиваемые свойства для разделителя CDC отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="70744-135">There are no configurable properties for the CDC splitter.</span></span>  
  
 <span data-ttu-id="70744-136">Дополнительные сведения об использовании разделителя CDC см. в разделе «Компоненты CDC для служб Microsoft SQL Server Integration Services».</span><span class="sxs-lookup"><span data-stu-id="70744-136">For more information about using the CDC splitter, see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
 <span data-ttu-id="70744-137">Диалоговое окно **Расширенный редактор** содержит свойства, которые могут быть заданы программным путем.</span><span class="sxs-lookup"><span data-stu-id="70744-137">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="70744-138">Открытие диалогового окна **Расширенный редактор** .</span><span class="sxs-lookup"><span data-stu-id="70744-138">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="70744-139">На экране **Поток данных** вашего проекта [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] щелкните правой кнопкой мыши разделитель CDC и выберите элемент **Показать расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="70744-139">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70744-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="70744-140">See Also</span></span>  
 [<span data-ttu-id="70744-141">Выбор направления потока CDC в соответствии с типом изменения</span><span class="sxs-lookup"><span data-stu-id="70744-141">Direct the CDC Stream According to the Type of Change</span></span>](direct-the-cdc-stream-according-to-the-type-of-change.md)  
  
  
