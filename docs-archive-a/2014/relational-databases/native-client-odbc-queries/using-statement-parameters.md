---
title: Использование параметров инструкции | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- ODBC, parameters
- statements [ODBC], parameters
- parameter markers [ODBC]
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
ms.assetid: 2427d886-ec6c-49d7-b0b6-0d998b64cdb9
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b7e207416e60af94efd59555980a0edff68a38b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655111"
---
# <a name="using-statement-parameters"></a><span data-ttu-id="8a274-102">Использование параметров инструкции</span><span class="sxs-lookup"><span data-stu-id="8a274-102">Using Statement Parameters</span></span>
  <span data-ttu-id="8a274-103">Параметр — это переменная в инструкции SQL, позволяющая в приложении ODBC осуществлять следующее.</span><span class="sxs-lookup"><span data-stu-id="8a274-103">A parameter is a variable in an SQL statement that can enable an ODBC application to:</span></span>  
  
-   <span data-ttu-id="8a274-104">Эффективно передавать значения для столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="8a274-104">Efficiently provide values for columns in a table.</span></span>  
  
-   <span data-ttu-id="8a274-105">Повышать степень взаимодействия с пользователем при конструировании критериев запроса.</span><span class="sxs-lookup"><span data-stu-id="8a274-105">Enhance user interaction in constructing query criteria.</span></span>  
  
-   <span data-ttu-id="8a274-106">Управление данными типа **Text**, **ntext**и **Image** и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] конкретными типами данных C.</span><span class="sxs-lookup"><span data-stu-id="8a274-106">Manage **text**, **ntext**, and **image** data and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific C data types.</span></span>  
  
 <span data-ttu-id="8a274-107">Например, таблица **Parts** содержит столбцы с именами **PartID**, **Description**и **Price**.</span><span class="sxs-lookup"><span data-stu-id="8a274-107">For example, a **Parts** table has columns named **PartID**, **Description**, and **Price**.</span></span> <span data-ttu-id="8a274-108">Для добавления компонента без параметров необходимо составить инструкцию SQL, например:</span><span class="sxs-lookup"><span data-stu-id="8a274-108">To add a part without parameters requires constructing an SQL statement such as:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (2100, 'Drive shaft', 50.00)  
```  
  
 <span data-ttu-id="8a274-109">Эта инструкция вполне подходит для вставки одной строки с заранее известным набором значений, но если в приложении необходимо вставить несколько строк, она становится менее приемлемой.</span><span class="sxs-lookup"><span data-stu-id="8a274-109">Although this statement is acceptable for inserting one row with a known set of values, it is awkward when an application is required to insert several rows.</span></span> <span data-ttu-id="8a274-110">Поэтому в ODBC разрешается заменять в приложении любое значение данных в инструкции SQL маркером параметра.</span><span class="sxs-lookup"><span data-stu-id="8a274-110">ODBC addresses this by letting an application to replace any data value in an SQL statement by a parameter maker.</span></span> <span data-ttu-id="8a274-111">Он обозначается вопросительным знаком (?).</span><span class="sxs-lookup"><span data-stu-id="8a274-111">This is denoted by a question mark (?).</span></span> <span data-ttu-id="8a274-112">В следующем примере маркерами параметров заменены три значения данных.</span><span class="sxs-lookup"><span data-stu-id="8a274-112">In the following example, three data values are replaced with parameter markers:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="8a274-113">Затем происходит привязка маркеров параметров к переменным приложения.</span><span class="sxs-lookup"><span data-stu-id="8a274-113">The parameter markers are then bound to application variables.</span></span> <span data-ttu-id="8a274-114">Для вставки новой строки в приложении достаточно только задать значения параметров и выполнить инструкцию.</span><span class="sxs-lookup"><span data-stu-id="8a274-114">To insert a new row, the application has only to set the values of the variables and execute the statement.</span></span> <span data-ttu-id="8a274-115">После этого драйвер получает текущие значения переменных и передает их в источник данных.</span><span class="sxs-lookup"><span data-stu-id="8a274-115">The driver then retrieves the current values of the variables and sends them to the data source.</span></span> <span data-ttu-id="8a274-116">Если инструкция выполняется неоднократно, то в приложении можно дополнительно оптимизировать этот процесс с помощью подготовки инструкции.</span><span class="sxs-lookup"><span data-stu-id="8a274-116">If the statement is executed multiple times, the application can make the process even more efficient by preparing the statement.</span></span>  
  
 <span data-ttu-id="8a274-117">Ссылка на каждый маркер параметра осуществляется по порядковому номеру; параметры нумеруются слева направо.</span><span class="sxs-lookup"><span data-stu-id="8a274-117">Each parameter marker is referenced by its ordinal number assigned to the parameters from left to right.</span></span> <span data-ttu-id="8a274-118">Первый слева параметр в инструкции SQL имеет порядковый номер 1; следующий — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="8a274-118">The leftmost parameter marker in an SQL statement has an ordinal value of 1; the next one is ordinal 2, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a274-119">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="8a274-119">In This Section</span></span>  
  
-   [<span data-ttu-id="8a274-120">Привязка параметров</span><span class="sxs-lookup"><span data-stu-id="8a274-120">Binding Parameters</span></span>](using-statement-parameters-binding-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a274-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a274-121">See Also</span></span>  
 [<span data-ttu-id="8a274-122">Выполняя запросы &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="8a274-122">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
