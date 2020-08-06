---
title: Команды, формирующие результаты с несколькими наборами строк | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- multiple rowsets
- rowsets [OLE DB], multiple
- SQL Server Native Client OLE DB provider, commands
- SQL Server Native Client OLE DB provider, multiple rowsets
- commands [OLE DB]
- multiple-rowset results
ms.assetid: 4567668d-35fd-4162-b61f-f7536862cdcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b42a89c0b043e4c72e8b5634cf70e16b435167a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728233"
---
# <a name="commands-generating-multiple-rowset-results"></a><span data-ttu-id="54856-102">Команды, формирующие результаты с несколькими наборами строк</span><span class="sxs-lookup"><span data-stu-id="54856-102">Commands Generating Multiple-Rowset Results</span></span>
  <span data-ttu-id="54856-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента может возвращать несколько наборов строк из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] инструкций.</span><span class="sxs-lookup"><span data-stu-id="54856-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can return multiple rowsets from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements.</span></span> <span data-ttu-id="54856-104">Инструкции [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] возвращают результаты, содержащие несколько наборов строк, в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="54856-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements return multiple-rowset results under the following conditions:</span></span>  
  
-   <span data-ttu-id="54856-105">Пакетные инструкции SQL представляются как единая команда.</span><span class="sxs-lookup"><span data-stu-id="54856-105">Batched SQL statements are submitted as a single command.</span></span>  
  
-   <span data-ttu-id="54856-106">Хранимые процедуры реализуют пакет инструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="54856-106">Stored procedures implement a batch of SQL statements.</span></span>  
  
## <a name="batches"></a><span data-ttu-id="54856-107">Пакеты</span><span class="sxs-lookup"><span data-stu-id="54856-107">Batches</span></span>  
 <span data-ttu-id="54856-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Поставщик OLE DB собственного клиента распознает символ точки с запятой как разделитель пакетной службы для инструкций SQL:</span><span class="sxs-lookup"><span data-stu-id="54856-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes the semicolon character as a batch delimiter for SQL statements:</span></span>  
  
```  
WCHAR*       wSQLString = L"SELECT * FROM Categories; "  
                          L"SELECT * FROM Products";  
```  
  
 <span data-ttu-id="54856-109">Отправка нескольких инструкций SQL в одном пакете более эффективна, чем выполнение каждой инструкции SQL по отдельности.</span><span class="sxs-lookup"><span data-stu-id="54856-109">Sending multiple SQL statements in one batch is more efficient than executing each SQL statement separately.</span></span> <span data-ttu-id="54856-110">Отправка одного пакета уменьшает количество циклов приема-передачи данных с клиента на сервер.</span><span class="sxs-lookup"><span data-stu-id="54856-110">Sending one batch reduces the network round trips from the client to the server.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="54856-111">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="54856-111">Stored Procedures</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="54856-112">возвращает результирующий набор для каждой инструкции в хранимой процедуре, поэтому большинство хранимых процедур [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] возвращает несколько результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="54856-112">returns a result set for each statement in a stored procedure, so most [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return multiple result sets.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54856-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="54856-113">In This Section</span></span>  
  
-   [<span data-ttu-id="54856-114">Обработка нескольких результирующих наборов при помощи интерфейса IMultipleResults</span><span class="sxs-lookup"><span data-stu-id="54856-114">Using IMultipleResults to Process Multiple Result Sets</span></span>](using-imultipleresults-to-process-multiple-result-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="54856-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="54856-115">See Also</span></span>  
 [<span data-ttu-id="54856-116">Команды</span><span class="sxs-lookup"><span data-stu-id="54856-116">Commands</span></span>](commands.md)  
  
  
