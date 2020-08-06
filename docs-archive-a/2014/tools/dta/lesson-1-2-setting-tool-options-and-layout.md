---
title: Настройка параметров и макета инструментов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 43e97ce0-97bc-4a27-9485-5bbeb7190b85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 96d853a85b8ee4d451c55d7ea59af3755887be22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734786"
---
# <a name="setting-tool-options-and-layout"></a><span data-ttu-id="17608-102">Настройка параметров и вида средств</span><span class="sxs-lookup"><span data-stu-id="17608-102">Setting Tool Options and Layout</span></span>
  <span data-ttu-id="17608-103">Чтобы повысить удобство работы с помощником по настройке ядра СУБД, можно настроить параметры, влияющие на вид графического интерфейса пользователя помощника при запуске и применяемый шрифт, а также воспользоваться другими возможностями этого средства.</span><span class="sxs-lookup"><span data-stu-id="17608-103">You can set options that configure what the Database Engine Tuning Advisor graphical user interface (GUI) displays on startup, the font it uses, and other tool functionality to best support how you use it.</span></span> <span data-ttu-id="17608-104">Выполнение практических заданий на этой странице позволит изучить эти параметры и способ их настройки.</span><span class="sxs-lookup"><span data-stu-id="17608-104">The practices on this page familiarize you with the options you can set, and how to set them.</span></span>  
  
### <a name="set-the-tool-options"></a><span data-ttu-id="17608-105">Настройка параметров средства</span><span class="sxs-lookup"><span data-stu-id="17608-105">Set the tool options</span></span>  
  
1.  <span data-ttu-id="17608-106">Запустите помощник по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="17608-106">Start the Database Engine Tuning Advisor.</span></span> <span data-ttu-id="17608-107">В меню ОС Windows **Пуск** последовательно укажите **Все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Средства обеспечения производительности**и выберите пункт **Помощник по настройке ядра СУБД**.</span><span class="sxs-lookup"><span data-stu-id="17608-107">On the Windows **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and click **Database Engine Tuning Advisor**.</span></span>  
  
2.  <span data-ttu-id="17608-108">В меню **Сервис** выберите команду **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="17608-108">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="17608-109">В диалоговом окне **Параметры** просмотрите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="17608-109">In the **Options** dialog box, view the following options:</span></span>  
  
    -   <span data-ttu-id="17608-110">Раскройте список **При запуске** , чтобы просмотреть доступные варианты вида помощника по настройке ядра СУБД при запуске.</span><span class="sxs-lookup"><span data-stu-id="17608-110">Expand the **On startup** list to view what Database Engine Tuning Advisor can display when it is started.</span></span> <span data-ttu-id="17608-111">По умолчанию выбран параметр **Показать новый сеанс** .</span><span class="sxs-lookup"><span data-stu-id="17608-111">By default, **Show a new session** is selected.</span></span>  
  
    -   <span data-ttu-id="17608-112">Щелкните **изменить шрифт** , чтобы увидеть, какие шрифты можно выбрать для списков баз данных и таблиц на вкладке **Общие** . Шрифты, выбранные для этого параметра, также используются в помощник по настройке ядра СУБД сетках рекомендаций и отчетах после выполнения настройки.</span><span class="sxs-lookup"><span data-stu-id="17608-112">Click **Change Font** to see what fonts you can choose for the lists of databases and tables on the **General** tab. The fonts you choose for this option also are used in Database Engine Tuning Advisor recommendation grids and reports after you have performed tuning.</span></span> <span data-ttu-id="17608-113">По умолчанию в помощнике по настройке ядра СУБД используются системные шрифты.</span><span class="sxs-lookup"><span data-stu-id="17608-113">By default, Database Engine Tuning Advisor uses system fonts.</span></span>  
  
    -   <span data-ttu-id="17608-114">Значение параметра **Помнить список последних использованных объектов** может находиться в диапазоне от **1** до **10**.</span><span class="sxs-lookup"><span data-stu-id="17608-114">The **Number of items in most recently used lists** can be set between **1** and **10**.</span></span> <span data-ttu-id="17608-115">Этот параметр устанавливает максимальное количество элементов в списках, отображаемых при выборе в меню **Файл** команд **Последние сеансы** или **Последние файлы** .</span><span class="sxs-lookup"><span data-stu-id="17608-115">This sets the maximum number of items in the lists displayed by clicking **Recent Sessions** or **Recent Files** on the **File** menu.</span></span> <span data-ttu-id="17608-116">По умолчанию для этого параметра указано значение **4**.</span><span class="sxs-lookup"><span data-stu-id="17608-116">By default, this option is set to **4**.</span></span>  
  
    -   <span data-ttu-id="17608-117">Если установлен флажок **Запоминать последние параметры настройки** , по умолчанию для следующего сеанса настройки в помощнике по настройке ядра СУБД будут использоваться значения параметров, заданные в прошлом сеансе.</span><span class="sxs-lookup"><span data-stu-id="17608-117">When **Remember my last tuning options** is checked, by default Database Engine Tuning Advisor uses the tuning options you specified for your last tuning session for the next tuning session.</span></span> <span data-ttu-id="17608-118">Снимите этот флажок, чтобы использовать установленные по умолчанию параметры помощника по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="17608-118">Clear this check box to use Database Engine Tuning Advisor tuning option defaults.</span></span> <span data-ttu-id="17608-119">По умолчанию этот параметр выбран.</span><span class="sxs-lookup"><span data-stu-id="17608-119">By default, this option is selected.</span></span>  
  
    -   <span data-ttu-id="17608-120">По умолчанию установлен флажок **Запрашивать подтверждение перед окончательным удалением сеансов** , что позволяет избежать случайного удаления сеансов настройки.</span><span class="sxs-lookup"><span data-stu-id="17608-120">By default, **Ask before permanently deleting sessions** is checked to avoid accidentally deleting tuning sessions.</span></span>  
  
    -   <span data-ttu-id="17608-121">По умолчанию установлен флажок **Запрашивать подтверждение перед остановкой анализа сеанса** , что позволяет избежать случайной остановки сеанса настройки до завершения анализа рабочей нагрузки в помощнике по настройке ядра СУБД.</span><span class="sxs-lookup"><span data-stu-id="17608-121">By default, **Ask before stopping session analysis** is checked to avoid accidentally stopping a tuning session before Database Engine Tuning Advisor has finished analyzing a workload.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="17608-122">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="17608-122">Next Lesson</span></span>  
 [<span data-ttu-id="17608-123">Занятие 2. Использование помощника по настройке ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="17608-123">Lesson 2: Using Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
