---
title: Частичное обновление данных FILESTREAM | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
- FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
ms.assetid: d6f7661e-6c14-4d31-9541-4520ca0f82b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 696c1a6421e14568877e24f015e5094395f1051b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740034"
---
# <a name="make-partial-updates-to-filestream-data"></a><span data-ttu-id="35f53-102">Создание частичных обновлений данных FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="35f53-102">Make Partial Updates to FILESTREAM Data</span></span>
  <span data-ttu-id="35f53-103">Приложение использует команду FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT для выполнения частичных обновлений в данных FILESTREAM BLOB.</span><span class="sxs-lookup"><span data-stu-id="35f53-103">An application uses FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT to make partial updates to FILESTREAM BLOB data.</span></span> <span data-ttu-id="35f53-104">Функция [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) передает это значение и дескриптор, возвращаемый функцией [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) драйверу FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="35f53-104">The [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) function passes this value and the handle that is returned from [OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) to the FILESTREAM driver.</span></span> <span data-ttu-id="35f53-105">Затем драйвер принудительно реализует копирование на стороне сервера текущих данных FILESTREAM в файл, упоминаемый в дескрипторе.</span><span class="sxs-lookup"><span data-stu-id="35f53-105">The driver then forces a server-side copy of the current FILESTREAM data into the file that is referenced by the handle.</span></span> <span data-ttu-id="35f53-106">Если приложение выдает значение для команды FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT после того, как была произведена запись в дескриптор, то последняя операция записи будет зафиксирована, а предыдущие операции записи в дескриптор будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="35f53-106">If the application issues the FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT value after the handle has been written to, the last write operation persists and previous write operations that were made to the handle are lost.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35f53-107">Для удаленного доступа FILESTREAM использует [протокол SMB](https://go.microsoft.com/fwlink/?LinkId=112454) .</span><span class="sxs-lookup"><span data-stu-id="35f53-107">FILESTREAM relies on the [SMB protocol](https://go.microsoft.com/fwlink/?LinkId=112454) for remote access.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35f53-108">Пример</span><span class="sxs-lookup"><span data-stu-id="35f53-108">Example</span></span>  
 <span data-ttu-id="35f53-109">В следующем примере показывается, как можно использовать значение команды `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` для выполнения частичного обновления вставленных данных FILESTREAM BLOB.</span><span class="sxs-lookup"><span data-stu-id="35f53-109">The following example shows you how to use the `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` value to perform a partial update of an inserted FILESTREAM BLOB.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35f53-110">Для этого примера требуется база данных с поддержкой FILESTREAM и таблица, которая создана в разделе [Создание базы данных с поддержкой FILESTREAM](create-a-filestream-enabled-database.md) и [Создание таблицы для хранения данных FILESTREAM](create-a-table-for-storing-filestream-data.md).</span><span class="sxs-lookup"><span data-stu-id="35f53-110">This example requires the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
 [!code-cpp[FILESTREAM#FS_CPP_FSCTL](../../snippets/tsql/SQL15/tsql/filestream/cpp/filestream.cpp#fs_cpp_fsctl)]  
  
## <a name="see-also"></a><span data-ttu-id="35f53-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="35f53-111">See Also</span></span>  
 <span data-ttu-id="35f53-112">[Доступ к данным FILESTREAM с OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="35f53-112">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="35f53-113">Создание клиентских приложений для данных FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="35f53-113">Create Client Applications for FILESTREAM Data</span></span>](create-client-applications-for-filestream-data.md)  
  
  
