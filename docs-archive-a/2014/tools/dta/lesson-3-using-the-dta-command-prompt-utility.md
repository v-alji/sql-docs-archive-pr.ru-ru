---
title: Занятие 3. Использование программы командной строки dta | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 30f27f4d-8852-4b12-ba62-57f63e496f1d
author: stevestein
ms.author: sstein
ms.openlocfilehash: abbde02cd73e01937e6d0669c10f2db28da8a76e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727641"
---
# <a name="lesson-3-using-the-dta-command-prompt-utility"></a><span data-ttu-id="cd205-102">Занятие 3. Использование программы командной строки dta</span><span class="sxs-lookup"><span data-stu-id="cd205-102">Lesson 3: Using the dta Command Prompt Utility</span></span>
  <span data-ttu-id="cd205-103">Программа командной строки **dta** расширяет функциональные возможности помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="cd205-103">The **dta** command-prompt utility offers functionality in addition to that provided by the Database Engine Tuning Advisor.</span></span>  
  
 <span data-ttu-id="cd205-104">Применяя XML-схему помощника по настройке ядра СУБД, пользователь может создавать входные файлы данной программы с помощью удобных для себя средств XML.</span><span class="sxs-lookup"><span data-stu-id="cd205-104">You can use your favorite XML tools to create input files for the utility by using the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="cd205-105">Эта схема устанавливается вместе со службами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и находится по следующему адресу: C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span><span class="sxs-lookup"><span data-stu-id="cd205-105">This schema is installed when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and can be found at: C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span></span>  
  
 <span data-ttu-id="cd205-106">XML-схема помощника по настройке ядра СУБД также доступна на [веб-сайте корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="cd205-106">The Database Engine Tuning Advisor XML schema is also available online at [this Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span></span>  
  
 <span data-ttu-id="cd205-107">XML-схема помощника по настройке ядра СУБД расширяет спектр параметров настройки.</span><span class="sxs-lookup"><span data-stu-id="cd205-107">The Database Engine Tuning Advisor XML schema provides more flexibility to set tuning options.</span></span> <span data-ttu-id="cd205-108">Например, с ее помощью можно проводить анализ гипотетических вариантов.</span><span class="sxs-lookup"><span data-stu-id="cd205-108">For example, it enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="cd205-109">При этом виде анализа задается набор существующих и допустимых структур физического проектирования для базы данных, которую необходимо настроить, а затем с использованием помощника по настройке ядра СУБД выполняется анализ данного набора, цель которого — выявить, повысит ли такая допустимая структура физического проектирования скорость обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="cd205-109">"What-if" analysis involves specifying a set of existing and hypothetical physical design structures for the database you want to tune, and then analyzing it with the Database Engine Tuning Advisor to find out whether this hypothetical physical design will improve query processing performance.</span></span> <span data-ttu-id="cd205-110">Этот тип анализа позволяет проводить оценку новой конфигурации без затрат, связанных с ее фактическим внедрением.</span><span class="sxs-lookup"><span data-stu-id="cd205-110">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="cd205-111">Если предложенная допустимая физическая структура не дает требуемого улучшения производительности, ее можно легко изменить и снова выполнить анализ, повторяя эту процедуру до тех пор, пока не будет найдена конфигурация, обеспечивающая необходимые результаты.</span><span class="sxs-lookup"><span data-stu-id="cd205-111">If your hypothetical physical design does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="cd205-112">Кроме того, использование схемы XML помощника по настройке ядра СУБД и программы командной строки **dta** позволяет внедрить функциональность помощника по настройке ядра СУБД в скрипты и использовать его в сочетании с другими средствами проектирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="cd205-112">In addition, using the Database Engine Tuning Advisor XML schema and the **dta** command-prompt utility, you can incorporate Database Engine Tuning Advisor functionality into scripts and use it with other database design tools.</span></span>  
  
 <span data-ttu-id="cd205-113">Тематика применения функциональности ввода данных на языке XML с использованием помощника по настройке ядра СУБД выходит за рамки данного занятия.</span><span class="sxs-lookup"><span data-stu-id="cd205-113">Using the XML input functionality of Database Engine Tuning Advisor is beyond the scope of this lesson.</span></span>  
  
 <span data-ttu-id="cd205-114">Это занятие содержит введение в синтаксис программы командной строки **dta** , объясняет доступ к справке и осуществление настройки простых рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="cd205-114">This lesson provides an introduction to the basic **dta** command-prompt utility syntax, how to access help, and practice for tuning simple workloads.</span></span>  
  
 <span data-ttu-id="cd205-115">Занятие содержит следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="cd205-115">It contains the following topic:</span></span>  
  
-   <span data-ttu-id="cd205-116">Запуск программы командной строки **dta** и Настройка рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="cd205-116">Starting the **dta** Command Prompt Utility and Tuning a Workload</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="cd205-117">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="cd205-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="cd205-118">Начало работы с программой командной строки dta и настройка рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="cd205-118">Starting the dta Command Prompt Utility and Tuning a Workload</span></span>](lesson-1-1-tuning-a-workload.md)  
  
  
