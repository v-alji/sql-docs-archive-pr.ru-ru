---
title: Средства устранения неполадок при подключении к пакету | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, troubleshooting
- SSIS packages, troubleshooting
- Integration Services, troubleshooting
- connectivity [Integration Services], troubleshooting
- errors [Integration Services], troubleshooting
- packages [Integration Services], troubleshooting
ms.assetid: 08a019f5-8ba7-4527-97c1-e9846d4022ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1baac9af5a30fdc0f5b15e8ac56eb5badacc0edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731874"
---
# <a name="troubleshooting-tools-package-connectivity"></a><span data-ttu-id="743b8-102">Инструменты устранения неполадок соединения пакетов</span><span class="sxs-lookup"><span data-stu-id="743b8-102">Troubleshooting Tools Package Connectivity</span></span>
  <span data-ttu-id="743b8-103">Службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] включают в себя функции и средства, которые используются для устранения неполадок соединений между пакетами и источниками данных, из которых пакеты извлекают и загружают данные.</span><span class="sxs-lookup"><span data-stu-id="743b8-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes features and tools that you can use to troubleshoot connectivity between packages and the data sources from which packages extract and load data.</span></span>  
  
## <a name="troubleshooting-issues-with-external-data-providers"></a><span data-ttu-id="743b8-104">Устранение неполадок, связанных с внешними поставщиками данных</span><span class="sxs-lookup"><span data-stu-id="743b8-104">Troubleshooting Issues with External Data Providers</span></span>  
 <span data-ttu-id="743b8-105">Многие ошибки в работе пакетов возникают при взаимодействии с внешними поставщиками данных.</span><span class="sxs-lookup"><span data-stu-id="743b8-105">Many packages fail during interactions with external data providers.</span></span> <span data-ttu-id="743b8-106">Однако сообщения, которые возвращают эти поставщики в службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , часто не предоставляют достаточных сведений для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="743b8-106">However, the messages that those providers return to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] frequently do not provide enough information to start troubleshooting the interaction.</span></span> <span data-ttu-id="743b8-107">В ответ на требования, связанные с устранением неисправностей, в состав служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] были добавлены новые сообщения ведения журналов, которые можно использовать для устранения неполадок взаимодействия пакета с внешними источниками данных.</span><span class="sxs-lookup"><span data-stu-id="743b8-107">To address this troubleshooting need, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes logging messages that you can use to troubleshoot a package's interaction with external data sources.</span></span>  
  
-   <span data-ttu-id="743b8-108">**Чтобы просматривать сообщения, связанные с устранением неисправностей, необходимо разрешить запись в журнал и выбрать событие пакета «Диагностика».**</span><span class="sxs-lookup"><span data-stu-id="743b8-108">**Enable logging and select the package's Diagnostic event to see the troubleshooting messages**.</span></span> <span data-ttu-id="743b8-109">Следующие компоненты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] обеспечивают возможность записи сообщений в журнал перед каждым обращением к внешнему поставщику данных и после этого.</span><span class="sxs-lookup"><span data-stu-id="743b8-109">The following [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components are capable of writing a message to the log before and after every call to an external data provider:</span></span>  
  
    -   <span data-ttu-id="743b8-110">Диспетчер соединений OLE DB, источник OLE DB и назначение «OLE DB»</span><span class="sxs-lookup"><span data-stu-id="743b8-110">OLE DB connection manager, OLE DB source, and OLE DB destination</span></span>  
  
    -   <span data-ttu-id="743b8-111">Диспетчер подключений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] и источник ADO NET</span><span class="sxs-lookup"><span data-stu-id="743b8-111">[!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and ADO NET source</span></span>  
  
    -   <span data-ttu-id="743b8-112">Задача «Выполнение SQL»</span><span class="sxs-lookup"><span data-stu-id="743b8-112">Execute SQL task</span></span>  
  
    -   <span data-ttu-id="743b8-113">Преобразование «Уточняющий запрос», преобразование «Команда OLE DB» и преобразование «Медленно изменяющееся измерение»</span><span class="sxs-lookup"><span data-stu-id="743b8-113">Lookup transformation, OLE DB Command transformation, and Slowly Changing Dimension transformation</span></span>  
  
     <span data-ttu-id="743b8-114">Сообщения журнала содержат название вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="743b8-114">The log messages include the name of the method being called.</span></span> <span data-ttu-id="743b8-115">Например, эти сообщения журнала могут содержать метод `Open` объекта OLE DB `Connection` или метод `ExecuteNonQuery` объекта `Command`.</span><span class="sxs-lookup"><span data-stu-id="743b8-115">For example, these log messages might include the `Open` method of an OLE DB `Connection` object or the `ExecuteNonQuery` method of a `Command` object.</span></span> <span data-ttu-id="743b8-116">Сообщения имеют следующий формат, где "%1!s!" —</span><span class="sxs-lookup"><span data-stu-id="743b8-116">The messages have the following format, where '%1!s!'</span></span> <span data-ttu-id="743b8-117">заполнитель для сведений метода:</span><span class="sxs-lookup"><span data-stu-id="743b8-117">is a placeholder for the method information:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: '%1!s!'.  
    ExternalRequest_post: '%1!s!'. The external request has completed.  
    ```  
  
     <span data-ttu-id="743b8-118">Для устранения неполадок взаимодействия с внешним поставщиком данных просмотрите журнал, чтобы убедиться, что каждое входящее сообщение (`ExternalRequest_pre`) имеет соответствующее подтверждающее сообщение (`ExternalRequest_post`).</span><span class="sxs-lookup"><span data-stu-id="743b8-118">To troubleshoot the interaction with the external data provider, review the log to see whether every "before" message (`ExternalRequest_pre`) has a corresponding "after" message (`ExternalRequest_post`).</span></span> <span data-ttu-id="743b8-119">Если соответствующее подтверждающее сообщение отсутствует, то это означает, что внешний поставщик данных не ответил так, как это ожидалось.</span><span class="sxs-lookup"><span data-stu-id="743b8-119">If there is no corresponding "after" message, you know that the external data provider did not respond as expected.</span></span>  
  
     <span data-ttu-id="743b8-120">В следующем примере показаны несколько образцов строк из журнала, содержащего эти сообщения.</span><span class="sxs-lookup"><span data-stu-id="743b8-120">The following example shows some sample rows from a log that contains these logging messages:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: 'ITransactionJoin::JoinTransaction'.  
    ExternalRequest_post: 'ITransactionJoin::JoinTransaction succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Open'.  
    ExternalRequest_post: 'IDbConnection.Open succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.CreateCommand'.  
    ExternalRequest_post: 'IDbConnection.CreateCommand finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbCommand.ExecuteReader'.  
    ExternalRequest_post: 'IDbCommand.ExecuteReader finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.GetSchemaTable'.  
    ExternalRequest_post: 'IDataReader.GetSchemaTable finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.Close'.  
    ExternalRequest_post: 'IDataReader.Close finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Close'.  
    ExternalRequest_post: 'IDbConnection.Close finished'. The external request has completed."  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="743b8-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="743b8-121">See Also</span></span>  
 <span data-ttu-id="743b8-122">[Инструменты устранения неполадок при разработке пакета](troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="743b8-122">[Troubleshooting Tools for Package Development](troubleshooting-tools-for-package-development.md) </span></span>  
 [<span data-ttu-id="743b8-123">Устранение неполадок инструментов с помощью отчетов</span><span class="sxs-lookup"><span data-stu-id="743b8-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
