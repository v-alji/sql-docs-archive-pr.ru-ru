---
title: Эвристические методы режима AUTO, используемые при формировании возвращаемого XML-кода | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, heuristics in shaping returned XML
ms.assetid: 6c5cb6c1-2921-4ba1-8100-0bf8074f9103
author: rothja
ms.author: jroth
ms.openlocfilehash: 7a64cda8989e1e45d4ad869f8883e1c9d65f4b7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654962"
---
# <a name="auto-mode-heuristics-in-shaping-returned-xml"></a><span data-ttu-id="f6c94-102">Эвристические методы режима AUTO, используемые при формировании возвращаемого XML-кода</span><span class="sxs-lookup"><span data-stu-id="f6c94-102">AUTO Mode Heuristics in Shaping Returned XML</span></span>
  <span data-ttu-id="f6c94-103">Режим AUTO определяет основанную на запросе структуру возвращаемого XML.</span><span class="sxs-lookup"><span data-stu-id="f6c94-103">AUTO mode determines the shape of returned XML based on the query.</span></span> <span data-ttu-id="f6c94-104">При определении схемы вложения элементов применяемые в режиме AUTO эвристические процедуры сравнивают значения столбцов в соседних строках.</span><span class="sxs-lookup"><span data-stu-id="f6c94-104">In determining how elements are to be nested, AUTO mode heuristics compare column values in adjacent rows.</span></span> <span data-ttu-id="f6c94-105">Сравниваются столбцы всех типов, за исключением **ntext**, **text**, **image**и **xml**.</span><span class="sxs-lookup"><span data-stu-id="f6c94-105">Columns of all types, except **ntext**, **text**, **image**, and **xml**, are compared.</span></span> <span data-ttu-id="f6c94-106">Проводится также сравнение столбцов **(n)varchar(max)** и **varbinary(max)** .</span><span class="sxs-lookup"><span data-stu-id="f6c94-106">Columns of type **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="f6c94-107">В следующем примере иллюстрируются эвристики режима AUTO, определяющие структуру результирующего XML:</span><span class="sxs-lookup"><span data-stu-id="f6c94-107">The following example illustrates the AUTO mode heuristics that determine the shape of the resulting XML:</span></span>  
  
```  
SELECT T1.Id, T2.Id, T1.Name  
FROM   T1, T2  
WHERE ...  
FOR XML AUTO  
ORDER BY T1.Id  
```  
  
 <span data-ttu-id="f6c94-108">Для определения начала нового элемента <`T1`> сравниваются все значения столбцов таблицы T1, за исключением столбцов типов данных **ntext**, **text**, **image** и **xml**, если ключ таблицы Т1 не задан.</span><span class="sxs-lookup"><span data-stu-id="f6c94-108">To determine where a new <`T1`> element starts, all column values of T1, except **ntext**, **text**, **image** and **xml**, are compared if the key on the table T1 is not specified.</span></span> <span data-ttu-id="f6c94-109">Далее предположим, что столбец **Name** имеет тип данных **nvarchar(40)** и инструкция SELECT возвращает следующий набор строк:</span><span class="sxs-lookup"><span data-stu-id="f6c94-109">Next, assume that the **Name** column is **nvarchar(40)** and the SELECT statement returns this rowset:</span></span>  
  
```  
T1.Id  T1.Name  T2.Id  
-----------------------  
1       Andrew    2  
1       Andrew    3  
1       Nancy     4  
```  
  
 <span data-ttu-id="f6c94-110">Эвристики режима AUTO сравнивают все значения столбцов Id и Name таблицы Т1.</span><span class="sxs-lookup"><span data-stu-id="f6c94-110">The AUTO mode heuristics compare all the values of table T1, the Id and Name columns.</span></span> <span data-ttu-id="f6c94-111">Так как первые две строки имеют одинаковые значения столбцов Id и Name, в результат добавляется один элемент \<T1>, имеющий два дочерних элемента \<T2>.</span><span class="sxs-lookup"><span data-stu-id="f6c94-111">Because the first two rows have the same values for the Id and Name columns, one \<T1> element having two \<T2> child elements is added in the result.</span></span>  
  
 <span data-ttu-id="f6c94-112">Далее показан возвращенный XML:</span><span class="sxs-lookup"><span data-stu-id="f6c94-112">Following is the XML that is returned:</span></span>  
  
```  
<T1 Id="1" Name="Andrew">  
    <T2 Id="2" />  
    <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
      <T2 Id="4" />  
</T>  
```  
  
 <span data-ttu-id="f6c94-113">Теперь предположим, что столбец Name имеет тип данных **text** .</span><span class="sxs-lookup"><span data-stu-id="f6c94-113">Now assume that the Name column is of **text** type.</span></span> <span data-ttu-id="f6c94-114">Эвристики режима AUTO не выполняют сравнения для этого типа.</span><span class="sxs-lookup"><span data-stu-id="f6c94-114">The AUTO mode heuristics do not compare the values for this type.</span></span> <span data-ttu-id="f6c94-115">Вместо этого в них предполагается, что значения различны.</span><span class="sxs-lookup"><span data-stu-id="f6c94-115">Instead, it assumes that the values are not the same.</span></span> <span data-ttu-id="f6c94-116">Это приводит к формированию приведенного ниже XML:</span><span class="sxs-lookup"><span data-stu-id="f6c94-116">This results in XML generation as shown in the following:</span></span>  
  
```  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="2" />  
</T1>  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
  <T2 Id="4" />  
</T1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6c94-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="f6c94-117">See Also</span></span>  
 [<span data-ttu-id="f6c94-118">Использование AUTO Mode с FOR XML</span><span class="sxs-lookup"><span data-stu-id="f6c94-118">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
