---
title: Объект Склксмладаптер (управляемые классы SQLXML) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- void Update(DataSet ds) method
- SqlXmlAdapter object
- void Fill(DataSet ds) method
- SQLXML Managed Classes, SqlXmlAdapter object
- Managed Classes [SQLXML], SqlXmlAdapter object
ms.assetid: 0a16eddf-fc26-4d92-82d4-359b5fb905d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 1357ab7d070c7c2e451e31bccfda22c58eac42d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655012"
---
# <a name="sqlxmladapter-object-sqlxml-managed-classes"></a><span data-ttu-id="a327b-102">Объект SqlXmlAdapter (управляемые классы SQLXML)</span><span class="sxs-lookup"><span data-stu-id="a327b-102">SqlXmlAdapter Object (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="a327b-103">В этом объекте реализованы методы, облегчающие взаимодействие с набором данных в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a327b-103">This object provides methods that facilitate interaction with the dataset in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="a327b-104">Рабочий пример см. в разделе [доступ к функциям SQLXML в среде .NET](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a327b-104">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="a327b-105">Объект Склксмладаптер поддерживает следующие методы:</span><span class="sxs-lookup"><span data-stu-id="a327b-105">The SqlXmlAdapter object supports these methods:</span></span>  
  
 <span data-ttu-id="a327b-106">void Fill (набор данных DS)</span><span class="sxs-lookup"><span data-stu-id="a327b-106">void Fill(DataSet ds)</span></span>  
 <span data-ttu-id="a327b-107">Заполняет набор данных в .NET Framework XML-данными, полученными от [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a327b-107">Fills the dataset in the .NET Framework with the XML data retrieved from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a327b-108">пустое обновление (набор данных DS)</span><span class="sxs-lookup"><span data-stu-id="a327b-108">void Update(DataSet ds)</span></span>  
 <span data-ttu-id="a327b-109">Применяет обновления к записям в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] из данных, содержащихся в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="a327b-109">Applies updates to records in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the data in the dataset.</span></span>  
  
 <span data-ttu-id="a327b-110">Объект Склксмладаптер поддерживает следующие конструкторы:</span><span class="sxs-lookup"><span data-stu-id="a327b-110">The SqlXmlAdapter object supports these constructors:</span></span>  
  
```  
public SqlXmlAdapter(SqlXmlCommand  cmd)   
  
public SqlXmlAdapter(  
                     string commandText,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                      )   
  
public SqlXmlAdapter(  
                     Stream commandStream,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                     )   
```  
  
## <a name="see-also"></a><span data-ttu-id="a327b-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="a327b-111">See Also</span></span>  
 <span data-ttu-id="a327b-112">[Объект SqlXmlCommand &#40;управляемые классы SQLXML&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="a327b-112">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 [<span data-ttu-id="a327b-113">Объект SqlXmlParameter &#40;управляемые классы SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="a327b-113">SqlXmlParameter Object &#40;SQLXML Managed Classes&#41;</span></span>](sqlxml-managed-classes-sqlxmlparameter-object.md)  
  
  
