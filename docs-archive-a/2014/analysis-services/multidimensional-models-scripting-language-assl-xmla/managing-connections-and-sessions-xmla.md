---
title: Управление подключениями и сеансами (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- statefulness [XML for Analysis]
- statelessness [XML for Analysis]
- XML for Analysis, sessions
- states [XML for Analysis]
- XMLA, sessions
- sessions [XML for Analysis]
ms.assetid: b83bb3ff-09be-4fda-9d1d-6248e04ffb21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bfe876f6874193fd0885f16d91caa9f6fe8b172
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658482"
---
# <a name="managing-connections-and-sessions-xmla"></a><span data-ttu-id="b6479-102">Управление соединениями и сеансами (XMLA)</span><span class="sxs-lookup"><span data-stu-id="b6479-102">Managing Connections and Sessions (XMLA)</span></span>
  <span data-ttu-id="b6479-103">*Пользуясь* — это условие, во время которого сервер сохраняет удостоверение и контекст клиента между вызовами методов.</span><span class="sxs-lookup"><span data-stu-id="b6479-103">*Statefulness* is a condition during which the server preserves the identity and context of a client between method calls.</span></span> <span data-ttu-id="b6479-104">*Стателесснесс* — это условие, в течение которого сервер не запоминает удостоверение и контекст клиента после завершения вызова метода.</span><span class="sxs-lookup"><span data-stu-id="b6479-104">*Statelessness* is a condition during which the server does not remember the identity and context of a client after a method call finishes.</span></span>  
  
 <span data-ttu-id="b6479-105">Чтобы обеспечить пользуясь, XML для аналитики (XMLA) поддерживает *сеансы* , которые позволяют выполнять несколько инструкций вместе.</span><span class="sxs-lookup"><span data-stu-id="b6479-105">To provide statefulness, XML for Analysis (XMLA) supports *sessions* that allow a series of statements to be performed together.</span></span> <span data-ttu-id="b6479-106">Примером такого ряда инструкций служит создание вычисляемого элемента, который должен использоваться в последующих запросах.</span><span class="sxs-lookup"><span data-stu-id="b6479-106">An example of such a series of statements would be the creation of a calculated member that is to be used in subsequent queries.</span></span>  
  
 <span data-ttu-id="b6479-107">В целом поведение сеансов в XMLA соответствует описанию, приведенному в спецификации OLE DB 2.6.</span><span class="sxs-lookup"><span data-stu-id="b6479-107">In general, sessions in XMLA follow the following behavior outlined by the OLE DB 2.6 specification:</span></span>  
  
-   <span data-ttu-id="b6479-108">Сеансы определяют область контекста команд и транзакций.</span><span class="sxs-lookup"><span data-stu-id="b6479-108">Sessions define transaction and command context scope.</span></span>  
  
-   <span data-ttu-id="b6479-109">В контексте одного сеанса могут выполняться несколько команд.</span><span class="sxs-lookup"><span data-stu-id="b6479-109">Multiple commands can be run in the context of a single session.</span></span>  
  
-   <span data-ttu-id="b6479-110">Поддержка транзакций в контексте XMLA осуществляется с помощью команд, относящихся к поставщику, которые отправляются с помощью метода [EXECUTE](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="b6479-110">Support for transactions in the XMLA context is through provider-specific commands sent with the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
 <span data-ttu-id="b6479-111">XMLA определяет способ поддержки сеансов в веб-среде, похожий на тот, который используется в протоколе DAV для реализации блокировки в слабосвязанной среде.</span><span class="sxs-lookup"><span data-stu-id="b6479-111">XMLA defines a way to support sessions in a Web environment in a mode similar to the approach used by the Distributed Authoring and Versioning (DAV) protocol to implement locking in a loosely coupled environment.</span></span> <span data-ttu-id="b6479-112">Эта реализация соответствует протоколу DAV в том, что поставщик может закрывать сеансы по различным причинам (например, из-за ошибки времени ожидания или соединения).</span><span class="sxs-lookup"><span data-stu-id="b6479-112">This implementation parallels DAV in that the provider is allowed to expire sessions for various reasons (for example, a timeout or connection error).</span></span> <span data-ttu-id="b6479-113">В случае поддержки сеансов веб-службы должны знать об этом и быть готовыми к обработке прерванных наборов команд, которые необходимо перезапускать.</span><span class="sxs-lookup"><span data-stu-id="b6479-113">When sessions are supported, Web services must be aware and ready to handle interrupted sets of commands that must be restarted.</span></span>  
  
 <span data-ttu-id="b6479-114">В спецификации протокола SOAP консорциума World Wide Web (W3C) рекомендуется использовать заголовки SOAP для построения новых протоколов поверх сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="b6479-114">The World Wide Web Consortium (W3C) Simple Object Access Protocol (SOAP) specification recommends using SOAP headers for building up new protocols on top of SOAP messages.</span></span> <span data-ttu-id="b6479-115">В приведенной далее таблице перечислены элементы и атрибуты заголовков SOAP, которые XMLA определяет для запуска, ведения и закрытия сеанса.</span><span class="sxs-lookup"><span data-stu-id="b6479-115">The following table lists the SOAP header elements and attributes that XMLA defines for initiating, maintaining, and closing a session.</span></span>  
  
|<span data-ttu-id="b6479-116">Заголовок SOAP</span><span class="sxs-lookup"><span data-stu-id="b6479-116">SOAP header</span></span>|<span data-ttu-id="b6479-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b6479-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b6479-118">BeginSession</span><span class="sxs-lookup"><span data-stu-id="b6479-118">BeginSession</span></span>|<span data-ttu-id="b6479-119">Этот заголовок запрашивает у поставщика создание нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="b6479-119">This header requests the provider to create a new session.</span></span> <span data-ttu-id="b6479-120">В ответ поставщик должен создать новый сеанс и возвратить его идентификатор, как часть заголовка Session в ответе SOAP.</span><span class="sxs-lookup"><span data-stu-id="b6479-120">The provider should respond by constructing a new session and returning the session ID as part of the Session header in the SOAP response.</span></span>|  
|<span data-ttu-id="b6479-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="b6479-121">SessionId</span></span>|<span data-ttu-id="b6479-122">Область значения содержит идентификатор сеанса, который необходимо использовать в каждом вызове метода в течение сеанса.</span><span class="sxs-lookup"><span data-stu-id="b6479-122">The value area contains the session ID that must be used in each method call for the rest of the session.</span></span> <span data-ttu-id="b6479-123">В ответе SOAP поставщик отправляет этот тег, а клиент также должен отправлять этот атрибут с каждым элементом заголовка Session.</span><span class="sxs-lookup"><span data-stu-id="b6479-123">The provider in the SOAP response sends this tag and the client must also send this attribute with each Session header element.</span></span>|  
|<span data-ttu-id="b6479-124">Сеанс</span><span class="sxs-lookup"><span data-stu-id="b6479-124">Session</span></span>|<span data-ttu-id="b6479-125">Этот заголовок должен использоваться для каждого вызова метода в рамках данного сеанса, а на панели значения заголовка должен быть указан идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="b6479-125">For every method call that occurs in the session, this header must be used, and the session ID must be included in the value area of the header.</span></span>|  
|<span data-ttu-id="b6479-126">EndSession</span><span class="sxs-lookup"><span data-stu-id="b6479-126">EndSession</span></span>|<span data-ttu-id="b6479-127">Используйте этот заголовок для завершения сеанса.</span><span class="sxs-lookup"><span data-stu-id="b6479-127">To terminate the session, use this header.</span></span> <span data-ttu-id="b6479-128">Идентификатор сеанса необходимо указывать в области значения.</span><span class="sxs-lookup"><span data-stu-id="b6479-128">The session ID must be included with the value area.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="b6479-129">Наличие идентификатора сеанса не гарантирует того, что сеанс остается допустимым.</span><span class="sxs-lookup"><span data-stu-id="b6479-129">A session ID does not guarantee that a session stays valid.</span></span> <span data-ttu-id="b6479-130">Если время сеанса истекает (например, если истекло его время ожидания или потеряно соединение), поставщик может завершить и выполнить откат действий, выполнявшихся во время сеанса.</span><span class="sxs-lookup"><span data-stu-id="b6479-130">If the session expires (for example, if it times out or the connection is lost), the provider can choose to end and roll back that session's actions.</span></span> <span data-ttu-id="b6479-131">В результате все последующие вызовы методов, отправленные клиентом с идентификатором сеанса, завершатся ошибкой, сигнализирующей, что сеанс недопустим.</span><span class="sxs-lookup"><span data-stu-id="b6479-131">As a result, all subsequent method calls from the client on a session ID fail with an error signaling a session that is not valid.</span></span> <span data-ttu-id="b6479-132">Клиент должен обработать это условие и быть готовым повторно отправить вызовы метода сеанса с самого начала.</span><span class="sxs-lookup"><span data-stu-id="b6479-132">A client should handle this condition and be prepared to resend the session method calls from the beginning.</span></span>  
  
## <a name="legacy-code-example"></a><span data-ttu-id="b6479-133">Пример кода прежних версий</span><span class="sxs-lookup"><span data-stu-id="b6479-133">Legacy Code Example</span></span>  
 <span data-ttu-id="b6479-134">В следующем примере показано, как поддерживаются сеансы.</span><span class="sxs-lookup"><span data-stu-id="b6479-134">The following example shows how sessions are supported.</span></span>  
  
1.  <span data-ttu-id="b6479-135">Чтобы начать сеанс, добавьте заголовок BeginSession в SOAP в исходящий от клиента вызов метода XMLA.</span><span class="sxs-lookup"><span data-stu-id="b6479-135">To begin the session, add a BeginSession header in SOAP to the outbound XMLA method call from the client.</span></span> <span data-ttu-id="b6479-136">Первоначально область значения остается пустой, поскольку идентификатор сеанса пока не известен.</span><span class="sxs-lookup"><span data-stu-id="b6479-136">The value area is initially blank because the session ID is not yet known.</span></span>  
  
    ```  
    <SOAP-ENV:Envelope  
       xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
       SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
       <SOAP-ENV:Header>  
          <XA:BeginSession  
             xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
             xsi:type="xsd:int"  
             mustUnderstand="1"/>  
       </SOAP-ENV:Header>  
       <SOAP-ENV:Body>  
          ...<!-- Discover or Execute call goes here.-->  
       </SOAP-ENV:Body>  
    </SOAP-ENV:Envelope>  
    ```  
  
2.  <span data-ttu-id="b6479-137">Ответное сообщение SOAP от поставщика включает идентификатор сеанса в области заголовка возврата с помощью тега заголовка XMLA \<SessionId> .</span><span class="sxs-lookup"><span data-stu-id="b6479-137">The SOAP response message from the provider includes the session ID in the return header area, using the XMLA header tag \<SessionId>.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
3.  <span data-ttu-id="b6479-138">В каждый вызов метода в рамках этого сеанса необходимо добавлять заголовок Session, содержащий идентификатор сеанса, который возвратил поставщик.</span><span class="sxs-lookup"><span data-stu-id="b6479-138">For each method call in the session, the Session header must be added, containing the session ID returned from the provider.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
4.  <span data-ttu-id="b6479-139">По завершении сеанса \<EndSession> используется тег, содержащий значение идентификатора связанного сеанса.</span><span class="sxs-lookup"><span data-stu-id="b6479-139">When the session is complete, the \<EndSession> tag is used, containing the related session ID value.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:EndSession  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          xsi:type="xsd:int"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b6479-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="b6479-140">See Also</span></span>  
 [<span data-ttu-id="b6479-141">Разработка с использованием XMLA в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b6479-141">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
