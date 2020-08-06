---
title: ISSCommandWithParameters (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSCommandWithParameters interface
ms.assetid: 3419b7f3-36a3-4863-816e-e641e4e90496
author: rothja
ms.author: jroth
ms.openlocfilehash: 295026497a97b4ce13d1a1a68de48079809390ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657752"
---
# <a name="isscommandwithparameters-ole-db"></a><span data-ttu-id="30171-102">Интерфейс ISSCommandWithParameters (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="30171-102">ISSCommandWithParameters (OLE DB)</span></span>
  <span data-ttu-id="30171-103">Интерфейс**ISSCommandWithParameters** обеспечивает поддержку [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML и определяемых пользователем типов данных.</span><span class="sxs-lookup"><span data-stu-id="30171-103">**ISSCommandWithParameters** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML and user-defined types (UDT).</span></span> <span data-ttu-id="30171-104">Этот дополнительный интерфейс наследует основной интерфейс OLE DB, **ICommandWithParameters**.</span><span class="sxs-lookup"><span data-stu-id="30171-104">This is an optional interface that inherits from the core OLE DB interface **ICommandWithParameters**.</span></span> <span data-ttu-id="30171-105">Помимо трех методов, наследуемых из интерфейса **ICommandWithParameters**( **GetParameterInfo**, **MapParameterNames**и **SetParameterInfo**), интерфейс **ISSCommandWithParameters** содержит два новых метода, которые используются для обработки серверных типов данных.</span><span class="sxs-lookup"><span data-stu-id="30171-105">In addition to the three methods inherited from **ICommandWithParameters**; **GetParameterInfo**, **MapParameterNames**, and **SetParameterInfo**; **ISSCommandWithParameters** provides two new methods that are used to handle server specific data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30171-106"> Интерфейс **ISSCommandWithParameters** может использоваться при применении компонентов службы, однако сами компоненты службы этот интерфейс не используют.</span><span class="sxs-lookup"><span data-stu-id="30171-106">The **ISSCommandWithParameters** interface can be used when Service Components are used, but the Service Components themselves will not use this interface.</span></span>  
  
|<span data-ttu-id="30171-107">Метод</span><span class="sxs-lookup"><span data-stu-id="30171-107">Method</span></span>|<span data-ttu-id="30171-108">Описание</span><span class="sxs-lookup"><span data-stu-id="30171-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30171-109">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="30171-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-getparameterproperties-ole-db.md)|<span data-ttu-id="30171-110">Возвращает одну структуру набора свойств **SSPARAMPROPS** в массиве для каждого определяемого пользователем типа данных или XML-параметра, переданного команде, однако для других типов параметров не возвращается ничего.</span><span class="sxs-lookup"><span data-stu-id="30171-110">Returns one **SSPARAMPROPS** property set structure in the array for each UDT or XML parameter passed to the command, but none is returned for other types of parameters.</span></span>|  
|[<span data-ttu-id="30171-111">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="30171-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-setparameterproperties-ole-db.md)|<span data-ttu-id="30171-112">Задает свойства параметров для каждого параметра в отдельности по порядковому номеру либо задает свойства всех параметров сразу путем указания массива структур **SSPARAMPROPS** .</span><span class="sxs-lookup"><span data-stu-id="30171-112">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of **SSPARAMPROPS** structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30171-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="30171-113">See Also</span></span>  
 <span data-ttu-id="30171-114">[Интерфейсы &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="30171-114">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="30171-115">[Использование типов данных XML](../native-client/features/using-xml-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="30171-115">[Using XML Data Types](../native-client/features/using-xml-data-types.md) </span></span>  
 [<span data-ttu-id="30171-116">Использование определяемых пользователем типов данных</span><span class="sxs-lookup"><span data-stu-id="30171-116">Using User-Defined Types</span></span>](../native-client/features/using-user-defined-types.md)  
  
  
