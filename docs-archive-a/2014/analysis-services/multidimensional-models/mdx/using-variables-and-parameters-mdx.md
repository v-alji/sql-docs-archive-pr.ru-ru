---
title: Использование переменных и параметров (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [MDX]
- queries [MDX], variables
- queries [MDX], parameters
- variables [MDX]
ms.assetid: a4754d16-d9c4-49f6-9be0-392180b912e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd01cf78ea5e3284aa51cad7dc848176a5dc9298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736989"
---
# <a name="using-variables-and-parameters-mdx"></a><span data-ttu-id="5fed9-102">Переменные и параметры (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="5fed9-102">Using Variables and Parameters (MDX)</span></span>
  <span data-ttu-id="5fed9-103">В [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] можно параметризовать инструкцию многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="5fed9-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], you can parameterize a Multidimensional Expressions (MDX) statement.</span></span> <span data-ttu-id="5fed9-104">Благодаря параметризации можно создавать универсальные инструкции, настраиваемые во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5fed9-104">A parameterized statement lets you create generic statements that can be customized at runtime.</span></span>  
  
 <span data-ttu-id="5fed9-105">Имена параметров при создании параметризованных инструкций обозначаются префиксом «@».</span><span class="sxs-lookup"><span data-stu-id="5fed9-105">In creating a parameterized statement, you identify the parameter name by prefixing the name with the at sign (@).</span></span> <span data-ttu-id="5fed9-106">Например, @Year является допустимым именем параметра.</span><span class="sxs-lookup"><span data-stu-id="5fed9-106">For example, @Year would be a valid parameter name</span></span>  
  
 <span data-ttu-id="5fed9-107">В языке многомерных выражений поддерживаются только параметры для строковых и скалярных значений.</span><span class="sxs-lookup"><span data-stu-id="5fed9-107">MDX supports only parameters for literal or scalar values.</span></span> <span data-ttu-id="5fed9-108">Чтобы создать параметр, который ссылается на элемент, набор или кортеж, необходимо использовать функцию, например [StrToMember](/sql/mdx/strtomember-mdx) или [StrToSet](/sql/mdx/strtoset-mdx).</span><span class="sxs-lookup"><span data-stu-id="5fed9-108">To create a parameter that references a member, set, or tuple, you would have to use a function such as [StrToMember](/sql/mdx/strtomember-mdx) or [StrToSet](/sql/mdx/strtoset-mdx).</span></span>  
  
 <span data-ttu-id="5fed9-109">В следующем примере XML для аналитики (XMLA) @CountryName параметр будет содержать страну, для которой извлекаются данные клиента:</span><span class="sxs-lookup"><span data-stu-id="5fed9-109">In the following XML for Analysis (XMLA) example, the @CountryName parameter will contain the country for which customer data is retrieved:</span></span>  
  
```  
<Envelope xmlns="http://schemas.xmlsoap.org/soap/envelope/">  
  <Body>  
    <Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
      <Command>  
        <Statement>  
select [Measures].members on 0,   
       Filter(Customer.[Customer Geography].Country.members,   
              Customer.[Customer Geography].CurrentMember.Name =  
              @CountryName) on 1  
from [Adventure Works]  
</Statement>  
      </Command>  
      <Properties />  
      <Parameters>  
        <Parameter>  
          <Name>CountryName</Name>  
          <Value>'United Kingdom'</Value>  
        </Parameter>  
      </Parameters>  
    </Execute>  
  </Body>  
</Envelope>  
```  
  
 <span data-ttu-id="5fed9-110">В OLE DB эти возможности доступны через интерфейс `ICommandWithParameters`.</span><span class="sxs-lookup"><span data-stu-id="5fed9-110">To use this functionality with OLE DB, you would use the `ICommandWithParameters` interface.</span></span> <span data-ttu-id="5fed9-111">В ADOMD.Net для этого необходимо использовать коллекцию **AdomdCommand.Parameters** .</span><span class="sxs-lookup"><span data-stu-id="5fed9-111">To use this functionality with ADOMD.Net, you would use the **AdomdCommand.Parameters** collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fed9-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="5fed9-112">See Also</span></span>  
 [<span data-ttu-id="5fed9-113">Основные принципы создания скриптов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="5fed9-113">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
