---
title: Большие коллекции XML-схем и состояние нехватки памяти | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- out-of-memory conditions
- XML schema collections [SQL Server], large
ms.assetid: 29b9d839-aaaf-48fb-be17-840c751f36f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443207bbbdff5db7e54d61fcebabe70e34cc540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751947"
---
# <a name="large-xml-schema-collections-and-out-of-memory-conditions"></a><span data-ttu-id="113d5-102">Большие коллекции схем XML и условия исчерпания памяти</span><span class="sxs-lookup"><span data-stu-id="113d5-102">Large XML Schema Collections and Out-of-Memory Conditions</span></span>
  <span data-ttu-id="113d5-103">В ходе вызова встроенной функции XML_SCHEMA_NAMESPACE () на большой коллекции схем XML или при попытке удалить большую коллекцию схем XML может возникнуть условие исчерпания памяти.</span><span class="sxs-lookup"><span data-stu-id="113d5-103">During a call to the built-in XML_SCHEMA_NAMESPACE() function on a large XML schema collection, or when you try to drop large XML schema collections, an out-of-memory condition may occur.</span></span> <span data-ttu-id="113d5-104">Далее приводятся решения, которыми можно воспользоваться в данных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="113d5-104">The following are solutions you can use to handle this:</span></span>  
  
-   <span data-ttu-id="113d5-105">При небольшой системной загрузке используйте команду DROP_XML_SCHEMA_COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="113d5-105">When the system load is light, use the DROP_XML_SCHEMA_COLLECTION command.</span></span> <span data-ttu-id="113d5-106">При неудачном выполнении команды переведите базу данных в однопользовательский режим с помощью инструкции ALTER DATABASE и попытайтесь выполнить DROP XML SCHEMA COLLECTION снова.</span><span class="sxs-lookup"><span data-stu-id="113d5-106">If this fails, put the database in single-user mode by using the ALTER DATABASE statement and trying DROP XML SCHEMA COLLECTION again.</span></span> <span data-ttu-id="113d5-107">Если коллекция XML-схем присутствует в базе данных **master**, **model**или **tempdb**, то для перехода в однопользовательский режим потребуется перезапуск сервера.</span><span class="sxs-lookup"><span data-stu-id="113d5-107">If the XML schema collection exists in **master**, **model**, or **tempdb**, a server restart is required for single-user mode.</span></span>  
  
-   <span data-ttu-id="113d5-108">При вызове XML_SCHEMA_NAMESPACE можно попытаться получить одиночное пространство имен XML-схемы, попробовать сделать вызов позже, когда снизится нагрузка в системе, или же попытаться произвести вызов в однопользовательском режиме.</span><span class="sxs-lookup"><span data-stu-id="113d5-108">When you call the XML_SCHEMA_NAMESPACE, you can try to retrieve a single XML schema namespace, you can try the call when the system load is lighter, or you can try the call in single-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113d5-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="113d5-109">See Also</span></span>  
 [<span data-ttu-id="113d5-110">Требования и ограничения для коллекций схем XML на сервере</span><span class="sxs-lookup"><span data-stu-id="113d5-110">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
