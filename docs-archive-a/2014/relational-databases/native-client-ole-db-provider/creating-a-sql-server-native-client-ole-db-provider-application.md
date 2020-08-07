---
title: Создание приложения поставщика SQL Server Native Client OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, application creation
- applications [SQL Server Native Client]
- OLE DB, creating applications
ms.assetid: f3ae6815-f32d-4913-a1a2-2ba2f20cfd88
author: rothja
ms.author: jroth
ms.openlocfilehash: a661f23cdacc4b581dadbe7625cb6e2ea318857f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730622"
---
# <a name="creating-a-sql-server-native-client-ole-db-provider-application"></a><span data-ttu-id="25b48-102">Создание приложения поставщика OLE DB для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="25b48-102">Creating a SQL Server Native Client OLE DB Provider Application</span></span>
  <span data-ttu-id="25b48-103">Создание [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] приложения поставщика собственного клиента OLE DB включает следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="25b48-103">Creating a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider application involves these steps:</span></span>  
  
1.  <span data-ttu-id="25b48-104">установление соединения с источником данных;</span><span class="sxs-lookup"><span data-stu-id="25b48-104">Establishing a connection to a data source.</span></span>  
  
2.  <span data-ttu-id="25b48-105">выполнение команды;</span><span class="sxs-lookup"><span data-stu-id="25b48-105">Executing a command.</span></span>  
  
3.  <span data-ttu-id="25b48-106">обработку результатов.</span><span class="sxs-lookup"><span data-stu-id="25b48-106">Processing the results.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25b48-107">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="25b48-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="25b48-108">Если проверка подлинности Windows недоступна, запросите у пользователя ввод учетных данных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="25b48-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="25b48-109">Избегайте хранения учетных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="25b48-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="25b48-110">Если необходимо сохранение учетных данных, зашифруйте их с помощью [API-интерфейса шифрования Win32](https://go.microsoft.com/fwlink/?LinkId=9504).</span><span class="sxs-lookup"><span data-stu-id="25b48-110">If you must persist credentials, you should encrypt them with [the Win32 cryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25b48-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="25b48-111">In This Section</span></span>  
  
-   [<span data-ttu-id="25b48-112">Установление соединения с источником данных</span><span class="sxs-lookup"><span data-stu-id="25b48-112">Establishing a Connection to a Data Source</span></span>](establishing-a-connection-to-a-data-source.md)  
  
-   [<span data-ttu-id="25b48-113">Выполнение команды</span><span class="sxs-lookup"><span data-stu-id="25b48-113">Executing a Command</span></span>](executing-a-command.md)  
  
-   [<span data-ttu-id="25b48-114">Обработка результатов</span><span class="sxs-lookup"><span data-stu-id="25b48-114">Processing Results</span></span>](processing-results.md)  
  
-   [<span data-ttu-id="25b48-115">О свойствах OLE DB</span><span class="sxs-lookup"><span data-stu-id="25b48-115">About OLE DB Properties</span></span>](about-ole-db-properties.md)  
  
-   [<span data-ttu-id="25b48-116">Использование предложения OUTPUT с OLE DB в SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="25b48-116">Using the OUTPUT Clause with OLE DB in SQL Server Native Client</span></span>](using-the-output-clause-with-ole-db-in-sql-server-native-client.md)  
  
## <a name="see-also"></a><span data-ttu-id="25b48-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="25b48-117">See Also</span></span>  
 [<span data-ttu-id="25b48-118">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="25b48-118">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
