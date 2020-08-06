---
title: SQLConnect | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLConnect function
ms.assetid: 6da74e3a-4388-4907-81cb-987389bae467
author: rothja
ms.author: jroth
ms.openlocfilehash: 43b37ae16638e461e37edaead83cd9ceedc1c86d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664180"
---
# <a name="sqlconnect"></a><span data-ttu-id="80ccb-102">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="80ccb-102">SQLConnect</span></span>
  <span data-ttu-id="80ccb-103">При открытии соединения собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] задает SQL_COPT_SS_MUTUALLY_AUTHENTICATED и SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD метод проверки подлинности, используемый для открытия соединения.</span><span class="sxs-lookup"><span data-stu-id="80ccb-103">When a connection is opened, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sets SQL_COPT_SS_MUTUALLY_AUTHENTICATED and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD to the authentication method used to open the connection.</span></span> <span data-ttu-id="80ccb-104">Дополнительные сведения о SPN см. [в статье имена субъектов-служб &#40;имен участников-служб&#41; в клиентских подключениях &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="80ccb-104">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="sqlconnect-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="80ccb-105">Поддержка высокого уровня доступности и аварийного восстановления SQLConnect</span><span class="sxs-lookup"><span data-stu-id="80ccb-105">SQLConnect Support for High Availability, Disaster Recovery</span></span>  
 <span data-ttu-id="80ccb-106">Дополнительные сведения об использовании **SQLConnect** для подключения к [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] кластеру см. в разделе [Поддержка высокой доступности и аварийного восстановления в SQL Server Native Client](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="80ccb-106">For more information on using **SQLConnect** to connect to a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, see [SQL Server Native Client Support for High Availability, Disaster Recovery](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ccb-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="80ccb-107">See Also</span></span>  
 <span data-ttu-id="80ccb-108">[Функция SQLConnect](https://go.microsoft.com/fwlink/?LinkId=101541) </span><span class="sxs-lookup"><span data-stu-id="80ccb-108">[SQLConnect Function](https://go.microsoft.com/fwlink/?LinkId=101541) </span></span>  
 [<span data-ttu-id="80ccb-109">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="80ccb-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
