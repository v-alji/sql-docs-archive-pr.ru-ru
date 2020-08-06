---
title: Поддержка FILESTREAM (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB [FILESTREAM support]
- FILESTREAM [SQL Server], OLE DB
ms.assetid: c2bd3dfd-6103-43d1-859e-8ed8d19c58d3
author: rothja
ms.author: jroth
ms.openlocfilehash: cde3c2cd1b72773cfcf17eacedeb3276dd2f63da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666010"
---
# <a name="filestream-support-ole-db"></a><span data-ttu-id="7247d-102">Поддержка FILESTREAM (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7247d-102">FILESTREAM Support (OLE DB)</span></span>
  <span data-ttu-id="7247d-103">Начиная с [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] собственного клиента 10,0, OLE DB поддерживает расширенную функцию FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7247d-103">Beginning with [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, OLE DB supports the enhanced FILESTREAM feature.</span></span> <span data-ttu-id="7247d-104">Дополнительные сведения об этой функции см. в разделе [Поддержка FILESTREAM](../features/filestream-support.md).</span><span class="sxs-lookup"><span data-stu-id="7247d-104">For more information about this feature, see [FILESTREAM Support](../features/filestream-support.md).</span></span> <span data-ttu-id="7247d-105">Примеры см. в статье [Filestream and OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md) (Filestream и OLE DB).</span><span class="sxs-lookup"><span data-stu-id="7247d-105">For samples, see [Filestream and OLE DB](../../native-client-ole-db-how-to/filestream/filestream-and-ole-db.md).</span></span>  
  
 <span data-ttu-id="7247d-106">Для отправки и получения значений `varbinary(max)` размером больше 2 ГБ приложение использует для привязки параметров и результата тип `DBTYPE_IUNKNOWN`.</span><span class="sxs-lookup"><span data-stu-id="7247d-106">To send and receive `varbinary(max)` values greater than 2 GB, an application uses `DBTYPE_IUNKNOWN` in parameter and result bindings.</span></span> <span data-ttu-id="7247d-107">Для получения параметров поставщик должен вызвать IUnknown::QueryInterface для ISequentialStream и для получения результатов, возвращающих ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="7247d-107">For parameters the provider must call IUnknown::QueryInterface for ISequentialStream and for results that return ISequentialStream.</span></span>  
  
 <span data-ttu-id="7247d-108">Для OLE DB проверка, связанная со значениями ISequentialStream, выполняется менее строго.</span><span class="sxs-lookup"><span data-stu-id="7247d-108">For OLE DB, checking related to ISequentialStream values will be relaxed.</span></span> <span data-ttu-id="7247d-109">Если *wType* находится `DBTYPE_IUNKNOWN` в `DBBINDING` структуре, проверка длины может быть отключена либо путем пропуска `DBPART_LENGTH` из *двпарт* , либо путем установки длины данных (в смещении *обленгс* в буфере данных) в ~ 0.</span><span class="sxs-lookup"><span data-stu-id="7247d-109">When *wType* is `DBTYPE_IUNKNOWN` in the `DBBINDING` struct, length checking can be disabled either by omitting `DBPART_LENGTH` from *dwPart* or by setting the length of the data (at offset *obLength* in the data buffer) to ~0.</span></span> <span data-ttu-id="7247d-110">В этом случае поставщик не будет проверять длину значения, а запросит и возвратит все данные, которые можно получить по потоку.</span><span class="sxs-lookup"><span data-stu-id="7247d-110">In this case, the provider will not check the length of the value and will request and return all of the data available through the stream.</span></span> <span data-ttu-id="7247d-111">Это изменение относится ко всем типам больших объектов (LOB) и XML, но только при подключении к серверу [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="7247d-111">This change will be applied to all large object (LOB) types and XML, but only when connected to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] (or later) servers.</span></span> <span data-ttu-id="7247d-112">Это предоставляет разработчикам большую гибкость, в то же время поддерживая согласованность и обратную совместимость с существующими приложениями и серверами предыдущих версий.</span><span class="sxs-lookup"><span data-stu-id="7247d-112">This will provide greater flexibility for developers, while maintaining consistency and backwards compatibility for existing applications and downlevel servers.</span></span>  
  
 <span data-ttu-id="7247d-113">Это изменение затрагивает все интерфейсы, которые передают данные, в основном IRowset::GetData, ICommand::Execute и IRowsetFastLoad::InsertRow.</span><span class="sxs-lookup"><span data-stu-id="7247d-113">This change affects all interfaces that transfer data, principally IRowset::GetData, ICommand::Execute, and IRowsetFastLoad::InsertRow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7247d-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="7247d-114">See Also</span></span>  
 [<span data-ttu-id="7247d-115">Программирование собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="7247d-115">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
