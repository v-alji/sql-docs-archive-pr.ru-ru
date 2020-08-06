---
title: Ведение журнала в компоненте скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], logging
ms.assetid: 17c19787-379e-43fe-9107-e36e17ecda53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c29dfffee6cacb39272aef07caa5539555cdd4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665426"
---
# <a name="logging-in-the-script-component"></a><span data-ttu-id="7258f-102">Ведение журнала в компоненте скрипта</span><span class="sxs-lookup"><span data-stu-id="7258f-102">Logging in the Script Component</span></span>
  <span data-ttu-id="7258f-103">Ведение журнала в пакетах служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] позволяет сохранить подробные сведения о процессе выполнения, результатах и проблемах, записывая стандартные события или определенные пользователем сообщения с целью последующего анализа.</span><span class="sxs-lookup"><span data-stu-id="7258f-103">Logging in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages lets you save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="7258f-104">Компонент скрипта может использовать метод <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> класса `ScriptMain` для записи определяемых пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="7258f-104">The Script component can use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class to log user-defined data.</span></span> <span data-ttu-id="7258f-105">Если ведение журнала включено и событие **ScriptComponentLogEntry** выбрано для записи на вкладке **Подробности** диалогового окна **Настройка журналов служб SSIS**, единичный вызов метода <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> сохраняет сведения о событии во всех поставщиках журналов, настроенных для задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="7258f-105">If logging is enabled, and the **ScriptComponentLogEntry** event is selected for logging on the **Details** tab of the **Configure SSIS Logs** dialog box, a single call to the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method stores the event information in all the log providers that have been configured for the data flow task.</span></span>  
  
 <span data-ttu-id="7258f-106">Далее приведен простой пример ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="7258f-106">Here is a simple example of logging:</span></span>  
  
 `Dim bt(0) As Byte`  
  
 `Me.Log("Test Log Event", _`  
  
 `0, _`  
  
 `bt)`  
  
> [!NOTE]  
>  <span data-ttu-id="7258f-107">Хотя журнал можно вести непосредственно из компонента скрипта, может потребоваться реализовать события, а не журнал.</span><span class="sxs-lookup"><span data-stu-id="7258f-107">Although you can perform logging directly from your Script component, you may want to consider implementing events rather than logging.</span></span> <span data-ttu-id="7258f-108">При использовании событий кто угодно может включить запись сообщений о событиях в журнал, но можно использовать для отклика на события стандартные или определяемые пользователем обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="7258f-108">When using events, not only can you enable the logging of event messages, but you can respond to the event with default or user-defined event handlers.</span></span>  
  
 <span data-ttu-id="7258f-109">Дополнительные сведения о ведении журналов см. в разделе [Ведение журналов в службах Integration Services (SSIS)](../../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="7258f-109">For more information about logging, see [Integration Services &#40;SSIS&#41; Logging](../../performance/integration-services-ssis-logging.md).</span></span>  
  
<span data-ttu-id="7258f-110">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="7258f-110">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="7258f-111">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="7258f-111">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="7258f-112">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="7258f-112">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="7258f-113">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="7258f-113">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7258f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="7258f-114">See Also</span></span>  
 [<span data-ttu-id="7258f-115">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="7258f-115">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
