---
title: Общие сведения о настраиваемых атрибутах интеграции со средой CLR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- custom attributes [CLR integration]
- attributes [CLR integration]
- common language runtime [SQL Server], attributes
- database objects [CLR integration], custom attributes
- building database objects [CLR integration], custom attributes
ms.assetid: ecf5c097-0972-48e2-a9c0-b695b7dd2820
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: aa0bf94ee27fd89a6aa690e0ff2f8e3295648946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655343"
---
# <a name="overview-of-clr-integration-custom-attributes"></a><span data-ttu-id="ec403-102">Общие сведения о пользовательских атрибутах интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="ec403-102">Overview of CLR Integration Custom Attributes</span></span>
  <span data-ttu-id="ec403-103">В среде CLR [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] допускается использование описательных ключевых слов, именуемых атрибутами.</span><span class="sxs-lookup"><span data-stu-id="ec403-103">The common language runtime (CLR) of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] allows the use of descriptive keywords, called attributes.</span></span> <span data-ttu-id="ec403-104">Эти атрибуты содержат дополнительную информацию по многим элементам, таким как методы и классы.</span><span class="sxs-lookup"><span data-stu-id="ec403-104">These attributes provide additional information for many elements, such as methods and classes.</span></span> <span data-ttu-id="ec403-105">Эти атрибуты сохраняются в сборке с метаданными объекта и могут быть использованы для описания кода другим инструментальным средствам разработки или для изменения поведения на этапе выполнения внутри [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec403-105">The attributes are saved in the assembly with the metadata of the object, and can be used to describe your code to other development tools or to affect runtime behavior inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ec403-106">При регистрации подпрограммы среды CLR в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] получает набор свойств этой подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="ec403-106">When you register a CLR routine with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives a set of properties about the routine.</span></span> <span data-ttu-id="ec403-107">Эти свойства подпрограммы определяют возможности подпрограммы и в частности указывают на то, может ли она быть индексирована.</span><span class="sxs-lookup"><span data-stu-id="ec403-107">These routine properties determine the capabilities of the routine, including whether the routine can be indexed.</span></span> <span data-ttu-id="ec403-108">Так, если свойству `DataAccess` задается значение `DataAccessKind.Read`, тем самым открывается возможность обращения к данным из пользовательских таблиц [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] внутри функции CLR.</span><span class="sxs-lookup"><span data-stu-id="ec403-108">For example, setting the `DataAccess` property to `DataAccessKind.Read` lets you access data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user tables inside a CLR function.</span></span> <span data-ttu-id="ec403-109">В следующем примере показан простой случай, в котором `DataAccess` свойство задано для упрощения доступа к данным из пользовательской таблицы **Table1**.</span><span class="sxs-lookup"><span data-stu-id="ec403-109">The following example shows a simple case in which the `DataAccess` property is set to facilitate data access from a user table **table1**.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public partial class UserDefinedFunctions  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static string func1()  
    {  
        // Open a connection and create a command  
        SqlConnection conn = new SqlConnection("context connection = true");  
        conn.Open();  
        SqlCommand cmd = conn.CreateCommand();  
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10";  
        // where table1 is a user table  
        // Execute this command   
        SqlDataReader rd = cmd.ExecuteReader();  
        // Set string ret_val to str_val returned from the query  
        string ret_val = rd.GetValue(0).ToString();  
        rd.Close();  
        return ret_val;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public partial Class UserDefinedFunctions  
    <SqlFunction(DataAccess = DataAccessKind.Read)> _   
    Public Shared Function func1() As String  
        ' Open a connection and create a command  
        Dim conn As SqlConnection = New SqlConnection("context connection = true")   
        conn.Open()  
        Dim cmd As SqlCommand =  conn.CreateCommand()   
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10"  
        ' where table1 is a user table  
        ' Execute this command   
        Dim rd As SqlDataReader =  cmd.ExecuteReader()   
        ' Set string ret_val to str_val returned from the query  
        Dim ret_val As String =  rd.GetValue(0).ToString()   
        rd.Close()  
        Return ret_val  
    End Function  
End Class  
```  
  
 <span data-ttu-id="ec403-110">Что же касается подпрограмм [!INCLUDE[tsql](../../includes/tsql-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] получает свойства подпрограмм непосредственно из их определений.</span><span class="sxs-lookup"><span data-stu-id="ec403-110">For [!INCLUDE[tsql](../../includes/tsql-md.md)] routines, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives routine properties directly from the routine definition.</span></span> <span data-ttu-id="ec403-111">Сервер не анализирует тексты подпрограмм CLR для получения этих свойств.</span><span class="sxs-lookup"><span data-stu-id="ec403-111">For CLR routines, the server does not analyze the body of the routine to derive these properties.</span></span> <span data-ttu-id="ec403-112">Вместо этого можно использовать пользовательские атрибуты для классов и членов классов, реализованных в языке [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec403-112">Instead, you can use custom attributes for classes and class members implemented in a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language.</span></span>  
  
 <span data-ttu-id="ec403-113">Пользовательские атрибуты, необходимые для подпрограмм CLR, пользовательских типов и агрегатов, определяются в пространстве имен `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="ec403-113">The custom attributes needed for CLR routines, user-defined types, and aggregates are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec403-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="ec403-114">See Also</span></span>  
 [<span data-ttu-id="ec403-115">Пользовательские атрибуты для подпрограмм среды CLR</span><span class="sxs-lookup"><span data-stu-id="ec403-115">Custom Attributes for CLR Routines</span></span>](../../relational-databases/clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md)  
  
  
