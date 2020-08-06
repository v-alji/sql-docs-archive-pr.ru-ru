---
title: Селективные XML-индексы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 598ecdcd-084b-4032-81b2-eed6ae9f5d44
author: rothja
ms.author: jroth
ms.openlocfilehash: 37dd72c5de2892672dc9f63066075ab5e770d758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668672"
---
# <a name="selective-xml-indexes-sxi"></a><span data-ttu-id="b548e-102">Выборочный XML-индекс (SXI)</span><span class="sxs-lookup"><span data-stu-id="b548e-102">Selective XML Indexes (SXI)</span></span>
  <span data-ttu-id="b548e-103">Селективные XML-индексы — это еще один тип XML-индексов, доступный наряду с обычными XML-индексами.</span><span class="sxs-lookup"><span data-stu-id="b548e-103">Selective XML indexes are another type of XML index that is available to you in addition to ordinary XML indexes.</span></span> <span data-ttu-id="b548e-104">Селективный XML-индекс используется в следующих целях.</span><span class="sxs-lookup"><span data-stu-id="b548e-104">The goals of the selective XML index feature are the following:</span></span>  
  
-   <span data-ttu-id="b548e-105">Для повышения производительности запросов к XML-данным, хранящимся в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b548e-105">To improve the performance of queries over XML data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b548e-106">Для поддержки более быстрого индексирования больших объемов XML-данных.</span><span class="sxs-lookup"><span data-stu-id="b548e-106">To support faster indexing of large XML data workloads.</span></span>  
  
-   <span data-ttu-id="b548e-107">Для повышения масштабируемости путем уменьшения затрат на хранение XML-индексов.</span><span class="sxs-lookup"><span data-stu-id="b548e-107">To improve scalability by reducing the storage costs of XML indexes.</span></span>  
  
 <span data-ttu-id="b548e-108">Основным ограничением обычных XML-индексов является то, что они индексируют весь XML-документ.</span><span class="sxs-lookup"><span data-stu-id="b548e-108">The main limitation with ordinary XML indexes is that they index the entire XML document.</span></span> <span data-ttu-id="b548e-109">Это ограничение влечет за собой несколько значительных недостатков, например снижение производительности запросов и увеличенные затрат на обслуживание, в основном относящихся к затратам на хранение индекса.</span><span class="sxs-lookup"><span data-stu-id="b548e-109">This leads to several significant drawbacks, such as decreased query performance and increased index maintenance cost, mostly related to the storage costs of the index.</span></span>  
  
 <span data-ttu-id="b548e-110">Функция селективного XML-индекса позволяет повышать только некоторые пути из XML-документов в индекс.</span><span class="sxs-lookup"><span data-stu-id="b548e-110">The selective XML index feature lets you promote only certain paths from the XML documents to index.</span></span> <span data-ttu-id="b548e-111">Во время создания индекса производится вычисление этих путей, а узлы, на которые они указывают, разделяются и сохраняются в реляционной таблице в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b548e-111">At index creation time, these paths are evaluated, and the nodes that they point to are shredded and stored inside a relational table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b548e-112">Эта функция использует эффективный алгоритм сопоставления, разработанный [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research в сотрудничестве с группой разработчиков [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b548e-112">This feature uses an efficient mapping algorithm developed by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research in collaboration with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product team.</span></span> <span data-ttu-id="b548e-113">Этот алгоритм сопоставляет узлы XML с одной реляционной таблицей и достигает исключительной производительности при использовании небольшого пространства для хранения.</span><span class="sxs-lookup"><span data-stu-id="b548e-113">This algorithm maps the XML nodes to a single relational table, and achieves exceptional performance while requiring only modest storage space.</span></span>  
  
 <span data-ttu-id="b548e-114">Функция селективного XML-индекса также поддерживает вторичные селективные XML-индексы для узлов, которые были индексированы селективным XML-индексом.</span><span class="sxs-lookup"><span data-stu-id="b548e-114">The selective XML index feature also supports secondary selective XML indexes over nodes that have been indexed by a selective XML index.</span></span> <span data-ttu-id="b548e-115">Эти вторичные селективные индексы являются эффективными и еще более повышают производительность запросов.</span><span class="sxs-lookup"><span data-stu-id="b548e-115">These secondary selective indexes are efficient and further improve the performance of queries.</span></span>  
  
##  <a name="benefits-of-selective-xml-indexes"></a><a name="benefits"></a> <span data-ttu-id="b548e-116">Преимущества селективных XML-индексов</span><span class="sxs-lookup"><span data-stu-id="b548e-116">Benefits of Selective XML Indexes</span></span>  
 <span data-ttu-id="b548e-117">Селективные XML-индексы дают следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="b548e-117">Selective XML indexes provide the following benefits:</span></span>  
  
1.  <span data-ttu-id="b548e-118">Значительное улучшение производительности запросов к типу данных XML для типичных нагрузок по запросам.</span><span class="sxs-lookup"><span data-stu-id="b548e-118">Greatly improved query performance over the XML data type for typical query loads.</span></span>  
  
2.  <span data-ttu-id="b548e-119">Сниженные требования к хранилищу по сравнению с обычными XML-индексами.</span><span class="sxs-lookup"><span data-stu-id="b548e-119">Reduced storage requirements compared to ordinary XML indexes.</span></span>  
  
3.  <span data-ttu-id="b548e-120">Сниженные расходы на обслуживание индекса по сравнению с обычными XML-индексами.</span><span class="sxs-lookup"><span data-stu-id="b548e-120">Reduced index maintenance costs compared to ordinary XML indexes.</span></span>  
  
4.  <span data-ttu-id="b548e-121">Нет необходимости обновлять приложения для получения пользы от селективных XML-индексов.</span><span class="sxs-lookup"><span data-stu-id="b548e-121">No need to update applications to benefit from selective XML indexes.</span></span>  
  

  
##  <a name="selective-xml-indexes-and-primary-xml-indexes"></a><a name="compare"></a> <span data-ttu-id="b548e-122">Селективные XML-индексы и первичные XML-индексы</span><span class="sxs-lookup"><span data-stu-id="b548e-122">Selective XML Indexes and Primary XML Indexes</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b548e-123">Создание селективного XML-индекса вместо обычного XML-индекса в большинстве случаев приводит к повышению производительности и более эффективному использованию хранилища.</span><span class="sxs-lookup"><span data-stu-id="b548e-123">Create a selective XML index instead of an ordinary XML index in most cases for better performance and more efficient storage.</span></span>  
  
 <span data-ttu-id="b548e-124">Однако селективный XML-индекс не рекомендуется использовать при наличии следующих условий.</span><span class="sxs-lookup"><span data-stu-id="b548e-124">However, a selective XML index is not recommended when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="b548e-125">Необходимо сопоставить большое число путей узлов.</span><span class="sxs-lookup"><span data-stu-id="b548e-125">You map a large number of node paths.</span></span>  
  
-   <span data-ttu-id="b548e-126">Поддерживаются запросы неизвестных элементов или элементов в неизвестном месте структуры документа.</span><span class="sxs-lookup"><span data-stu-id="b548e-126">You support queries for unknown elements or elements in an unknown location in the document structure.</span></span>  
  

  
##  <a name="simple-example-of-a-selective-xml-index"></a><a name="example"></a> <span data-ttu-id="b548e-127">Простой пример селективного XML-индекса</span><span class="sxs-lookup"><span data-stu-id="b548e-127">Simple Example of a Selective XML Index</span></span>  
 <span data-ttu-id="b548e-128">Рассмотрим следующий фрагмент XML как XML-документ в таблице из приблизительно 500 000 строк.</span><span class="sxs-lookup"><span data-stu-id="b548e-128">Consider the following XML fragment as an XML document in a table of approximately 500,000 rows:</span></span>  
  
```xml  
<book>  
    <created>2004-03-01</created>   
    <authors>Various</authors>  
    <subjects>  
        <subject>English wit and humor -- Periodicals</subject>  
        <subject>AP</subject>   
    </subjects>  
    <title>Punch, or the London Charivari, Volume 156, April 2, 1919</title>  
    <id>etext11617</id>  
</book>  
```  
  
 <span data-ttu-id="b548e-129">Создание первичного XML-индекса для такого большого количества строк этой простой схемы занимает длительное время.</span><span class="sxs-lookup"><span data-stu-id="b548e-129">Creating a primary XML index over so many rows of this simple schema takes a long time.</span></span> <span data-ttu-id="b548e-130">Создание запросов к этим данным также является неэффективным, поскольку первичный XML-индекс не поддерживает селективное индексирование.</span><span class="sxs-lookup"><span data-stu-id="b548e-130">Querying this data also suffers from the fact that a primary XML index does not support selective indexing.</span></span>  
  
 <span data-ttu-id="b548e-131">Если запросы к данным выполняются только по путям `/book/title` и `/book/subjects` , вы можете создать следующий селективный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="b548e-131">If you only need to query this data over the `/book/title` path and the `/book/subjects` path, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX SXI_index  
ON Tbl(xmlcol)  
FOR   
(  
    pathTitle = '/book/title/text()' AS XQUERY 'xs:string',   
    pathAuthors = '/book/authors' AS XQUERY 'node()',  
    pathId = '/book/id' AS SQL NVARCHAR(100)  
)  
```  
  
 <span data-ttu-id="b548e-132">Предыдущая инструкция — это хороший пример синтаксиса CREATE, используемого при создании селективного XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="b548e-132">The preceding statement is a good example of the CREATE syntax that you use when you create a selective XML index.</span></span> <span data-ttu-id="b548e-133">В инструкции CREATE указывается имя индекса и определяется таблица и XML-столбец для индексирования.</span><span class="sxs-lookup"><span data-stu-id="b548e-133">In the CREATE statement, first you provide a name for the index and identify the table and the XML column to index.</span></span> <span data-ttu-id="b548e-134">Затем передаются пути для индексирования.</span><span class="sxs-lookup"><span data-stu-id="b548e-134">Then you provide the paths to index.</span></span> <span data-ttu-id="b548e-135">Путь состоит из 3 частей:</span><span class="sxs-lookup"><span data-stu-id="b548e-135">A path has three parts:</span></span>  
  
1.  <span data-ttu-id="b548e-136">имя, однозначно определяющее путь;</span><span class="sxs-lookup"><span data-stu-id="b548e-136">A name that uniquely identifies the path.</span></span>  
  
2.  <span data-ttu-id="b548e-137">выражение XQuery, описывающее путь;</span><span class="sxs-lookup"><span data-stu-id="b548e-137">An XQuery expression that describes the path.</span></span>  
  
3.  <span data-ttu-id="b548e-138">необязательные указания по оптимизации.</span><span class="sxs-lookup"><span data-stu-id="b548e-138">Optional optimization hints.</span></span>  
  
 <span data-ttu-id="b548e-139">Дополнительные сведения об этих элементах см. в разделе [Связанные задачи](#reltasks).</span><span class="sxs-lookup"><span data-stu-id="b548e-139">For more information about these elements, see [Related Tasks](#reltasks).</span></span>  
  

  
## <a name="supported-features-prerequisites-and-limitations"></a><span data-ttu-id="b548e-140">Поддерживаемые функции, предварительные требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="b548e-140">Supported Features, Prerequisites, and Limitations</span></span>  
  
###  <a name="supported-xml-features"></a><a name="features"></a> <span data-ttu-id="b548e-141">Поддерживаемые функции XML</span><span class="sxs-lookup"><span data-stu-id="b548e-141">Supported XML Features</span></span>  
 <span data-ttu-id="b548e-142">Селективные XML-индексы поддерживают XQuery, поддерживаемые [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в методах exist(), value() и nodes().</span><span class="sxs-lookup"><span data-stu-id="b548e-142">Selective XML indexes support the XQuery supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inside the exist(), value() and nodes() methods.</span></span>  
  
-   <span data-ttu-id="b548e-143">Для методов exist(), value() и nodes() селективные XML-индексы содержат достаточно данных для преобразования всего выражения.</span><span class="sxs-lookup"><span data-stu-id="b548e-143">For the exist(), value() and nodes() methods, selective XML indexes contain enough information to transform the entire expression.</span></span>  
  
-   <span data-ttu-id="b548e-144">Для методов query() и modify() селективные XML-индексы можно использовать только для фильтрации узлов.</span><span class="sxs-lookup"><span data-stu-id="b548e-144">For the query() and modify() methods, selective XML indexes may be used for node filtering only.</span></span>  
  
-   <span data-ttu-id="b548e-145">Для метода query() селективные XML-индексы не используются для получения результатов.</span><span class="sxs-lookup"><span data-stu-id="b548e-145">For the query() method, selective XML indexes are not used to retrieve results.</span></span>  
  
-   <span data-ttu-id="b548e-146">Для метода modify() селективные XML-индексы не используются для обновления XML-документов.</span><span class="sxs-lookup"><span data-stu-id="b548e-146">For the modify() method, selective XML indexes are not used to update XML documents.</span></span>  
  

  
###  <a name="unsupported-xml-features"></a><a name="unsupported"></a> <span data-ttu-id="b548e-147">Неподдерживаемые функции XML</span><span class="sxs-lookup"><span data-stu-id="b548e-147">Unsupported XML Features</span></span>  
 <span data-ttu-id="b548e-148">Селективные XML-индексы не поддерживают следующие функции, поддерживаемые в реализации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML:</span><span class="sxs-lookup"><span data-stu-id="b548e-148">Selective XML indexes do not support the following features that are supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implementation of XML:</span></span>  
  
-   <span data-ttu-id="b548e-149">Индексирование узлов со сложными типами XS: типами объединений, типами последовательностей и типами списков.</span><span class="sxs-lookup"><span data-stu-id="b548e-149">Indexing of nodes with complex XS types: union types, sequence types, and list types.</span></span>  
  
-   <span data-ttu-id="b548e-150">Индексирование узлов с двоичными типами XS: например, base64Binary и hexBinary.</span><span class="sxs-lookup"><span data-stu-id="b548e-150">Indexing of nodes with binary XS types: for example, base64Binary and hexBinary.</span></span>  
  
-   <span data-ttu-id="b548e-151">Указание узлов для индексирования с выражениями XPath, которые содержат подстановочный знак `*` в конце. Например, `/a/b/c/*`, `/a//b/*` или `/a/b/*:c`.</span><span class="sxs-lookup"><span data-stu-id="b548e-151">Specifying the nodes to index with XPath expressions that contain the wildcard character `*` at the end: For example,  `/a/b/c/*`, `/a//b/*`, or `/a/b/*:c`.</span></span>  
  
-   <span data-ttu-id="b548e-152">Индексирование любых осей, отличных от осей дочерних элементов, атрибутов или объектов-потомков.</span><span class="sxs-lookup"><span data-stu-id="b548e-152">Indexing any axis other than child, attribute, or descendant.</span></span> <span data-ttu-id="b548e-153">Вариант `//<step>` допускается как исключение.</span><span class="sxs-lookup"><span data-stu-id="b548e-153">The `//<step>` case is allowed as a special case.</span></span>  
  
-   <span data-ttu-id="b548e-154">Индексирование инструкций и комментариев по обработке XML.</span><span class="sxs-lookup"><span data-stu-id="b548e-154">Indexing of XML processing instructions and comments.</span></span>  
  
-   <span data-ttu-id="b548e-155">Указание и получение идентификатора для узла с помощью функции id().</span><span class="sxs-lookup"><span data-stu-id="b548e-155">Specifying and retrieving the identifier for a node by using the id() function.</span></span>  
  

  
###  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="b548e-156">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b548e-156">Prerequisites</span></span>  
 <span data-ttu-id="b548e-157">Следующие предварительные условия должны существовать до создания селективного XML-индекса для XML-столбца в пользовательской таблице.</span><span class="sxs-lookup"><span data-stu-id="b548e-157">The following prerequisites must exist before you can create a selective XML index over an XML column in a user table:</span></span>  
  
-   <span data-ttu-id="b548e-158">Кластеризованный индекс должен существовать для первичного ключа таблицы пользователя.</span><span class="sxs-lookup"><span data-stu-id="b548e-158">A clustered index must exist on the primary key of the user table.</span></span>  
  
-   <span data-ttu-id="b548e-159">Первичный ключ пользовательской таблицы ограничивается размером в 128 байт при использовании с селективными XML-индексами.</span><span class="sxs-lookup"><span data-stu-id="b548e-159">The primary key of the user table is limited to a size of 128 bytes when used with selective XML indexes.</span></span>  
  
-   <span data-ttu-id="b548e-160">Ключ кластеризации пользовательской таблицы имеет ограничение в 15 столбцов при использовании с селективными XML-индексами.</span><span class="sxs-lookup"><span data-stu-id="b548e-160">The clustering key of the user table is limited to 15 columns when used with selective XML indexes.</span></span>  
  

  
###  <a name="limitations"></a><a name="limits"></a> <span data-ttu-id="b548e-161">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b548e-161">Limitations</span></span>  
 <span data-ttu-id="b548e-162">**Общие требования и ограничения**</span><span class="sxs-lookup"><span data-stu-id="b548e-162">**General requirements and limitations**</span></span>  
  
-   <span data-ttu-id="b548e-163">Каждый селективный XML-индекс может быть создан только для одного XML-столбца.</span><span class="sxs-lookup"><span data-stu-id="b548e-163">Each selective XML index can only be created on a single XML column.</span></span>  
  
-   <span data-ttu-id="b548e-164">Невозможно создать селективный XML-индекс для столбца, имеющего тип, отличный от XML.</span><span class="sxs-lookup"><span data-stu-id="b548e-164">You cannot create a selective XML index on a non-XML column.</span></span>  
  
-   <span data-ttu-id="b548e-165">Каждый XML-столбец в таблице может иметь только один селективный XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="b548e-165">Each XML column in a table can have only one selective XML index.</span></span>  
  
-   <span data-ttu-id="b548e-166">Каждая таблица может иметь до 249 селективных XML-индексов.</span><span class="sxs-lookup"><span data-stu-id="b548e-166">Each table can have up to 249 selective XML indexes.</span></span>  
  
 <span data-ttu-id="b548e-167">**Ограничения для поддерживаемых объектов**</span><span class="sxs-lookup"><span data-stu-id="b548e-167">**Limitations on supported objects**</span></span>  
  
 <span data-ttu-id="b548e-168">Нельзя создавать селективные XML-индексы для следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="b548e-168">You cannot create selective XML indexes on the following objects:</span></span>  
  
1.  <span data-ttu-id="b548e-169">XML-столбцы в представлении.</span><span class="sxs-lookup"><span data-stu-id="b548e-169">XML columns in a view.</span></span>  
  
2.  <span data-ttu-id="b548e-170">Возвращающая табличное значение переменная с XML-столбцами.</span><span class="sxs-lookup"><span data-stu-id="b548e-170">Table-valued variable with XML columns.</span></span>  
  
3.  <span data-ttu-id="b548e-171">Переменные типа XML.</span><span class="sxs-lookup"><span data-stu-id="b548e-171">XML type variables.</span></span>  
  
4.  <span data-ttu-id="b548e-172">Вычисляемые XML-столбцы.</span><span class="sxs-lookup"><span data-stu-id="b548e-172">Computed XML columns.</span></span>  
  
5.  <span data-ttu-id="b548e-173">XML-столбец с глубиной более чем в 128 вложенных узлов.</span><span class="sxs-lookup"><span data-stu-id="b548e-173">XML columns with a depth of more than 128 nested nodes.</span></span>  
  
 <span data-ttu-id="b548e-174">**Ограничения, относящиеся к хранению**</span><span class="sxs-lookup"><span data-stu-id="b548e-174">**Limitations related to storage**</span></span>  
  
 <span data-ttu-id="b548e-175">Существует ограниченное предельное число узлов из XML-документа, которое можно добавить в индекс.</span><span class="sxs-lookup"><span data-stu-id="b548e-175">There is a finite limit on the number of nodes from the XML document that can be added to the index.</span></span> <span data-ttu-id="b548e-176">Селективный XML-индекс сопоставляет XML-документы с одной реляционной таблицей.</span><span class="sxs-lookup"><span data-stu-id="b548e-176">A selective XML index maps XML documents to a single relational table.</span></span> <span data-ttu-id="b548e-177">Поэтому он не может содержать более 1024 столбцов со значениями, отличными от NULL, в любой заданной строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="b548e-177">Therefore it cannot have more than 1024 non-null columns in any given row of the table.</span></span> <span data-ttu-id="b548e-178">Кроме того, многие из ограничений для разреженных столбцов также применяются к селективным XML-индексам, поскольку индексы используют разреженные столбцы для хранения.</span><span class="sxs-lookup"><span data-stu-id="b548e-178">Furthermore, many of the limitations of sparse columns also apply to selective XML indexes, because the indexes use sparse columns for storage.</span></span>  
  
 <span data-ttu-id="b548e-179">Максимальное количество столбцов со значениями, отличными от NULL, поддерживаемое в любой заданной строке, зависит от размера данных в столбцах.</span><span class="sxs-lookup"><span data-stu-id="b548e-179">The maximum number of non-null columns supported in any given row depends on the size of the data in the columns:</span></span>  
  
-   <span data-ttu-id="b548e-180">В лучшем случае поддерживается 1024 столбца со значениями, отличными от NULL, если все столбцы имеют тип **bit**.</span><span class="sxs-lookup"><span data-stu-id="b548e-180">In the best case, 1024 non-null columns are supported when all columns are of type **bit**.</span></span>  
  
-   <span data-ttu-id="b548e-181">В худшем случае поддерживается только 236 столбцов со значениями, отличными от NULL, если все столбцы являются большими объектами типа **varchar**.</span><span class="sxs-lookup"><span data-stu-id="b548e-181">In the worst case, only 236 non-null columns are supported when all columns are large objects of type **varchar**.</span></span>  
  
 <span data-ttu-id="b548e-182">Селективные XML-индексы внутренним образом используют от одного до четырех столбцов для каждого индексированного пути узла.</span><span class="sxs-lookup"><span data-stu-id="b548e-182">Selective XML indexes use from one to four columns internally for every node path that is indexed.</span></span> <span data-ttu-id="b548e-183">Общее количество доступных для индексации узлов лежит в диапазоне от 60 до нескольких сотен узлов и зависит от фактического размера данных в индексированных путях.</span><span class="sxs-lookup"><span data-stu-id="b548e-183">The total number of nodes that can be indexed ranges from 60 to several hundred nodes, depending on the actual size of the data in the indexed paths.</span></span>  
  
-   <span data-ttu-id="b548e-184">В худшем случае, если некоторые или все узлы сопоставлены с помощью `//` в определении пути узла, максимальное количество индексируемых узлов равно 60.</span><span class="sxs-lookup"><span data-stu-id="b548e-184">In the worst case, when some or all nodes are mapped using `//` in the node path definition, the maximum number of indexed nodes is 60.</span></span>  
  
-   <span data-ttu-id="b548e-185">В лучшем случае, если узлы сопоставлены без использования `//` в определении пути узла, максимальное количество индексируемых узлов равно 200.</span><span class="sxs-lookup"><span data-stu-id="b548e-185">In the best case, when nodes are mapped without using `//` in the node path definition, the maximum number of indexed nodes is 200.</span></span>  
  
 <span data-ttu-id="b548e-186">**Селективные XML-индексы перестраиваются при создании и изменении индекса при помощи инструкций CREATE и ALTER.**</span><span class="sxs-lookup"><span data-stu-id="b548e-186">**Selective XML indexes are rebuilt when you CREATE or ALTER the index.**</span></span>  
  
 <span data-ttu-id="b548e-187">При создании или изменении селективного XML-индекса при помощи инструкций CREATE и ALTER оно перестраивается в однопотоковом режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="b548e-187">When you CREATE or ALTER a selective XML index, it is rebuilt in a single-threaded, offline mode.</span></span> <span data-ttu-id="b548e-188">Часто инструкции ALTER отрицательно влияют на производительность запросов к индексированным XML-документам.</span><span class="sxs-lookup"><span data-stu-id="b548e-188">Frequently ALTER statements negatively affect the performance of queries over the indexed XML documents.</span></span>  
  
 <span data-ttu-id="b548e-189">**Прочие ограничения**</span><span class="sxs-lookup"><span data-stu-id="b548e-189">**Other limitations**</span></span>  
  
-   <span data-ttu-id="b548e-190">Селективные XML-индексы не поддерживаются в указаниях запросов.</span><span class="sxs-lookup"><span data-stu-id="b548e-190">Selective XML indexes are not supported in query hints.</span></span>  
  
-   <span data-ttu-id="b548e-191">Селективные XML-индексы и вторичные селективные XML-индексы не поддерживаются в помощнике по настройке базы данных.</span><span class="sxs-lookup"><span data-stu-id="b548e-191">Selective XML indexes and secondary selective XML indexes are not supported in Database Tuning Advisor.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="b548e-192">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="b548e-192">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b548e-193">**Задача**</span><span class="sxs-lookup"><span data-stu-id="b548e-193">**Task**</span></span>|<span data-ttu-id="b548e-194">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="b548e-194">**Topic**</span></span>|  
|<span data-ttu-id="b548e-195">При создании или изменении селективного XML-индекса необходимо указать пути узлов, которые нужно индексировать, а также необязательные указания по оптимизации.</span><span class="sxs-lookup"><span data-stu-id="b548e-195">Specify the node paths that you want to index and optional optimization hints when you create or alter a selective XML index.</span></span>|[<span data-ttu-id="b548e-196">Задание путей и указания по оптимизации для селективных XML-индексов</span><span class="sxs-lookup"><span data-stu-id="b548e-196">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>](specify-paths-and-optimization-hints-for-selective-xml-indexes.md)|  
|<span data-ttu-id="b548e-197">Создание, изменение и удаление селективного XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="b548e-197">Create, alter, or drop a selective XML index.</span></span>|[<span data-ttu-id="b548e-198">Создание, изменение и удаление селективных XML-индексов</span><span class="sxs-lookup"><span data-stu-id="b548e-198">Create, Alter, and Drop Selective XML Indexes</span></span>](create-alter-and-drop-selective-xml-indexes.md)|  
|<span data-ttu-id="b548e-199">Создание, изменение и удаление вторичного селективного XML-индекса.</span><span class="sxs-lookup"><span data-stu-id="b548e-199">Create, alter, or drop a secondary selective XML index.</span></span>|[<span data-ttu-id="b548e-200">Создание, изменение и удаление вторичных селективных XML-индексов</span><span class="sxs-lookup"><span data-stu-id="b548e-200">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>](create-alter-and-drop-secondary-selective-xml-indexes.md)|  
  

  
  
