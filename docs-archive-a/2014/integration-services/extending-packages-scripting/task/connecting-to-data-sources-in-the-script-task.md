---
title: Соединение с источниками данных в задаче "Скрипт" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- connections [Integration Services], scripts
- Integration Services packages, connections
- connection managers [Integration Services], scripts
- scripts [Integration Services], connections
- SSIS packages, connections
- packages [Integration Services], connections
- Script task [Integration Services], connections
- Connections property
- SQL Server Integration Services packages, connections
- SSIS Script task, connections
ms.assetid: 9c008380-715b-455b-9da7-22572d67c388
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c8374271c7972498361a83e4bbe87ad12265827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731909"
---
# <a name="connecting-to-data-sources-in-the-script-task"></a><span data-ttu-id="bc2c8-102">Соединение с источниками данных в задаче «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="bc2c8-102">Connecting to Data Sources in the Script Task</span></span>
  <span data-ttu-id="bc2c8-103">Диспетчеры соединений обеспечивают доступ к источникам данных, которые были настроены в пакете.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-103">Connection managers provide access to data sources that have been configured in the package.</span></span> <span data-ttu-id="bc2c8-104">Дополнительные сведения см. в разделе [Соединения в службах Integration Services (SSIS)](../../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="bc2c8-104">For more information, see [Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
 <span data-ttu-id="bc2c8-105">Задача "Скрипт" может обращаться к диспетчерам соединений через свойство <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> объекта **Dts**.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-105">The Script task can access these connection managers through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property of the **Dts** object.</span></span> <span data-ttu-id="bc2c8-106">Каждый диспетчер соединений в коллекции <xref:Microsoft.SqlServer.Dts.Runtime.Connections> хранит сведения о том, как соединиться с базовым источником данных.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-106">Each connection manager in the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection stores information about how to connect to the underlying data source.</span></span>  
  
 <span data-ttu-id="bc2c8-107">При вызове метода <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> диспетчера соединений диспетчер соединяется с источником данных, если соединение еще не было установлено, и возвращает соответствующее соединение или сведения о соединении для использования в коде задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="bc2c8-107">When you call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a connection manager, the connection manager connects to the data source, if it is not already connected, and returns the appropriate connection or connection information for you to use in your Script task code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc2c8-108">Прежде чем вызывать метод `AcquireConnection`, необходимо знать тип соединения, возвращаемого диспетчером соединений.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-108">You must know the type of connection returned by the connection manager before calling `AcquireConnection`.</span></span> <span data-ttu-id="bc2c8-109">Поскольку в задаче «Скрипт» включен параметр `Option Strict`, перед использованием необходимо привести соединение, возвращаемое с типом `Object`, к подходящему типу соединения.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-109">Because the Script task has `Option Strict` enabled, you must cast the connection, which is returned as type `Object`, to the appropriate connection type before you can use it.</span></span>  
  
 <span data-ttu-id="bc2c8-110">Можно воспользоваться методом <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> коллекции <xref:Microsoft.SqlServer.Dts.Runtime.Connections>, возвращаемой свойством <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A>, чтобы выполнить поиск существующего соединения, прежде чем использовать соединение в коде.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-110">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property to look for an existing connection before using the connection in your code.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bc2c8-111">В управляемом коде задачи "Скрипт" нельзя вызывать метод AcquireConnection диспетчеров соединений, возвращающих неуправляемые объекты, например диспетчера соединений OLE DB или диспетчера соединений Excel.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-111">You cannot call the AcquireConnection method of connection managers that return unmanaged objects, such as the OLE DB connection manager and the Excel connection manager, in the managed code of a Script task.</span></span> <span data-ttu-id="bc2c8-112">Тем не менее можно прочитать свойство ConnectionString этих диспетчеров соединений и подключиться к источнику данных непосредственно в коде, используя строку подключения `OledbConnection` из пространства имен **System. Data. OLEDB** .</span><span class="sxs-lookup"><span data-stu-id="bc2c8-112">However, you can read the ConnectionString property of these connection managers, and connect to the data source directly in your code by using the connection string with an `OledbConnection` from the **System.Data.OleDb** namespace.</span></span>  
>   
>  <span data-ttu-id="bc2c8-113">Если необходимо вызвать метод AcquireConnection диспетчера соединений, возвращающего неуправляемый объект, используйте диспетчер соединений [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc2c8-113">If you must call the AcquireConnection method of a connection manager that returns an unmanaged object, use an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager.</span></span> <span data-ttu-id="bc2c8-114">При настройке диспетчера соединений [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] для использования поставщика OLE DB, он соединяется с помощью поставщика данных [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] для OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-114">When you configure the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager to use an OLE DB provider, it connects by using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB.</span></span> <span data-ttu-id="bc2c8-115">В этом случае метод AcquireConnection возвращает `System.Data.OleDb.OleDbConnection` вместо неуправляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-115">In this case, the AcquireConnection method returns a `System.Data.OleDb.OleDbConnection` instead of an unmanaged object.</span></span> <span data-ttu-id="bc2c8-116">Чтобы настроить диспетчер соединений [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] для работы с источником данных Excel, выберите поставщик OLE DB [!INCLUDE[msCoName](../../../includes/msconame-md.md)] для Jet (Майкрософт), укажите книгу Excel, а затем введите `Excel 8.0` (для Excel 97 и более поздних версий) в качестве значения параметра **Расширенные свойства** на странице **Все** диалогового окна **Диспетчер соединений**.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-116">To configure an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager for use with an Excel data source, select the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] OLE DB Provider for Jet, specify an Excel file, and enter `Excel 8.0` (for Excel 97 and later) as the value of **Extended Properties** on the **All** page of the **Connection Manager** dialog box.</span></span>  
  
## <a name="connections-example"></a><span data-ttu-id="bc2c8-117">Пример соединений</span><span class="sxs-lookup"><span data-stu-id="bc2c8-117">Connections Example</span></span>  
 <span data-ttu-id="bc2c8-118">В следующем примере демонстрируется, как получить доступ к диспетчерам соединений из задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="bc2c8-118">The following example demonstrates how to access connection managers from within the Script task.</span></span> <span data-ttu-id="bc2c8-119">В образце предполагается, что был создан и настроен диспетчер соединений [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] с именем **Test ADO.NET Connection** и диспетчер соединений с неструктурированными файлами с именем **Test Flat File Connection**.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-119">The sample assumes that you have created and configured an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager named **Test ADO.NET Connection** and a Flat File connection manager named **Test Flat File Connection**.</span></span> <span data-ttu-id="bc2c8-120">Обратите внимание, что диспетчер соединений [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] возвращает объект `SqlConnection`, который можно использовать немедленно для соединения с источником данных.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-120">Note that the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager returns a `SqlConnection` object that you can use immediately to connect to the data source.</span></span> <span data-ttu-id="bc2c8-121">Диспетчер соединений с неструктурированными файлами, в то же время, возвращает лишь строку, содержащую путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-121">The Flat File connection manager, on the other hand, returns only a string that contains the path and file name.</span></span> <span data-ttu-id="bc2c8-122">Необходимо использовать методы из пространства имен `System.IO`, чтобы открыть неструктурированный файл и работать с ним.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-122">You must use methods from the `System.IO` namespace to open and work with the flat file.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myADONETConnection As SqlClient.SqlConnection  
    myADONETConnection = _  
        DirectCast(Dts.Connections("Test ADO.NET Connection").AcquireConnection(Dts.Transaction), _  
        SqlClient.SqlConnection)  
    MsgBox(myADONETConnection.ConnectionString, _  
        MsgBoxStyle.Information, "ADO.NET Connection")  
  
    Dim myFlatFileConnection As String  
    myFlatFileConnection = _  
        DirectCast(Dts.Connections("Test Flat File Connection").AcquireConnection(Dts.Transaction), _  
        String)  
    MsgBox(myFlatFileConnection, MsgBoxStyle.Information, "Flat File Connection")  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
  
public class ScriptMain  
{  
  
        public void Main()  
        {  
            SqlConnection myADONETConnection = new SqlConnection();  
            myADONETConnection = (SqlConnection)(Dts.Connections["Test ADO.NET Connection"].AcquireConnection(Dts.Transaction)as SqlConnection);  
            MessageBox.Show(myADONETConnection.ConnectionString, "ADO.NET Connection");  
  
            string myFlatFileConnection;  
            myFlatFileConnection = (string)(Dts.Connections["Test Flat File Connection"].AcquireConnection(Dts.Transaction) as String);  
            MessageBox.Show(myFlatFileConnection, "Flat File Connection");  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
  
```  
  
<span data-ttu-id="bc2c8-123">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="bc2c8-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bc2c8-124">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="bc2c8-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bc2c8-125">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="bc2c8-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bc2c8-126">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="bc2c8-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc2c8-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="bc2c8-127">See Also</span></span>  
 <span data-ttu-id="bc2c8-128">[Integration Services &#40;соединений&#41; SSIS](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="bc2c8-128">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="bc2c8-129">Создание диспетчеров соединений</span><span class="sxs-lookup"><span data-stu-id="bc2c8-129">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  
