---
title: IBCPSession::BCPInit (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPInit (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPInit method
ms.assetid: 583096d7-da34-49be-87fd-31210aac81aa
author: rothja
ms.author: jroth
ms.openlocfilehash: 25a01c71811de9d47ce01714402460bb53d4c70e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730633"
---
# <a name="ibcpsessionbcpinit-ole-db"></a><span data-ttu-id="2cd84-102">IBCPSession::BCPInit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="2cd84-102">IBCPSession::BCPInit (OLE DB)</span></span>
  <span data-ttu-id="2cd84-103">Инициализирует структуру массового копирования, выполняет проверку ошибок, проверяет правильность имен файла данных и файла форматирования, а затем открывает эти файлы.</span><span class="sxs-lookup"><span data-stu-id="2cd84-103">Initializes the bulk copy structure, performs some error checking, verifies that the data and format file names are correct, and then opens them.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cd84-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2cd84-104">Syntax</span></span>  
  
```  
  
HRESULT BCPInit(   
const wchar_t *pwszTable,  
const wchar_t *pwszDataFile,  
const wchar_t *pwszErrorFile,  
inteDirection);  
```  
  
## <a name="remarks"></a><span data-ttu-id="2cd84-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="2cd84-105">Remarks</span></span>  
 <span data-ttu-id="2cd84-106">Метод **BCPInit** необходимо вызывать перед вызовом любого другого метода массового копирования.</span><span class="sxs-lookup"><span data-stu-id="2cd84-106">The **BCPInit** method should be called before any other bulk-copy method.</span></span> <span data-ttu-id="2cd84-107">Метод **BCPInit** выполняет необходимые инициализации для массового копирования данных между рабочей станцией и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cd84-107">The **BCPInit** method performs the necessary initializations for a bulk copy of data between the workstation and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2cd84-108">Метод **BCPInit** проверяет структуру конечной или исходной таблицы базы данных, а не файл данных.</span><span class="sxs-lookup"><span data-stu-id="2cd84-108">The **BCPInit** method examines the structure of the database source or target table, not the data file.</span></span> <span data-ttu-id="2cd84-109">Он указывает значения форматов данных для файла данных на основе каждого столбца в таблице, представлении базы данных или результирующем наборе SELECT.</span><span class="sxs-lookup"><span data-stu-id="2cd84-109">It specifies data format values for the data file based on each column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="2cd84-110">Эта спецификация включает тип данных каждого столбца, присутствие или отсутствие длины и допустимости значений NULL и строки байтов признака конца, а также ширину для типов данных с фиксированной длиной.</span><span class="sxs-lookup"><span data-stu-id="2cd84-110">This specification includes the data type of each column, the presence or absence of a length or null indicator and terminator byte strings in the data, and the width of fixed-length data types.</span></span> <span data-ttu-id="2cd84-111">Метод **BCPInit** устанавливает эти значения указанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="2cd84-111">The **BCPInit** method sets these values as follows:</span></span>  
  
-   <span data-ttu-id="2cd84-112">Указанный тип данных представляет собой тип данных столбца в таблице базы данных, представлении или результирующем наборе SELECT.</span><span class="sxs-lookup"><span data-stu-id="2cd84-112">The data type specified is the data type of the column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="2cd84-113">Тип данных перечисляется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственными типами данных, указанными в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файле заголовка собственного клиента (sqlncli. h).</span><span class="sxs-lookup"><span data-stu-id="2cd84-113">The data type is enumerated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types specified in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client header file (sqlncli.h).</span></span> <span data-ttu-id="2cd84-114">Их значения строятся по следующему шаблону: BCP_TYPE_XXX.</span><span class="sxs-lookup"><span data-stu-id="2cd84-114">Their values are in the pattern of BCP_TYPE_XXX.</span></span> <span data-ttu-id="2cd84-115">Данные представлены в компьютерной форме.</span><span class="sxs-lookup"><span data-stu-id="2cd84-115">The data is represented in its computer form.</span></span> <span data-ttu-id="2cd84-116">Это значит, что данные из столбца с типом данных integer представлены четырехбайтовой последовательностью с прямым или обратным порядком следования байтов в зависимости от компьютера, создавшего файл данных.</span><span class="sxs-lookup"><span data-stu-id="2cd84-116">That is, data from a column of integer data type is represented by a four-byte sequence that is big-or little-endian based on the computer that created the data file.</span></span>  
  
-   <span data-ttu-id="2cd84-117">Если тип данных базы данных имеет фиксированную длину, то для данных файла данных также задается фиксированная длина.</span><span class="sxs-lookup"><span data-stu-id="2cd84-117">If a database data type is fixed in length, the data file data is also fixed in length.</span></span> <span data-ttu-id="2cd84-118">Методы массового копирования, обрабатывающие данные (например, [IBCPSession::BCPExec](ibcpsession-bcpexec-ole-db.md)) анализируют строки данных, ожидая, что длина данных в файле данных будет совпадать с длиной данных, определенной в таблице или представлении базы данных или списке столбцов SELECT.</span><span class="sxs-lookup"><span data-stu-id="2cd84-118">Bulk-copy methods that process data (for example, [IBCPSession::BCPExec](ibcpsession-bcpexec-ole-db.md)) parse data rows expecting the length of the data in the data file to be identical to the length of the data specified in the database table, view, or SELECT column list.</span></span> <span data-ttu-id="2cd84-119">Например, данные в столбце базы данных, определенные как `char(13)`, должны быть представлены в виде 13 символов для каждой строки данных в файле.</span><span class="sxs-lookup"><span data-stu-id="2cd84-119">For example, data for a database column defined as `char(13)` must be represented by 13 characters for each row of data in the file.</span></span> <span data-ttu-id="2cd84-120">Данные фиксированной длины могут быть обозначены префиксом с признаком значения NULL, если столбец базы данных допускает значения NULL.</span><span class="sxs-lookup"><span data-stu-id="2cd84-120">Fixed-length data can be prefixed with a null indicator if the database column allows null values.</span></span>  
  
-   <span data-ttu-id="2cd84-121">При копировании данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файл данных должен содержать данные для каждого столбца в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="2cd84-121">When copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data file must have data for each column in the database table.</span></span> <span data-ttu-id="2cd84-122">При копировании данных из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] данные из всех столбцов таблицы, представления или результирующего набора SELECT базы данных копируются в файл данных.</span><span class="sxs-lookup"><span data-stu-id="2cd84-122">When copying data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data from all columns in the database table, view, or SELECT result set are copied to the data file.</span></span>  
  
-   <span data-ttu-id="2cd84-123">При копировании данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] порядковый номер столбца в файле данных должен совпадать с порядковым номером столбца в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="2cd84-123">When copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the ordinal position of a column in the data file must be identical to the ordinal position of the column in the database table.</span></span> <span data-ttu-id="2cd84-124">При копировании из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] метод **BCPExec** размещает данные, исходя из порядкового номера столбца в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="2cd84-124">When copying data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the **BCPExec** method places data based on the ordinal position of the column in the database table.</span></span>  
  
-   <span data-ttu-id="2cd84-125">Если тип данных в базе данных является типом с переменной длиной (например, `varbinary(22)`), или если столбец базы данных может содержать значения NULL, данные в файле данных предваряются признаком длины и допустимости значений NULL.</span><span class="sxs-lookup"><span data-stu-id="2cd84-125">If a database data type is variable in length (for example, `varbinary(22)`) or if a database column can contain null values, data in the data file is prefixed by a length/null indicator.</span></span> <span data-ttu-id="2cd84-126">Ширина признака изменяется в зависимости от типа данных и версии массового копирования.</span><span class="sxs-lookup"><span data-stu-id="2cd84-126">The width of the indicator varies based on the data type and version of bulk copy.</span></span> <span data-ttu-id="2cd84-127">Параметр BCP_OPTION_FILEFMT метода [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) обеспечивает совместимость между более ранними файлами данных для массового копирования и серверами с более новыми версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], указывая, когда ширина признаков в данных меньше, чем ожидаемая.</span><span class="sxs-lookup"><span data-stu-id="2cd84-127">The [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) method option BCP_OPTION_FILEFMT provides compatibility between earlier bulk-copy data files and servers running later versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by indicating when the width of indicators in the data is narrower than expected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2cd84-128">Чтобы изменить значения форматов данных, указанные для файла данных, используйте методы [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) и [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="2cd84-128">To change the data format values specified for a data file, use the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods.</span></span>  
  
 <span data-ttu-id="2cd84-129">Для таблиц, не содержащих индексы, можно оптимизировать массовое копирование в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], установив параметр базы данных **select into/bulkcopy**.</span><span class="sxs-lookup"><span data-stu-id="2cd84-129">Bulk copies to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be optimized for tables that do not contain indexes by setting the database option **select into/bulkcopy**.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="2cd84-130">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2cd84-130">Arguments</span></span>  
 <span data-ttu-id="2cd84-131">*pwszTable*[IN]</span><span class="sxs-lookup"><span data-stu-id="2cd84-131">*pwszTable*[in]</span></span>  
 <span data-ttu-id="2cd84-132">Имя таблицы базы данных, в которую или из которой выполняется копирование.</span><span class="sxs-lookup"><span data-stu-id="2cd84-132">The name of the database table to be copied into or out of.</span></span> <span data-ttu-id="2cd84-133">Имя может включать имя базы данных или имя владельца.</span><span class="sxs-lookup"><span data-stu-id="2cd84-133">The name can include the database name or the owner name.</span></span> <span data-ttu-id="2cd84-134">Примеры: «pubs.username.titles», «pubs..titles», «username.titles».</span><span class="sxs-lookup"><span data-stu-id="2cd84-134">For example, "pubs.username.titles", "pubs..titles", "username.titles".</span></span>  
  
 <span data-ttu-id="2cd84-135">Если аргумент eDirection имеет значение BCP_DIRECTION_OUT, аргумент pwszTable может являться именем представления базы данных.</span><span class="sxs-lookup"><span data-stu-id="2cd84-135">If the eDirection argument is set to BCP_DIRECTION_OUT, the pwszTable argument can be the name of a database view.</span></span>  
  
 <span data-ttu-id="2cd84-136">Если аргумент eDirection имеет значение BCP_DIRECTION_OUT и инструкция SELECT указана с помощью метода **BCPControl** перед вызовом метода **BCPExec**, аргумент *pwszTable* должен иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="2cd84-136">If the eDirection argument is set to BCP_DIRECTION_OUT and a SELECT statement is specified using the **BCPControl** method before the **BCPExec** method is called, the *pwszTable* argument must be set to NULL.</span></span>  
  
 <span data-ttu-id="2cd84-137">*pwszDataFile*[IN]</span><span class="sxs-lookup"><span data-stu-id="2cd84-137">*pwszDataFile*[in]</span></span>  
 <span data-ttu-id="2cd84-138">Имя пользовательского файла, в который или из которого выполняется копирование.</span><span class="sxs-lookup"><span data-stu-id="2cd84-138">The name of the user file to be copied into or out of.</span></span>  
  
 <span data-ttu-id="2cd84-139">*pwszErrorFile*[IN]</span><span class="sxs-lookup"><span data-stu-id="2cd84-139">*pwszErrorFile*[in]</span></span>  
 <span data-ttu-id="2cd84-140">Имя файла ошибок, который заполняется сообщениями о ходе выполнения, сообщениями об ошибках и копиями строк, которые не удалось скопировать из пользовательского файла в таблицу.</span><span class="sxs-lookup"><span data-stu-id="2cd84-140">The name of the error file to be filled with progress messages, error messages, and copies of any rows that could not be copied from a user file to a table.</span></span> <span data-ttu-id="2cd84-141">Если аргумент *pwszErrorFile* имеет значение NULL, файл ошибок не используется.</span><span class="sxs-lookup"><span data-stu-id="2cd84-141">If the *pwszErrorFile* argument is set to NULL, no error file is used.</span></span>  
  
 <span data-ttu-id="2cd84-142">*eDirection*[IN]</span><span class="sxs-lookup"><span data-stu-id="2cd84-142">*eDirection*[in]</span></span>  
 <span data-ttu-id="2cd84-143">Направление операции копирования: BCP_DIRECTION_IN или BCP_DIRECTION _OUT.</span><span class="sxs-lookup"><span data-stu-id="2cd84-143">The direction of the copy operation, either BCP_DIRECTION_IN or BCP_DIRECTION _OUT.</span></span> <span data-ttu-id="2cd84-144">BCP_DIRECTION _IN обозначает копирование из пользовательского файла в таблицу базы данных; BCP_DIRECTION _OUT обозначает копирование из таблицы базы данных в пользовательский файл.</span><span class="sxs-lookup"><span data-stu-id="2cd84-144">BCP_DIRECTION _IN indicates a copy from a user file to a database table; BCP_DIRECTION _OUT indicates a copy from a database table to a user file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="2cd84-145">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="2cd84-145">Return Code Values</span></span>  
 <span data-ttu-id="2cd84-146">S_OK</span><span class="sxs-lookup"><span data-stu-id="2cd84-146">S_OK</span></span>  
 <span data-ttu-id="2cd84-147">Метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="2cd84-147">The method succeeded.</span></span>  
  
 <span data-ttu-id="2cd84-148">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2cd84-148">E_FAIL</span></span>  
 <span data-ttu-id="2cd84-149">Произошла ошибка, специфическая для поставщика. для получения подробных сведений используйте интерфейс [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="2cd84-149">A provider specific error occurred' for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="2cd84-150">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2cd84-150">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2cd84-151">Недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="2cd84-151">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="2cd84-152">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2cd84-152">E_INVALIDARG</span></span>  
 <span data-ttu-id="2cd84-153">Один или несколько аргументов были указаны неправильно.</span><span class="sxs-lookup"><span data-stu-id="2cd84-153">One or more of the arguments was not correctly specified.</span></span> <span data-ttu-id="2cd84-154">Например, указано недопустимое имя файла.</span><span class="sxs-lookup"><span data-stu-id="2cd84-154">For example, an invalid file name was given.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd84-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="2cd84-155">See Also</span></span>  
 <span data-ttu-id="2cd84-156">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="2cd84-156">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="2cd84-157">Выполнение операций массового копирования</span><span class="sxs-lookup"><span data-stu-id="2cd84-157">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
