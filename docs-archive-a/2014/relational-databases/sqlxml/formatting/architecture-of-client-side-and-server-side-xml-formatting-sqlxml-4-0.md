---
title: Архитектура форматирования XML на стороне клиента и на стороне сервера (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], XML formatting architecture
- SQLOLEDB provider
- client-side XML formatting
- data providers [SQLXML], XML formatting architecture
- SQLNCLI, XML
- server-side XML formatting
- SQL Server Native Client, XML
- SQLXMLOLEDB Provider, XML formatting architecture
ms.assetid: 52440d9e-89fd-4c15-a008-a1ea99f41387
author: rothja
ms.author: jroth
ms.openlocfilehash: ae1a9c60a7a7966f4eff2a08b4557487f5aec58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665934"
---
# <a name="architecture-of-client-side-and-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="60e7f-102">Архитектура форматирования XML на стороне клиента и сервера (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="60e7f-102">Architecture of Client-side and Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="60e7f-103">На следующей иллюстрации показана архитектура форматирования XML на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="60e7f-103">The following illustration shows the architecture of XML formatting on the server side.</span></span>  
  
 <span data-ttu-id="60e7f-104">![Архитектура форматирования XML-кода на стороне сервера.](../../../database-engine/dev-guide/media/serversidexml.gif "Архитектура форматирования XML-кода на стороне сервера.")</span><span class="sxs-lookup"><span data-stu-id="60e7f-104">![Architecture of XML formatting on the server side.](../../../database-engine/dev-guide/media/serversidexml.gif "Architecture of XML formatting on the server side.")</span></span>  
  
 <span data-ttu-id="60e7f-105">В этом примере команда, указанная на стороне клиента, передается на сервер.</span><span class="sxs-lookup"><span data-stu-id="60e7f-105">In this example, the command that is specified on the client is sent to the server.</span></span> <span data-ttu-id="60e7f-106">Сервер создает XML-документ и возвращает его клиенту.</span><span class="sxs-lookup"><span data-stu-id="60e7f-106">The server produces an XML document and returns it to the client.</span></span> <span data-ttu-id="60e7f-107">В этом случае сервер имеет экземпляр [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60e7f-107">In this case, the server has an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60e7f-108">Чтобы форматировать XML-документ на стороне сервера, можно применять либо поставщик SQLXMLOLEDB, либо SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="60e7f-108">With server-side XML formatting, you can use either the SQLXMLOLEDB provider or the SQLOLEDB provider.</span></span>  <span data-ttu-id="60e7f-109">Поставщик SQLXMLOLEDB использует библиотеку Sqlxml4.dll, входящую в SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="60e7f-109">The SQLXMLOLEDB provider uses Sqlxml4.dll, which is included in SQLXML 4.0.</span></span> <span data-ttu-id="60e7f-110">Если используется поставщик SQLOLEDB, по умолчанию получаем функциональность SQLXML, предоставляемую библиотекой Sqlxmlx.dll, входящей в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows, или компоненты доступа к данным MDAC 2.6 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="60e7f-110">When you use the SQLOLEDB provider, by default you get the SQLXML functionality provided by Sqlxmlx.dll, which is included with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows or in Microsoft Data Access Components (MDAC) 2.6 or later.</span></span> <span data-ttu-id="60e7f-111">Чтобы использовать Sqlxml4.dll с SQLOLEDB, необходимо задать для свойства версия SQLXML значение SQLXML. 4.0 в объекте подключения SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="60e7f-111">To use Sqlxml4.dll with SQLOLEDB, you must set the SQLXML Version property to "SQLXML.4.0" on the SQLOLEDB Connection object.</span></span> <span data-ttu-id="60e7f-112">В любом случае сервер создает XML-документ и передает его клиенту.</span><span class="sxs-lookup"><span data-stu-id="60e7f-112">In either case, the server produces the XML document and sends it to the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="60e7f-113">Запросы XPath и диаграммы обновления анализируются на клиенте.</span><span class="sxs-lookup"><span data-stu-id="60e7f-113">XPath queries and updategrams are parsed on the client.</span></span> <span data-ttu-id="60e7f-114">Чтобы вернуть шаблон XPath или диаграмму обновления в SQLXML 4.0, используйте библиотеку Sqlxml4.dll.</span><span class="sxs-lookup"><span data-stu-id="60e7f-114">To get the XPath template or updategram functionality in SQLXML 4.0, use Sqlxml4.dll.</span></span>  
  
 <span data-ttu-id="60e7f-115">На следующей иллюстрации показана архитектура форматирования XML на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="60e7f-115">The following illustration shows the architecture of XML formatting on the client side.</span></span>  
  
 <span data-ttu-id="60e7f-116">![Архитектура форматирования XML-кода на стороне клиента.](../../../database-engine/dev-guide/media/clientsidexml.gif "Архитектура форматирования XML-кода на стороне клиента.")</span><span class="sxs-lookup"><span data-stu-id="60e7f-116">![Architecture of XML formatting on the client side.](../../../database-engine/dev-guide/media/clientsidexml.gif "Architecture of XML formatting on the client side.")</span></span>  
  
 <span data-ttu-id="60e7f-117">В этом примере клиент использует поставщик SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="60e7f-117">In this example, the client uses the SQLXMLOLEDB provider.</span></span> <span data-ttu-id="60e7f-118">В строке подключения для свойства поставщика данных необходимо задать значение SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="60e7f-118">In the connection string, the Data Provider property must be set to SQLOLEDB.</span></span> <span data-ttu-id="60e7f-119">(Это единственное значение, допустимое в SQLXML 4,0.) Команда, выполняемая на клиенте, отправляется на сервер.</span><span class="sxs-lookup"><span data-stu-id="60e7f-119">(This is the only value accepted in SQLXML 4.0.) The command that is executed on the client is sent to the server.</span></span> <span data-ttu-id="60e7f-120">Созданный на сервере набор строк отправляется клиенту.</span><span class="sxs-lookup"><span data-stu-id="60e7f-120">The rowset that is generated on the server is sent to the client.</span></span> <span data-ttu-id="60e7f-121">Форматирование XML-документа на основе набора строк выполняется на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="60e7f-121">The formatting of the XML document from the rowset is performed on the client.</span></span>  
  
 <span data-ttu-id="60e7f-122">В SQLXML 4.0 в качестве поставщика данных может использоваться собственный клиент [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SQLNCLI11) или поставщик SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="60e7f-122">In SQLXML 4.0, either the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) or the SQLOLEDB provider can be used as the data provider.</span></span> <span data-ttu-id="60e7f-123">Теоретически можно получить доступ к любому источнику данных.</span><span class="sxs-lookup"><span data-stu-id="60e7f-123">You can potentially access any data source.</span></span> <span data-ttu-id="60e7f-124">Если запрос возвращает единственный набор строк, преобразование XML может применяться на клиенте.</span><span class="sxs-lookup"><span data-stu-id="60e7f-124">As long as the query returns a single rowset, the XML transformation can be applied on the client.</span></span>  
  
  
