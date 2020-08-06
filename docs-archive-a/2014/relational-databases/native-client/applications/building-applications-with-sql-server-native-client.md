---
title: Создание приложений с помощью SQL Server Native Client | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], building applications
- SQLNCLI, building applications
- applications [SQL Server Native Client]
- SQL Server Native Client, building applications
ms.assetid: 254a2b48-f0e3-43b5-a48d-3d666c2a779f
author: rothja
ms.author: jroth
ms.openlocfilehash: d08fe1042ab1a79f6b48648f5a774b4fbac49ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665296"
---
# <a name="building-applications-with-sql-server-native-client"></a><span data-ttu-id="27569-102">Построение приложений с использованием собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="27569-102">Building Applications with SQL Server Native Client</span></span>
  <span data-ttu-id="27569-103">При разработке приложения, использующего библиотеку собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], следует учитывать ряд проблем.</span><span class="sxs-lookup"><span data-stu-id="27569-103">When developing an application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library, there are a number of issues that come into play.</span></span> <span data-ttu-id="27569-104">В этом разделе обсуждаются многие из этих проблем, в том числе переход от компонентов MDAC к собственному клиенту [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и использование файлов заголовков и библиотек собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], а также приведены общие сведения о различных строках соединения, которые можно использовать с собственным клиентом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27569-104">The topics in this section discuss many of these issues including upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files, and an overview of the various connection strings that can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27569-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="27569-105">In This Section</span></span>  
 [<span data-ttu-id="27569-106">Установка собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="27569-106">Installing SQL Server Native Client</span></span>](installing-sql-server-native-client.md)  
 <span data-ttu-id="27569-107">Обсуждаются способ установки собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], местоположения установки различных компонентов, а также способ удаления собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27569-107">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is installed, the locations that various components are installed to, and how to uninstall [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="27569-108">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="27569-108">Components of SQL Server Native Client</span></span>](components-of-sql-server-native-client.md)  
 <span data-ttu-id="27569-109">Обсуждаются компоненты, входящие в состав собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], в том числе файлы библиотек, ресурсов, справки и заголовков.</span><span class="sxs-lookup"><span data-stu-id="27569-109">Discusses the components that make up [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client including library, resource, help, and header files.</span></span>  
  
 [<span data-ttu-id="27569-110">Использование ключевых слов строки подключения с собственным клиентом SQL Server</span><span class="sxs-lookup"><span data-stu-id="27569-110">Using Connection String Keywords with SQL Server Native Client</span></span>](using-connection-string-keywords-with-sql-server-native-client.md)  
 <span data-ttu-id="27569-111">Обсуждаются различные типы строк соединения, которые можно использовать для соединения с базой данных через собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27569-111">Discusses the various types of connection strings that can be used when connecting to a database through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="27569-112">Использование файлов заголовков и библиотек собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="27569-112">Using the SQL Server Native Client Header and Library Files</span></span>](using-the-sql-server-native-client-header-and-library-files.md)  
 <span data-ttu-id="27569-113">Обсуждается использование файлов заголовков и библиотек собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в приложении.</span><span class="sxs-lookup"><span data-stu-id="27569-113">Discusses how to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files within an application.</span></span>  
  
 [<span data-ttu-id="27569-114">Обновление приложения с переходом от компонентов MDAC к собственному клиенту SQL Server</span><span class="sxs-lookup"><span data-stu-id="27569-114">Updating an Application to SQL Server Native Client from MDAC</span></span>](updating-an-application-to-sql-server-native-client-from-mdac.md)  
 <span data-ttu-id="27569-115">Обсуждаются отличия собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] от компонентов MDAC и проблемы, которые следует принимать во внимание при переходе с компонентов MDAC на собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27569-115">Discusses the differences between [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and MDAC and issues that should be considered when upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="27569-116">Обновление приложения с SQL Server 2005 Native Client</span><span class="sxs-lookup"><span data-stu-id="27569-116">Updating an Application from SQL Server 2005 Native Client</span></span>](updating-an-application-from-sql-server-2005-native-client.md)  
 <span data-ttu-id="27569-117">Обсуждаются вопросы, которые необходимо учитывать при обновлении собственного клиента [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] до собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27569-117">Discusses issues that should be considered when upgrading from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="27569-118">Использование ADO с собственным клиентом SQL Server</span><span class="sxs-lookup"><span data-stu-id="27569-118">Using ADO with SQL Server Native Client</span></span>](using-ado-with-sql-server-native-client.md)  
 <span data-ttu-id="27569-119">Обсуждается использование собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] технологией ADO для доступа к СУБД [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и ее функциям.</span><span class="sxs-lookup"><span data-stu-id="27569-119">Discusses how ADO can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access and use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span>  
  
 [<span data-ttu-id="27569-120">Политики поддержки собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="27569-120">Support Policies for SQL Server Native Client</span></span>](support-policies-for-sql-server-native-client.md)  
 <span data-ttu-id="27569-121">Объясняет, как могут использоваться различные компоненты доступа к данным с разными версиями [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="27569-121">Discusses how various data-access components can be used with different versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="27569-122">Подключение к базе данных SQL Azure с помощью SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="27569-122">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>](connecting-to-a-windows-azure-sql-database-using-sql-server-native-client.md)  
 <span data-ttu-id="27569-123">Содержит сведения о соединении с базой данных [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] через [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="27569-123">Discusses how to connect to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27569-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="27569-124">See Also</span></span>  
 <span data-ttu-id="27569-125">[SQL Server Native Client программирование](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="27569-125">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="27569-126">[Разделы руководства по ODBC](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="27569-126">[ODBC How-to Topics](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 [<span data-ttu-id="27569-127">Инструкции по OLE DB</span><span class="sxs-lookup"><span data-stu-id="27569-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
