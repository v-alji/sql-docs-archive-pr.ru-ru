---
title: Когда следует использовать SQL Server Native Client | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- SQLNCLI, about SQL Server Native Client
- data access [SQL Server Native Client], about SQL Server Native Client
ms.assetid: 08f18b36-209d-4cf7-9623-ebc61859a91d
author: rothja
ms.author: jroth
ms.openlocfilehash: f8aeb34525bbe5c1b003e8fd95e7a414025965a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658222"
---
# <a name="when-to-use-sql-server-native-client"></a><span data-ttu-id="56075-102">Когда использовать собственный клиент SQL Server</span><span class="sxs-lookup"><span data-stu-id="56075-102">When to Use SQL Server Native Client</span></span>
  <span data-ttu-id="56075-103">Собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] — одна из технологий для доступа к данным в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56075-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is one technology that you can use to access data in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  <span data-ttu-id="56075-104">Обсуждение других технологий доступа к данным см. в разделе [Схема технологий доступа к данным](https://go.microsoft.com/fwlink/?LinkID=179186).</span><span class="sxs-lookup"><span data-stu-id="56075-104">For a discussion of the different data-access technologies, see [Data Access Technologies Road Map](https://go.microsoft.com/fwlink/?LinkID=179186)</span></span>  
  
 <span data-ttu-id="56075-105">В принятии решения о необходимости использования в качестве технологии доступа к данным собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо принимать во внимание ряд факторов.</span><span class="sxs-lookup"><span data-stu-id="56075-105">When deciding whether to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client as the data access technology of your application, you should consider several factors.</span></span>  
  
 <span data-ttu-id="56075-106">Если используется язык программирования с управляемым кодом, например Microsoft Visual C# или Visual Basic, и необходимо обращаться к новым функциям [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], то для новых приложений следует пользоваться поставщиком данных .NET Framework для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], который является частью платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="56075-106">For new applications, if you're using a managed programming language such as Microsoft Visual C# or Visual Basic, and you need to access the new features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should use the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which is part of the .NET Framework.</span></span>  
  
 <span data-ttu-id="56075-107">Если разрабатывается приложение на основе COM и необходим доступ к новым функциям [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], следует использовать собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56075-107">If you are developing a COM-based application and need to access the new features introduced in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="56075-108">Если доступ к новым возможностям [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не требуется, то можно продолжать использовать компоненты WDAC.</span><span class="sxs-lookup"><span data-stu-id="56075-108">If you don't need access to the new features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can continue to use Windows Data Access Components (WDAC).</span></span>  
  
 <span data-ttu-id="56075-109">Для существующих приложений OLE DB и ODBC самый важный вопрос — необходим ли доступ к новым функциям [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56075-109">For existing OLE DB and ODBC applications, the primary issue is whether you need to access the new features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="56075-110">Если имеется отлаженное приложение, не требующее новых возможностей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], то можно продолжать использование компонентов WDAC.</span><span class="sxs-lookup"><span data-stu-id="56075-110">If you have a mature application that does not need the new features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can continue to use WDAC.</span></span> <span data-ttu-id="56075-111">Но если вам нужно получить доступ к этим новым функциям, таким как [тип данных XML](/sql/t-sql/xml/xml-transact-sql), следует использовать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный клиент.</span><span class="sxs-lookup"><span data-stu-id="56075-111">But if you do need to access those new features, such as the [xml data type](/sql/t-sql/xml/xml-transact-sql), you should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="56075-112">Собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и MDAC поддерживают уровень изоляции транзакций read committed при использовании управления версиями строк, однако изоляцию транзакций моментальных снимков поддерживает только собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56075-112">Both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and MDAC support read committed transaction isolation using row versioning, but only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client supports snapshot transaction isolation.</span></span> <span data-ttu-id="56075-113">С точки зрения программирования уровень изоляции транзакции READ COMMITTED с управлением версиями строк — то же самое, что и транзакция READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="56075-113">(In programming terms, read committed transaction isolation with row versioning is the same as Read-Committed transaction.)</span></span>  
  
 <span data-ttu-id="56075-114">Сведения о различиях между [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственным клиентом и компонентами MDAC см. в разделе [Обновление приложения для SQL Server Native Client из MDAC](../../relational-databases/native-client/applications/updating-an-application-to-sql-server-native-client-from-mdac.md).</span><span class="sxs-lookup"><span data-stu-id="56075-114">For information about the differences between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and MDAC, see [Updating an Application to SQL Server Native Client from MDAC](../../relational-databases/native-client/applications/updating-an-application-to-sql-server-native-client-from-mdac.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56075-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="56075-115">See Also</span></span>  
 <span data-ttu-id="56075-116">[SQL Server Native Client программирование](../../relational-databases/native-client/sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="56075-116">[SQL Server Native Client Programming](../../relational-databases/native-client/sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="56075-117">[Разделы руководства по ODBC](../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="56075-117">[ODBC How-to Topics](../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 [<span data-ttu-id="56075-118">Инструкции по OLE DB</span><span class="sxs-lookup"><span data-stu-id="56075-118">OLE DB How-to Topics</span></span>](../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
