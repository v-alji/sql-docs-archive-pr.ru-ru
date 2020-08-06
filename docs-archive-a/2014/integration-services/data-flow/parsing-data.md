---
title: Анализ данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parsing [Integration Services]
- data parsing [Integration Services]
ms.assetid: 8893ea9d-634c-4309-b52c-6337222dcb39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bd34cd83351e31313ae96ff5709ec999a60f2f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657190"
---
# <a name="parsing-data"></a><span data-ttu-id="a4d21-102">Анализ данных</span><span class="sxs-lookup"><span data-stu-id="a4d21-102">Parsing Data</span></span>
  <span data-ttu-id="a4d21-103">Потоки данных в пакетах извлекают и загружают данные между разнородными хранилищами данных, которые могут использовать различные стандартные и пользовательские типы данных.</span><span class="sxs-lookup"><span data-stu-id="a4d21-103">Data flows in packages extract and load data between heterogeneous data stores, which may use a variety of standard and custom data types.</span></span> <span data-ttu-id="a4d21-104">В потоке данных источники служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] выполняют извлечение, анализ строковых данных и преобразование в тип данных служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4d21-104">In a data flow, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources do the work of extracting data, parsing string data, and converting data to an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type.</span></span> <span data-ttu-id="a4d21-105">Последующие преобразования могут анализировать данные для их преобразования в другой тип данных или для создания копий столбцов с различными типами данных.</span><span class="sxs-lookup"><span data-stu-id="a4d21-105">Subsequent transformations may parse data to convert it to a different data type, or create column copies with different data types.</span></span> <span data-ttu-id="a4d21-106">Выражения, используемые в компонентах, могут также приводить аргументы и операнды к различным типам данных.</span><span class="sxs-lookup"><span data-stu-id="a4d21-106">Expressions used in components may also cast arguments and operands to different data types.</span></span> <span data-ttu-id="a4d21-107">Наконец, когда данные загружены в хранилище данных, целевой объект может проанализировать данные для их преобразования в используемый этим назначением тип данных.</span><span class="sxs-lookup"><span data-stu-id="a4d21-107">Finally, when the data is loaded into a data store, the destination may parse the data to convert it to a data type that the destination uses.</span></span> <span data-ttu-id="a4d21-108">Дополнительные сведения см. в разделе [Integration Services Data Types](integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a4d21-108">For more information, see [Integration Services Data Types](integration-services-data-types.md).</span></span>  
  
## <a name="types-of-parsing"></a><span data-ttu-id="a4d21-109">Типы синтаксического анализа</span><span class="sxs-lookup"><span data-stu-id="a4d21-109">Types of Parsing</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="a4d21-110">предусматривают два типа анализа для преобразования данных: быстрый и стандартный синтаксический анализ.</span><span class="sxs-lookup"><span data-stu-id="a4d21-110">provides two types of parsing for converting data: Fast parse and Standard parse.</span></span>  
  
-   <span data-ttu-id="a4d21-111">Быстрый анализ — это быстрый, простой набор операций анализа, не поддерживающий преобразования местных типов данных и поддерживающий только наиболее часто используемые форматы даты и времени.</span><span class="sxs-lookup"><span data-stu-id="a4d21-111">Fast parse is a fast, simple set of parsing routines that does not support locale-specific data type conversions, and supports only the most frequently used date and time formats.</span></span> <span data-ttu-id="a4d21-112">Дополнительные сведения см. в статье [Fast Parse](../fast-parse.md).</span><span class="sxs-lookup"><span data-stu-id="a4d21-112">For more information, see [Fast Parse](../fast-parse.md).</span></span>  
  
-   <span data-ttu-id="a4d21-113">Стандартный анализ — это большой набор операций анализа, поддерживающий преобразования всех типов данных, предусмотренных интерфейсами автоматического преобразования типов данных API-интерфейса в библиотеках Oleaut32.dll и Ole2dsip.dll.</span><span class="sxs-lookup"><span data-stu-id="a4d21-113">Standard parse is a rich set of parsing routines that supports all the data type conversions that are provided by the Automation data type conversion APIs available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="a4d21-114">Дополнительные сведения см. в статье [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="a4d21-114">For more information, see [Standard Parse](../standard-parse.md).</span></span>  
  
  
