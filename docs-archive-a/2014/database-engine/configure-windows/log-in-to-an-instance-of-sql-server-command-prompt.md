---
title: Вход в экземпляр SQL Server (командная строка) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], named instance of SQL Server
- log ins [SQL Server]
- logins [SQL Server], default instance of SQL Server
- command prompt [SQL Server], logins
- logging in [SQL Server]
ms.assetid: f67c11e3-c519-40c9-82c1-07efa9d9985e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 32028a30786117f2cafa76150867a0e726b07cda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655352"
---
# <a name="log-in-to-an-instance-of-sql-server-command-prompt"></a><span data-ttu-id="45dc8-102">Вход в экземпляр SQL Server (командная строка)</span><span class="sxs-lookup"><span data-stu-id="45dc8-102">Log In to an Instance of SQL Server (Command Prompt)</span></span>
  <span data-ttu-id="45dc8-103">В этом разделе описывается, как проверить связь с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], используя программу **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="45dc8-103">This topic describes how to test connectivity to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the **sqlcmd** utility.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-log-in-to-the-default-instance-of-sql-server"></a><span data-ttu-id="45dc8-104">Вход в экземпляр SQL Server по умолчанию</span><span class="sxs-lookup"><span data-stu-id="45dc8-104">To log in to the default instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="45dc8-105">В командной строке введите следующую команду для соединения с использованием проверки подлинности Windows:</span><span class="sxs-lookup"><span data-stu-id="45dc8-105">From a command prompt, enter the following command to connect by using Windows Authentication:</span></span>  
  
    ```  
    sqlcmd [ /E ] [ /S servername ]  
  
    ```  
  
#### <a name="to-log-in-to-a-named-instance-of-sql-server"></a><span data-ttu-id="45dc8-106">Вход в именованный экземпляр SQL Server</span><span class="sxs-lookup"><span data-stu-id="45dc8-106">To log in to a named instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="45dc8-107">В командной строке введите следующую команду для соединения с использованием проверки подлинности Windows:</span><span class="sxs-lookup"><span data-stu-id="45dc8-107">From a command prompt, enter the following command to connect by using Windows Authentication:</span></span>  
  
    ```  
    sqlcmd [ /E ] /S servername\instancename  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="45dc8-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="45dc8-108">See Also</span></span>  
 <span data-ttu-id="45dc8-109">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="45dc8-109">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 [<span data-ttu-id="45dc8-110">Программа osql</span><span class="sxs-lookup"><span data-stu-id="45dc8-110">osql Utility</span></span>](../../tools/osql-utility.md)  
  
  
