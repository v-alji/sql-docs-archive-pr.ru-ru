---
title: ISQLServerErrorInfo (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- ISQLServerErrorInfo interface
ms.assetid: a8323b5c-686a-4235-a8d2-bda43617b3a1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 222349bcaa88058dea1d9c5302883667c22d4092
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751391"
---
# <a name="isqlservererrorinfo-ole-db"></a><span data-ttu-id="e1c0b-102">ISQLServerErrorInfo (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="e1c0b-102">ISQLServerErrorInfo (OLE DB)</span></span>
  <span data-ttu-id="e1c0b-103">Поставщик OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяет интерфейс для работы с ошибками **ISQLServerErrorInfo** .</span><span class="sxs-lookup"><span data-stu-id="e1c0b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the **ISQLServerErrorInfo** error interface.</span></span> <span data-ttu-id="e1c0b-104">Этот интерфейс возвращает подробные сведения об ошибке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], в том числе уровень серьезности и состояние.</span><span class="sxs-lookup"><span data-stu-id="e1c0b-104">This interface returns details from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error, including its severity and state.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1c0b-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e1c0b-105">In This Section</span></span>  
  
|<span data-ttu-id="e1c0b-106">Метод</span><span class="sxs-lookup"><span data-stu-id="e1c0b-106">Method</span></span>|<span data-ttu-id="e1c0b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e1c0b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1c0b-108">ISQLServerErrorInfo:: Жетерроринфо &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e1c0b-108">ISQLServerErrorInfo::GetErrorInfo &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md)|<span data-ttu-id="e1c0b-109">Возвращает указатель на структуру SSERRORINFO поставщика OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , содержащей сведения об ошибке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1c0b-109">Returns a pointer to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider SSERRORINFO structure that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error details.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1c0b-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1c0b-110">See Also</span></span>  
 <span data-ttu-id="e1c0b-111">[Интерфейсы &#40;OLE DB&#41;](../../../2014/database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="e1c0b-111">[Interfaces &#40;OLE DB&#41;](../../../2014/database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 [<span data-ttu-id="e1c0b-112">Подробные сведения об ошибках SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1c0b-112">SQL Server Error Detail</span></span>](../../relational-databases/native-client-ole-db-errors/sql-server-error-detail.md)  
  
  
