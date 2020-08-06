---
title: Настройка ведения журнала с помощью сохраненного файла конфигурации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], logs
- logs [Integration Services], containers
ms.assetid: e5fdbbcb-94ca-4912-aa7c-0d89cebbd308
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8eb517462d9e932906f739678fbd46c1004fb84d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665492"
---
# <a name="configure-logging-by-using-a-saved-configuration-file"></a><span data-ttu-id="75dc4-102">Настройка ведения журналов с помощью сохраненного файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="75dc4-102">Configure Logging by Using a Saved Configuration File</span></span>
  <span data-ttu-id="75dc4-103">Эта процедура описывает, как настроить ведение журнала для новых контейнеров в пакете с помощью загрузки предварительно сохраненного файла конфигурации ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="75dc4-103">This procedure describes how to configure logging for new containers in a package by loading a previously saved logging configuration file.</span></span>  
  
 <span data-ttu-id="75dc4-104">По умолчанию все контейнеры пакета используют такую же конфигурацию ведения журнала, что и родительский контейнер.</span><span class="sxs-lookup"><span data-stu-id="75dc4-104">By default, all containers in a package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="75dc4-105">Например, задачи в контейнере «цикл по каждому элементу» используют такую же конфигурацию ведения журнала, какую использует контейнер «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="75dc4-105">For example, the tasks in a Foreach Loop use the same logging configuration as the Foreach Loop.</span></span>  
  
### <a name="to-configure-logging-for-a-container"></a><span data-ttu-id="75dc4-106">Настройка ведения журнала для контейнера</span><span class="sxs-lookup"><span data-stu-id="75dc4-106">To configure logging for a container</span></span>  
  
1.  <span data-ttu-id="75dc4-107">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="75dc4-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="75dc4-108">В меню **Службы SSIS** нажмите **Ведение журнала**.</span><span class="sxs-lookup"><span data-stu-id="75dc4-108">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="75dc4-109">Разверните представление пакета в виде дерева и выберите контейнер для настройки.</span><span class="sxs-lookup"><span data-stu-id="75dc4-109">Expand the package tree view and select the container to configure.</span></span>  
  
4.  <span data-ttu-id="75dc4-110">На вкладке **Поставщики и журналы** выберите журналы, которые будут использоваться для контейнера.</span><span class="sxs-lookup"><span data-stu-id="75dc4-110">On the **Providers and Logs** tab, select the logs to use for the container.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75dc4-111">Создавать журналы можно только на уровне пакета.</span><span class="sxs-lookup"><span data-stu-id="75dc4-111">You can create logs only at the package level.</span></span> <span data-ttu-id="75dc4-112">Дополнительные сведения см. в разделе [Включение средств ведения журналов в SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="75dc4-112">For more information, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
5.  <span data-ttu-id="75dc4-113">Перейдите на вкладку **Подробности** и нажмите кнопку **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="75dc4-113">Click the **Details** tab and click **Load**.</span></span>  
  
6.  <span data-ttu-id="75dc4-114">Найдите файл конфигурации ведения журнала, который необходимо использовать, и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="75dc4-114">Locate the logging configuration file you want to use and click **Open**.</span></span>  
  
7.  <span data-ttu-id="75dc4-115">Можно выбрать другую запись журнала, установив соответствующий ей флажок в столбце **События** .</span><span class="sxs-lookup"><span data-stu-id="75dc4-115">Optionally, select a different log entry to log by selecting its check box in the **Events** column.</span></span> <span data-ttu-id="75dc4-116">Нажмите кнопку **Дополнительно** , чтобы выбрать тип сведений для занесения в журнал для этой записи.</span><span class="sxs-lookup"><span data-stu-id="75dc4-116">Click **Advanced** to select the type of information to log for this entry.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75dc4-117">Новый контейнер может включать дополнительные записи журнала, которые недоступны для контейнера, изначально использованного для создания конфигурации ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="75dc4-117">The new container may include additional log entries that are not available for the container originally used to create the logging configuration.</span></span> <span data-ttu-id="75dc4-118">Эти дополнительные записи журнала должны быть выбраны вручную, если необходимо их ведение.</span><span class="sxs-lookup"><span data-stu-id="75dc4-118">These additional log entries must be selected manually if you want them to be logged.</span></span>  
  
8.  <span data-ttu-id="75dc4-119">Чтобы сохранить обновленную версию конфигурации ведения журнала, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75dc4-119">To save the updated version of the logging configuration, click **Save**.</span></span>  
  
9. <span data-ttu-id="75dc4-120">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="75dc4-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75dc4-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="75dc4-121">See Also</span></span>  
 [<span data-ttu-id="75dc4-122">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="75dc4-122">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
