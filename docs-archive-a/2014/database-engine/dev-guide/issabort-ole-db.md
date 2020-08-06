---
title: ISSAbort (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- ISSAbort interface
ms.assetid: 7c4df482-4a83-4da0-802b-3637b507693a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7195311fefe3f0f1b7b4d6d789aa8d8487bc3bfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751384"
---
# <a name="issabort-ole-db"></a><span data-ttu-id="8cad2-102">ISSAbort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="8cad2-102">ISSAbort (OLE DB)</span></span>
  <span data-ttu-id="8cad2-103">Интерфейс **ISSAbort** , доступ к которому обеспечивает поставщик OLE DB собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , предоставляет метод [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) , используемый для отмены текущего набора строк, а также любых команд, находящихся в одном пакете с командой, первоначально создавшей этот набор строк, и еще не завершивших выполнение.</span><span class="sxs-lookup"><span data-stu-id="8cad2-103">The **ISSAbort** interface, which is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, provides the [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) method that is used to cancel the current rowset plus any commands batched with the command that initially generated the rowset, and that have not yet completed execution.</span></span>  
  
 <span data-ttu-id="8cad2-104">Интерфейс**ISSAbилиt** является специфичным для поставщика собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; доступ к этому интерфейсу можно получить с помощью метода **QueryInterface** интерфейса **IMultipleResults** объекта, возвращенного методом **ICommand::Execute** или **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="8cad2-104">**ISSAbort** is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider-specific interface available by using **QueryInterface** on the **IMultipleResults** object returned by **ICommand::Execute** or **IOpenRowset::OpenRowset**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8cad2-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="8cad2-105">In This Section</span></span>  
  
|<span data-ttu-id="8cad2-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8cad2-106">Method</span></span>|<span data-ttu-id="8cad2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8cad2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8cad2-108">ISSAbort:: Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8cad2-108">ISSAbort::Abort &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md)|<span data-ttu-id="8cad2-109">Отменяет текущий набор строк и любые пакетные команды, ассоциированные с текущей командой.</span><span class="sxs-lookup"><span data-stu-id="8cad2-109">Cancels the current rowset plus any batched commands associated with the current command.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8cad2-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="8cad2-110">See Also</span></span>  
 [<span data-ttu-id="8cad2-111">Интерфейсы (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="8cad2-111">Interfaces &#40;OLE DB&#41;</span></span>](../../../2014/database-engine/dev-guide/interfaces-ole-db.md)  
  
  
