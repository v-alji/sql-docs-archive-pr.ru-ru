---
title: Пользовательские типы больших данных в среде CLR | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- large CLR user-defined types
ms.assetid: b65eb61d-ccf6-49c0-98e7-9a4ef4b2f790
author: rothja
ms.author: jroth
ms.openlocfilehash: 27f0c13caea8c4aca63d78238509c6d05f1bf7bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730594"
---
# <a name="large-clr-user-defined-types"></a><span data-ttu-id="10af4-102">Большие определяемые пользователем типы данных CLR</span><span class="sxs-lookup"><span data-stu-id="10af4-102">Large CLR User-Defined Types</span></span>
  <span data-ttu-id="10af4-103">В SQL Server 2005 определяемые пользователем типы данных (UDT) в среде CLR были ограничены размером в 8000 байт.</span><span class="sxs-lookup"><span data-stu-id="10af4-103">In SQL Server 2005, user-defined types (UDTs) in the common language runtime (CLR) were restricted to 8,000 bytes in size.</span></span> <span data-ttu-id="10af4-104">Это ограничение было снято в [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="10af4-104">This restriction has been lifted in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and later versions.</span></span> <span data-ttu-id="10af4-105">Теперь определяемые пользователем типы данных CLR обрабатываются подобно типам больших объектов (LOB).</span><span class="sxs-lookup"><span data-stu-id="10af4-105">CLR UDTs are now treated in a similar way to large object (LOB) types.</span></span> <span data-ttu-id="10af4-106">То есть объекты определяемого пользователем типа размером не более 8000 байт ведут себя так же, как в SQL Server 2005, но такие же объекты большего размера поддерживаются и сообщают о своем размере как о неограниченном.</span><span class="sxs-lookup"><span data-stu-id="10af4-106">That is, UDTs less than or equal to 8,000 bytes behave the same way as in SQL Server 2005, but larger UDTs are supported and report their size as "unlimited".</span></span>  
  
 <span data-ttu-id="10af4-107">Дополнительные сведения см. в разделе [большие определяемые пользователем типы данных clr &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) и [большие определяемые пользователем типы данных CLR &#40;&#41;ODBC ](../odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="10af4-107">For more information, see [Large CLR User-Defined Types &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) and [Large CLR User-Defined Types &#40;ODBC&#41;](../odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="use-cases"></a><span data-ttu-id="10af4-108">Варианты использования</span><span class="sxs-lookup"><span data-stu-id="10af4-108">Use Cases</span></span>  
 <span data-ttu-id="10af4-109">Для ODBC поддержка больших объектов определяемого пользователем типа включает в себя возможность отправить значения определяемого пользователем типа по частям как параметры с данными времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="10af4-109">For ODBC, support for large UDTs includes the ability to send UDT values in pieces as data-at-execution parameters.</span></span> <span data-ttu-id="10af4-110">Это делается с помощью SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="10af4-110">This is done by using SQLPutData.</span></span>  
  
 <span data-ttu-id="10af4-111">Для OLE DB поддержка больших пользовательских типов включает в себя возможность передать потоком значения пользовательского типа на сервер и обратно с помощью привязки ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="10af4-111">For OLE DB, support for large UDTs includes the ability to stream UDT values to and from the server by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="10af4-112">Определяемые пользователем типы размером меньше или равным 8 000 байт будут вести себя так же, как в SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="10af4-112">UDTs less than or equal to 8,000 bytes will behave as they did in SQL Server 2005.</span></span> <span data-ttu-id="10af4-113">Для OLE DB по-прежнему можно передавать потоком малые пользовательские типы, используя привязку ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="10af4-113">For OLE DB, you can still stream small UDTs by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="10af4-114">Иногда собственному коду будет необходимо понять содержимое определяемых пользователем типов CLR, но не придется создавать экземпляр управляющего объекта.</span><span class="sxs-lookup"><span data-stu-id="10af4-114">Sometimes native code will have to understand the contents of CLR UDTs, but will not have to instantiate managed objects.</span></span> <span data-ttu-id="10af4-115">В таком случае можно использовать пользовательскую сериализацию для преобразования на сервере значений определяемых пользователем типов в хорошо знакомый клиенту формат.</span><span class="sxs-lookup"><span data-stu-id="10af4-115">If this is the case, you can use custom serialization to convert UDT values on the server into a well known format for clients.</span></span>  
  
 <span data-ttu-id="10af4-116">Для приложений, имеющих существующий код доступа к данным, можно использовать поведение определяемых пользователем типов CLR на клиенте путем получения определяемых пользователем типов через собственные API-интерфейсы и создания их экземпляров при помощи CLI-взаимодействия языка C++ в приложениях смешанного режима.</span><span class="sxs-lookup"><span data-stu-id="10af4-116">For applications that have existing data access code, you can exploit CLR UDT behavior on the client by retrieving UDTs through native APIs and instantiating them by using C++ CLI interop in mixed mode applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10af4-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="10af4-117">See Also</span></span>  
 [<span data-ttu-id="10af4-118">Компоненты собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="10af4-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
