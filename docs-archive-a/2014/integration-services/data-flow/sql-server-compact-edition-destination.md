---
title: Назначение "SQL Server Compact Edition" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlservercompactdest.f1
helpviewer_keywords:
- destinations [Integration Services], SQL Server Compact
- SQL Server Compact, destination
- inserting data
ms.assetid: 697742ba-cc14-414d-8187-1845ad0dd99b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfeb0bfce54c9ebefb5c526656be6b736dc0d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667330"
---
# <a name="sql-server-compact-edition-destination"></a><span data-ttu-id="5f6b6-102">Назначение «SQL Server Compact Edition»</span><span class="sxs-lookup"><span data-stu-id="5f6b6-102">SQL Server Compact Edition Destination</span></span>
  <span data-ttu-id="5f6b6-103">Назначение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact записывает данные в базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination writes data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact databases.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f6b6-104">На 64-разрядном компьютере пакеты, которые соединяются с источниками данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, должны запускаться в 32-разрядном режиме.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-104">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="5f6b6-105">Поставщик [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, используемый службами [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] для соединения с источниками данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, доступен только в 32-разрядной версии.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
 <span data-ttu-id="5f6b6-106">Настройка назначения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact производится путем указания имени таблицы, в которую назначение SQL [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact вставляет данные.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-106">You configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination by specifying the name of the table into which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination inserts the data.</span></span> <span data-ttu-id="5f6b6-107">Пользовательское свойство TableName назначения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact содержит имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-107">The custom property TableName of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination contains the table name.</span></span>  
  
 <span data-ttu-id="5f6b6-108">Назначение использует диспетчер соединений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, чтобы подключиться к источнику данных; диспетчер соединений определяет поставщик OLE DB для использования.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-108">This destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="5f6b6-109">Дополнительные сведения см. в разделе [Диспетчер соединений SQL Server Compact Edition](../connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5f6b6-109">For more information, see [SQL Server Compact Edition Connection Manager](../connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
 <span data-ttu-id="5f6b6-110">Назначение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact содержит пользовательское свойство TableName, которое может быть обновлено выражением свойства после загрузки пакета.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination includes the TableName custom property, which can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="5f6b6-111">Дополнительные сведения см. в разделах [Выражения служб Integration Services (SSIS)](../expressions/integration-services-ssis-expressions.md), [Использование выражений свойств в пакетах](../expressions/use-property-expressions-in-packages.md) и [Пользовательские свойства назначения SQL Server Compact Edition](sql-server-compact-edition-destination-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5f6b6-111">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [SQL Server Compact Edition Destination Custom Properties](sql-server-compact-edition-destination-custom-properties.md).</span></span>  
  
 <span data-ttu-id="5f6b6-112">Назначение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact имеет один вход и не поддерживает вывод ошибок.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination has one input and does not support an error output.</span></span>  
  
## <a name="configuration-of-the-sql-server-compact-edition-destination"></a><span data-ttu-id="5f6b6-113">Настройка назначения SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="5f6b6-113">Configuration of the SQL Server Compact Edition Destination</span></span>  
 <span data-ttu-id="5f6b6-114">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-114">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="5f6b6-115">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-115">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="5f6b6-116">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="5f6b6-116">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="5f6b6-117">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="5f6b6-117">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="5f6b6-118">Пользовательские свойства назначения «SQL Server»</span><span class="sxs-lookup"><span data-stu-id="5f6b6-118">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="5f6b6-119">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="5f6b6-119">Related Tasks</span></span>  
 <span data-ttu-id="5f6b6-120">Дополнительные сведения о настройке свойств компонента см. в разделе [Установление свойств компонента потока данных](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="5f6b6-120">For more information about how to set properties of this component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6b6-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f6b6-121">See Also</span></span>  
 [<span data-ttu-id="5f6b6-122">Поток данных</span><span class="sxs-lookup"><span data-stu-id="5f6b6-122">Data Flow</span></span>](data-flow.md)  
  
  
