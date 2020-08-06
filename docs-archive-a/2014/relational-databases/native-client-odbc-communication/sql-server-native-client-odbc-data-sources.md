---
title: Источники данных SQL Server Native Client ODBC | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, about data sources
- ODBC data sources, names
- data sources [SQL Server Native Client]
- names [ODBC]
- ODBC applications, data sources
- SQL Server Native Client ODBC driver, data sources
- ODBC data sources
ms.assetid: a6a50fd0-d439-43fd-b76f-16ec02f478c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 6960118e13f0843640b18056bda655726cbbbd29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664162"
---
# <a name="sql-server-native-client-odbc-data-sources"></a><span data-ttu-id="0bd8b-102">Источники данных ODBC собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="0bd8b-102">SQL Server Native Client ODBC Data Sources</span></span>
  <span data-ttu-id="0bd8b-103">Имя источника данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (data source name, DSN) указывает источник данных ODBC, содержащий всю информацию, нужную ODBC-приложению для соединения с базой данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на конкретном сервере.</span><span class="sxs-lookup"><span data-stu-id="0bd8b-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source name (DSN) identifies an ODBC data source containing all of the information that an ODBC application needs to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a specific server.</span></span> <span data-ttu-id="0bd8b-104">Задать имя источника данных ODBC можно двумя способами.</span><span class="sxs-lookup"><span data-stu-id="0bd8b-104">There are two ways you can define an ODBC data source name:</span></span>  
  
-   <span data-ttu-id="0bd8b-105">На клиентском компьютере откройте меню Администрирование на панели управления и дважды щелкните элемент **Источники данных (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="0bd8b-105">On a client computer, open Administrative Tools in Control Panel, and double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="0bd8b-106">Откроется окно администратора источника данных ODBC, с помощью которого создается DSN.</span><span class="sxs-lookup"><span data-stu-id="0bd8b-106">This will open the ODBC Data Source Administrator, which you can use to create a DSN.</span></span>  
  
-   <span data-ttu-id="0bd8b-107">В приложении ODBC вызовите [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="0bd8b-107">In an ODBC application, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="0bd8b-108">Источник данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] содержит следующие данные.</span><span class="sxs-lookup"><span data-stu-id="0bd8b-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source contains:</span></span>  
  
-   <span data-ttu-id="0bd8b-109">Имя источника данных.</span><span class="sxs-lookup"><span data-stu-id="0bd8b-109">The name of the data source.</span></span>  
  
-   <span data-ttu-id="0bd8b-110">Всю информацию, нужную для подключения к конкретному экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bd8b-110">Any information needed to connect to a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="0bd8b-111">Базу данных, используемую по умолчанию в конкретном экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="0bd8b-111">The default database to use on a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (optional).</span></span>  
  
-   <span data-ttu-id="0bd8b-112">Настройки: например различные параметры ANSI, местонахождение журнала для занесения показателей производительности и т. п. (необязательные параметры).</span><span class="sxs-lookup"><span data-stu-id="0bd8b-112">Settings such as which ANSI options to use, whether to log performance statistics, and so on (optional).</span></span>  
  
 <span data-ttu-id="0bd8b-113">Приложение ODBC не обязательно должно использовать для подключения источник данных.</span><span class="sxs-lookup"><span data-stu-id="0bd8b-113">An ODBC application is not required to connect through a data source.</span></span> <span data-ttu-id="0bd8b-114">Однако в этом случае приложение обязано предоставить функции соединения ODBC ту же информацию о соединении, которую драйвер в противном случае нашел бы в DSN.</span><span class="sxs-lookup"><span data-stu-id="0bd8b-114">However, the application must provide the same connectivity information to an ODBC connect function that the driver would otherwise find in a DSN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd8b-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="0bd8b-115">See Also</span></span>  
 [<span data-ttu-id="0bd8b-116">Взаимодействие с SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0bd8b-116">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
