---
title: Просмотр записей журнала в окне "события журнала" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], viewing
- Integration Services packages, logs
- packages [Integration Services], logs
ms.assetid: c02123c3-67fc-4370-ad14-91ed259f1873
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16b6f11758d7de2c833731cd007426000a01d8ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728434"
---
# <a name="view-log-entries-in-the-log-events-window"></a><span data-ttu-id="1858d-102">Просмотр записей журнала в окне "Регистрация событий"</span><span class="sxs-lookup"><span data-stu-id="1858d-102">View Log Entries in the Log Events Window</span></span>
  <span data-ttu-id="1858d-103">Эта процедура описывает, как выполнить пакет и просмотреть записи журнала, которые он записывает.</span><span class="sxs-lookup"><span data-stu-id="1858d-103">This procedure describes how to run a package and view the log entries it writes.</span></span> <span data-ttu-id="1858d-104">Записи журнала можно просмотреть в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="1858d-104">You can view the log entries in real time.</span></span> <span data-ttu-id="1858d-105">Записи журнала, которые записываются в окно **Регистрация событий** , также можно копировать и сохранять для будущего анализа.</span><span class="sxs-lookup"><span data-stu-id="1858d-105">The log entries that are written to the **Log Events** window can also be copied and saved for further analysis.</span></span>  
  
 <span data-ttu-id="1858d-106">При отсутствии необходимости записи в журнал запись введется в окно **Регистрация событий** .</span><span class="sxs-lookup"><span data-stu-id="1858d-106">It is not necessary to write the log entries to a log to write the entries to the **Log Events** window.</span></span>  
  
### <a name="to-view-log-entries"></a><span data-ttu-id="1858d-107">Просмотр записей журнала</span><span class="sxs-lookup"><span data-stu-id="1858d-107">To view log entries</span></span>  
  
1.  <span data-ttu-id="1858d-108">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="1858d-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="1858d-109">В меню **Службы SSIS** выберите пункт **Регистрация событий**.</span><span class="sxs-lookup"><span data-stu-id="1858d-109">On the **SSIS** menu, click **Log Events**.</span></span> <span data-ttu-id="1858d-110">При необходимости можно вывести окно **Регистрация событий** , сопоставив команду View.LogEvents комбинации клавиш по своему выбору на странице **Клавиатура** диалогового окна **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="1858d-110">You can optionally display the **Log Events** window by mapping the View.LogEvents command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
3.  <span data-ttu-id="1858d-111">В меню **Отладка** выберите пункт **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="1858d-111">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="1858d-112">По мере того, как среда выполнения определяет события и пользовательские сообщения, для которых разрешена запись в журнал, записи журнала для таких событий и сообщений записываются в окно **Регистрация событий** .</span><span class="sxs-lookup"><span data-stu-id="1858d-112">As the runtime encounters the events and custom messages that are enabled for logging, log entries for each event or message are written to the **Log Events** window.</span></span>  
  
4.  <span data-ttu-id="1858d-113">В меню **Отладка** выберите пункт **Остановить отладку**.</span><span class="sxs-lookup"><span data-stu-id="1858d-113">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
     <span data-ttu-id="1858d-114">Записи в журнале остаются доступными в окне **Регистрация событий** до тех пор, пока не будет перезапущен пакет, или пока не будет запущен другой пакет, или пока не будет закрыта среда [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1858d-114">The log entries remain available in the **Log Events** window until you rerun the package, run a different package, or close [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span>  
  
5.  <span data-ttu-id="1858d-115">Просмотрите записи журнала в окне **Регистрация событий** .</span><span class="sxs-lookup"><span data-stu-id="1858d-115">View the log entries in the **Log Events** window.</span></span>  
  
6.  <span data-ttu-id="1858d-116">По желанию выберите запись журнала для копирования. Щелкнув правой кнопки мыши, откройте контекстное меню и выберите пункт **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="1858d-116">Optionally, click the log entries to copy, right-click, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="1858d-117">По желанию дважды щелкните запись журнала и в диалоговом окне **Запись журнала** просмотрите детали по выбранной записи.</span><span class="sxs-lookup"><span data-stu-id="1858d-117">Optionally, double-click a log entry, and in the **Log Entry** dialog box, view the details for a single log entry.</span></span>  
  
8.  <span data-ttu-id="1858d-118">В диалоговом окне **Запись журнала** щелкните стрелки вверх и вниз, чтобы отображать предыдущую и следующую записи журнала или щелкните значок копирования для копирования записи журнала.</span><span class="sxs-lookup"><span data-stu-id="1858d-118">In the **Log Entry** dialog box, click the up and down arrows to display the previous or next log entry, and click the copy icon to copy the log entry.</span></span>  
  
9. <span data-ttu-id="1858d-119">Откройте текстовый редактор, вставьте и сохраните запись журнала в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="1858d-119">Open a text editor, paste, and then save the log entry to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1858d-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="1858d-120">See Also</span></span>  
 [<span data-ttu-id="1858d-121">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="1858d-121">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
