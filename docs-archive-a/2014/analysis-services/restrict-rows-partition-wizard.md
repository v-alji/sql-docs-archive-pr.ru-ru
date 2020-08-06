---
title: Ограничение строк (мастер секционирования) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.typefilterexpression.f1
ms.assetid: eec8da8f-eab4-4ac4-a81d-995c814f88ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b0acc9ab24cfe92877d9abcd86353c85b4f8905
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656654"
---
# <a name="restrict-rows-partition-wizard"></a><span data-ttu-id="162ae-102">Ограничение строк (мастер секционирования)</span><span class="sxs-lookup"><span data-stu-id="162ae-102">Restrict Rows (Partition Wizard)</span></span>
  <span data-ttu-id="162ae-103">Используйте страницу **Ограничение на строки** для ограничения строк, которые будут извлечены из указанной таблицы, затем агрегированы и включены в секцию.</span><span class="sxs-lookup"><span data-stu-id="162ae-103">Use the **Restrict Rows** page to restrict the rows that will be retrieved from the specified table and will be aggregated and included in the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="162ae-104"> Эта страница появляется только в случае, когда пользователем была выбрана сводная таблица на странице **Определение исходных сведений** .</span><span class="sxs-lookup"><span data-stu-id="162ae-104">This page is appears only if you selected a single table in the **Specify Source Information** page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="162ae-105"> Если задана таблицу в **Доступные таблицы** на странице **Определение исходных сведений** , которая используется другой секцией, необходимо задать запрос на странице **Ограничение на строки** или существует риск получить дублирующиеся данные в кубе.</span><span class="sxs-lookup"><span data-stu-id="162ae-105">If you specified a table in **Available Tables** on the **Specify Source Information** page that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="162ae-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="162ae-106">Options</span></span>  
 <span data-ttu-id="162ae-107">**Определите запрос для ограничения на строки**</span><span class="sxs-lookup"><span data-stu-id="162ae-107">**Specify a query to restrict rows**</span></span>  
 <span data-ttu-id="162ae-108">Выберите, чтобы ввести запрос, который ограничивает строки, в поле **Запрос** .</span><span class="sxs-lookup"><span data-stu-id="162ae-108">Select to enter a query that restricts rows into the **Query** box.</span></span>  
  
 <span data-ttu-id="162ae-109">Если поле **Ввести предложение WHERE** пусто, в момент, когда этот параметр выбран, параметр заполняется инструкцией SQL, которая извлекает все столбцы и строки из предварительно выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="162ae-109">If **Supply a WHERE clause** is empty when this option is selected, that option is populated with an SQL statement that retrieves all columns and all rows from the previously selected table.</span></span>  
  
 <span data-ttu-id="162ae-110">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="162ae-110">**Query**</span></span>  
 <span data-ttu-id="162ae-111">Введите или измените инструкцию SQL, используемую во время извлечения строк из таблицы в процессе обработки секции.</span><span class="sxs-lookup"><span data-stu-id="162ae-111">Type or modify the SQL statement used when retrieving rows from the table when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="162ae-112">Указав предложение WHERE, для этой секции можно использовать вложенный набор записей.</span><span class="sxs-lookup"><span data-stu-id="162ae-112">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="162ae-113">Данное действие необходимо во избежание дублирования данных в случае, если несколько параллельных секций функционируют с помощью единственной таблицы фактов.</span><span class="sxs-lookup"><span data-stu-id="162ae-113">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span>  
  
 <span data-ttu-id="162ae-114">**Проверка**</span><span class="sxs-lookup"><span data-stu-id="162ae-114">**Check**</span></span>  
 <span data-ttu-id="162ae-115">Проверка того, что инструкция в поле **Запрос** является корректной инструкцией SQL.</span><span class="sxs-lookup"><span data-stu-id="162ae-115">Verifies that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="162ae-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="162ae-116">See Also</span></span>  
 [<span data-ttu-id="162ae-117">Секции (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="162ae-117">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
