---
title: Проверка данных (надстройка MDS для Excel) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 71eda98f-01a4-4fff-8246-be3133782523
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f8e97ff6481996b2e16436e1f78478bd234fe6ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664298"
---
# <a name="validating-data-mds-add-in-for-excel"></a><span data-ttu-id="644b3-102">Проверка данных (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="644b3-102">Validating Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="644b3-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]при публикации данных происходят проверки двух типов:</span><span class="sxs-lookup"><span data-stu-id="644b3-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], when you publish data, two types of validation take place:</span></span>  
  
-   <span data-ttu-id="644b3-104">К данным применяются все определенные бизнес-правила.</span><span class="sxs-lookup"><span data-stu-id="644b3-104">Any defined business rules are applied to the data.</span></span>  
  
-   <span data-ttu-id="644b3-105">Данные проверяются на допустимость в качестве значений атрибута (например, у них должно быть определенные количество знаков или тип данных).</span><span class="sxs-lookup"><span data-stu-id="644b3-105">Data is checked against allowed attribute values (for example, number of characters or type of data).</span></span>  
  
 <span data-ttu-id="644b3-106">В обоих случаях допустимые данные публикуются в репозитории MDS.</span><span class="sxs-lookup"><span data-stu-id="644b3-106">In each case, valid data is published to the MDS repository.</span></span> <span data-ttu-id="644b3-107">Недопустимые данные выделяются, а в столбцах состояния могут отображаться сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="644b3-107">Data that is not valid is highlighted, and details of the error can be shown in status columns.</span></span>  
  
## <a name="when-validation-occurs"></a><span data-ttu-id="644b3-108">Когда осуществляется проверка</span><span class="sxs-lookup"><span data-stu-id="644b3-108">When Validation Occurs</span></span>  
 <span data-ttu-id="644b3-109">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]проверка происходит при публикации новых или измененных данных, а также при применении бизнес-правил вручную.</span><span class="sxs-lookup"><span data-stu-id="644b3-109">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], validation occurs when you publish new or changed data, or when you manually apply business rules.</span></span>  
  
 <span data-ttu-id="644b3-110">Если проверка с использованием бизнес-правил не прошла, данные все равно публикуются в репозитории MDS.</span><span class="sxs-lookup"><span data-stu-id="644b3-110">When business rules fail, the data is still published to the MDS repository.</span></span> <span data-ttu-id="644b3-111">Если входные данные не проходят проверку, они не публикуются в репозитории.</span><span class="sxs-lookup"><span data-stu-id="644b3-111">When input validation fails, the data is not published to the repository.</span></span>  
  
## <a name="validation-statuses"></a><span data-ttu-id="644b3-112">Состояния проверки</span><span class="sxs-lookup"><span data-stu-id="644b3-112">Validation Statuses</span></span>  
 <span data-ttu-id="644b3-113">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]возможны приведенные ниже состояния проверки.</span><span class="sxs-lookup"><span data-stu-id="644b3-113">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following validation statuses are possible.</span></span>  
  
|<span data-ttu-id="644b3-114">Состояние</span><span class="sxs-lookup"><span data-stu-id="644b3-114">Status</span></span>|<span data-ttu-id="644b3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="644b3-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="644b3-116">Ошибка</span><span class="sxs-lookup"><span data-stu-id="644b3-116">Error</span></span>|<span data-ttu-id="644b3-117">Одно или несколько значений в строке не прошли проверку с использованием бизнес-правил, определенных администратором MDS.</span><span class="sxs-lookup"><span data-stu-id="644b3-117">One or more values in the row failed validation against business rules defined by an MDS administrator.</span></span>|  
|<span data-ttu-id="644b3-118">Не проверялось.</span><span class="sxs-lookup"><span data-stu-id="644b3-118">Not Validated</span></span>|<span data-ttu-id="644b3-119">Значения в строке еще не проверялись с использованием бизнес-правил.</span><span class="sxs-lookup"><span data-stu-id="644b3-119">Values in the row have not yet been validated against business rules.</span></span>|  
|<span data-ttu-id="644b3-120">Успешно</span><span class="sxs-lookup"><span data-stu-id="644b3-120">Success</span></span>|<span data-ttu-id="644b3-121">Все значения в строке прошли проверку с использованием бизнес-правил.</span><span class="sxs-lookup"><span data-stu-id="644b3-121">All values in the row have passed validation against business rules.</span></span>|  
  
## <a name="input-statuses"></a><span data-ttu-id="644b3-122">Состояния входных данных</span><span class="sxs-lookup"><span data-stu-id="644b3-122">Input Statuses</span></span>  
 <span data-ttu-id="644b3-123">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]возможны приведенные ниже состояния входных данных.</span><span class="sxs-lookup"><span data-stu-id="644b3-123">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following input statuses are possible</span></span>  
  
|<span data-ttu-id="644b3-124">Состояние</span><span class="sxs-lookup"><span data-stu-id="644b3-124">Status</span></span>|<span data-ttu-id="644b3-125">Описание</span><span class="sxs-lookup"><span data-stu-id="644b3-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="644b3-126">Ошибка</span><span class="sxs-lookup"><span data-stu-id="644b3-126">Error</span></span>|<span data-ttu-id="644b3-127">Одно или несколько значений в строке не соответствуют системным требованиям, таким как длина или тип данных.</span><span class="sxs-lookup"><span data-stu-id="644b3-127">One or more values in the row don't meet system requirements like length or data type.</span></span> <span data-ttu-id="644b3-128">Значение не обновляется в репозитории MDS.</span><span class="sxs-lookup"><span data-stu-id="644b3-128">The value is not updated in the MDS repository.</span></span>|  
|<span data-ttu-id="644b3-129">Новая строка</span><span class="sxs-lookup"><span data-stu-id="644b3-129">New Row</span></span>|<span data-ttu-id="644b3-130">Значения в строке еще не опубликованы в репозитории MDS.</span><span class="sxs-lookup"><span data-stu-id="644b3-130">The values in the row have not yet been published to the MDS repository.</span></span>|  
|<span data-ttu-id="644b3-131">Только для чтения</span><span class="sxs-lookup"><span data-stu-id="644b3-131">Read Only</span></span>|<span data-ttu-id="644b3-132">Вошедший в систему пользователь имеет разрешения «Только для чтения» на одно или несколько значений в строке, и значения нельзя обновить.</span><span class="sxs-lookup"><span data-stu-id="644b3-132">The logged in user has Read-only permissions to one or more values in the row and the value(s) cannot be updated.</span></span>|  
|<span data-ttu-id="644b3-133">Без изменений</span><span class="sxs-lookup"><span data-stu-id="644b3-133">Unchanged</span></span>|<span data-ttu-id="644b3-134">Ни одно значение в строке на листе не было изменено.</span><span class="sxs-lookup"><span data-stu-id="644b3-134">No values in the row have been changed in the worksheet.</span></span> <span data-ttu-id="644b3-135">Это не означает, что значения в хранилище не изменились. Чтобы получить последние данные на листе, в группе **Подключение и загрузка** нажмите кнопку **Загрузить или обновить**.</span><span class="sxs-lookup"><span data-stu-id="644b3-135">This does not mean the values in the repository have not changed; to get the latest data in the sheet, in the **Connect and Load** group, click **Load or Refresh**.</span></span><br /><br /> <span data-ttu-id="644b3-136">Это параметр по умолчанию для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="644b3-136">This is the default setting for each row.</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="644b3-137">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="644b3-137">Related Tasks</span></span>  
  
|<span data-ttu-id="644b3-138">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="644b3-138">Task Description</span></span>|<span data-ttu-id="644b3-139">Раздел</span><span class="sxs-lookup"><span data-stu-id="644b3-139">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="644b3-140">Определяет, какие значения не соответствуют определенным бизнес-правилам.</span><span class="sxs-lookup"><span data-stu-id="644b3-140">Determine which values do not pass the defined business rules.</span></span>|[<span data-ttu-id="644b3-141">Применение бизнес-правил (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="644b3-141">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)|  
|<span data-ttu-id="644b3-142">Чтобы исправить ошибки проверки, просмотрите все транзакции, выполненные для элемента.</span><span class="sxs-lookup"><span data-stu-id="644b3-142">To help correct validation errors, view all transactions that have taken place for a member.</span></span>|[<span data-ttu-id="644b3-143">Просмотр всех заметок или транзакций для элемента (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="644b3-143">View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;</span></span>](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="644b3-144">См. также</span><span class="sxs-lookup"><span data-stu-id="644b3-144">Related Content</span></span>  
  
-   [<span data-ttu-id="644b3-145">Публикация &#40;данных надстройка MDS для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="644b3-145">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
