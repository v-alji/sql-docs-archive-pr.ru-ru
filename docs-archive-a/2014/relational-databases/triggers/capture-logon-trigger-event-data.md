---
title: Данные о захвате событий триггера входа | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e05b1ab4-c10b-402a-9591-f6ec1e3db8c0
author: rothja
ms.author: jroth
ms.openlocfilehash: b11323702d7468d07783b4d1c763dba691479d9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668169"
---
# <a name="capture-logon-trigger-event-data"></a><span data-ttu-id="e76db-102">Захват данных событий триггера входа</span><span class="sxs-lookup"><span data-stu-id="e76db-102">Capture Logon Trigger Event Data</span></span>
  <span data-ttu-id="e76db-103">XML-данные о событиях LOGON для использования внутри триггеров входа могут быть захвачены с использованием функции [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e76db-103">To capture XML data about LOGON events for use inside logon triggers, use the [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) function.</span></span> <span data-ttu-id="e76db-104">Для события LOGON возвращается следующая схема данных событий:</span><span class="sxs-lookup"><span data-stu-id="e76db-104">The LOGON event returns the following event data schema:</span></span>  
  
 `<EVENT_INSTANCE>`  
  
 `<EventType>event_type</EventType>`  
  
 `<PostTime>post_time</PostTime>`  
  
 `<SPID>spid</SPID>`  
  
 `<ServerName>server_name</ServerName>`  
  
 `<LoginName>login_name</LoginName>`  
  
 `<LoginType>login_type</LoginType>`  
  
 `<SID>sid</SID>`  
  
 `<ClientHost>client_host</ClientHost>`  
  
 `<IsPooled>is_pooled</IsPooled>`  
  
 `</EVENT_INSTANCE>`  
  
 `<EventType>`  
 <span data-ttu-id="e76db-105">Содержит `LOGON`.</span><span class="sxs-lookup"><span data-stu-id="e76db-105">Contains `LOGON`.</span></span>  
  
 `<PostTime>`  
 <span data-ttu-id="e76db-106">Содержит время запроса на установление сеанса.</span><span class="sxs-lookup"><span data-stu-id="e76db-106">Contains the time when a session is requested to be established.</span></span>  
  
 `<SID>`  
 <span data-ttu-id="e76db-107">Содержит закодированный в base 64-битовый бинарный поток идентификационного номера безопасности (SID) для указанного имени входа.</span><span class="sxs-lookup"><span data-stu-id="e76db-107">Contains the base 64-encoded binary stream of the security identification number (SID) for the specified login name.</span></span>  
  
 `<ClientHost>`  
 <span data-ttu-id="e76db-108">Содержит имя узла клиента, с которого устанавливается подключение.</span><span class="sxs-lookup"><span data-stu-id="e76db-108">Contains the host name of the client from where the connection is made.</span></span> <span data-ttu-id="e76db-109">Если имя сервера совпадает с именем клиента, то значение по умолчанию — «`<local_machine>`».</span><span class="sxs-lookup"><span data-stu-id="e76db-109">The value is '`<local_machine>`' if the client and server name are the same.</span></span> <span data-ttu-id="e76db-110">Иначе значение равно IP-адресу клиента.</span><span class="sxs-lookup"><span data-stu-id="e76db-110">Otherwise, the value is the IP address of the client.</span></span>  
  
 `<IsPooled>`  
 <span data-ttu-id="e76db-111">`1` , если соединение повторно используется с помощью пула соединений.</span><span class="sxs-lookup"><span data-stu-id="e76db-111">Is `1` if the connection is reused by using connection pooling.</span></span> <span data-ttu-id="e76db-112">В противном случае — значение `0`.</span><span class="sxs-lookup"><span data-stu-id="e76db-112">Otherwise, the value is `0`.</span></span>  
  
  
