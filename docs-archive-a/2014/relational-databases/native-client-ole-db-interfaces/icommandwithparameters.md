---
title: ICommandWithParameters | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 66644c70-def7-46d8-8c47-b883292a0288
author: rothja
ms.author: jroth
ms.openlocfilehash: df3103181b3cad772e7d1c73068b8864bf591b73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667711"
---
# <a name="icommandwithparameters"></a><span data-ttu-id="12ccc-102">ICommandWithParameters</span><span class="sxs-lookup"><span data-stu-id="12ccc-102">ICommandWithParameters</span></span>
  <span data-ttu-id="12ccc-103">Улучшения ядра СУБД, появившиеся с версии [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], позволяют методу ICommandWithParameters::GetParameterInfo получать более точные описания ожидаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="12ccc-103">Improvements in the database engine beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ICommandWithParameters::GetParameterInfo to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="12ccc-104">Эти более точные результаты могут отличаться от значений, которые метод CommandWithParameters::GetParameterInfo возвращает в предыдущих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ccc-104">These more accurate results may differ from the values returned by CommandWithParameters::GetParameterInfo in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="12ccc-105">Дополнительные сведения см. в разделе [Обнаружение метаданных](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="12ccc-105">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="12ccc-106">Кроме того, начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] при вызове интерфейса ICommandWithParameters::SetParameterInfo значение, передаваемое параметру *pwszName*, должно быть допустимым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="12ccc-106">Also beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], when calling ICommandWithParameters::SetParameterInfo, the value passed to the *pwszName* parameter must be a valid identifier.</span></span> <span data-ttu-id="12ccc-107">Дополнительные сведения см. в разделе [Идентификаторы баз данных](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="12ccc-107">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12ccc-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="12ccc-108">See Also</span></span>  
 [<span data-ttu-id="12ccc-109">Интерфейсы (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="12ccc-109">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
