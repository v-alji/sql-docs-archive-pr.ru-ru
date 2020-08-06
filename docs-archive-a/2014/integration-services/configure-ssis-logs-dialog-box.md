---
title: Диалоговое окно «Настройка журналов служб SSIS» | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.configuredtslogs.loggingdetails.f1
- sql12.dts.designer.configuredtslogs.providersandlogs.f1
- sql12.dts.designer.configuredtslogs.containers.f1
helpviewer_keywords:
- Configure SSIS Logs dialog box
ms.assetid: 4b980275-cd9a-4943-8c36-727d51f9a484
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 252b45765fb784790bcca0fb86e2e56e7e7baddc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658346"
---
# <a name="configure-ssis-logs-dialog-box"></a><span data-ttu-id="25837-102">Диалоговое окно «Конфигурация журналов служб SSIS»</span><span class="sxs-lookup"><span data-stu-id="25837-102">Configure SSIS Logs Dialog Box</span></span>
  <span data-ttu-id="25837-103">Используйте диалоговое окно **Настройка журналов служб SSIS** для настройки параметров ведения журнала для пакета.</span><span class="sxs-lookup"><span data-stu-id="25837-103">Use the **Configure SSIS Logs** dialog box to define logging options for a package.</span></span>  
  
 <span data-ttu-id="25837-104">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="25837-104">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="25837-105">Откройте диалоговое окно «Настройка журналов служб SSIS»</span><span class="sxs-lookup"><span data-stu-id="25837-105">Open the Configure SSIS Logs Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="25837-106">Настройка параметров на панели «Контейнеры»</span><span class="sxs-lookup"><span data-stu-id="25837-106">Configure the Options in the Containers Pane</span></span>](#container)  
  
3.  [<span data-ttu-id="25837-107">Настройка параметров на вкладке «Поставщики и журналы»</span><span class="sxs-lookup"><span data-stu-id="25837-107">Configure the Options on the Providers and Logs Tab</span></span>](#provider)  
  
4.  [<span data-ttu-id="25837-108">Настройка параметров на вкладке «Подробные сведения»</span><span class="sxs-lookup"><span data-stu-id="25837-108">Configure the Options on the Details Tab</span></span>](#detail)  
  
##  <a name="open-the-configure-ssis-logs-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="25837-109">Откройте диалоговое окно «Настройка журналов служб SSIS»</span><span class="sxs-lookup"><span data-stu-id="25837-109">Open the Configure SSIS Logs Dialog Box</span></span>  
 <span data-ttu-id="25837-110">**Открытие диалогового окна «Настройка журналов служб SSIS»**</span><span class="sxs-lookup"><span data-stu-id="25837-110">**To open the Configure SSIS Logs dialog box**</span></span>  
  
-   <span data-ttu-id="25837-111">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] выберите пункт **Ведение журнала** в меню **SSIS** .</span><span class="sxs-lookup"><span data-stu-id="25837-111">In the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click **Logging** on the **SSIS** menu.</span></span>  
  
##  <a name="configure-the-options-in-the-containers-pane"></a><a name="container"></a> <span data-ttu-id="25837-112">Настройка параметров на панели «Контейнеры»</span><span class="sxs-lookup"><span data-stu-id="25837-112">Configure the Options in the Containers Pane</span></span>  
 <span data-ttu-id="25837-113">Используйте панель **Контейнеры** в диалоговом окне **Настройка журналов служб SSIS** для включения записи в журнал пакета и его контейнеров.</span><span class="sxs-lookup"><span data-stu-id="25837-113">Use the **Containers** pane of the **Configure SSIS Logs** dialog box to enable the package and its containers for logging.</span></span>  
  
### <a name="options"></a><span data-ttu-id="25837-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="25837-114">Options</span></span>  
 <span data-ttu-id="25837-115">**Контейнеры**</span><span class="sxs-lookup"><span data-stu-id="25837-115">**Containers**</span></span>  
 <span data-ttu-id="25837-116">Установите флажки в иерархическом представлении, чтобы включить запись в журнал пакета и его контейнеров:</span><span class="sxs-lookup"><span data-stu-id="25837-116">Select the check boxes in the hierarchical view to enable the package and its containers for logging:</span></span>  
  
-   <span data-ttu-id="25837-117">Если флажок снят, контейнеры недоступны для записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="25837-117">If cleared, the container is not enabled for logging.</span></span> <span data-ttu-id="25837-118">Установите флажок для включения записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="25837-118">Select to enable logging.</span></span>  
  
-   <span data-ttu-id="25837-119">Если контейнер недоступен для выбора, используются параметры записи в журнал его родителя.</span><span class="sxs-lookup"><span data-stu-id="25837-119">If dimmed, the container uses the logging options of its parent.</span></span> <span data-ttu-id="25837-120">Данный параметр недоступен для пакетов.</span><span class="sxs-lookup"><span data-stu-id="25837-120">This option is not available for the package.</span></span>  
  
-   <span data-ttu-id="25837-121">Если флажок установлен, контейнер определяет собственные параметры записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="25837-121">If checked, the container defines its own logging options.</span></span>  
  
 <span data-ttu-id="25837-122">Если контейнер недоступен для выбора и для него требуется задать параметры записи в журнал, дважды щелкните флажок этого контейнера.</span><span class="sxs-lookup"><span data-stu-id="25837-122">If a container is dimmed and you want to set logging options on the container, click its check box twice.</span></span> <span data-ttu-id="25837-123">Первый щелчок снимает флажок, второй — устанавливает, позволяя выбрать регистраторы и данные, которые будут записываться в журналы.</span><span class="sxs-lookup"><span data-stu-id="25837-123">The first click clears the check box, and the second click selects it, enabling you to choose the log providers to use and select the information to log.</span></span>  
  
##  <a name="configure-the-options-on-the-providers-and-logs-tab"></a><a name="provider"></a> <span data-ttu-id="25837-124">Настройка параметров на вкладке «Поставщики и журналы»</span><span class="sxs-lookup"><span data-stu-id="25837-124">Configure the Options on the Providers and Logs Tab</span></span>  
 <span data-ttu-id="25837-125">Используйте вкладку **Поставщики и журналы** диалогового окна **Конфигурация журналов служб SSIS** , чтобы создать и конфигурировать журналы, регистрирующие события выполнения.</span><span class="sxs-lookup"><span data-stu-id="25837-125">Use the **Providers and Logs** tab of the **Configure SSIS Logs** dialog box to create and configure logs for capturing run-time events.</span></span>  
  
### <a name="options"></a><span data-ttu-id="25837-126">Параметры</span><span class="sxs-lookup"><span data-stu-id="25837-126">Options</span></span>  
 <span data-ttu-id="25837-127">**Тип поставщика**</span><span class="sxs-lookup"><span data-stu-id="25837-127">**Provider type**</span></span>  
 <span data-ttu-id="25837-128">Выберите тип регистратора из списка.</span><span class="sxs-lookup"><span data-stu-id="25837-128">Select a type of log provider from the list.</span></span>  
  
 <span data-ttu-id="25837-129">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="25837-129">**Add**</span></span>  
 <span data-ttu-id="25837-130">Добавьте журнал заданного типа к коллекции регистраторов пакета.</span><span class="sxs-lookup"><span data-stu-id="25837-130">Add a log of the specified type to the collection of log providers of the package.</span></span>  
  
 <span data-ttu-id="25837-131">**Название**</span><span class="sxs-lookup"><span data-stu-id="25837-131">**Name**</span></span>  
 <span data-ttu-id="25837-132">Включите или отключите журналы для контейнеров или задач, выбранных на панели **Контейнеры** диалогового окна **Настройка журналов служб SSIS** с помощью флажков.</span><span class="sxs-lookup"><span data-stu-id="25837-132">Enable or disable logs for containers or tasks selected in the **Containers** pane of the **Configure SSIS Logs** dialog box, by using the check boxes.</span></span> <span data-ttu-id="25837-133">Поле имени является редактируемым.</span><span class="sxs-lookup"><span data-stu-id="25837-133">The name field is editable.</span></span> <span data-ttu-id="25837-134">Используйте для поставщика имя по умолчанию или введите уникальное описательное имя.</span><span class="sxs-lookup"><span data-stu-id="25837-134">Use the default name for the provider, or type a unique descriptive name.</span></span>  
  
 <span data-ttu-id="25837-135">**Описание**</span><span class="sxs-lookup"><span data-stu-id="25837-135">**Description**</span></span>  
 <span data-ttu-id="25837-136">Поле описания является редактируемым.</span><span class="sxs-lookup"><span data-stu-id="25837-136">The description field is editable.</span></span> <span data-ttu-id="25837-137">Нажмите и отредактируйте описание журнала по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="25837-137">Click and then modify the default description of the log.</span></span>  
  
 <span data-ttu-id="25837-138">**Конфигурация**</span><span class="sxs-lookup"><span data-stu-id="25837-138">**Configuration**</span></span>  
 <span data-ttu-id="25837-139">Выберите в списке существующий диспетчер подключений или щелкните \<**New connection...**>, чтобы создать диспетчер подключений.</span><span class="sxs-lookup"><span data-stu-id="25837-139">Select an existing connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span> <span data-ttu-id="25837-140">В зависимости от типа регистратора можно настраивать диспетчер соединений OLE DB или диспетчер соединений файлов.</span><span class="sxs-lookup"><span data-stu-id="25837-140">Depending on the type of log provider, you can configure an OLE DB connection manager or a File connection manager.</span></span> <span data-ttu-id="25837-141">Регистратору журнала событий [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows не требуется соединение.</span><span class="sxs-lookup"><span data-stu-id="25837-141">The log provider for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Event Log requires no connection.</span></span>  
  
 <span data-ttu-id="25837-142">См. также диспетчер [Диспетчер соединений OLE DB](connection-manager/ole-db-connection-manager.md) , [диспетчер подключения файлов](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="25837-142">Related Topics: [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md) manager, [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
 <span data-ttu-id="25837-143">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="25837-143">**Delete**</span></span>  
 <span data-ttu-id="25837-144">Выберите регистратор и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="25837-144">Select a log provider and then click **Delete**.</span></span>  
  
##  <a name="configure-the-options-on-the-details-tab"></a><a name="detail"></a> <span data-ttu-id="25837-145">Настройка параметров на вкладке «Подробные сведения»</span><span class="sxs-lookup"><span data-stu-id="25837-145">Configure the Options on the Details Tab</span></span>  
 <span data-ttu-id="25837-146">Вкладка **Подробности** в диалоговом окне **Настройка журналов служб SSIS** позволяет задать события, по которым включается запись в журнал, и определить записываемые в журнал сведения.</span><span class="sxs-lookup"><span data-stu-id="25837-146">Use the **Details** tab of the **Configure SSIS Logs** dialog box to specify the events to enable for logging and the information details to log.</span></span> <span data-ttu-id="25837-147">Выбранные сведения записываются во все регистраторы, находящиеся в пакете.</span><span class="sxs-lookup"><span data-stu-id="25837-147">The information that you select applies to all the log providers in the package.</span></span> <span data-ttu-id="25837-148">Например, нельзя записать некоторые сведения в экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и другие сведения в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="25837-148">For example, you cannot write some information to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and different information to a text file.</span></span>  
  
### <a name="options"></a><span data-ttu-id="25837-149">Параметры</span><span class="sxs-lookup"><span data-stu-id="25837-149">Options</span></span>  
 <span data-ttu-id="25837-150">**События**</span><span class="sxs-lookup"><span data-stu-id="25837-150">**Events**</span></span>  
 <span data-ttu-id="25837-151">Включить или отключить события для записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="25837-151">Enable or disable events for logging.</span></span>  
  
 <span data-ttu-id="25837-152">**Описание**</span><span class="sxs-lookup"><span data-stu-id="25837-152">**Description**</span></span>  
 <span data-ttu-id="25837-153">Просмотрите описание события.</span><span class="sxs-lookup"><span data-stu-id="25837-153">View a description of the event.</span></span>  
  
 <span data-ttu-id="25837-154">**Дополнительно**</span><span class="sxs-lookup"><span data-stu-id="25837-154">**Advanced**</span></span>  
 <span data-ttu-id="25837-155">Выберите или удалите события для записи, выберите или удалите сведения, которые должны записываться в журнал для каждого события.</span><span class="sxs-lookup"><span data-stu-id="25837-155">Select or clear events to log, and select or clear information to log for each event.</span></span> <span data-ttu-id="25837-156">Чтобы скрыть сведения, записываемые в журнал, и оставить только список событий, нажмите кнопку **Основной** .</span><span class="sxs-lookup"><span data-stu-id="25837-156">Click **Basic** to hide all logging details, except the list of events.</span></span> <span data-ttu-id="25837-157">Записывать в журнал можно следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="25837-157">The following information is available for logging:</span></span>  
  
|<span data-ttu-id="25837-158">Значение</span><span class="sxs-lookup"><span data-stu-id="25837-158">Value</span></span>|<span data-ttu-id="25837-159">Description</span><span class="sxs-lookup"><span data-stu-id="25837-159">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="25837-160">**Компьютер**</span><span class="sxs-lookup"><span data-stu-id="25837-160">**Computer**</span></span>|<span data-ttu-id="25837-161">Имя компьютера, на котором произошло записываемое в журнал событие.</span><span class="sxs-lookup"><span data-stu-id="25837-161">The name of the computer on which the logged event occurred.</span></span>|  
|<span data-ttu-id="25837-162">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="25837-162">**Operator**</span></span>|<span data-ttu-id="25837-163">Имя пользователя, запустившего пакет.</span><span class="sxs-lookup"><span data-stu-id="25837-163">The user name of the person who started the package.</span></span>|  
|<span data-ttu-id="25837-164">**SourceName**</span><span class="sxs-lookup"><span data-stu-id="25837-164">**SourceName**</span></span>|<span data-ttu-id="25837-165">Имя пакета, контейнера или задачи, в котором произошло записываемое в журнал событие.</span><span class="sxs-lookup"><span data-stu-id="25837-165">The name of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="25837-166">**SourceID**</span><span class="sxs-lookup"><span data-stu-id="25837-166">**SourceID**</span></span>|<span data-ttu-id="25837-167">Глобальный уникальный идентификатор (GUID) пакета, контейнера или задачи, в котором произошло записываемое в журнал событие.</span><span class="sxs-lookup"><span data-stu-id="25837-167">The global unique identifier (GUID) of the package, container, or task in which the logged event occurred.</span></span>|  
|<span data-ttu-id="25837-168">**ExecutionID**</span><span class="sxs-lookup"><span data-stu-id="25837-168">**ExecutionID**</span></span>|<span data-ttu-id="25837-169">Глобальный уникальный идентификатор экземпляра выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="25837-169">The global unique identifier of the package execution instance.</span></span>|  
|<span data-ttu-id="25837-170">**MessageText**</span><span class="sxs-lookup"><span data-stu-id="25837-170">**MessageText**</span></span>|<span data-ttu-id="25837-171">Сообщение, связанное с записью журнала.</span><span class="sxs-lookup"><span data-stu-id="25837-171">A message associated with the log entry.</span></span>|  
|<span data-ttu-id="25837-172">**DataBytes**</span><span class="sxs-lookup"><span data-stu-id="25837-172">**DataBytes**</span></span>|<span data-ttu-id="25837-173">Зарезервировано для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="25837-173">Reserved for future use.</span></span>|  
  
 <span data-ttu-id="25837-174">**Основной**</span><span class="sxs-lookup"><span data-stu-id="25837-174">**Basic**</span></span>  
 <span data-ttu-id="25837-175">Выберите или удалите события для записи в журнал.</span><span class="sxs-lookup"><span data-stu-id="25837-175">Select or clear events to log.</span></span> <span data-ttu-id="25837-176">Этот параметр позволяет скрыть записываемые в журнал сведения, за исключением списка событий.</span><span class="sxs-lookup"><span data-stu-id="25837-176">This option hides logging details except the list of events.</span></span> <span data-ttu-id="25837-177">Если выбрать событие, то все записываемые в журнал сведения для события выбираются автоматически.</span><span class="sxs-lookup"><span data-stu-id="25837-177">If you select an event, all logging details are selected for the event by default.</span></span> <span data-ttu-id="25837-178">Чтобы просмотреть все записываемые в журнал сведения, выберите параметр **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="25837-178">Click **Advanced** to show all logging details.</span></span>  
  
 <span data-ttu-id="25837-179">**Загрузить**</span><span class="sxs-lookup"><span data-stu-id="25837-179">**Load**</span></span>  
 <span data-ttu-id="25837-180">Укажите XML-файл, используемый в качестве шаблона настройки параметров журнала.</span><span class="sxs-lookup"><span data-stu-id="25837-180">Specify an existing XML file to use as a template for setting logging options.</span></span>  
  
 <span data-ttu-id="25837-181">**Сохранить**</span><span class="sxs-lookup"><span data-stu-id="25837-181">**Save**</span></span>  
 <span data-ttu-id="25837-182">Сохраните детализацию настройки в виде шаблона в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="25837-182">Save configuration details as a template to an XML file.</span></span>  
  
  
