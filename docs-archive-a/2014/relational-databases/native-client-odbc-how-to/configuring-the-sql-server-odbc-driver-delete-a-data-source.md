---
title: Удаление источника данных (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: 910e3e16-7b91-49d8-80bb-b4243926afaa
author: rothja
ms.author: jroth
ms.openlocfilehash: 6e8acd6414b39b317ff0fcfe1b7b9fbab38ae0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657757"
---
# <a name="delete-a-data-source-odbc"></a><span data-ttu-id="ea532-102">Удаление источника данных (ODBC)</span><span class="sxs-lookup"><span data-stu-id="ea532-102">Delete a Data Source (ODBC)</span></span>
  <span data-ttu-id="ea532-103">Источник данных можно удалить с помощью администратора ODBC, программно (с помощью [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) или путем удаления файла (если имя источника данных файла).</span><span class="sxs-lookup"><span data-stu-id="ea532-103">You can delete a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by deleting a file (if a file data source name).</span></span>  
  
### <a name="to-delete-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="ea532-104">Удаление источника данных с помощью администратора ODBC</span><span class="sxs-lookup"><span data-stu-id="ea532-104">To delete a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="ea532-105">На **панели управления**откройте **Администрирование**, а затем дважды щелкните элемент **Источники данных (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="ea532-105">In **Control Panel**, open **Administrative Tools**, and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="ea532-106">Либо можно запустить файл odbcad32.exe из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ea532-106">Alternatively, you can run odbcad32.exe from the command prompt.</span></span>  
  
2.  <span data-ttu-id="ea532-107">Щелкните вкладку **DSN пользователя**, **системное имя DSN**или **Файловый DSN** .</span><span class="sxs-lookup"><span data-stu-id="ea532-107">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="ea532-108">Щелкните источник данных, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="ea532-108">Click the data source to delete.</span></span>  
  
4.  <span data-ttu-id="ea532-109">Нажмите кнопку **Удалить**, а затем подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="ea532-109">Click **Remove**, and then confirm the deletion.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea532-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ea532-110">Example</span></span>  
 <span data-ttu-id="ea532-111">Чтобы программно удалить источник данных, вызовите [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) , используя либо ODBC_REMOVE_DSN, либо ODBC_REMOVE_SYS_DSN в качестве второго параметра.</span><span class="sxs-lookup"><span data-stu-id="ea532-111">To programmatically delete a data source, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) using either ODBC_REMOVE_DSN or ODBC_REMOVE_SYS_DSN as the second parameter.</span></span>  
  
 <span data-ttu-id="ea532-112">В следующем образце показана процедура удаления источника данных программным способом.</span><span class="sxs-lookup"><span data-stu-id="ea532-112">The following sample shows how you can programmatically delete a data source.</span></span>  
  
```  
// remove_odbc_data_source.cpp  
// compile with: ODBCCP32.lib user32.lib  
#include <iostream>  
#include <windows.h>  
#include <odbcinst.h>  
  
int main() {   
   LPCSTR provider = "SQL Server";   // Windows SQL Server Driver  
   LPCSTR provider = "SQL Server";   // Windows SQL Server driver  
   LPCSTR provider2 = "SQL Server Native Client 11.0";   // SQL Server 2012 Native Client driver  
   LPCSTR dsnname = "DSN=data2";  
   BOOL retval = SQLConfigDataSource(NULL, ODBC_REMOVE_DSN, provider, dsnname);  
   std::cout << retval;   // 1 if successful  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea532-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea532-113">See Also</span></span>  
 [<span data-ttu-id="ea532-114">Инструкции по настройке драйвера ODBC SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea532-114">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
