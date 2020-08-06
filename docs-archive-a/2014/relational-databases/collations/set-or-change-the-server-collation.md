---
title: Установка и изменение параметров сортировки для сервера| Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- server collations [SQL Server]
- collations [SQL Server], server
ms.assetid: 3242deef-6f5f-4051-a121-36b3b4da851d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7be051c8cf63a272f2bf42fb54b1c45ed4160
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668911"
---
# <a name="set-or-change-the-server-collation"></a><span data-ttu-id="b4bba-102">Задание или изменение параметров сортировки сервера</span><span class="sxs-lookup"><span data-stu-id="b4bba-102">Set or Change the Server Collation</span></span>
  <span data-ttu-id="b4bba-103">Параметры сортировки сервера применяются по умолчанию для всех установленных системных баз данных с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], а также для новых пользовательских баз данных.</span><span class="sxs-lookup"><span data-stu-id="b4bba-103">The server collation acts as the default collation for all system databases that are installed with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and also any newly created user databases.</span></span> <span data-ttu-id="b4bba-104">Параметры сортировки сервера задаются во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4bba-104">The server collation is specified during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="b4bba-105">Дополнительные сведения см. в статье [Collation and Unicode Support](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="b4bba-105">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
## <a name="changing-the-server-collation"></a><span data-ttu-id="b4bba-106">Изменение параметров сортировки сервера</span><span class="sxs-lookup"><span data-stu-id="b4bba-106">Changing the Server Collation</span></span>  
 <span data-ttu-id="b4bba-107">Чтобы изменить параметры сортировки по умолчанию для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (эта операция может оказаться сложной), выполните следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="b4bba-107">Changing the default collation for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be a complex operation and involves the following steps:</span></span>  
  
-   <span data-ttu-id="b4bba-108">Проверьте наличие данных и скриптов, необходимых для повторного создания пользовательской базы данных и всех ее объектов.</span><span class="sxs-lookup"><span data-stu-id="b4bba-108">Make sure you have all the information or scripts needed to re-create your user databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="b4bba-109">Экспортируйте все данные с помощью такого средства, как [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b4bba-109">Export all your data using a tool such as the [bcp Utility](../../tools/bcp-utility.md).</span></span> <span data-ttu-id="b4bba-110">Дополнительные сведения см. в разделе [Массовый импорт и экспорт данных (SQL Server)](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4bba-110">For more information, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
-   <span data-ttu-id="b4bba-111">Удалите все пользовательские базы данных.</span><span class="sxs-lookup"><span data-stu-id="b4bba-111">Drop all the user databases.</span></span>  
  
-   <span data-ttu-id="b4bba-112">Перестройте базу данных master, указав новые параметры сортировки в свойстве SQLCOLLATION команды **setup** .</span><span class="sxs-lookup"><span data-stu-id="b4bba-112">Rebuild the master database specifying the new collation in the SQLCOLLATION property of the **setup** command.</span></span> <span data-ttu-id="b4bba-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="b4bba-113">For example:</span></span>  
  
    ```  
    Setup /QUIET /ACTION=REBUILDDATABASE /INSTANCENAME=InstanceName   
    /SQLSYSADMINACCOUNTS=accounts /[ SAPWD= StrongPassword ]   
    /SQLCOLLATION=CollationName  
    ```  
  
     <span data-ttu-id="b4bba-114">Дополнительные сведения см. в разделе [Перестроение системных баз данных](../databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b4bba-114">For more information, see [Rebuild System Databases](../databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="b4bba-115">Создайте все базы данных и все их объекты.</span><span class="sxs-lookup"><span data-stu-id="b4bba-115">Create all the databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="b4bba-116">Импортируйте все данные.</span><span class="sxs-lookup"><span data-stu-id="b4bba-116">Import all your data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4bba-117">Вместо изменения параметров сортировки по умолчанию для всего экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]можно указывать параметры сортировки по умолчанию для каждой новой базы данных.</span><span class="sxs-lookup"><span data-stu-id="b4bba-117">Instead of changing the default collation of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can specify a default collation for each new database you create.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4bba-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4bba-118">See Also</span></span>  
 <span data-ttu-id="b4bba-119">[Поддержка параметров сортировки и Юникода](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="b4bba-119">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="b4bba-120">[Установка и изменение параметров сортировки базы данных](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="b4bba-120">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 <span data-ttu-id="b4bba-121">[Задание или изменение параметров сортировки столбца](set-or-change-the-column-collation.md) </span><span class="sxs-lookup"><span data-stu-id="b4bba-121">[Set or Change the Column Collation](set-or-change-the-column-collation.md) </span></span>  
 [<span data-ttu-id="b4bba-122">Перестроение системных баз данных</span><span class="sxs-lookup"><span data-stu-id="b4bba-122">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
