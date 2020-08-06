---
title: Коды возврата | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB error handling, return codes
- SQL Server Native Client OLE DB provider, errors
- failed function [OLE DB]
- successful function [OLE DB]
- S_FALSE
- IS_ERROR macro
- DB_S_ERRORSOCCURRED return
- return codes [OLE DB]
- S_OK
- FAILED macro
- errors [OLE DB], return codes
ms.assetid: 7f7457e9-fce4-400c-82e5-ee02e9e811c6
author: rothja
ms.author: jroth
ms.openlocfilehash: dd033d16b1e95773d2cab1c4e1fca733dc491b96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667058"
---
# <a name="return-codes"></a><span data-ttu-id="de1ab-102">Коды возврата</span><span class="sxs-lookup"><span data-stu-id="de1ab-102">Return Codes</span></span>
  <span data-ttu-id="de1ab-103">Для краткости можно сказать, что вызов функции-члена класса или структуры завершается успешно либо с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="de1ab-103">At the most basic level, a member function either succeeds or fails.</span></span> <span data-ttu-id="de1ab-104">Точнее сказать, вызов функции может оказаться успешным, но результат оказывается не таким, на какой рассчитывал разработчик приложения.</span><span class="sxs-lookup"><span data-stu-id="de1ab-104">At a somewhat more precise level, a function can succeed, but its success may not be what the application developer intended.</span></span>  
  
 <span data-ttu-id="de1ab-105">Дополнительные сведения о кодах возврата OLE DB см. в статье [Коды возврата (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span><span class="sxs-lookup"><span data-stu-id="de1ab-105">For more information about OLE DB return codes, see [Return Codes (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span></span>  
  
 <span data-ttu-id="de1ab-106">Когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] функция-член поставщика собственного клиента OLE DB возвращает S_OK, функция прошла удачно.</span><span class="sxs-lookup"><span data-stu-id="de1ab-106">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function returns S_OK, the function succeeded.</span></span>  
  
 <span data-ttu-id="de1ab-107">Когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] функция-член поставщика собственного клиента OLE DB не возвращает S_OK, ошибка HRESULT OLE/COM-распаковки, а IS_ERROR макросы могут определить общую успешность или сбой функции.</span><span class="sxs-lookup"><span data-stu-id="de1ab-107">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function does not return S_OK, the OLE/COM HRESULT-unpacking FAILED and IS_ERROR macros can determine the overall success or failure of a function.</span></span>  
  
 <span data-ttu-id="de1ab-108">Если сбой или IS_ERROR возвращает значение TRUE, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребитель поставщика OLE DB собственного клиента гарантирует, что выполнение функции-члена завершилось ошибкой.</span><span class="sxs-lookup"><span data-stu-id="de1ab-108">If FAILED or IS_ERROR returns TRUE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that member function execution failed.</span></span> <span data-ttu-id="de1ab-109">Если сбой или IS_ERROR возвращают значение FALSE, а значение HRESULT не равно S_OK, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] потребитель поставщика OLE DB собственного клиента гарантирует, что функция была успешно выполнена в определенном смысле.</span><span class="sxs-lookup"><span data-stu-id="de1ab-109">When FAILED or IS_ERROR return FALSE and the HRESULT does not equal S_OK, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that the function succeeded in some sense.</span></span> <span data-ttu-id="de1ab-110">Потребитель может получить подробную информацию о возврате данных об успешном выполнении с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственного клиента OLE DB интерфейсах ошибок поставщика.</span><span class="sxs-lookup"><span data-stu-id="de1ab-110">The consumer can retrieve detailed information on this "success with information" return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span> <span data-ttu-id="de1ab-111">Кроме того, в случае, когда функция явно завершается неудачей (макрос FAILed возвращает значение TRUE), расширенные сведения об ошибке можно получить из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственного клиента OLE DB интерфейсы ошибок поставщика.</span><span class="sxs-lookup"><span data-stu-id="de1ab-111">Also, in the case where a function clearly fails (the FAILED macro returns TRUE), extended error information is available from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="de1ab-112">Потребители собственного клиента OLE DB поставщика обычно сталкиваются с возвратом DB_S_ERRORSOCCURRED "Success with Information".</span><span class="sxs-lookup"><span data-stu-id="de1ab-112">Native Client OLE DB provider consumers commonly encounter the DB_S_ERRORSOCCURRED "success with information" HRESULT return.</span></span> <span data-ttu-id="de1ab-113">Функции-члены, возвращающие значение DB_S_ERRORSOCCURRED, обычно определяют один или несколько параметров, предоставляющих потребителю значения состояния.</span><span class="sxs-lookup"><span data-stu-id="de1ab-113">Typically, member functions that return DB_S_ERRORSOCCURRED define one or more parameters that deliver status values to the consumer.</span></span> <span data-ttu-id="de1ab-114">Информация, возвращаемая через параметры состояния, может быть единственной информацией о состоянии, доступной потребителю; поэтому для получения значений состояния, когда они доступны, потребители должны реализовать собственную логику приложения.</span><span class="sxs-lookup"><span data-stu-id="de1ab-114">No error information may be available to the consumer other than that returned in status-value parameters, so consumers should implement application logic to retrieve status values when they are available.</span></span>  
  
 <span data-ttu-id="de1ab-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Функции члена поставщика собственного клиента OLE DB не возвращают код успешного выполнения S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="de1ab-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions do not return the success code S_FALSE.</span></span> <span data-ttu-id="de1ab-116">Все [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] функции члена поставщика собственного клиента OLE DB всегда возвращают S_OK, чтобы указать на успешное выполнение.</span><span class="sxs-lookup"><span data-stu-id="de1ab-116">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions always return S_OK to indicate success.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de1ab-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="de1ab-117">See Also</span></span>  
 [<span data-ttu-id="de1ab-118">ошибки</span><span class="sxs-lookup"><span data-stu-id="de1ab-118">Errors</span></span>](errors.md)  
  
  
