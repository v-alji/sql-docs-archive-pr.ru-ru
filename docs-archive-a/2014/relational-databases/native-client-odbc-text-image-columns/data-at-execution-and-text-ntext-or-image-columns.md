---
title: Данные во время выполнения и столбцы типа Text, ntext или Image | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- data-at-execution
- ODBC data-at-execution
- image columns [ODBC]
ms.assetid: 67ffb1a6-f38d-4712-ba64-96bdd41ec2b2
author: rothja
ms.author: jroth
ms.openlocfilehash: 404fade34862fe4705ec440eef7f466a9073250b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750859"
---
# <a name="data-at-execution-and-text-ntext-or-image-columns"></a><span data-ttu-id="dfafa-102">Данные времени выполнения и столбцы text, ntext или image</span><span class="sxs-lookup"><span data-stu-id="dfafa-102">Data-at-Execution and Text, ntext, or Image Columns</span></span>
  <span data-ttu-id="dfafa-103">Данные времени выполнения ODBC позволяют приложениям работать с очень большими объемами данных в связанных столбцах или параметрах.</span><span class="sxs-lookup"><span data-stu-id="dfafa-103">ODBC data-at-execution is a feature that enables applications to work with extremely large amounts of data on bound columns or parameters.</span></span> <span data-ttu-id="dfafa-104">При получении очень больших столбцов **Text**, **ntext**или **Image** приложение может не позволить просто выделить огромный буфер, привязать столбец к буферу и получить строку.</span><span class="sxs-lookup"><span data-stu-id="dfafa-104">When retrieving very large **text**, **ntext**, or **image** columns, an application may not be able to simply allocate a huge buffer, bind the column into the buffer, and fetch the row.</span></span> <span data-ttu-id="dfafa-105">При обновлении очень больших столбцов **Text**, **ntext**или **Image** приложение может не позволить просто выделить огромный буфер, привязать его к маркеру параметра в инструкции SQL, а затем выполнить инструкцию.</span><span class="sxs-lookup"><span data-stu-id="dfafa-105">When updating very large **text**, **ntext**, or **image** columns, the application might not be able to simply allocate a huge buffer, bind it to a parameter marker in an SQL statement, and then execute the statement.</span></span> <span data-ttu-id="dfafa-106">В таких случаях приложение должно использовать [SQLGetData](../native-client-odbc-api/sqlgetdata.md) или [SQLPutData](../native-client-odbc-api/sqlputdata.md) с параметрами, выполняемыми при выполнении.</span><span class="sxs-lookup"><span data-stu-id="dfafa-106">In these cases, the application must use [SQLGetData](../native-client-odbc-api/sqlgetdata.md) or [SQLPutData](../native-client-odbc-api/sqlputdata.md) with its data-at-execution options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfafa-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="dfafa-107">See Also</span></span>  
 [<span data-ttu-id="dfafa-108">Управление столбцами text и image</span><span class="sxs-lookup"><span data-stu-id="dfafa-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
