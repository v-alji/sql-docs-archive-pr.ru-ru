---
title: bcp_columns | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_columns
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_columns function
ms.assetid: 5376f6fe-9508-439a-8c66-778d77f19ac3
author: rothja
ms.author: jroth
ms.openlocfilehash: 028bb80e88a29b366e3a489abae06c8b3b30cdf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730646"
---
# <a name="bcp_columns"></a><span data-ttu-id="e590c-102">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="e590c-102">bcp_columns</span></span>
  <span data-ttu-id="e590c-103">Задает общее количество столбцов в файле пользователя, используемых для массового копирования на сервер или с сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e590c-103">Sets the total number of columns found in the user file for use with a bulk copy into or out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e590c-104">[bcp_setbulkmode](bcp-setbulkmode.md) можно использовать вместо bcp_columns и [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="e590c-104">[bcp_setbulkmode](bcp-setbulkmode.md) can be used instead of bcp_columns and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e590c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e590c-105">Syntax</span></span>  
  
```  
  
RETCODE bcp_columns (  
HDBC   
hdbc  
,  
INT   
nColumns  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e590c-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e590c-106">Arguments</span></span>  
 <span data-ttu-id="e590c-107">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="e590c-107">*hdbc*</span></span>  
 <span data-ttu-id="e590c-108">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="e590c-108">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="e590c-109">*nColumns*</span><span class="sxs-lookup"><span data-stu-id="e590c-109">*nColumns*</span></span>  
 <span data-ttu-id="e590c-110">Общее количество столбцов в файле пользователя.</span><span class="sxs-lookup"><span data-stu-id="e590c-110">Is the total number of columns in the user file.</span></span> <span data-ttu-id="e590c-111">Даже если вы готовитесь к копированию данных из файла пользователя в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таблицу и не собираетесь копировать все столбцы в файл пользователя, необходимо установить *нколумнс* в общее число столбцов User-Files.</span><span class="sxs-lookup"><span data-stu-id="e590c-111">Even if you are preparing to bulk copy data from the user file to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table and do not intend to copy all columns in the user file, you must still set *nColumns* to the total number of user-file columns.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e590c-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e590c-112">Returns</span></span>  
 <span data-ttu-id="e590c-113">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="e590c-113">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e590c-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="e590c-114">Remarks</span></span>  
 <span data-ttu-id="e590c-115">Эту функцию можно вызвать только после вызова [bcp_init](bcp-init.md) с допустимым именем файла.</span><span class="sxs-lookup"><span data-stu-id="e590c-115">This function can be called only after [bcp_init](bcp-init.md) has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="e590c-116">Эту функцию следует вызывать только в том случае, если планируется использовать формат файла пользователя, отличный от формата по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e590c-116">You should call this function only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="e590c-117">Дополнительные сведения об описании формата пользовательских файлов по умолчанию см. в разделе **bcp_init**.</span><span class="sxs-lookup"><span data-stu-id="e590c-117">For more information about a description of the default user-file format, see **bcp_init**.</span></span>  
  
 <span data-ttu-id="e590c-118">После вызова `bcp_columns` необходимо вызвать [bcp_colfmt](bcp-colfmt.md)для каждого столбца в файле пользователя, чтобы полностью определить пользовательский формат файла.</span><span class="sxs-lookup"><span data-stu-id="e590c-118">After calling `bcp_columns`, you must call [bcp_colfmt](bcp-colfmt.md)for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e590c-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="e590c-119">See Also</span></span>  
 [<span data-ttu-id="e590c-120">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="e590c-120">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
