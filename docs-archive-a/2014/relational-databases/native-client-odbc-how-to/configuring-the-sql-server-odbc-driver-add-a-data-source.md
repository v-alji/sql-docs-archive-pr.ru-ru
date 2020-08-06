---
title: Добавление источника данных (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: b4ac6f0e-8e6a-4b1a-9a7e-60e0a69b2180
author: rothja
ms.author: jroth
ms.openlocfilehash: 519990e9dd9d84f75c4efc6c76b910f0a359f52f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657759"
---
# <a name="add-a-data-source-odbc"></a><span data-ttu-id="c6350-102">Добавление источника данных (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c6350-102">Add a Data Source (ODBC)</span></span>
  <span data-ttu-id="c6350-103">Источник данных можно добавить с помощью администратора ODBC, программно (с помощью [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) или путем создания файла.</span><span class="sxs-lookup"><span data-stu-id="c6350-103">You can add a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by creating a file.</span></span>  
  
### <a name="to-add-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="c6350-104">Добавление источника данных при помощи администратора ODBC</span><span class="sxs-lookup"><span data-stu-id="c6350-104">To add a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="c6350-105">В **панели управления**откройте **меню Администрирование** и выберите пункт **Источники данных (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="c6350-105">From the **Control Panel**, access **Administrative Tools** and then **Data Sources (ODBC)**.</span></span> <span data-ttu-id="c6350-106">Можно также вызвать программу odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="c6350-106">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="c6350-107">Щелкните вкладку **DSN пользователя**, **системное имя DSN**или **Файловый DSN** , а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c6350-107">Click the **User DSN**, **System DSN**, or **File DSN** tab, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="c6350-108">Щелкните **SQL Server**и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c6350-108">Click **SQL Server**, and then click **Finish**.</span></span>  
  
4.  <span data-ttu-id="c6350-109">Выполните шаги по созданию нового источника данных в мастере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6350-109">Complete the Steps in the Create a New Data Source to SQL Server Wizard.</span></span>  
  
### <a name="to-add-a-data-source-programmatically"></a><span data-ttu-id="c6350-110">Добавление источника данных программно</span><span class="sxs-lookup"><span data-stu-id="c6350-110">To add a data source programmatically</span></span>  
  
1.  <span data-ttu-id="c6350-111">Вызовите [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) со вторым параметром, имеющим значение ODBC_ADD_DSN или ODBC_ADD_SYS_DSN.</span><span class="sxs-lookup"><span data-stu-id="c6350-111">Call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) with the second parameter set to either ODBC_ADD_DSN or ODBC_ADD_SYS_DSN.</span></span>  
  
### <a name="to-add-a-file-data-source"></a><span data-ttu-id="c6350-112">Добавление файла источника данных</span><span class="sxs-lookup"><span data-stu-id="c6350-112">To add a file data source</span></span>  
  
1.  <span data-ttu-id="c6350-113">Вызовите [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) с параметром SAVEFILE = file_name в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="c6350-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) with a SAVEFILE=file_name parameter in the connect string.</span></span> <span data-ttu-id="c6350-114">Если соединение успешно, драйвер ODBC создаст файл источника данных с параметрами соединения, место расположения которого указано параметром SAVEFILE.</span><span class="sxs-lookup"><span data-stu-id="c6350-114">If the connect is successful, the ODBC driver creates a file data source with the connection parameters in the location pointed to by the SAVEFILE parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6350-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="c6350-115">See Also</span></span>  
 [<span data-ttu-id="c6350-116">Инструкции по настройке драйвера ODBC SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6350-116">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
