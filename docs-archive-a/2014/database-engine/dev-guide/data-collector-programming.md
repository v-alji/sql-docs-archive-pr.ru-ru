---
title: Программирование сборщика данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- data collector [SQL Server], programming
ms.assetid: 53b4752b-055d-4716-b2bc-75b4cce84101
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9f4da839f25da8f8aab3e21fa98547eff72d2140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751439"
---
# <a name="data-collector-programming"></a><span data-ttu-id="01ab3-102">Программирование сборщика данных</span><span class="sxs-lookup"><span data-stu-id="01ab3-102">Data Collector Programming</span></span>
  <span data-ttu-id="01ab3-103">API-интерфейс сборщика данных (пространство имен <xref:Microsoft.SqlServer.Management.Collector>) обеспечивает программное управление всеми операциями настройки через объектную модель.</span><span class="sxs-lookup"><span data-stu-id="01ab3-103">The data collector API, in <xref:Microsoft.SqlServer.Management.Collector>, allows programmatic control of all configuration operations through the object model.</span></span> <span data-ttu-id="01ab3-104">Кроме того, многие операции сбора данных, использующие API, реализованы в виде хранимых процедур, установленных на сервере.</span><span class="sxs-lookup"><span data-stu-id="01ab3-104">In addition, many of the data collection operations that use the API are implemented as stored procedures that are installed on the server.</span></span>

 <span data-ttu-id="01ab3-105">На следующей иллюстрации показаны ключевые элементы модели объектов сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="01ab3-105">The following illustration shows key elements of the data collector object model.</span></span>

 <span data-ttu-id="01ab3-106">![Модель объектов сборщика данных](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "Модель объектов сборщика данных")</span><span class="sxs-lookup"><span data-stu-id="01ab3-106">![The Data Collector Object Model](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "The Data Collector Object Model")</span></span>


