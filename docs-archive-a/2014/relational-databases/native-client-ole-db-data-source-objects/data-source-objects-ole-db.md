---
title: Объекты источника данных (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], data source objects
- SQL Server Native Client, data source objects
- SQLNCLI, data source objects
- SQL Server Native Client OLE DB provider, data source objects
- OLE DB data source objects [SQL Server Native Client]
- data source objects [OLE DB]
- CLSID
ms.assetid: c1d4ed20-ad3b-4e33-a26b-38d7517237b7
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cf3f0b0308d655b50149c174547c19966f550ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728229"
---
# <a name="data-source-objects-ole-db"></a><span data-ttu-id="19600-102">Объекты источников данных (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="19600-102">Data Source Objects (OLE DB)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="19600-103">Собственный клиент использует термин источник данных для набора OLE DB интерфейсов, используемых для установления связи с хранилищем данных, например [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19600-103">Native Client uses the term data source for the set of OLE DB interfaces used to establish a link to a data store, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="19600-104">Создание экземпляра объекта источника данных поставщика является первой задачей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребителя собственного клиента.</span><span class="sxs-lookup"><span data-stu-id="19600-104">Creating an instance of the data source object of the provider is the first task of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client consumer.</span></span>  
  
 <span data-ttu-id="19600-105">Каждый поставщик OLE DB объявляет свой идентификатор класса (CLSID).</span><span class="sxs-lookup"><span data-stu-id="19600-105">Every OLE DB provider declares a class identifier (CLSID) for itself.</span></span> <span data-ttu-id="19600-106">Идентификатором CLSID для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщика собственного клиента OLE DB является GUID C/C++, CLSID_SQLNCLI10 (символ SQLNCLI_CLSID будет разрешаться в правильный идентификатор ProgID в файле sqlncli. h, на который вы ссылаетесь).</span><span class="sxs-lookup"><span data-stu-id="19600-106">The CLSID for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is the C/C++ GUID CLSID_SQLNCLI10 (the symbol SQLNCLI_CLSID will resolve to the correct progid in the sqlncli.h file that you reference).</span></span> <span data-ttu-id="19600-107">Используя CLSID, потребитель может вызвать функцию OLE **CoCreateInstance** для создания экземпляра объекта источника данных.</span><span class="sxs-lookup"><span data-stu-id="19600-107">With the CLSID, the consumer uses the OLE **CoCreateInstance** function to manufacture an instance of the data source object.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="19600-108">Собственный клиент — это внутрипроцессный сервер.</span><span class="sxs-lookup"><span data-stu-id="19600-108">Native Client is an in-process server.</span></span> <span data-ttu-id="19600-109">Экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] объектов поставщика собственного клиента OLE DB создаются с помощью макроса CLSCTX_INPROC_SERVER для указания контекста исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="19600-109">Instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider objects are created using the CLSCTX_INPROC_SERVER macro to indicate the executable context.</span></span>  
  
 <span data-ttu-id="19600-110">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Объект источника данных поставщика собственного клиента OLE DB предоставляет интерфейсы инициализации OLE DB, позволяющие потребителю подключаться к существующим [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базам данных.</span><span class="sxs-lookup"><span data-stu-id="19600-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object exposes the OLE DB initialization interfaces that allow the consumer to connect to existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
 <span data-ttu-id="19600-111">Каждое подключение, устанавливаемое [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставщиком OLE DB собственного клиента, задает эти параметры автоматически:</span><span class="sxs-lookup"><span data-stu-id="19600-111">Every connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets these options automatically:</span></span>  
  
-   <span data-ttu-id="19600-112">SET ANSI_WARNINGS ON</span><span class="sxs-lookup"><span data-stu-id="19600-112">SET ANSI_WARNINGS ON</span></span>  
  
-   <span data-ttu-id="19600-113">SET ANSI_NULLS ON</span><span class="sxs-lookup"><span data-stu-id="19600-113">SET ANSI_NULLS ON</span></span>  
  
-   <span data-ttu-id="19600-114">SET ANSI_PADDING ON</span><span class="sxs-lookup"><span data-stu-id="19600-114">SET ANSI_PADDING ON</span></span>  
  
-   <span data-ttu-id="19600-115">SET ANSI_NULL_DFLT_ON ON</span><span class="sxs-lookup"><span data-stu-id="19600-115">SET ANSI_NULL_DFLT_ON ON</span></span>  
  
-   <span data-ttu-id="19600-116">SET QUOTED_IDENTIFIER ON</span><span class="sxs-lookup"><span data-stu-id="19600-116">SET QUOTED_IDENTIFIER ON</span></span>  
  
-   <span data-ttu-id="19600-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span><span class="sxs-lookup"><span data-stu-id="19600-117">SET CONCAT_OF_NULL_YIELDS_NULL ON</span></span>  
  
 <span data-ttu-id="19600-118">В этом примере используется макрос идентификатора класса для создания [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственного клиента OLE DB объекта источника данных поставщика и получения ссылки на его интерфейс **IDBInitialize** .</span><span class="sxs-lookup"><span data-stu-id="19600-118">This example uses the class identifier macro to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object and get a reference to its **IDBInitialize** interface.</span></span>  
  
```  
IDBInitialize*   pIDBInitialize;  
HRESULT          hr;  
  
hr = CoCreateInstance(CLSID_SQLNCLI10, NULL, CLSCTX_INPROC_SERVER,  
    IID_IDBInitialize, (void**) &pIDBInitialize);  
  
if (SUCCEEDED(hr))  
{  
    //  Perform necessary processing with the interface.  
    pIDBInitialize->Uninitialize();  
    pIDBInitialize->Release();  
}  
else  
{  
    // Display error from CoCreateInstance.  
}  
```  
  
 <span data-ttu-id="19600-119">При успешном создании экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] объекта источника данных поставщика собственного клиента OLE DB приложение-потребитель может продолжать работу, инициализируя источник данных и создавая сеансы.</span><span class="sxs-lookup"><span data-stu-id="19600-119">With successful creation of an instance of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source object, the consumer application can continue by initializing the data source and creating sessions.</span></span> <span data-ttu-id="19600-120">Сеансы OLE DB предоставляют интерфейсы, через которые можно получать доступ к данным и манипулировать ими.</span><span class="sxs-lookup"><span data-stu-id="19600-120">OLE DB sessions present the interfaces that allow data access and manipulation.</span></span>  
  
 <span data-ttu-id="19600-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента выполняет свое первое подключение к указанному экземпляру в ходе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] успешной инициализации источника данных.</span><span class="sxs-lookup"><span data-stu-id="19600-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider makes its first connection to a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as part of a successful data source initialization.</span></span> <span data-ttu-id="19600-122">Соединение с источником данных поддерживается до тех пор, пока хранятся ссылки на любой интерфейс инициализации источника данных или пока не вызван метод **IDBInitialize::Uninitialize**.</span><span class="sxs-lookup"><span data-stu-id="19600-122">The connection is maintained as long as a reference is maintained on any data source initialization interface, or until the **IDBInitialize::Uninitialize** method is called.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19600-123">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="19600-123">In This Section</span></span>  
  
-   [<span data-ttu-id="19600-124">Свойства источника данных &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="19600-124">Data Source Properties &#40;OLE DB&#41;</span></span>](data-source-properties-ole-db.md)  
  
-   [<span data-ttu-id="19600-125">Свойства сведений об источнике данных</span><span class="sxs-lookup"><span data-stu-id="19600-125">Data Source Information Properties</span></span>](data-source-information-properties.md)  
  
-   [<span data-ttu-id="19600-126">Свойства инициализации и авторизации</span><span class="sxs-lookup"><span data-stu-id="19600-126">Initialization and Authorization Properties</span></span>](initialization-and-authorization-properties.md)  
  
-   [<span data-ttu-id="19600-127">Сеансы</span><span class="sxs-lookup"><span data-stu-id="19600-127">Sessions</span></span>](sessions.md)  
  
-   [<span data-ttu-id="19600-128">Свойства сеанса</span><span class="sxs-lookup"><span data-stu-id="19600-128">Session Properties</span></span>](session-properties-sql-server-native-client-ole-db-provider.md)  
  
-   [<span data-ttu-id="19600-129">Материализованные данные исходного объекта</span><span class="sxs-lookup"><span data-stu-id="19600-129">Persisted Data Source Objects</span></span>](persisted-data-source-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="19600-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="19600-130">See Also</span></span>  
 [<span data-ttu-id="19600-131">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="19600-131">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
