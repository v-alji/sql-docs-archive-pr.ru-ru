---
title: Диспетчер соединений ADO | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ADO
- connection managers [Integration Services], ADO
- ADO connection manager [Integration Services]
ms.assetid: 490418bc-5ef1-41b8-a9c8-de38aa96e0f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb4b667733f81eebbaf2b6a2ab9b205c09fe2c66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667365"
---
# <a name="ado-connection-manager"></a><span data-ttu-id="b7e1d-102">Диспетчер соединений ADO</span><span class="sxs-lookup"><span data-stu-id="b7e1d-102">ADO Connection Manager</span></span>
  <span data-ttu-id="b7e1d-103">Диспетчер соединений ADO позволяет пакету подключаться к таким объектам ADO, как набор записей.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-103">An ADO connection manager enables a package to connect to ActiveX Data Objects (ADO) objects, such as a recordset.</span></span> <span data-ttu-id="b7e1d-104">Текущий диспетчер соединений обычно используется в пользовательских задачах, созданных в ранних версиях таких языков, как Microsoft Visual Basic 6.0, или в пользовательских задачах, которые являются частью существующего приложения, использующего ADO для подключения к источникам данных.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-104">This connection manager is typically used in custom tasks written in an earlier version of a language, such as Microsoft Visual Basic 6.0, or in custom tasks that are part of an existing application that uses ADO to connect to a data source.</span></span>  
  
 <span data-ttu-id="b7e1d-105">При добавлении к пакету диспетчера соединений ADO [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] создает диспетчер соединений, который будет разрешаться в соединение ADO во время выполнения, устанавливает свойства диспетчера соединений и добавляет его в `Connections` коллекцию пакета.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-105">When you add an ADO connection manager to a package, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an ADO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="b7e1d-106">Свойству `ConnectionManagerType` диспетчера соединений присваивается значение `ADO`.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-106">The `ConnectionManagerType` property of the connection manager is set to `ADO`.</span></span>  
  
## <a name="troubleshooting-the-ado-connection-manager"></a><span data-ttu-id="b7e1d-107">Устранение неполадок диспетчера соединений ADO</span><span class="sxs-lookup"><span data-stu-id="b7e1d-107">Troubleshooting the ADO Connection Manager</span></span>  
 <span data-ttu-id="b7e1d-108">При считывании данных диспетчером соединений ADO некоторые типы данных даты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] формируют результаты, показанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-108">When being read by an ADO connection manager, certain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date data types will generate the results shown in the following table.</span></span>  
  
|<span data-ttu-id="b7e1d-109">Тип данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7e1d-109">SQL Server Data type</span></span>|<span data-ttu-id="b7e1d-110">Результат</span><span class="sxs-lookup"><span data-stu-id="b7e1d-110">Result</span></span>|  
|--------------------------|------------|  
|<span data-ttu-id="b7e1d-111">`time`, `datetimeoffset`</span><span class="sxs-lookup"><span data-stu-id="b7e1d-111">`time`, `datetimeoffset`</span></span>|<span data-ttu-id="b7e1d-112">Выполнение пакета завершается неудачей, если в пакете не используются параметризованные команды SQL.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-112">The package fails unless the package uses parameterized SQL commands.</span></span> <span data-ttu-id="b7e1d-113">Чтобы применить параметризованные команды SQL, используйте в пакете задачу «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="b7e1d-113">To use parameterized SQL commands, use the Execute SQL Task in your package.</span></span> <span data-ttu-id="b7e1d-114">Дополнительные сведения см. в разделах [Задача "Выполнение SQL"](../control-flow/execute-sql-task.md) и [Параметры и коды возврата в задаче "Выполнение SQL"](../parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="b7e1d-114">For more information, see [Execute SQL Task](../control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>|  
|`datetime2`|<span data-ttu-id="b7e1d-115">Диспетчер соединений ADO усекает значение миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-115">The ADO connection manager truncates the millisecond value.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="b7e1d-116">Дополнительные сведения о типах данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и их сопоставлении с типами данных [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] см. в разделе [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql) и [Типы данных службы Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b7e1d-116">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and how they map to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) and [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="configuring-the-ado-connection-manager"></a><span data-ttu-id="b7e1d-117">Настройка диспетчера соединений ADO</span><span class="sxs-lookup"><span data-stu-id="b7e1d-117">Configuring the ADO Connection Manager</span></span>  
 <span data-ttu-id="b7e1d-118">Настройку диспетчера соединений ADO можно осуществлять следующими способами.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-118">You can configure an ADO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="b7e1d-119">Укажите конкретную строку соединения, соответствующую требованиям конфигурации выбранного поставщика.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-119">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="b7e1d-120">В зависимости от поставщика предоставьте имя источника данных, к которому производится подключение.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-120">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="b7e1d-121">Предоставьте безопасные учетные данные, соответствующие выбранному поставщику.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-121">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="b7e1d-122">Обозначает, будет ли соединение, созданное из диспетчера соединений, сохранено во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-122">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="b7e1d-123">Значения свойств можно задавать с помощью конструктора [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или программными средствами.</span><span class="sxs-lookup"><span data-stu-id="b7e1d-123">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b7e1d-124">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="b7e1d-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="b7e1d-125">Настройка диспетчера подключений OLE DB</span><span class="sxs-lookup"><span data-stu-id="b7e1d-125">Configure OLE DB Connection Manager</span></span>](ole-db-connection-manager.md)  
  
 <span data-ttu-id="b7e1d-126">Дополнительные сведения о программной настройке диспетчера подключений см. в разделах <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> и [Добавление соединений программным образом](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="b7e1d-126">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e1d-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7e1d-127">See Also</span></span>  
 [<span data-ttu-id="b7e1d-128">Соединения в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="b7e1d-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
