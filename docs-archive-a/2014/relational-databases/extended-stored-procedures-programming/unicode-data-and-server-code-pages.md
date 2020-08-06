---
title: Данные в Юникоде и кодовые страницы сервера | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- metadata [SQL Server], stored procedures
- Unicode [SQL Server], extended stored procedures
- extended stored procedures [SQL Server], metadata
ms.assetid: 52310260-a892-4b27-ad2e-bf164b98ee80
author: rothja
ms.author: jroth
ms.openlocfilehash: e88a43ee242e9fa84ac3a5573c7d3ca3dc0369d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654283"
---
# <a name="unicode-data-and-server-code-pages"></a><span data-ttu-id="c0572-102">Данные в Юникоде и кодовые страницы сервера</span><span class="sxs-lookup"><span data-stu-id="c0572-102">Unicode Data and Server Code Pages</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="c0572-103">Пользуйтесь вместо этого интеграцией со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="c0572-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="c0572-104">API-интерфейс расширенных хранимых процедур разрешает использовать данные в кодировке Юникод, однако он не распознает метаданные в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="c0572-104">The Extended Stored Procedure API is enabled for Unicode data; however, it is not enabled for Unicode metadata.</span></span> <span data-ttu-id="c0572-105">Директива #define Unicode не влияет на API-интерфейс расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="c0572-105">The #define Unicode directive does not have any effect on the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="c0572-106">Все метаданные, возвращаемые API-интерфейсом расширенных хранимых процедур или предоставляемые ему из приложения расширенных хранимых процедур, должны быть в многобайтовой кодовой странице сервера.</span><span class="sxs-lookup"><span data-stu-id="c0572-106">All metadata returned by, or provided to the Extended Stored Procedure API by your extended stored procedure application is assumed to be in the multibyte code page of the server.</span></span> <span data-ttu-id="c0572-107">Кодовая страница по умолчанию для серверного приложения API расширенных хранимых процедур представляет собой кодовую страницу ANSI компьютера, на котором работает приложение, что может быть получено путем вызова **SRV_PFIELD** с параметром поля, для которого задано значение SRV_SPROC_CODEPAGE.</span><span class="sxs-lookup"><span data-stu-id="c0572-107">The default code page of an Extended Stored Procedure API server application is the ANSI code page of the computer on which the application is running, which can be obtained by calling **srv_pfield** with the field parameter set to SRV_SPROC_CODEPAGE.</span></span>  
  
 <span data-ttu-id="c0572-108">Если приложение API-интерфейса расширенных хранимых процедур поддерживает Юникод, необходимо преобразовать имена столбцов метаданных, сообщения об ошибках и т. д. в Юникоде в многобайтовые данные, прежде чем передавать эти данные в API-интерфейс расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="c0572-108">If your Extended Stored Procedure API application is Unicode-enabled, you must convert your Unicode metadata column names, error messages, and so on, to multibyte data before passing this data to the Extended Stored Procedure API.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0572-109">Пример</span><span class="sxs-lookup"><span data-stu-id="c0572-109">Example</span></span>  
 <span data-ttu-id="c0572-110">В следующей расширенной хранимой процедуре приведен пример указанного преобразования Юникода.</span><span class="sxs-lookup"><span data-stu-id="c0572-110">The following extended stored procedure provides an example of the Unicode conversions discussed.</span></span> <span data-ttu-id="c0572-111">Обратите внимание на следующее.</span><span class="sxs-lookup"><span data-stu-id="c0572-111">Note that:</span></span>  
  
-   <span data-ttu-id="c0572-112">Данные столбца передаются в виде данных в Юникоде в **srv_describe** , так как столбец ОПИСАН как срвнварчар.</span><span class="sxs-lookup"><span data-stu-id="c0572-112">Column data is passed as Unicode data to **srv_describe** because the column is described to be SRVNVARCHAR.</span></span>  
  
-   <span data-ttu-id="c0572-113">Метаданные имени столбца передаются в **srv_describe** в виде многобайтовых данных.</span><span class="sxs-lookup"><span data-stu-id="c0572-113">Column name metadata is passed to **srv_describe** as multibyte data.</span></span>  
  
     <span data-ttu-id="c0572-114">Расширенная хранимая процедура вызывает **SRV_PFIELD** с параметром поля, для которого задано значение SRV_SPROC_CODEPAGE, чтобы получить многобайтовую кодовую страницу из [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0572-114">The extended stored procedure calls **srv_pfield** with the field parameter set to SRV_SPROC_CODEPAGE to obtain the multibyte code page of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="c0572-115">Сообщения об ошибках передаются в **srv_sendmsg** в виде многобайтовых данных.</span><span class="sxs-lookup"><span data-stu-id="c0572-115">Error messages are passed to **srv_sendmsg** as multibyte data.</span></span>  
  
    ```  
    __declspec(dllexport) RETCODE proc1 (SRV_PROC *srvproc)  
    {  
        #define MAX_COL_NAME_LEN 25  
        #define MAX_COL_DATA_LEN 50  
        #define MAX_ERR_MSG_LEN 250  
        #define MAX_SERVER_ERROR 20000  
        #define XP_ERROR_NUMBER MAX_SERVER_ERROR+1  
  
        int retval;  
        UINT serverCodePage;  
        CHAR *szServerCodePage;  
  
        WCHAR unicodeColumnName[MAX_COL_NAME_LEN];  
        CHAR multibyteColumnName[MAX_COL_NAME_LEN];  
  
        WCHAR unicodeColumnData[MAX_COL_DATA_LEN];  
  
        WCHAR unicodeErrorMessage[MAX_ERR_MSG_LEN];  
        CHAR  multibyteErrorMessage[MAX_ERR_MSG_LEN];  
  
        lstrcpyW (unicodeColumnName, L"column1");  
        lstrcpyW (unicodeColumnData, L"column1 data");  
        lstrcpyW (unicodeErrorMessage, L"No Error!");  
  
        // Obtain server code page.  
        //  
        szServerCodePage = srv_pfield (srvproc, SRV_SPROC_CODEPAGE, NULL);      
        if (NULL != szServerCodePage)  
            serverCodePage = atol(szServerCodePage);  
        else   
        {   // Problem situation exists.  
            srv_senddone(srvproc, (SRV_DONE_ERROR | SRV_DONE_MORE), 0, 0);  
            return 1;  
        }  
  
        // Convert column name for Unicode to multibyte using the   
        // server code page.  
        //  
        retval = WideCharToMultiByte(    
            serverCodePage,                 // code page  
            0,                              // default  
            unicodeColumnName,              // wide-character string  
            -1,                             // string is null terminated  
            multibyteColumnName,            // address of buffer for new  
                                            //   string  
            sizeof (multibyteColumnName),   // size of buffer  
            NULL, NULL);  
  
        if (0 == retval)  
        {  
            lstrcpyW (unicodeErrorMessage, L"Conversion to multibyte  
            failed.");  
            goto Error;  
        }  
  
        retval = srv_describe (srvproc, 1, multibyteColumnName,  
        SRV_NULLTERM,   
          SRVNVARCHAR, MAX_COL_DATA_LEN*sizeof(WCHAR), // destination  
            SRVNVARCHAR, lstrlenW(unicodeColumnData)*sizeof(WCHAR),  
            unicodeColumnData); //source  
        if (FAIL == retval)  
        {  
            lstrcpyW (unicodeErrorMessage, L"srv_describe failed.");  
            goto Error;  
        }  
  
       retval = srv_sendrow(srvproc);  
        if (FAIL == retval)  
        {  
            lstrcpyW (unicodeErrorMessage, L"srv_sendrow failed.");  
            goto Error;  
        }  
  
        retval = srv_senddone (srvproc, SRV_DONE_MORE|SRV_DONE_COUNT, 0, 1);  
        if (FAIL == retval)  
        {  
            lstrcpyW (unicodeErrorMessage, L"srv_senddone failed.");  
            goto Error;  
        }  
  
        return 0;  
    Error:  
        // convert error message from Unicode to multibyte.  
        retval = WideCharToMultiByte(    
            serverCodePage,                 // code page  
            0,                              // default  
            unicodeErrorMessage,            // wide-character string  
            -1,                             // string is null terminated  
            multibyteErrorMessage,          // address of buffer for new  
                                            //   string  
            sizeof (multibyteErrorMessage), // size of buffer  
            NULL, NULL);  
  
    srv_sendmsg(srvproc, SRV_MSG_ERROR, XP_ERROR_NUMBER, SRV_INFO, 1,  
                NULL, 0, __LINE__,   
                multibyteErrorMessage,  
                SRV_NULLTERM);  
  
        srv_senddone(srvproc, (SRV_DONE_ERROR | SRV_DONE_MORE), 0, 0);  
  
        return 1;  
    }  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c0572-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0572-116">See Also</span></span>  
 [<span data-ttu-id="c0572-117">API srv_wsendmsg &#40;расширенных хранимых процедур&#41;</span><span class="sxs-lookup"><span data-stu-id="c0572-117">srv_wsendmsg &#40;Extended Stored Procedure API&#41;</span></span>](../extended-stored-procedures-reference/srv-wsendmsg-extended-stored-procedure-api.md)  
  
  
