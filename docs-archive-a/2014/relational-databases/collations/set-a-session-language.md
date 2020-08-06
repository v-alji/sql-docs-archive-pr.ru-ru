---
title: Задание языка сеанса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], international considerations
- globalization [SQL Server], sessions
- time [SQL Server]
- sessions [SQL Server], languages
- international considerations [SQL Server], sessions
- dates [SQL Server], session languages
- global considerations [SQL Server], sessions
- client-side session language
- time [SQL Server], session languages
- messages [SQL Server], international considerations
- server-side session language
ms.assetid: de7f2c90-8f4f-4cfc-94cc-4933a7fd2bde
author: stevestein
ms.author: sstein
ms.openlocfilehash: da8d6adce66ac5b97e533b5afaefabda40e4b966
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668920"
---
# <a name="set-a-session-language"></a><span data-ttu-id="80fb5-102">Задание языка сеанса</span><span class="sxs-lookup"><span data-stu-id="80fb5-102">Set a Session Language</span></span>
  <span data-ttu-id="80fb5-103">Язык сеанса можно применять для настройки отображения элементов на сервере в зависимости от языковых и культурных предпочтений.</span><span class="sxs-lookup"><span data-stu-id="80fb5-103">The session language can be used to set how the following elements are displayed on the server, based on language and cultural preference:</span></span>  
  
-   <span data-ttu-id="80fb5-104">Язык, на котором будут отображаться сообщения об ошибках и другие системные сообщения.</span><span class="sxs-lookup"><span data-stu-id="80fb5-104">The language that will be used for error and other system messages.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="80fb5-105">поддерживает работу с несколькими копиями всех строк и сообщений о системных ошибках на всех языках, для которых произведена локализация [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80fb5-105">supports having multiple copies of all system error strings and messages in all the languages in which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is available.</span></span> <span data-ttu-id="80fb5-106">Текст этих сообщений можно просмотреть в представлении каталога [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) .</span><span class="sxs-lookup"><span data-stu-id="80fb5-106">These messages can be viewed in the [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) catalog view.</span></span> <span data-ttu-id="80fb5-107">При установке локализованной версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]эти сообщения будут переведены на выбранный во время установки язык.</span><span class="sxs-lookup"><span data-stu-id="80fb5-107">When you install a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], these system messages are translated for the language version that you install.</span></span> <span data-ttu-id="80fb5-108">По умолчанию устанавливается также набор системных сообщений для языка «Английский (США)».</span><span class="sxs-lookup"><span data-stu-id="80fb5-108">By default, you also obtain the U.S. English set of these messages.</span></span> <span data-ttu-id="80fb5-109">Кроме этого, существует процедура [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql), которая позволяет добавлять пользовательские сообщения на выбранном языке.</span><span class="sxs-lookup"><span data-stu-id="80fb5-109">Additionally, you can add user-defined messages in a specific language by using [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span></span>  
  
-   <span data-ttu-id="80fb5-110">Формат даты и времени.</span><span class="sxs-lookup"><span data-stu-id="80fb5-110">The format of date and time data.</span></span>  
  
-   <span data-ttu-id="80fb5-111">Названия дней и месяцев, включая сокращения.</span><span class="sxs-lookup"><span data-stu-id="80fb5-111">The names of days and months, including abbreviations.</span></span>  
  
-   <span data-ttu-id="80fb5-112">Первый день недели.</span><span class="sxs-lookup"><span data-stu-id="80fb5-112">The first day of the week.</span></span>  
  
-   <span data-ttu-id="80fb5-113">Денежные единицы.</span><span class="sxs-lookup"><span data-stu-id="80fb5-113">Currency data.</span></span>  
  
 <span data-ttu-id="80fb5-114">Доступно 33 языка сеансов.</span><span class="sxs-lookup"><span data-stu-id="80fb5-114">There are 33 languages available for use as session settings.</span></span> <span data-ttu-id="80fb5-115">Список языков приведен в таблице [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="80fb5-115">For a list of languages, see [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-server"></a><span data-ttu-id="80fb5-116">Настройка языка сеанса на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="80fb5-116">Setting the Session Language from the Server</span></span>  
 <span data-ttu-id="80fb5-117">Язык сеанса задается с сервера с помощью команды [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="80fb5-117">To set the session language from the server side, use [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-client"></a><span data-ttu-id="80fb5-118">Настройка языка сеанса на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="80fb5-118">Setting the Session Language from the Client</span></span>  
 <span data-ttu-id="80fb5-119">Язык сеанса на компьютере клиента настраивается с помощью OLE DB, ODBC или ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="80fb5-119">The session language can be set on the client side by using OLE DB, ODBC or ADO.NET.</span></span> <span data-ttu-id="80fb5-120">Для OLE DB язык сеанса настраивается с помощью свойства SSPROP_INIT_CURRENTLANGUAGE.</span><span class="sxs-lookup"><span data-stu-id="80fb5-120">For OLE DB, use the SSPROP_INIT_CURRENTLANGUAGE property.</span></span> <span data-ttu-id="80fb5-121">Дополнительные сведения см. в статье [Свойства инициализации и авторизации](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span><span class="sxs-lookup"><span data-stu-id="80fb5-121">For more information, see [Initialization and Authorization Properties](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span></span>  
  
 <span data-ttu-id="80fb5-122">В ODBC используется ключевое слово Language.</span><span class="sxs-lookup"><span data-stu-id="80fb5-122">For ODBC, use the Language keyword.</span></span> <span data-ttu-id="80fb5-123">Дополнительные сведения см. в статье [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="80fb5-123">For more information, see [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="80fb5-124">В ADO.NET используется параметр **Текущий язык** объекта **ConnectionString** .</span><span class="sxs-lookup"><span data-stu-id="80fb5-124">For ADO.NET, use the **Current Language** parameter of the **ConnectionString** object.</span></span> <span data-ttu-id="80fb5-125">Дополнительные сведения см. в документации пакета средств разработки программного обеспечения (SDK) для компонентов доступа к данным [!INCLUDE[msCoName](../../includes/msconame-md.md)] (MDAC).</span><span class="sxs-lookup"><span data-stu-id="80fb5-125">For more information, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC) software development kit (SDK) documentation.</span></span>  
  
  
