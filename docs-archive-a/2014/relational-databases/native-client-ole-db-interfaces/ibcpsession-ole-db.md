---
title: IBCPSession (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IBCPSession interface
ms.assetid: 00d0311f-8b71-4ad6-824d-0e89119347a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d32da9c06a200d5924dbae18d6b7513f46c88ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739809"
---
# <a name="ibcpsession-ole-db"></a><span data-ttu-id="ed3d8-102">Интерфейс IBCPSession (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ed3d8-102">IBCPSession (OLE DB)</span></span>
  <span data-ttu-id="ed3d8-103">Интерфейс **IBCPSession** предоставляет поддержку операций массового копирования [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на основе файлов.</span><span class="sxs-lookup"><span data-stu-id="ed3d8-103">The **IBCPSession** interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file-based bulk copy operations.</span></span> <span data-ttu-id="ed3d8-104">Интерфейс **IBCPSession** представлен в поставщике OLE DB собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] под тем же уровнем, что и объекты Session.</span><span class="sxs-lookup"><span data-stu-id="ed3d8-104">The **IBCPSession** interface is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider under the same level as Sessions.</span></span> <span data-ttu-id="ed3d8-105">В поставщике OLE DB собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] объекты источника данных являются фабриками объектов Session, и операции массового копирования указываются в свойстве соединения SSPROP_ENABLEBULKCOPY.</span><span class="sxs-lookup"><span data-stu-id="ed3d8-105">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, data source objects are factories for Session objects, and bulk copy operations are specified in the connection property SSPROP_ENABLEBULKCOPY.</span></span> <span data-ttu-id="ed3d8-106">Кроме того, свойство SSPROP_ENABLEFASTLOAD должно быть установлено в значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="ed3d8-106">In addition, the SSPROP_ENABLEFASTLOAD property should be set to true.</span></span>  
  
 <span data-ttu-id="ed3d8-107">Вызов метода **IDBCreateSession::CreateSession** приведет к созданию объекта **BulkCopySession** .</span><span class="sxs-lookup"><span data-stu-id="ed3d8-107">Calling the **IDBCreateSession::CreateSession** method will then result in the creation of a **BulkCopySession** object.</span></span> <span data-ttu-id="ed3d8-108">Все методы массового копирования, основанные на файлах, доступные через объект **IBCPSession** , можно вызывать с помощью этих объектов **IBCPSession** интерфейса **IBCPSession** .</span><span class="sxs-lookup"><span data-stu-id="ed3d8-108">All the file-based bulk copy methods exposed through the **IBCPSession** object are then callable with nearly similar signatures on this **IBCPSession** object's **IBCPSession** interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed3d8-109">Поставщик OLE DB собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает операции массового копирования в памяти через интерфейс [IRowsetFastLoad](irowsetfastload-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="ed3d8-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports memory-based bulk copy operations through the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="ed3d8-110">Дополнительные сведения об использовании [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственного клиента OLE DB поставщика для операций с массовым копированием см. в разделе [выполнение операций с массовым копированием](../native-client/features/performing-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ed3d8-110">For more information about using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider for bulk copy operations, see [Performing Bulk Copy Operations](../native-client/features/performing-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="ed3d8-111">Пример использования интерфейса **IBCPSession** см. в статье [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="ed3d8-111">For a sample showing how to use the **IBCPSession** interface, see [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed3d8-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="ed3d8-112">In This Section</span></span>  
  
|<span data-ttu-id="ed3d8-113">Метод</span><span class="sxs-lookup"><span data-stu-id="ed3d8-113">Method</span></span>|<span data-ttu-id="ed3d8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ed3d8-114">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed3d8-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ed3d8-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolfmt-ole-db.md)|<span data-ttu-id="ed3d8-116">Создает привязку между переменными программы и столбцами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed3d8-116">Creates a binding between program variables and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns.</span></span>|  
|[<span data-ttu-id="ed3d8-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ed3d8-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolumns-ole-db.md)|<span data-ttu-id="ed3d8-118">Задает количество полей для привязки к столбцам в таблице [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed3d8-118">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="ed3d8-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ed3d8-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcontrol-ole-db.md)|<span data-ttu-id="ed3d8-120">Устанавливает параметры для операции массового копирования.</span><span class="sxs-lookup"><span data-stu-id="ed3d8-120">Sets the options for a bulk copy operation.</span></span>|  
|[<span data-ttu-id="ed3d8-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ed3d8-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span></span>](ibcpsession-bcpdone-ole-db.md)|<span data-ttu-id="ed3d8-122">Фиксирует оставшиеся строки для отправки в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed3d8-122">Commits the remaining rows to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="ed3d8-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ed3d8-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span></span>](ibcpsession-bcpexec-ole-db.md)|<span data-ttu-id="ed3d8-124">Выполняет операцию массового копирования.</span><span class="sxs-lookup"><span data-stu-id="ed3d8-124">Performs the bulk copy operation.</span></span>|  
|[<span data-ttu-id="ed3d8-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ed3d8-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span></span>](ibcpsession-bcpinit-ole-db.md)|<span data-ttu-id="ed3d8-126">Инициализирует структуру массового копирования, выполняет проверку ошибок, проверяет правильность имен файла данных и файла форматирования, а затем открывает эти файлы.</span><span class="sxs-lookup"><span data-stu-id="ed3d8-126">Initializes the bulk copy structure, performs some error checking, verifies that the data and format file names are correct, and then opens them.</span></span>|  
|[<span data-ttu-id="ed3d8-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ed3d8-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpreadfmt-ole-db.md)|<span data-ttu-id="ed3d8-128">Считывает сведения о формате для каждого столбца из файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="ed3d8-128">Reads format information for each column from the format file.</span></span>|  
|[<span data-ttu-id="ed3d8-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ed3d8-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpwritefmt-ole-db.md)|<span data-ttu-id="ed3d8-130">Записывает в файл форматирования сведения о формате каждого из столбцов.</span><span class="sxs-lookup"><span data-stu-id="ed3d8-130">Writes format information for each column to the format file.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed3d8-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed3d8-131">See Also</span></span>  
 [<span data-ttu-id="ed3d8-132">Интерфейсы (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ed3d8-132">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
