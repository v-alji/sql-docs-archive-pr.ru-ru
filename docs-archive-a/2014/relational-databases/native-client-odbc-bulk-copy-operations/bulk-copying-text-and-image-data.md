---
title: Копирование данных в виде текста и изображений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], text data
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], image data
- ODBC, bulk copy operations
ms.assetid: 87155bfa-3a73-4158-9d4d-cb7435dac201
author: rothja
ms.author: jroth
ms.openlocfilehash: 9240fd0eb8c32ed39613824ea5a07764e277160c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668843"
---
# <a name="bulk-copying-text-and-image-data"></a><span data-ttu-id="8e8d1-102">Массовое копирование данных text и image</span><span class="sxs-lookup"><span data-stu-id="8e8d1-102">Bulk Copying Text and Image Data</span></span>
  <span data-ttu-id="8e8d1-103">Значения типа Large **Text**, **ntext**и **Image** копируются с помощью функции [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) .</span><span class="sxs-lookup"><span data-stu-id="8e8d1-103">Large **text**, **ntext**, and **image** values are bulk copied using the [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) function.</span></span> <span data-ttu-id="8e8d1-104">Код [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) для столбца **Text**, **ntext**или **Image** с указателем *pData* , имеющим значение null, что означает, что данные будут предоставлены в **bcp_moretext**.</span><span class="sxs-lookup"><span data-stu-id="8e8d1-104">You code [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) for the **text**, **ntext**, or **image** column with a *pData* pointer set to NULL indicating the data will be provided with **bcp_moretext**.</span></span> <span data-ttu-id="8e8d1-105">Важно указать точную длину данных, предоставляемых для каждого столбца типа **Text**, **ntext**или **Image** в каждой строке с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="8e8d1-105">It is important to specify the exact length of data supplied for each **text**, **ntext**,or **image** column in each bulk-copied row.</span></span> <span data-ttu-id="8e8d1-106">Если длина данных столбца отличается от длины столбца, указанного в [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), используйте [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) , чтобы задать для длины правильное значение.</span><span class="sxs-lookup"><span data-stu-id="8e8d1-106">If the length of the data for a column is different from the column length specified in [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), use [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) to set the length to the proper value.</span></span> <span data-ttu-id="8e8d1-107">[Bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) отправляет все данные, не являющиеся**текстовыми**, не-**ntext**и не являющиеся**изображениями** ; Затем вызывается **bcp_moretext** для отправки данных типа **Text**, **ntext**или **Image** в отдельных единицах.</span><span class="sxs-lookup"><span data-stu-id="8e8d1-107">A [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) sends all the non-**text**, non-**ntext**, and non-**image** data; you then call **bcp_moretext** to send the **text**, **ntext**, or **image** data in separate units.</span></span> <span data-ttu-id="8e8d1-108">Функции операций с массовым копированием определяют, что все данные были отправлены для текущего столбца **Text**, **ntext**или **Image** , если сумма длин данных, отправленных с помощью **bcp_moretext** , равна длине, указанной в последней **bcp_collen** или **bcp_bind**.</span><span class="sxs-lookup"><span data-stu-id="8e8d1-108">Bulk copy functions determine that all data has been sent for the current **text**, **ntext**, or **image** column when the sum of the lengths of data sent through **bcp_moretext** equals the length specified in the latest **bcp_collen** or **bcp_bind**.</span></span>  
  
 <span data-ttu-id="8e8d1-109">**bcp_moretext** не имеет параметра для задания столбца.</span><span class="sxs-lookup"><span data-stu-id="8e8d1-109">**bcp_moretext** has no parameter to identify a column.</span></span> <span data-ttu-id="8e8d1-110">Если в строке имеется несколько столбцов типа **Text**, **ntext**или **Image** , **bcp_moretext** работает с столбцами типа **Text**, **ntext**или **Image** , начиная с столбца с наименьшим порядковым номером и Переходя к столбцу с наибольшим порядковым номером.</span><span class="sxs-lookup"><span data-stu-id="8e8d1-110">When there are multiple **text**, **ntext**, or **image** columns in a row, **bcp_moretext** operates on the **text**, **ntext**, or **image** columns starting with the column having the lowest ordinal number and proceeding to the column with the highest ordinal number.</span></span> <span data-ttu-id="8e8d1-111">**bcp_moretext** переходит от одного столбца к другому, когда сумма значений длины отправленных данных равна длине, указанной в последней **bcp_collen** или **bcp_bind** для текущего столбца.</span><span class="sxs-lookup"><span data-stu-id="8e8d1-111">**bcp_moretext** goes from one column to the next when the sum of the lengths of data sent equals the length specified in the latest **bcp_collen** or **bcp_bind** for the current column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e8d1-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e8d1-112">See Also</span></span>  
 [<span data-ttu-id="8e8d1-113">Выполнение операций с массовым копированием &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="8e8d1-113">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
