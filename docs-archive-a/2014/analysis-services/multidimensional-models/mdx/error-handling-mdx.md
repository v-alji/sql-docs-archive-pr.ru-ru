---
title: Обработка ошибок (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], exceptions
- exceptions [MDX]
ms.assetid: bc6ff0af-9fe6-44d6-bc3c-801d71ea41a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 357194b9f789fdeacfb65ce3c894d4747867eafb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666836"
---
# <a name="error-handling-mdx"></a><span data-ttu-id="03b83-102">Обработка ошибок (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="03b83-102">Error Handling (MDX)</span></span>
  <span data-ttu-id="03b83-103">Каждый куб может управлять способом обработки ошибок в скриптах многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="03b83-103">Each cube can control how errors within a Multidimensional Expressions (MDX) script are handled.</span></span> <span data-ttu-id="03b83-104">Обработка ошибок осуществляется с помощью перечислителя `ScriptErrorHandlingMode`.</span><span class="sxs-lookup"><span data-stu-id="03b83-104">Error handling is done through the `ScriptErrorHandlingMode` enumerator.</span></span> <span data-ttu-id="03b83-105">Перечислитель может принимать следующие значения.</span><span class="sxs-lookup"><span data-stu-id="03b83-105">The possible values for this enumerator are:</span></span>  
  
 `IgnoreNone`  
 <span data-ttu-id="03b83-106">Заставляет сервер вызывать ошибку при [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] обнаружении любой ошибки в скрипте многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="03b83-106">Causes the server to raise an error when [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] finds any error in the MDX script.</span></span>  
  
 `IgnoreAll`  
 <span data-ttu-id="03b83-107">Сервер игнорирует все команды с ошибками в скрипте многомерных выражений, включая синтаксические ошибки, ошибки разрешения имен и пр.</span><span class="sxs-lookup"><span data-stu-id="03b83-107">Causes the server to ignore all commands in the MDX script that contain an error, including syntax errors, name resolution errors, and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b83-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="03b83-108">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Cube.ScriptErrorHandlingMode%2A>  
  
  
