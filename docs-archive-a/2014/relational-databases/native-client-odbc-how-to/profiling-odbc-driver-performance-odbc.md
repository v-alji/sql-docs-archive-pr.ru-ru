---
title: Инструкции по профилированию производительности драйвера ODBC (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 0e6d7aed-28d2-419e-be6a-f60d3729bfd0
author: rothja
ms.author: jroth
ms.openlocfilehash: d27547862138b511a4defaa3cae80f48f69fdc4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655141"
---
# <a name="profiling-odbc-driver-performance-how-to-topics-odbc"></a><span data-ttu-id="55269-102">Инструкции по измерению производительности драйвера ODBC (ODBC)</span><span class="sxs-lookup"><span data-stu-id="55269-102">Profiling ODBC Driver Performance How-to Topics (ODBC)</span></span>
  <span data-ttu-id="55269-103">Драйвер ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет два параметра для измерения производительности драйвера.</span><span class="sxs-lookup"><span data-stu-id="55269-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver has two driver-specific options for profiling the performance of the driver.</span></span>  
  
 <span data-ttu-id="55269-104">Драйвер ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может записывать статистические показатели производительности в файл.</span><span class="sxs-lookup"><span data-stu-id="55269-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver can log performance statistics in file.</span></span> <span data-ttu-id="55269-105">Журнал статистики — это файл с разделителями-знаками табуляции, который можно проанализировать в приложении электронных таблиц, поддерживающем файлы с разделителями-знаками табуляции, например в Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="55269-105">The log file is a tab-delimited file that can be analyzed in any spreadsheet supporting tab-delimited files, such as Microsoft Excel.</span></span>  
  
 <span data-ttu-id="55269-106">Драйвер также может регистрировать долго выполняемые запросы (запросы, на которые сервер не возвращает ответа в течение заданного времени).</span><span class="sxs-lookup"><span data-stu-id="55269-106">The driver can also log long-running queries (queries that do not get a response from the server in a specified length of time).</span></span> <span data-ttu-id="55269-107">Эти запросы могут позднее анализироваться программистами и администраторами баз данных.</span><span class="sxs-lookup"><span data-stu-id="55269-107">These queries can later be analyzed by programmers and database administrators.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55269-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="55269-108">In This Section</span></span>  
  
-   [<span data-ttu-id="55269-109">Данные производительности драйвера профиля &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="55269-109">Profile Driver Performance Data &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-data.md)  
  
-   [<span data-ttu-id="55269-110">Регистрация долго выполняющихся запросов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="55269-110">Log Long-Running Queries &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-data-log-long-running-queries.md)  
  
## <a name="see-also"></a><span data-ttu-id="55269-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="55269-111">See Also</span></span>  
 [<span data-ttu-id="55269-112">ODBC How-to Topics</span><span class="sxs-lookup"><span data-stu-id="55269-112">ODBC How-to Topics</span></span>](odbc-how-to-topics.md)  
  
  
