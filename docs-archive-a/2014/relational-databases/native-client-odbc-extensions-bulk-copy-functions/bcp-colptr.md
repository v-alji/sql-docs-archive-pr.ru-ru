---
title: bcp_colptr | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colptr
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colptr function
ms.assetid: 02ece13e-1da3-4f9d-b860-3177e43d2471
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b725ace58ee1768fbca1a433cdea27e3e0e546e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750911"
---
# <a name="bcp_colptr"></a><span data-ttu-id="f1c28-102">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="f1c28-102">bcp_colptr</span></span>
  <span data-ttu-id="f1c28-103">Устанавливает адрес данных переменных программы для текущей копии в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1c28-103">Sets the program variable data address for the current copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1c28-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_colptr (  
HDBC   
hdbc  
,  
LPCBYTE   
pData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f1c28-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f1c28-105">Arguments</span></span>  
 <span data-ttu-id="f1c28-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="f1c28-106">*hdbc*</span></span>  
 <span data-ttu-id="f1c28-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="f1c28-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="f1c28-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="f1c28-108">*pData*</span></span>  
 <span data-ttu-id="f1c28-109">Указатель на копируемые данные.</span><span class="sxs-lookup"><span data-stu-id="f1c28-109">Is a pointer to the data to copy.</span></span> <span data-ttu-id="f1c28-110">Если привязанный тип данных имеет тип больших значений (например, SQLTEXT или SQLIMAGE), то параметр *pData* может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="f1c28-110">If the bound data type is large value type (such as SQLTEXT or SQLIMAGE), *pData* can be NULL.</span></span> <span data-ttu-id="f1c28-111">ЗНАЧЕНИЕ типа *pData* , указывающее, что данные длинных значений будут отправляться в SQL Server фрагментов с помощью [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="f1c28-111">A NULL *pData* indicates long data values will be sent to SQL Server in chunks using [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="f1c28-112">Если для *pData* установлено значение null, а столбец, соответствующий привязанному полю, не имеет тип больших значений, **bcp_colptr** завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f1c28-112">If *pData* is set to NULL and the column corresponding to the bound field is not a large value type, **bcp_colptr** fails.</span></span>  
  
 <span data-ttu-id="f1c28-113">Дополнительные сведения о типах больших значений см. в разделе [bcp_bind](bcp-bind.md)**.**</span><span class="sxs-lookup"><span data-stu-id="f1c28-113">For more information on large value types, see [bcp_bind](bcp-bind.md)**.**</span></span>  
  
 <span data-ttu-id="f1c28-114">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="f1c28-114">*idxServerCol*</span></span>  
 <span data-ttu-id="f1c28-115">Порядковый номер столбца в таблице базы данных, в которую копируются данные.</span><span class="sxs-lookup"><span data-stu-id="f1c28-115">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="f1c28-116">Первый столбец в таблице имеет порядковый номер 1.</span><span class="sxs-lookup"><span data-stu-id="f1c28-116">The first column in a table is column 1.</span></span> <span data-ttu-id="f1c28-117">Порядковый номер столбца возвращается функцией [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="f1c28-117">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f1c28-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f1c28-118">Returns</span></span>  
 <span data-ttu-id="f1c28-119">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="f1c28-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1c28-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1c28-120">Remarks</span></span>  
 <span data-ttu-id="f1c28-121">Функция **bcp_colptr** позволяет изменить адрес исходных данных для определенного столбца при копировании данных в SQL Server с помощью [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="f1c28-121">The **bcp_colptr** function allows you to change the address of source data for a particular column when copying data to SQL Server with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="f1c28-122">Изначально указатель на пользовательские данные задается вызовом **bcp_bind**.</span><span class="sxs-lookup"><span data-stu-id="f1c28-122">Initially, the pointer to user data is set by a call to **bcp_bind**.</span></span> <span data-ttu-id="f1c28-123">Если адрес данных переменной программы изменяется между вызовами **bcp_sendrow**, можно вызвать **bcp_colptr** , чтобы сбросить указатель на данные.</span><span class="sxs-lookup"><span data-stu-id="f1c28-123">If the program variable data address changes between calls to **bcp_sendrow**, you can call **bcp_colptr** to reset the pointer to the data.</span></span> <span data-ttu-id="f1c28-124">Следующий вызов **bcp_sendrow** отправляет данные, адресованные вызовом **bcp_colptr**.</span><span class="sxs-lookup"><span data-stu-id="f1c28-124">The next call to **bcp_sendrow** sends the data addressed by the call to **bcp_colptr**.</span></span>  
  
 <span data-ttu-id="f1c28-125">Должен существовать отдельный вызов **bcp_colptr** для каждого столбца в таблице, адрес данных которого необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="f1c28-125">There must be a separate **bcp_colptr** call for every column in the table whose data address you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c28-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="f1c28-126">See Also</span></span>  
 [<span data-ttu-id="f1c28-127">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="f1c28-127">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
