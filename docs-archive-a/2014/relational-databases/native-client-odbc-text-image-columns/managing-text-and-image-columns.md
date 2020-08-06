---
title: Управление столбцами Text и Image | Документация Майкрософт
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
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- data types [ODBC], mapping
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 7b543556-ff36-4d35-ac08-de96223d92cd
author: rothja
ms.author: jroth
ms.openlocfilehash: e9d7d5b0f48c68e8ac911f5e274c9afdb8cfe17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750832"
---
# <a name="managing-text-and-image-columns"></a><span data-ttu-id="44f09-102">Управление столбцами text и image</span><span class="sxs-lookup"><span data-stu-id="44f09-102">Managing Text and Image Columns</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="44f09-103">данные типа **Text**, **ntext**и **Image** (также называемые длинными данными) представляют собой символьные или двоичные строковые типы данных, которые могут содержать слишком большие значения данных для размещения в столбцах **char**, **varchar**, **binary**или **varbinary** .</span><span class="sxs-lookup"><span data-stu-id="44f09-103">**text**, **ntext**, and **image** data (also referred to as long data) are character or binary string data types that can hold data values too large to fit into **char**, **varchar**, **binary**, or **varbinary** columns.</span></span> <span data-ttu-id="44f09-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Тип данных **Text** сопоставляется с типом данных ODBC SQL_LONGVARCHAR. **ntext** сопоставляется с SQL_WLONGVARCHAR; **изображения** и сопоставляются с SQL_LONGVARBINARY.</span><span class="sxs-lookup"><span data-stu-id="44f09-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **text** data type maps to the ODBC SQL_LONGVARCHAR data type; **ntext** maps to SQL_WLONGVARCHAR; and **image** maps to SQL_LONGVARBINARY.</span></span> <span data-ttu-id="44f09-105">Некоторые объекты данных (например, длинные документы или большие битовые карты) слишком велики для их размещения в памяти.</span><span class="sxs-lookup"><span data-stu-id="44f09-105">Some data items, such as long documents or large bitmaps, may be too large to store reasonably in memory.</span></span> <span data-ttu-id="44f09-106">Для получения длинных данных из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] последовательных частей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента позволяет приложению вызывать [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span><span class="sxs-lookup"><span data-stu-id="44f09-106">To retrieve long data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in sequential parts, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to call [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span></span> <span data-ttu-id="44f09-107">Для отправки длинных данных в последовательных частях приложение может вызвать [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="44f09-107">To send long data in sequential parts, the application can call [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span></span> <span data-ttu-id="44f09-108">Параметры, для которых данные посылаются во время выполнения, называются параметрами c данными времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="44f09-108">Parameters for which data is sent at execution time are known as data-at-execution parameters.</span></span>  
  
 <span data-ttu-id="44f09-109">Приложение может на самом деле записывать или извлекать данные любого типа (не только длинные данные) с **SQLPutData** или **SQLGetData**, хотя в частях могут быть отправлены и получены только **символьные** и **двоичные** данные.</span><span class="sxs-lookup"><span data-stu-id="44f09-109">An application can actually write or retrieve any type of data (not just long data) with **SQLPutData** or **SQLGetData**, although only **character** and **binary** data can be sent or retrieved in parts.</span></span> <span data-ttu-id="44f09-110">Однако если данные достаточно малы для размещения в одном буфере, обычно нет причин использовать **SQLPutData** или **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="44f09-110">However, if the data is small enough to fit in a single buffer, there is generally no reason to use **SQLPutData** or **SQLGetData**.</span></span> <span data-ttu-id="44f09-111">Гораздо проще привязать единичный буфер к параметру или столбцу.</span><span class="sxs-lookup"><span data-stu-id="44f09-111">It is much easier to bind the single buffer to the parameter or column.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44f09-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="44f09-112">In This Section</span></span>  
  
-   [<span data-ttu-id="44f09-113">Привязанные и непривязанные столбцы text и image</span><span class="sxs-lookup"><span data-stu-id="44f09-113">Bound vs. Unbound Text and Image Columns</span></span>](bound-vs-unbound-text-and-image-columns.md)  
  
-   [<span data-ttu-id="44f09-114">Изменения с ведением журнала и без ведения журнала</span><span class="sxs-lookup"><span data-stu-id="44f09-114">Logged vs. Unlogged Modifications</span></span>](logged-vs-unlogged-modifications.md)  
  
-   [<span data-ttu-id="44f09-115">Данные времени выполнения и столбцы text, ntext или image</span><span class="sxs-lookup"><span data-stu-id="44f09-115">Data-at-Execution and Text, ntext, or Image Columns</span></span>](data-at-execution-and-text-ntext-or-image-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="44f09-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="44f09-116">See Also</span></span>  
 [<span data-ttu-id="44f09-117">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="44f09-117">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
