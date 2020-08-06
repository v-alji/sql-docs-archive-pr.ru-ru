---
title: Диспетчер подключений Excel | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- files [Integration Services], connections
- connections [Integration Services], Excel
- Excel [Integration Services]
- connection managers [Integration Services], Excel
ms.assetid: 667419f2-74fb-4b50-b963-9197d1368cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7561361c6d4ab7e22282b25367906aa4b75e5bc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658953"
---
# <a name="excel-connection-manager"></a><span data-ttu-id="c7b47-102">Диспетчер соединений с Excel</span><span class="sxs-lookup"><span data-stu-id="c7b47-102">Excel Connection Manager</span></span>
  <span data-ttu-id="c7b47-103">Диспетчер соединений Excel делает доступным соединение пакета с существующим файлом рабочей книги [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="c7b47-103">An Excel connection manager enables a package to connect to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbook file.</span></span> <span data-ttu-id="c7b47-104">Источник Excel и назначение «Excel», которые [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] включают в себя использование диспетчера соединений Excel.</span><span class="sxs-lookup"><span data-stu-id="c7b47-104">The Excel source and the Excel destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] include use the Excel connection manager.</span></span>  
  
 <span data-ttu-id="c7b47-105">Если происходит добавление диспетчера соединений Excel к пакету, служба [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создает диспетчер соединений, который будет разрешен как соединение Excel во время выполнения, задает свойства диспетчера соединений и добавляет диспетчер соединений к коллекции `Connections` пакета.</span><span class="sxs-lookup"><span data-stu-id="c7b47-105">When you add an Excel connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an Excel connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="c7b47-106">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `EXCEL`.</span><span class="sxs-lookup"><span data-stu-id="c7b47-106">The `ConnectionManagerType` property of the connection manager is set to `EXCEL`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7b47-107">Подключить защищенный паролем файл Excel нельзя.</span><span class="sxs-lookup"><span data-stu-id="c7b47-107">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="configuration-of-the-excel-connection-manager"></a><span data-ttu-id="c7b47-108">Настройка диспетчера соединений Excel</span><span class="sxs-lookup"><span data-stu-id="c7b47-108">Configuration of the Excel Connection Manager</span></span>  
 <span data-ttu-id="c7b47-109">Чтобы настроить диспетчер соединений Excel, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="c7b47-109">You can configure the Excel connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="c7b47-110">Укажите путь файла рабочей книги Excel.</span><span class="sxs-lookup"><span data-stu-id="c7b47-110">Specify the path of the Excel workbook file.</span></span>  
  
-   <span data-ttu-id="c7b47-111">Укажите версию приложения Excel, использовавшуюся при создании файла.</span><span class="sxs-lookup"><span data-stu-id="c7b47-111">Specify the version of Excel that was used to create the file.</span></span>  
  
-   <span data-ttu-id="c7b47-112">Укажите, содержатся ли имена столбцов в первой строке данных выбранного рабочего листа или диапазона.</span><span class="sxs-lookup"><span data-stu-id="c7b47-112">Indicate whether the first row of accessed data in the selected worksheets or ranges contains column names.</span></span>  
  
 <span data-ttu-id="c7b47-113">Если диспетчер соединений Excel используется источником Excel, имена столбцов содержатся с извлеченными данными.</span><span class="sxs-lookup"><span data-stu-id="c7b47-113">If the Excel connection manager is used by an Excel source, the column names are included with the extracted data.</span></span> <span data-ttu-id="c7b47-114">Если он используется назначением Excel, имена столбцов включены в записанные данные.</span><span class="sxs-lookup"><span data-stu-id="c7b47-114">If it is used by an Excel destination, the column names are included in the written data.</span></span>  
  
 <span data-ttu-id="c7b47-115">Диспетчер соединений Excel использует поставщик [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB для Jet 4.0, который поддерживает драйвер Excel ISAM (индексно-последовательный метод доступа) для соединения, считывания и записи данных в источники данных Excel.</span><span class="sxs-lookup"><span data-stu-id="c7b47-115">The Excel connection manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span> <span data-ttu-id="c7b47-116">Дополнительные сведения о поведении этого поставщика и драйвера при использовании с источниками и назначениями Excel см. в разделе [Excel Source](../data-flow/excel-source.md) и [назначение](../data-flow/excel-destination.md)Excel.</span><span class="sxs-lookup"><span data-stu-id="c7b47-116">For more information about the behavior of this provider and driver when used with Excel sources and Excel destinations, see [Excel Source](../data-flow/excel-source.md) and [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
 <span data-ttu-id="c7b47-117">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="c7b47-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="c7b47-118">Дополнительные сведения о свойствах, которые можно задавать в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , см. в разделе [Редактор диспетчера соединений с Excel](../excel-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="c7b47-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Excel Connection Manager Editor](../excel-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="c7b47-119">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="c7b47-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
 <span data-ttu-id="c7b47-120">Дополнительные сведения о переходе между файлами в группе файлов Excel см. в разделе [Просмотр файлов и таблиц Excel с помощью контейнера "Цикл по каждому элементу"](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="c7b47-120">For information about looping through a group of Excel files, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c7b47-121">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="c7b47-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c7b47-122">Просмотр файлов и таблиц Excel с помощью контейнера «цикл по каждому элементу»</span><span class="sxs-lookup"><span data-stu-id="c7b47-122">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="c7b47-123">Импорт данных из Excel или экспорт данных в Excel с помощью служб SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="c7b47-123">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)
  
  
