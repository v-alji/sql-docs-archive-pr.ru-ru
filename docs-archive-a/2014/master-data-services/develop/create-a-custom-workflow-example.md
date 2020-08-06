---
title: Пример настраиваемого рабочего процесса (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: dfd1616c-a75c-4f32-bdb1-7569e367bf41
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ee9d6e18bf4e54ae5eb6af6a56494fff0db28684
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728406"
---
# <a name="custom-workflow-example-master-data-services"></a><span data-ttu-id="66f96-102">Пример настраиваемого рабочего процесса (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="66f96-102">Custom Workflow Example (Master Data Services)</span></span>
  <span data-ttu-id="66f96-103">В [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] при создании библиотеки пользовательского класса рабочего процесса создается класс, реализующий интерфейс [Microsoft. MasterDataServices. Воркфловтипикстендер. иворкфловтипикстендер](/previous-versions/sql/sql-server-2016/hh758785(v=sql.130)) .</span><span class="sxs-lookup"><span data-stu-id="66f96-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)], when you create a custom workflow class library, you create a class that implements the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender](/previous-versions/sql/sql-server-2016/hh758785(v=sql.130)) interface.</span></span> <span data-ttu-id="66f96-104">Этот интерфейс включает один метод [Microsoft. MasterDataServices. воркфловтипикстендер. иворкфловтипикстендер. стартворкфлов \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)), который вызывается службой интеграции рабочего процесса MDS SQL Server при запуске рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="66f96-104">This interface includes one method, [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)), that is called by SQL Server MDS Workflow Integration Service when a workflow starts.</span></span> <span data-ttu-id="66f96-105">Метод [Microsoft. MasterDataServices. воркфловтипикстендер. иворкфловтипикстендер. стартворкфлов \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) содержит два параметра: *воркфловтипе* содержит текст, введенный в текстовом поле **тип рабочего процесса** в [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] , а *элемент* DataItem содержит метаданные и данные элементов для элемента, который активировал бизнес-правило рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="66f96-105">The [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method contains two parameters: *workflowType* contains the text you entered in the **Workflow type** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], and *dataElement* contains metadata and item data for the item that triggered the workflow business rule.</span></span>  
  
## <a name="custom-workflow-example"></a><span data-ttu-id="66f96-106">Пример пользовательского рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="66f96-106">Custom Workflow Example</span></span>  
 <span data-ttu-id="66f96-107">В следующем примере кода показано, как реализовать метод [Microsoft. MasterDataServices. воркфловтипикстендер. иворкфловтипикстендер. стартворкфлов \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) для извлечения атрибутов Name, Code и ластчгусернаме из XML-данных для элемента, который активировал бизнес-правило рабочего процесса, а также как вызывать хранимую процедуру для их вставки в другую базу данных.</span><span class="sxs-lookup"><span data-stu-id="66f96-107">The following code example shows how you how to implement the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method to extract the Name, Code, and LastChgUserName attributes from the XML data for the element that triggered the workflow business rule, and how to call a stored procedure to insert them into another database.</span></span> <span data-ttu-id="66f96-108">Пример XML-данных элемента с описанием содержащихся в них тегов см. в разделе [Описание XML настраиваемого рабочего процесса (службы Master Data Services)](create-a-custom-workflow-xml-description.md).</span><span class="sxs-lookup"><span data-stu-id="66f96-108">For an example of the item data XML and an explanation of the tags it contains, see [Custom Workflow XML Description &#40;Master Data Services&#41;](create-a-custom-workflow-xml-description.md).</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Data.SqlClient;  
using System.Xml;  
  
using Microsoft.MasterDataServices.Core.Workflow;  
  
namespace MDSWorkflowTestLib  
{  
    public class WorkflowTester : IWorkflowTypeExtender  
    {  
        #region IWorkflowTypeExtender Members  
  
        public void StartWorkflow(string workflowType, System.Xml.XmlElement dataElement)  
        {  
            // Extract the attributes we want out of the element data.  
            XmlNode NameNode = dataElement.SelectSingleNode("//ExternalAction/MemberData/Name");  
            XmlNode CodeNode = dataElement.SelectSingleNode("//ExternalAction/MemberData/Code");  
            XmlNode EnteringUserNode = dataElement.SelectSingleNode("//ExternalAction/MemberData/LastChgUserName");  
  
            // Open a connection on the workflow database.  
            SqlConnection workflowConn = new SqlConnection(@"Data Source=<Server instance>; Initial Catalog=WorkflowTest; Integrated Security=True");  
  
            // Create a command to call the stored procedure that adds a new user to the workflow database.  
            SqlCommand addCustomerCommand = new SqlCommand("AddNewCustomer", workflowConn);  
            addCustomerCommand.CommandType = System.Data.CommandType.StoredProcedure;  
            addCustomerCommand.Parameters.Add(new SqlParameter("@Name", NameNode.InnerText));  
            addCustomerCommand.Parameters.Add(new SqlParameter("@Code", CodeNode.InnerText));  
            addCustomerCommand.Parameters.Add(new SqlParameter("@EnteringUser", EnteringUserNode.InnerText));  
  
            // Execute the command.  
            workflowConn.Open();  
            addCustomerCommand.ExecuteNonQuery();  
            workflowConn.Close();  
        }  
  
        #endregion  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="66f96-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="66f96-109">See Also</span></span>  
 [<span data-ttu-id="66f96-110">Создание настраиваемого рабочего процесса (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="66f96-110">Create a Custom Workflow &#40;Master Data Services&#41;</span></span>](create-a-custom-workflow-master-data-services.md)  
  
  
