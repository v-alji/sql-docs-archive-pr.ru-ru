---
title: Объекты OLE-автоматизации (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], OLE Automation
- batches [SQL Server], OLE Automation
- OLE Automation [SQL Server]
- OLE Automation [SQL Server], about OLE Automation
ms.assetid: a887d956-4cd0-400a-aa96-00d7abd7c44b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f36846565bb60fbf875e9babdabbb6d1667f5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669384"
---
# <a name="ole-automation-objects-in-transact-sql"></a><span data-ttu-id="37342-102">Объекты OLE-автоматизации в Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="37342-102">OLE Automation Objects in Transact-SQL</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="37342-103">включен ряд системных хранимых процедур, позволяющих ссылаться на объекты OLE-автоматизации из пакетов [!INCLUDE[tsql](../../includes/tsql-md.md)] , хранимых процедур и триггеров.</span><span class="sxs-lookup"><span data-stu-id="37342-103">includes several system stored procedures that allow OLE Automation objects to be referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] batches, stored procedures, and triggers.</span></span> <span data-ttu-id="37342-104">Они выполняются как расширенные хранимые процедуры, при этом объекты OLE-автоматизации, запускаемые посредством хранимых процедур, работают в адресном пространстве экземпляра [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] аналогично расширенным хранимым процедурам.</span><span class="sxs-lookup"><span data-stu-id="37342-104">These system stored procedures run as extended stored procedures, and the OLE Automation objects that are executed through the stored procedures run in the address space of an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in the same way that an extended stored procedure runs.</span></span>  
  
 <span data-ttu-id="37342-105">Хранимые процедуры OLE-автоматизации позволяют пакетам [!INCLUDE[tsql](../../includes/tsql-md.md)] ссылаться на объекты SQL-DMO и пользовательские объекты OLE-автоматизации, например на объекты, реализующие интерфейс **IDispatch** .</span><span class="sxs-lookup"><span data-stu-id="37342-105">The OLE Automation stored procedures enable [!INCLUDE[tsql](../../includes/tsql-md.md)] batches to reference SQL-DMO objects and custom OLE Automation objects, such as objects that expose the **IDispatch** interface.</span></span> <span data-ttu-id="37342-106">Пользовательский внутрипроцессный OLE-сервер, созданный в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], должен иметь обработчик ошибок (определяемый по инструкции **On Error GoTo**) для подпрограмм **Class_Initialize** и **Class_Terminate**.</span><span class="sxs-lookup"><span data-stu-id="37342-106">A custom in-process OLE server that is created by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] must have an error handler (specified with the **On Error GoTo** statement) for the **Class_Initialize** and **Class_Terminate** subroutines.</span></span> <span data-ttu-id="37342-107">Все исключения, не обработанные в подпрограммах **Class_Initialize** и **Class_Terminate** , могут привести к непредвиденным ошибкам, в том числе вызвать нарушение общей защиты экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37342-107">Unhandled errors in the **Class_Initialize** and **Class_Terminate** subroutines can cause unpredictable errors, such as an access violation in an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="37342-108">Рекомендуется создавать обработчики ошибок и для остальных подпрограмм.</span><span class="sxs-lookup"><span data-stu-id="37342-108">Error handlers for other subroutines are also recommended.</span></span>  
  
 <span data-ttu-id="37342-109">При обращении к объекту OLE-автоматизации из [!INCLUDE[tsql](../../includes/tsql-md.md)] сперва необходимо вызвать системную хранимую процедуру **sp_OACreate** , которая создает экземпляр объекта в адресном пространстве экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37342-109">The first step when using an OLE Automation object in [!INCLUDE[tsql](../../includes/tsql-md.md)] is to call the **sp_OACreate** system stored procedure to create an instance of the object in the address space of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="37342-110">После создания экземпляра объекта можно вызывать следующие хранимые процедуры для работы со свойствами, методами и получением сведений об ошибках, связанных с созданным объектом.</span><span class="sxs-lookup"><span data-stu-id="37342-110">After an instance of the object has been created, call the following stored procedures to work with the properties, methods, and error information related to the object:</span></span>  
  
-   <span data-ttu-id="37342-111">**sp_OAGetProperty** возвращает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="37342-111">**sp_OAGetProperty** obtains the value of a property.</span></span>  
  
-   <span data-ttu-id="37342-112">**sp_OASetProperty** устанавливает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="37342-112">**sp_OASetProperty** sets the value of a property.</span></span>  
  
-   <span data-ttu-id="37342-113">**sp_OAMethod** вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="37342-113">**sp_OAMethod** calls a method.</span></span>  
  
-   <span data-ttu-id="37342-114">**sp_OAGetErrorInfo** возвращает сведения о последней возникшей ошибке.</span><span class="sxs-lookup"><span data-stu-id="37342-114">**sp_OAGetErrorInfo** obtains the most recent error information.</span></span>  
  
 <span data-ttu-id="37342-115">Когда объект больше не нужен, вызов хранимой процедуры **sp_OADestroy** позволяет освободить память, удалив объект, созданный хранимой процедурой **sp_OACreate**.</span><span class="sxs-lookup"><span data-stu-id="37342-115">When there is no more need for the object, call **sp_OADestroy** to deallocate the instance of the object created by using **sp_OACreate**.</span></span>  
  
 <span data-ttu-id="37342-116">Объекты OLE-автоматизации возвращают данные в качестве значений свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="37342-116">OLE Automation objects return data through property values and methods.</span></span> <span data-ttu-id="37342-117">**sp_OAGetProperty** и **sp_OAMethod** возвращают эти значения данных в форме результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="37342-117">**sp_OAGetProperty** and **sp_OAMethod** return these data values in the form of a result set.</span></span>  
  
 <span data-ttu-id="37342-118">Областью видимости объекта OLE-автоматизации является пакет.</span><span class="sxs-lookup"><span data-stu-id="37342-118">The scope of an OLE Automation object is a batch.</span></span> <span data-ttu-id="37342-119">Все ссылки на объект должны находиться в одном пакете, хранимой процедуре или триггере.</span><span class="sxs-lookup"><span data-stu-id="37342-119">All references to the object must be contained in a single batch, stored procedure, or trigger.</span></span>  
  
 <span data-ttu-id="37342-120">Объект OLE-автоматизации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по переданной ссылке позволяет производить доступ к другим содержащимся в нем объектам.</span><span class="sxs-lookup"><span data-stu-id="37342-120">When it references objects, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE Automation objects support traversing the referenced object to other objects that it contains.</span></span> <span data-ttu-id="37342-121">Например, если используется объект SQL-DMO **SQLServer** , возможна передача ссылок на базы данных и таблицы, содержащиеся на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="37342-121">For example, when using the SQL-DMO **SQLServer** object, references can be made to databases and tables contained on that server.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="37342-122">См. также</span><span class="sxs-lookup"><span data-stu-id="37342-122">Related Content</span></span>  
 [<span data-ttu-id="37342-123">Синтаксис иерархии объектов (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="37342-123">Object Hierarchy Syntax &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/object-hierarchy-syntax-transact-sql)  
  
 [<span data-ttu-id="37342-124">Настройка контактной зоны</span><span class="sxs-lookup"><span data-stu-id="37342-124">Surface Area Configuration</span></span>](../security/surface-area-configuration.md)  
  
 [<span data-ttu-id="37342-125">Параметр конфигурации сервера «Ole Automation Procedures»</span><span class="sxs-lookup"><span data-stu-id="37342-125">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
 [<span data-ttu-id="37342-126">sp_OACreate (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="37342-126">sp_OACreate &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oacreate-transact-sql)  
  
 [<span data-ttu-id="37342-127">sp_OAGetProperty (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="37342-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oagetproperty-transact-sql)  
  
 [<span data-ttu-id="37342-128">sp_OASetProperty (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="37342-128">sp_OASetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oasetproperty-transact-sql)  
  
 [<span data-ttu-id="37342-129">sp_OAMethod (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="37342-129">sp_OAMethod &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oamethod-transact-sql)  
  
 [<span data-ttu-id="37342-130">sp_OAGetErrorInfo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="37342-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql)  
  
 [<span data-ttu-id="37342-131">sp_OADestroy (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="37342-131">sp_OADestroy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oadestroy-transact-sql)  
  
  
