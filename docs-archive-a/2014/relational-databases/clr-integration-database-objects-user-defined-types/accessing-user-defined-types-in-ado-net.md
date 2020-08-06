---
title: Доступ к определяемым пользователем типам в ADO.NET | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- UDTs [CLR integration], ADO.NET
- user-defined types [CLR integration], ADO.NET
ms.assetid: 4b0d876c-8066-490e-8e18-327c0e942b19
author: rothja
ms.author: jroth
ms.openlocfilehash: a94e333ad743ed07dff6b973ebfe227312a1cab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666664"
---
# <a name="accessing-user-defined-types-in-adonet"></a><span data-ttu-id="60a5b-102">Доступ к определяемым пользователем типам в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="60a5b-102">Accessing User-Defined Types in ADO.NET</span></span>
  <span data-ttu-id="60a5b-103">Определяемые пользователем типы записываются с помощью любого языка, поддерживаемого [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework среде CLR, которая создает проверяемый код.</span><span class="sxs-lookup"><span data-stu-id="60a5b-103">User-defined types (UDTs) are written using any of the languages supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="60a5b-104">Сюда относятся языки [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# и [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="60a5b-104">This includes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span></span> <span data-ttu-id="60a5b-105">Определяемые пользователем типы разрешают сохранять объекты и пользовательские структуры данных в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60a5b-105">UDTs allow objects and custom data structures to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="60a5b-106">Данные представляются как открытые элементы класса или структуры .NET Framework, а поведение определяется методами класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="60a5b-106">The data is exposed as public members of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span> <span data-ttu-id="60a5b-107">Пользовательский тип можно использовать в качестве определения столбца таблицы, переменной в пакете [!INCLUDE[tsql](../../includes/tsql-md.md)], аргумента функции или хранимой процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60a5b-107">A UDT can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
 <span data-ttu-id="60a5b-108">В ADO.NET поставщик `System.Data.SqlClient` представляет определяемые пользователем типы следующими способами.</span><span class="sxs-lookup"><span data-stu-id="60a5b-108">In ADO.NET, the `System.Data.SqlClient` provider exposes UDTs in the following ways:</span></span>  
  
-   <span data-ttu-id="60a5b-109">Через класс `System.Data.SqlClient.SqlDataReader` в виде объекта.</span><span class="sxs-lookup"><span data-stu-id="60a5b-109">Through the `System.Data.SqlClient.SqlDataReader` as an object.</span></span>  
  
-   <span data-ttu-id="60a5b-110">Через объект `SqlDataReader` в виде необработанных байт.</span><span class="sxs-lookup"><span data-stu-id="60a5b-110">Through the `SqlDataReader` as raw bytes.</span></span>  
  
-   <span data-ttu-id="60a5b-111">В виде параметра объекта `System.Data.SqlClient.SqlParameter`.</span><span class="sxs-lookup"><span data-stu-id="60a5b-111">As a parameter of a `System.Data.SqlClient.SqlParameter` object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60a5b-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="60a5b-112">In This Section</span></span>  
 [<span data-ttu-id="60a5b-113">Получение данных определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="60a5b-113">Retrieving UDT Data</span></span>](accessing-user-defined-types-retrieving-udt-data.md)  
 <span data-ttu-id="60a5b-114">Описывает, как получить данные определяемого пользователем типа и как указать параметры.</span><span class="sxs-lookup"><span data-stu-id="60a5b-114">Describes how to retrieve UDT data and how to specify parameters.</span></span>  
  
 [<span data-ttu-id="60a5b-115">Обновление столбцов определяемых пользователем типов с помощью DataAdapter</span><span class="sxs-lookup"><span data-stu-id="60a5b-115">Updating UDT Columns with DataAdapters</span></span>](accessing-user-defined-types-updating-udt-columns-with-dataadapters.md)  
 <span data-ttu-id="60a5b-116">Описывает, как работать с определяемыми пользователем типами в `DataSets` и как обновить данные определяемого пользователем типа с помощью `DataAdapters`.</span><span class="sxs-lookup"><span data-stu-id="60a5b-116">Describes how to work with UDTs in `DataSets` and how to update UDT data using `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a5b-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="60a5b-117">See Also</span></span>  
 [<span data-ttu-id="60a5b-118">Определяемые пользователем типы CLR</span><span class="sxs-lookup"><span data-stu-id="60a5b-118">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
  
  
