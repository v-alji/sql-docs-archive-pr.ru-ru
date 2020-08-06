---
title: bcp_collen | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_collen
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_collen function
ms.assetid: faaf1f7a-81f2-4852-a178-56602c33673a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3099e26b0c2cd0d1cfee7578f5b149b812f01765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750907"
---
# <a name="bcp_collen"></a><span data-ttu-id="f9a71-102">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="f9a71-102">bcp_collen</span></span>
  <span data-ttu-id="f9a71-103">Устанавливает длину данных в переменной программы для текущего массового копирования в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9a71-103">Sets the data length in the program variable for the current bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a71-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9a71-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_collen (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f9a71-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f9a71-105">Arguments</span></span>  
 <span data-ttu-id="f9a71-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="f9a71-106">*hdbc*</span></span>  
 <span data-ttu-id="f9a71-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="f9a71-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="f9a71-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="f9a71-108">*cbData*</span></span>  
 <span data-ttu-id="f9a71-109">Длина данных в переменной программы, не включая длину признака длины или конца данных.</span><span class="sxs-lookup"><span data-stu-id="f9a71-109">Is the length of the data in the program variable, not including the length of any length indicator or terminator.</span></span> <span data-ttu-id="f9a71-110">Установка параметра *cbData* в значение SQL_NULL_DATA означает все строки, скопированные на сервер, которые содержат в столбце значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f9a71-110">Setting *cbData* to SQL_NULL_DATA indicates all rows copied to the server contain a NULL value for the column.</span></span> <span data-ttu-id="f9a71-111">Установка в значение SQL_VARLEN_DATA означает, что для определения длины скопированных данных используется признак конца строки или другой метод.</span><span class="sxs-lookup"><span data-stu-id="f9a71-111">Setting it to SQL_VARLEN_DATA indicates that a string terminator or other method is used to determine the length of data copied.</span></span> <span data-ttu-id="f9a71-112">Если существует как признак длины, так и признак конца, система использует результат с меньшим количеством скопированных данных.</span><span class="sxs-lookup"><span data-stu-id="f9a71-112">If both a length indicator and a terminator exist, the system uses whichever one results in less data being copied.</span></span>  
  
 <span data-ttu-id="f9a71-113">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="f9a71-113">*idxServerCol*</span></span>  
 <span data-ttu-id="f9a71-114">Порядковый номер столбца таблицы, в которую копируются данные.</span><span class="sxs-lookup"><span data-stu-id="f9a71-114">Is the ordinal position of the column in the table to which the data is copied.</span></span> <span data-ttu-id="f9a71-115">Первый столбец имеет номер 1.</span><span class="sxs-lookup"><span data-stu-id="f9a71-115">The first column is 1.</span></span> <span data-ttu-id="f9a71-116">Порядковый номер столбца возвращается функцией [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="f9a71-116">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f9a71-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f9a71-117">Returns</span></span>  
 <span data-ttu-id="f9a71-118">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="f9a71-118">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9a71-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9a71-119">Remarks</span></span>  
 <span data-ttu-id="f9a71-120">Функция **bcp_collen** позволяет изменять для определенного столбца длину данных в переменной программы при копировании данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью функции [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="f9a71-120">The **bcp_collen** function allows you to change the data length in the program variable for a particular column when copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="f9a71-121">Первоначальная длина данных определяется при вызове функции [bcp_bind](bcp-bind.md) .</span><span class="sxs-lookup"><span data-stu-id="f9a71-121">Initially, the data length is determined when [bcp_bind](bcp-bind.md) is called.</span></span> <span data-ttu-id="f9a71-122">Если длина данных изменяется между вызовами функции **bcp_sendrow** и не используется ни одного префикса длины или признака конца, то для сброса длины можно вызвать **bcp_collen** .</span><span class="sxs-lookup"><span data-stu-id="f9a71-122">If the data length changes between calls to **bcp_sendrow** and no length prefix or terminator is being used, you can call **bcp_collen** to reset the length.</span></span> <span data-ttu-id="f9a71-123">При следующем вызове функции **bcp_sendrow** используется длина, заданная функцией **bcp_collen**.</span><span class="sxs-lookup"><span data-stu-id="f9a71-123">The next call to **bcp_sendrow** uses the length set by the call to **bcp_collen**.</span></span>  
  
 <span data-ttu-id="f9a71-124">Для каждого столбца таблицы, длину данных которого нужно изменить, необходимо вызвать функцию **bcp_collen** .</span><span class="sxs-lookup"><span data-stu-id="f9a71-124">You must call **bcp_collen** once for each column in the table whose data length you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a71-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9a71-125">See Also</span></span>  
 [<span data-ttu-id="f9a71-126">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="f9a71-126">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
