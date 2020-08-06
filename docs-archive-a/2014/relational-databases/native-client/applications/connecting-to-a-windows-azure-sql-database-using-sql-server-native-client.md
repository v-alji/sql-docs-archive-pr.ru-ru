---
title: Подключение к базе данных SQL Azure с помощью SQL Server Native Client | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 0dc20bb6-b142-4259-b87b-427d2ba798af
author: rothja
ms.author: jroth
ms.openlocfilehash: 177c655f97e32f2044460e87c6cd775cdf8fcde9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665294"
---
# <a name="connecting-to-an-azure-sql-database-using-sql-server-native-client"></a><span data-ttu-id="ba94a-102">Подключение к базе данных SQL Azure с помощью SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="ba94a-102">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>
  <span data-ttu-id="ba94a-103">Пример, в котором показано, как подключиться к [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] с помощью [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственного клиента, см. [в разделах о разработке: инструкции (база данных SQL Azure)](https://msdn.microsoft.com/library/ee621787.aspx).</span><span class="sxs-lookup"><span data-stu-id="ba94a-103">For a sample that shows how to connect to a [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Development: How-to Topics (Azure SQL Database)](https://msdn.microsoft.com/library/ee621787.aspx).</span></span>  
  
## <a name="known-issues-when-connecting-to-a-sql-database"></a><span data-ttu-id="ba94a-104">Известные проблемы при соединении с базой данных SQL</span><span class="sxs-lookup"><span data-stu-id="ba94a-104">Known Issues When Connecting to a SQL Database</span></span>  
 <span data-ttu-id="ba94a-105">Далее описаны известные проблемы при соединении с базой данных [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] через [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="ba94a-105">The following are known issues when connecting to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   <span data-ttu-id="ba94a-106">Соединение, установленное с помощью `SQLBrowseConnect`, может быть отклонено в случае поэтапного использования `SQLBrowseConnect`.</span><span class="sxs-lookup"><span data-stu-id="ba94a-106">A connection made with `SQLBrowseConnect` may be rejected if `SQLBrowseConnect` is used in stages.</span></span>  <span data-ttu-id="ba94a-107">Например, если имя драйвера передается в первом вызове, сервер и учетные данные (имя пользователя и пароль) — во втором вызове, устанавливающем соединение, а имя базы данных и язык — в третьем вызове.</span><span class="sxs-lookup"><span data-stu-id="ba94a-107">For example, if the driver name is sent in the first call, server and credentials (user and password) sent in the second call, establishing the connection, and a database name and a language in the third call.</span></span>  <span data-ttu-id="ba94a-108">После третьего вызова [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client выполняет инструкцию USE для смены базы данных.</span><span class="sxs-lookup"><span data-stu-id="ba94a-108">The third call will cause [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to issue a USE statement to change databases.</span></span> <span data-ttu-id="ba94a-109">Но инструкция USE не поддерживается в службах [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], и выдается следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="ba94a-109">However, the USE statement is not supported in [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], generating the following error:</span></span>  
  
    ```  
    [Microsoft][SQL Server Native Client 11.0][SQL Server]USE statement is not supported to switch between databases. Use a new connection to connect to a different Database.  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ba94a-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba94a-110">See Also</span></span>  
 [<span data-ttu-id="ba94a-111">Построение приложений с использованием SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="ba94a-111">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
