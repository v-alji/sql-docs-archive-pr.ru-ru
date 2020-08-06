---
title: Выполнение хранимых процедур (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [OLE DB], executing
- OLE DB, stored procedures
- SQL Server Native Client OLE DB provider, stored procedures
ms.assetid: c77d9be9-2176-4438-8c7a-04b63ebece08
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e6ce951f343002feea5aa793d0cc2092422b819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738198"
---
# <a name="running-stored-procedures-ole-db"></a><span data-ttu-id="ad30f-102">Выполнение хранимых процедур (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ad30f-102">Running Stored Procedures (OLE DB)</span></span>
  <span data-ttu-id="ad30f-103">При выполнении инструкций вызов хранимой процедуры в источнике данных (вместо выполнения или подготовки инструкции непосредственно в клиентском приложении) может обеспечить следующее:</span><span class="sxs-lookup"><span data-stu-id="ad30f-103">When executing statements, calling a stored procedure on the data source (instead of executing or preparing a statement in the client application directly) can provide:</span></span>  
  
-   <span data-ttu-id="ad30f-104">высокую производительность;</span><span class="sxs-lookup"><span data-stu-id="ad30f-104">Higher performance.</span></span>  
  
-   <span data-ttu-id="ad30f-105">низкие издержки сети;</span><span class="sxs-lookup"><span data-stu-id="ad30f-105">Reduced network overhead.</span></span>  
  
-   <span data-ttu-id="ad30f-106">лучшую согласованность;</span><span class="sxs-lookup"><span data-stu-id="ad30f-106">Better consistency.</span></span>  
  
-   <span data-ttu-id="ad30f-107">большую точность;</span><span class="sxs-lookup"><span data-stu-id="ad30f-107">Better accuracy.</span></span>  
  
-   <span data-ttu-id="ad30f-108">дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="ad30f-108">Added functionality.</span></span>  
  
 <span data-ttu-id="ad30f-109">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента поддерживает три механизма, с помощью которых [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] хранимые процедуры возвращают данные:</span><span class="sxs-lookup"><span data-stu-id="ad30f-109">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports three of the mechanisms that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stored procedures use to return data:</span></span>  
  
-   <span data-ttu-id="ad30f-110">Каждая инструкция SELECT в хранимой процедуре формирует результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="ad30f-110">Every SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="ad30f-111">Процедура может возвращать данные через выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="ad30f-111">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="ad30f-112">Процедура может иметь целочисленный код возврата.</span><span class="sxs-lookup"><span data-stu-id="ad30f-112">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="ad30f-113">Приложение должно быть способно обработать все эти данные, возвращаемые хранимыми процедурами.</span><span class="sxs-lookup"><span data-stu-id="ad30f-113">The application must be able to handle all of these outputs from stored procedures.</span></span>  
  
 <span data-ttu-id="ad30f-114">Разные поставщики OLE DB возвращают выходные параметры и значения на разных этапах во время обработки результатов.</span><span class="sxs-lookup"><span data-stu-id="ad30f-114">Different OLE DB providers return output parameters and return values at different times during result processing.</span></span> <span data-ttu-id="ad30f-115">В случае с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщиком собственного клиента OLE DB выходные параметры и коды возврата не предоставляются до тех пор, пока потребитель не извлек или не отменил результирующие наборы, возвращенные хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="ad30f-115">In case of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the output parameters and return codes are not supplied until after the consumer has retrieved or canceled the result sets returned by the stored procedure.</span></span> <span data-ttu-id="ad30f-116">Коды возврата и выходные параметры возвращаются сервером в последнем пакете потока табличных данных.</span><span class="sxs-lookup"><span data-stu-id="ad30f-116">The return codes and the output parameters are returned in the last TDS packet from the server.</span></span>  
  
 <span data-ttu-id="ad30f-117">Поставщики используют свойство DBPROP_OUTPUTPARAMETERAVAILABILITY для сообщения о возвращении выходных параметров и возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="ad30f-117">Providers use the DBPROP_OUTPUTPARAMETERAVAILABILITY property to report when it returns output parameters and return values.</span></span> <span data-ttu-id="ad30f-118">Это свойство доступно в наборе свойств DBPROPSET_DATASOURCEINFO.</span><span class="sxs-lookup"><span data-stu-id="ad30f-118">This property is in the DBPROPSET_DATASOURCEINFO property set.</span></span>  
  
 <span data-ttu-id="ad30f-119">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента задает для свойства DBPROP_OUTPUTPARAMETERAVAILABILITY значение DBPROPVAL_OA_ATROWRELEASE, чтобы указать, что коды возврата и выходные параметры не возвращаются до тех пор, пока результирующий набор не будет обработан или освобожден.</span><span class="sxs-lookup"><span data-stu-id="ad30f-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets the DBPROP_OUTPUTPARAMETERAVAILABILITY property to DBPROPVAL_OA_ATROWRELEASE to indicate that return codes and output parameters are not returned until the result set is processed or released.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad30f-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad30f-120">See Also</span></span>  
 [<span data-ttu-id="ad30f-121">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="ad30f-121">Stored Procedures</span></span>](stored-procedures.md)  
  
  
