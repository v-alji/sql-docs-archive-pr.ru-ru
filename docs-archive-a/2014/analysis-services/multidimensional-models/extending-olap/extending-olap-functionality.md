---
title: Расширение функциональности OLAP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 49a17ff3-94e9-4969-84fc-37d49e63933b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d64d1ac46e2571aa6f8065a8ea42e4cc43aa589e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669121"
---
# <a name="extending-olap-functionality"></a><span data-ttu-id="21f06-102">Расширение функциональных возможностей OLAP</span><span class="sxs-lookup"><span data-stu-id="21f06-102">Extending OLAP functionality</span></span>
  <span data-ttu-id="21f06-103">Программист может расширять службы Analysis Services, написав сборки, персонализированные расширения и хранимые процедуры, обеспечивающие нужные функциональные возможности, которые можно использовать один или несколько раз в разнообразных приложениях базы данных.</span><span class="sxs-lookup"><span data-stu-id="21f06-103">As a programmer, you can extend Analysis Services by writing assemblies, personalized extensions, and stored procedures that provide functionality you want to use and repurpose in multiple database applications.</span></span> <span data-ttu-id="21f06-104">Сборки используются для расширения функциональных возможностей многомерных моделей путем добавления новых процедур и функций в язык многомерных выражений или путем встраивания персонализации.</span><span class="sxs-lookup"><span data-stu-id="21f06-104">Assemblies are used to extend multidimensional models functionality by adding new procedures and functions to the MDX language or by means of the personalization addin.</span></span>  
  
 <span data-ttu-id="21f06-105">Хранимые процедуры могут использоваться для вызова внешних подпрограмм, упрощая разработку и внедрение баз данных служб Analysis Services за счет однократной разработки общего программного кода и сохранения его в единственном местоположении.</span><span class="sxs-lookup"><span data-stu-id="21f06-105">Stored procedures can be used to call external routines, simplifying Analysis Services database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="21f06-106">Хранимые процедуры можно использовать для расширения функциональности приложений за счет добавления дополнительных функций к собственной функциональности многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="21f06-106">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="21f06-107">Персонализации представляют собой пользовательские объекты, которые могут добавляться в куб для обеспечения функций, которые отличаются от пользователя к пользователю.</span><span class="sxs-lookup"><span data-stu-id="21f06-107">Personalizations are custom objects that you add to a cube to provide a behavior that varies by user.</span></span> <span data-ttu-id="21f06-108">Персонализации не являются постоянными объектами куба, но представляют собой объекты, которые динамически применяются клиентским приложением во время сеанса конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="21f06-108">Personalizations are not permanent objects in the cube, but are objects that the client application applies dynamically during the user's session.</span></span> <span data-ttu-id="21f06-109">Например, изменение валют в денежном выражении в зависимости от пользователя, который осуществляет доступ к данным, предоставление индивидуальных ключевых показателей эффективности или целевых списков предложений для постоянных покупателей в сети.</span><span class="sxs-lookup"><span data-stu-id="21f06-109">Examples include changing the currency of a monetary value depending on the person accessing the data, providing individualized KPIs, or a targeted suggestion list for regular customers who purchase online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21f06-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="21f06-110">In This Section</span></span>  
 [<span data-ttu-id="21f06-111">Расширение OLAP через личные настройки</span><span class="sxs-lookup"><span data-stu-id="21f06-111">Extending OLAP through personalizations</span></span>](extending-olap-through-personalizations.md)  
  
 [<span data-ttu-id="21f06-112">Модули персонализации служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="21f06-112">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
 [<span data-ttu-id="21f06-113">Определение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="21f06-113">Defining Stored Procedures</span></span>](../../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
