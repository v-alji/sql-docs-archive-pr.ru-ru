---
title: Коды возврата и сведения об ошибках OLE-автоматизации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- return codes [SQL Server]
- OLE Automation [SQL Server], return codes
- OLE Automation [SQL Server], errors
ms.assetid: 9696fb05-e9e8-4836-b359-d4de0be0eeb2
author: stevestein
ms.author: sstein
ms.openlocfilehash: aecdbaedca42b7456dbdbda0407760959e546f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669379"
---
# <a name="ole-automation-return-codes-and-error-information"></a><span data-ttu-id="3e468-102">Коды возврата и сведения об ошибках OLE-автоматизации</span><span class="sxs-lookup"><span data-stu-id="3e468-102">OLE Automation Return Codes and Error Information</span></span>
  <span data-ttu-id="3e468-103">Системные хранимые процедуры OLE-автоматизации возвращают код возврата типа `int`, который представляет собой значение HRESULT, возвращенное базовой операцией OLE-автоматизации.</span><span class="sxs-lookup"><span data-stu-id="3e468-103">The OLE Automation system stored procedures return an `int` return code that is the HRESULT returned by the underlying OLE Automation operation.</span></span> <span data-ttu-id="3e468-104">Значение HRESULT, равное 0, свидетельствует об успешном завершении операции.</span><span class="sxs-lookup"><span data-stu-id="3e468-104">An HRESULT of 0 indicates success.</span></span> <span data-ttu-id="3e468-105">Ненулевое значение HRESULT — это код ошибки OLE в шестнадцатеричной форме 0x800*nnnnn*, но при возвращении `int` в виде значения в коде возврата хранимой процедуры значение HRESULT имеет форму 214*ннннннн*.</span><span class="sxs-lookup"><span data-stu-id="3e468-105">A nonzero HRESULT is an OLE error code of the hexadecimal form 0x800*nnnnn*, but when returned as an `int` value in a stored procedure return code, HRESULT has the form 214*nnnnnnn*.</span></span>  
  
 <span data-ttu-id="3e468-106">Например, Передача недопустимого имени объекта (SQLDMO. Xyzzy) в sp_OACreate приводит к тому, что процедура возвращает `int` значение HRESULT 2147221005, которое 0x800401f3 в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="3e468-106">For example, passing an invalid object name (SQLDMO.Xyzzy) to sp_OACreate causes the procedure to return an `int` HRESULT of 2147221005, which is 0x800401f3 in hexadecimal.</span></span>  
  
 <span data-ttu-id="3e468-107">Процедуру `CONVERT(binary(4), @hresult)` можно использовать для преобразования значения HRESULT с типом `int` в значение с типом `binary`.</span><span class="sxs-lookup"><span data-stu-id="3e468-107">You can use `CONVERT(binary(4), @hresult)` to convert an `int` HRESULT to a `binary` value.</span></span> <span data-ttu-id="3e468-108">Однако в результате вызова `CONVERT(char(10), CONVERT(binary(4), @hresult))` будет получена нечитаемая строка, потому что каждый байт значения HRESULT будет преобразован в один символ ASCII.</span><span class="sxs-lookup"><span data-stu-id="3e468-108">However, using `CONVERT(char(10), CONVERT(binary(4), @hresult))` results in an unreadable string, because each byte of the HRESULT is converted to a single ASCII character.</span></span> <span data-ttu-id="3e468-109">Следующий пример хранимой процедуры HexToChar можно использовать для преобразования `int` HRESULT в `char` значение, которое содержит шестнадцатеричную строку, доступную для чтения.</span><span class="sxs-lookup"><span data-stu-id="3e468-109">You can use the following sample HexToChar stored procedure to convert an `int` HRESULT to a `char` value that contains a readable hexadecimal string.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF EXISTS(SELECT name FROM sys.objects  
          WHERE name = N'dbo.sp_HexToChar')  
    DROP PROCEDURE HexToChar;  
GO  
CREATE PROCEDURE dbo.sp_HexToChar  
    @BinValue varbinary(255),  
    @HexCharValue nvarchar(255) OUTPUT  
AS  
    DECLARE @CharValue nvarchar(255);  
    DECLARE @Position int;  
    DECLARE @Length int;  
    DECLARE @HexString nchar(16);  
    SELECT @CharValue = N'0x';  
    SELECT @Position = 1;  
    SELECT @Length = DATALENGTH(@BinValue);  
    SELECT @HexString = N'0123456789ABCDEF';  
    WHILE (@Position <= @Length)  
    BEGIN  
        DECLARE @TempInt int;  
        DECLARE @FirstInt int;  
        DECLARE @SecondInt int;  
        SELECT @TempInt = CONVERT(int, SUBSTRING(@BinValue,@Position,1));  
        SELECT @FirstInt = FLOOR(@TempInt/16);  
        SELECT @SecondInt = @TempInt - (@FirstInt*16);  
        SELECT @CharValue = @CharValue +  
            SUBSTRING(@HexString, @FirstInt+1, 1) +  
            SUBSTRING(@HexString, @SecondInt+1, 1);  
        SELECT @Position = @Position + 1;  
    END  
    SELECT @HexCharValue = @CharValue;  
GO  
DECLARE @BinVariable varbinary(35);  
DECLARE @CharValue nvarchar(35);  
  
SET @BinVariable = 123456;  
  
EXECUTE dbo.sp_HexToChar  
    @binvalue = @BinVariable,  
    @HexCharValue = @CharValue OUTPUT;  
  
SELECT @BinVariable AS BinaryValue,  
    @CharValue AS CharacterRep;  
GO  
```  
  
 <span data-ttu-id="3e468-110">Приведенный ниже образец хранимой процедуры **sp_displayoaerrorinfo** позволяет вывести сведения об ошибке OLE-автоматизации, если одна из процедур OLE-автоматизации возвратит ненулевой код возврата HRESULT.</span><span class="sxs-lookup"><span data-stu-id="3e468-110">You can use the following sample stored procedure, **sp_displayoaerrorinfo** to display OLE Automation error information when one of the OLE Automation procedures returns a nonzero HRESULT return code.</span></span> <span data-ttu-id="3e468-111">В этом образце хранимой процедуры используется `HexToChar` .</span><span class="sxs-lookup"><span data-stu-id="3e468-111">This sample stored procedure uses `HexToChar`.</span></span>  
  
```  
CREATE PROCEDURE dbo.sp_DisplayOAErrorInfo  
    @Object int,  
    @HResult int  
AS  
    DECLARE @Output nvarchar(255);  
    DECLARE @HRHex nchar(10);  
    DECLARE @HR int;  
    DECLARE @Source nvarchar(255);  
    DECLARE @Description nvarchar(255);  
    PRINT N'OLE Automation Error Information';  
    EXEC HexToChar @HResult, @HRHex OUT;  
    SELECT @Output = N'  HRESULT: ' + @HRHex;  
    PRINT @Output;  
    EXEC @HR = sp_OAGetErrorInfo  
        @Object,  
        @Source OUT,  
        @Description OUT;  
    IF @HR = 0  
    BEGIN  
        SELECT @Output = N'  Source: ' + @Source;  
        PRINT @Output;  
        SELECT @Output = N'  Description: '  
               + @Description;  
        PRINT @Output;  
    END  
    ELSE  
    BEGIN  
       PRINT N' sp_OAGetErrorInfo failed.';  
       RETURN;  
    END  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="3e468-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3e468-112">Related Content</span></span>  
 [<span data-ttu-id="3e468-113">sp_OAGetErrorInfo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3e468-113">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql)  
  
  
