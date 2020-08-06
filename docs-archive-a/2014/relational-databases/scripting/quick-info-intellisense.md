---
title: Краткие сведения (технология IntelliSense)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Quick Info option [IntelliSense]
- declarations [IntelliSense]
- IntelliSense [SQL Server], Quick Info
- identifier declarations [IntelliSense]
ms.assetid: 3c8b59f4-1922-4bde-844f-5f2306514d96
author: rothja
ms.author: jroth
ms.openlocfilehash: 4f173c57438301702a8e51acf4531c655fde0cc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752095"
---
# <a name="quick-info-intellisense"></a><span data-ttu-id="375b1-102">Краткие сведения (технология IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="375b1-102">Quick Info (IntelliSense)</span></span>
  <span data-ttu-id="375b1-103">При установленном параметре [!INCLUDE[msCoName](../../includes/msconame-md.md)] Краткие сведения **в технологии** IntelliSense отображается полное объявление декларации любого идентификатора в коде.</span><span class="sxs-lookup"><span data-stu-id="375b1-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] IntelliSense **Quick Info** option displays the complete declaration for any identifier in your code.</span></span> <span data-ttu-id="375b1-104">При наведении указателя мыши на идентификатор его объявление отобразится в желтом всплывающем окне.</span><span class="sxs-lookup"><span data-stu-id="375b1-104">When you move the mouse pointer over an identifier, its declaration is displayed in a yellow pop-up window.</span></span> <span data-ttu-id="375b1-105">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**Краткие сведения** доступны для компонента Database Engine и редактора XML-запросов.</span><span class="sxs-lookup"><span data-stu-id="375b1-105">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], **Quick Info** is available in the Database Engine and XML Query Editors.</span></span>  
  
## <a name="transact-sql-quick-info"></a><span data-ttu-id="375b1-106">Краткие сведения по Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="375b1-106">Transact-SQL Quick Info</span></span>  
 <span data-ttu-id="375b1-107">Модуль**Краткие сведения** отображает в редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] два типа сведений.</span><span class="sxs-lookup"><span data-stu-id="375b1-107">**Quick Info** displays two types of information in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="375b1-108">Во всех режимах, кроме режима отладки, модуль **Quick Info** отображает объявление выражения.</span><span class="sxs-lookup"><span data-stu-id="375b1-108">When not in debug mode, **Quick Info** displays the expression declaration.</span></span> <span data-ttu-id="375b1-109">В режиме отладки модуль **Краткие сведения** отображает имя выражения и его текущее значение.</span><span class="sxs-lookup"><span data-stu-id="375b1-109">When in debug mode, **Quick Info** instead displays the name of the expression and its current value.</span></span>  
  
 <span data-ttu-id="375b1-110">В редакторе запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]**Краткие сведения** доступны только для поддерживаемых технологией IntelliSense частей синтаксиса [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="375b1-110">In the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor, **Quick Info** is available only for those parts of the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax that IntelliSense supports.</span></span> <span data-ttu-id="375b1-111">Например, если навести указатель мыши на идентификатор объекта, который имеет тип данных, не поддерживаемый технологией IntelliSense, то во всплывающем окне **Краткие сведения** появится сообщение о том, что этот тип данных не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="375b1-111">For example, if you move the mouse pointer over the identifier for an object that has a data type that IntelliSense does not support, the **Quick Info** pop-up window contains a message that states that the data type is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="375b1-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="375b1-112">See Also</span></span>  
 [<span data-ttu-id="375b1-113">Синтаксис языка Transact-SQL с поддержкой технологии IntelliSense</span><span class="sxs-lookup"><span data-stu-id="375b1-113">Transact-SQL Syntax Supported by IntelliSense</span></span>](transact-sql-syntax-supported-by-intellisense.md)  
  
  
