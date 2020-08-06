---
title: Строка состояния (редактор запросов к ядру СУБД)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7f2d6f4-bb94-4cf5-a096-c34397e679af
author: rothja
ms.author: jroth
ms.openlocfilehash: 743ae0a4152daee19aa67f85337ae4077a3ed7f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667023"
---
# <a name="status-bar-database-engine-query-editor"></a><span data-ttu-id="78f83-102">Строка состояния (редактор запросов к ядру СУБД)</span><span class="sxs-lookup"><span data-stu-id="78f83-102">Status Bar (Database Engine Query Editor)</span></span>
  <span data-ttu-id="78f83-103">В строках состояния в окнах редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] могут быть цветовые обозначения, указывающие, к какому экземпляру [!INCLUDE[ssDE](../../includes/ssde-md.md)] подключено данное окно.</span><span class="sxs-lookup"><span data-stu-id="78f83-103">The status bar of [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor windows can be color coded to indicate which instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] each window is connected to.</span></span>  
  
1.  <span data-ttu-id="78f83-104">**Перед началом работы**  [Цвета строки состояния](#StatusBarColors)</span><span class="sxs-lookup"><span data-stu-id="78f83-104">**Before you begin:**  [Status Bar Colors](#StatusBarColors)</span></span>  
  
2.  <span data-ttu-id="78f83-105">**Задание цвета состояния сервера в**  [обозревателе объектов](#SetOEServerColor), [окне "Зарегистрированный сервер"](#SetRegServerColor)</span><span class="sxs-lookup"><span data-stu-id="78f83-105">**To set a server status color in:**  [Object Explorer](#SetOEServerColor), [Registered Server](#SetRegServerColor)</span></span>  
  
3.  <span data-ttu-id="78f83-106">**Использование цвета состояния:**  [открытие редактора запросов с помощью цвета сервера](#OpenServerColor), [открытие редактора запросов с помощью цвета состояния](#OpenSpecColor)</span><span class="sxs-lookup"><span data-stu-id="78f83-106">**To use a status color:**  [Open Query Editor Using a Server Color](#OpenServerColor), [Open a Query Editor Specifying a Status Color](#OpenSpecColor)</span></span>  
  
##  <a name="status-bar-colors"></a><a name="StatusBarColors"></a> <span data-ttu-id="78f83-107">Цвета строки состояния</span><span class="sxs-lookup"><span data-stu-id="78f83-107">Status Bar Colors</span></span>  
 <span data-ttu-id="78f83-108">Можно привязать цвет строки состояния к определенному узлу с помощью **обозревателя объектов** или в окне **Зарегистрированные серверы**.</span><span class="sxs-lookup"><span data-stu-id="78f83-108">You can associate a status bar color with a specific server node in either **Object Explorer** or **Registered Servers**.</span></span> <span data-ttu-id="78f83-109">Цвета можно указать только для узлов сервера, подключенных к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)], но не для узлов для других технологических решений SQL Server.</span><span class="sxs-lookup"><span data-stu-id="78f83-109">The colors can only be specified for server nodes connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], not server nodes for other SQL Server technologies.</span></span> <span data-ttu-id="78f83-110">Также можно указывать пользовательский цвет строки состояния при каждом подключении нового окна редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78f83-110">You can also specify a custom status bar color each time you connect a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="78f83-111">Затем можно открывать окно редактора запросов с помощью цвета состояния, определенного для узла сервера, или указать уникальный цвет для этого окна редактора.</span><span class="sxs-lookup"><span data-stu-id="78f83-111">You can then open a query editor window using either the status color defined for the server node, or specify a unique color for that editor window.</span></span>  
  
 <span data-ttu-id="78f83-112">Задавать пользовательский цвет строки состояния для узла сервера в обозревателе объектов необходимо при установке соединения.</span><span class="sxs-lookup"><span data-stu-id="78f83-112">Setting a custom status bar color for a server node in Object Explorer must be done when making the connection.</span></span> <span data-ttu-id="78f83-113">Чтобы изменить цвет, связанный с существующим узлом сервера, необходимо разорвать соединение, затем подключиться снова, указав новый цвет.</span><span class="sxs-lookup"><span data-stu-id="78f83-113">To change the color associated with an existing server node, you must disconnect and then reconnect specifying the new color.</span></span>  
  
##  <a name="set-the-status-color-for-a-server-in-object-explorer"></a><a name="SetOEServerColor"></a> <span data-ttu-id="78f83-114">Задание цвета состояния для сервера в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="78f83-114">Set the Status Color for a Server in Object Explorer</span></span>  
 <span data-ttu-id="78f83-115">**Задание цвета состояния сервера в обозревателе объектов**</span><span class="sxs-lookup"><span data-stu-id="78f83-115">**To set a server status color in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="78f83-116">В **обозревателе объектов** нажмите кнопку **Подключение**, затем выберите **Компонент Database Engine...** .</span><span class="sxs-lookup"><span data-stu-id="78f83-116">In **Object Explorer**, select the **Connect** button and then select **Database Engine...**.</span></span>  
  
2.  <span data-ttu-id="78f83-117">В диалоговом окне **Соединение с сервером** выберите **Параметры >>** .</span><span class="sxs-lookup"><span data-stu-id="78f83-117">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
3.  <span data-ttu-id="78f83-118">Установите флажок **Использовать пользовательский цвет** .</span><span class="sxs-lookup"><span data-stu-id="78f83-118">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="78f83-119">Чтобы выбрать цвет, нажмите кнопку **Выбрать...** .</span><span class="sxs-lookup"><span data-stu-id="78f83-119">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="78f83-120">Выберите основной или пользовательский цвет, затем нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="78f83-120">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="78f83-121">Укажите остальные сведения о подключении, а затем нажмите кнопку **Соединение** .</span><span class="sxs-lookup"><span data-stu-id="78f83-121">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
##  <a name="set-the-status-color-for-a-registered-server"></a><a name="SetRegServerColor"></a> <span data-ttu-id="78f83-122">Указание цвета состояния для зарегистрированного сервера</span><span class="sxs-lookup"><span data-stu-id="78f83-122">Set the Status Color For a Registered Server</span></span>  
 <span data-ttu-id="78f83-123">**Указание цвета состояния для зарегистрированного сервера**</span><span class="sxs-lookup"><span data-stu-id="78f83-123">**To set a server color For a Registered Server**</span></span>  
  
1.  <span data-ttu-id="78f83-124">В списке **Зарегистрированные серверы** щелкните правой кнопкой мыши узел сервера и выберите пункт **Свойства...** .</span><span class="sxs-lookup"><span data-stu-id="78f83-124">In **Registered Servers**, right click the server node and then select **Properties...**.</span></span>  
  
2.  <span data-ttu-id="78f83-125">В диалоговом окне **Изменение данных регистрации серверов** перейдите на вкладку **Свойства соединения** .</span><span class="sxs-lookup"><span data-stu-id="78f83-125">On the **Edit Server Registration Properties** dialog, select the **Connection Properties** tab.</span></span>  
  
3.  <span data-ttu-id="78f83-126">Установите флажок **Использовать пользовательский цвет** .</span><span class="sxs-lookup"><span data-stu-id="78f83-126">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="78f83-127">Чтобы выбрать цвет, нажмите кнопку **Выбрать...** .</span><span class="sxs-lookup"><span data-stu-id="78f83-127">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="78f83-128">Выберите основной или пользовательский цвет, затем нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="78f83-128">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="78f83-129">Нажмите кнопку **Сохранить** в диалоговом окне **Изменение данных регистрации серверов** .</span><span class="sxs-lookup"><span data-stu-id="78f83-129">Select the **Save** button on the **Edit Server Registration Properties** dialog.</span></span>  
  
##  <a name="open-an-editor-using-a-server-color"></a><a name="OpenServerColor"></a> <span data-ttu-id="78f83-130">Открытие редактора с помощью цвета сервера</span><span class="sxs-lookup"><span data-stu-id="78f83-130">Open An Editor Using a Server Color</span></span>  
 <span data-ttu-id="78f83-131">**Открытие окна редактора с помощью цвета сервера**</span><span class="sxs-lookup"><span data-stu-id="78f83-131">**To open an editor window using a server color**</span></span>  
  
-   <span data-ttu-id="78f83-132">Щелкните правой кнопкой мыши узел сервера в **обозревателе объектов** или в окне **Зарегистрированные серверы**и нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="78f83-132">Right-click a server node in either **Object Explorer** or **Registered Servers**, and select **New Query**.</span></span>  
  
-   <span data-ttu-id="78f83-133">Также можно выделить узел сервера, затем нажать кнопку **Создать запрос** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="78f83-133">Alternatively, highlight a server node, and then select the **New Query** toolbar button.</span></span>  
  
-   <span data-ttu-id="78f83-134">Строка состояния в окне редактора будет отображаться цветом, определенным для связанного сервера.</span><span class="sxs-lookup"><span data-stu-id="78f83-134">The status bar in the editor window will use the color defined for the associated server.</span></span>  
  
##  <a name="open-an-editor-specifying-a-status-color"></a><a name="OpenSpecColor"></a> <span data-ttu-id="78f83-135">Открытие редактора с помощью цвета состояния</span><span class="sxs-lookup"><span data-stu-id="78f83-135">Open an Editor Specifying a Status Color</span></span>  
 <span data-ttu-id="78f83-136">**Открытие окна редактора с помощью цвета состояния**</span><span class="sxs-lookup"><span data-stu-id="78f83-136">**To open an editor window specifying a status color**</span></span>  
  
-   <span data-ttu-id="78f83-137">Откройте меню **Файл** , выберите **Создать**, затем выберите **Запрос к ядру СУБД**.</span><span class="sxs-lookup"><span data-stu-id="78f83-137">Open the **File** menu, select **New**, and then select **Database Engine Query**.</span></span>  
  
-   <span data-ttu-id="78f83-138">В диалоговом окне **Соединение с сервером** выберите **Параметры >>** .</span><span class="sxs-lookup"><span data-stu-id="78f83-138">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
-   <span data-ttu-id="78f83-139">Установите флажок **Использовать пользовательский цвет** .</span><span class="sxs-lookup"><span data-stu-id="78f83-139">Select the **Use custom color** check box.</span></span>  
  
-   <span data-ttu-id="78f83-140">Чтобы выбрать цвет, нажмите кнопку **Выбрать...** .</span><span class="sxs-lookup"><span data-stu-id="78f83-140">To select the color, select the **Select...** button.</span></span>  
  
-   <span data-ttu-id="78f83-141">Выберите основной или пользовательский цвет, затем нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="78f83-141">Select either a basic or custom color, then select OK.</span></span>  
  
-   <span data-ttu-id="78f83-142">Укажите остальные сведения о подключении, а затем нажмите кнопку **Соединение** .</span><span class="sxs-lookup"><span data-stu-id="78f83-142">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f83-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="78f83-143">See Also</span></span>  
 [<span data-ttu-id="78f83-144">Редакторы запросов и текста (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="78f83-144">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](../scripting/query-and-text-editors-sql-server-management-studio.md)  
  
  
