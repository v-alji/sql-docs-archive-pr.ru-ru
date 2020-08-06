---
title: Передача параметров в диаграмм обновления (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nullvalue attribute
- passing parameters [SQLXML]
- parameters [SQLXML]
- updategrams [SQLXML], passing parameters
- null values [SQLXML]
ms.assetid: 2354e6e7-1860-471f-8711-4e374c5a4ed2
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bc29de2dab3d0bc3587cb21b7005c0c23dcf7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665959"
---
# <a name="passing-parameters-to-updategrams-sqlxml-40"></a><span data-ttu-id="e5bb3-102">Передача параметров для диаграмм обновления (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e5bb3-102">Passing Parameters to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="e5bb3-103">Диаграммы обновления представляют собой шаблоны; следовательно, им можно передавать параметры.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-103">Updategrams are templates; therefore, you can pass them parameters.</span></span> <span data-ttu-id="e5bb3-104">Дополнительные сведения о передаче параметров в шаблоны см. в разделе [Диаграмма обновления Security соображения &#40;SQLXML 4,0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-104">For more information about passing parameters to templates, see [Updategram Security Considerations &#40;SQLXML 4.0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="e5bb3-105">Диаграммы обновления позволяют передавать значение NULL в качестве значения параметра.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-105">Updategrams allow you to pass NULL as a parameter value.</span></span> <span data-ttu-id="e5bb3-106">Для передачи значения NULL в качестве значения параметра нужно задать атрибут `nullvalue`.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-106">To pass the NULL parameter value, you specify the `nullvalue` attribute.</span></span> <span data-ttu-id="e5bb3-107">После этого в качестве значения параметра передается значение, присвоенное атрибуту `nullvalue`.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-107">The value that is assigned to the `nullvalue` attribute is then provided as the parameter value.</span></span> <span data-ttu-id="e5bb3-108">В диаграммах обновления это значение рассматривается как NULL.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-108">Updategrams treat this value as NULL.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5bb3-109">В `<sql:header>` и `<updg:header>` следует задавать `nullvalue` как неполное имя; однако в `<updg:sync>` следует задавать `nullvalue` в виде полного имени (например, `updg:nullvalue`).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-109">In `<sql:header>` and `<updg:header>`, you should specify the `nullvalue` as unqualified; whereas, in `<updg:sync>`, you specify the `nullvalue` as qualified (for example, `updg:nullvalue`).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e5bb3-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="e5bb3-110">Examples</span></span>  
 <span data-ttu-id="e5bb3-111">Чтобы создать рабочие образцы с помощью следующих примеров, необходимо выполнить требования, указанные в [требованиях к запуску примеров SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-111">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="e5bb3-112">При использовании примеров диаграмм обновления необходимо учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-112">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="e5bb3-113">В примерах используется сопоставление по умолчанию (т. е. в диаграмме обновления не задана схема сопоставления).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-113">The examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="e5bb3-114">Дополнительные примеры диаграмм обновления, в которых используются схемы сопоставления, см. [в разделе Указание схемы сопоставления с заметками в диаграмма обновления &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-114">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="a-passing-parameters-to-an-updategram"></a><span data-ttu-id="e5bb3-115">A.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-115">A.</span></span> <span data-ttu-id="e5bb3-116">Передача параметров диаграмме обновления</span><span class="sxs-lookup"><span data-stu-id="e5bb3-116">Passing parameters to an updategram</span></span>  
 <span data-ttu-id="e5bb3-117">В данном примере диаграмма обновления применяется для изменения фамилии сотрудника в таблице HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-117">In this example, the updategram changes the last name of an employee in the HumanResources.Shift table.</span></span> <span data-ttu-id="e5bb3-118">Диаграмма обновления передается два параметра: Шифтид, который используется для уникальной идентификации сдвига и имени.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-118">The updategram is passed two parameters: ShiftID, which is used to uniquely identify a shift, and Name.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
  <updg:param name="ShiftID"/>  
  <updg:param name="Name" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="$ShiftID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="$Name" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e5bb3-119">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e5bb3-119">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e5bb3-120">Скопируйте приведенную выше диаграмму обновления в блокнот и сохраните как файл с именем UpdategramWithParameters.xml.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-120">Copy the updategram above into Notepad and save it to file as UpdategramWithParameters.xml.</span></span>  
  
2.  <span data-ttu-id="e5bb3-121">Подготовка тестового скрипта SQLXML 4,0 (Sqlxml4test. vbs) в [с помощью ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) для выполнения диаграмма обновления путем добавления следующих строк после `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="e5bb3-121">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value  
    cmd.Parameters.Append cmd.CreateParameter("@ShiftID",  2, 1,  0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@Name",   200, 1, 50, "New Name")  
    ```  
  
### <a name="b-passing-null-as-a-parameter-value-to-an-updategram"></a><span data-ttu-id="e5bb3-122">Б.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-122">B.</span></span> <span data-ttu-id="e5bb3-123">Передача NULL в качестве значения параметра для диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e5bb3-123">Passing NULL as a parameter value to an updategram</span></span>  
 <span data-ttu-id="e5bb3-124">При выполнении диаграммы обновления тому параметру, для которого нужно задать значение NULL, присваивается значение «isnull».</span><span class="sxs-lookup"><span data-stu-id="e5bb3-124">In executing an updategram, the "isnull" value is assigned to the parameter that you want to set to NULL.</span></span> <span data-ttu-id="e5bb3-125">Диаграмма обновления преобразовывает значение параметра «isnull» в NULL и обрабатывает соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-125">Updategram converts the "isnulll" parameter value to NULL and processes it accordingly.</span></span>  
  
 <span data-ttu-id="e5bb3-126">Следующая диаграмма обновления устанавливает значение NULL для названия должности сотрудника.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-126">The following updategram sets an employee title to NULL:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header nullvalue="isnull" >  
  <updg:param name="EmployeeID"/>  
  <updg:param name="ManagerID" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Employee EmployeeID="$EmployeeID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Employee ManagerID="$ManagerID" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e5bb3-127">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e5bb3-127">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e5bb3-128">Скопируйте приведенную выше диаграмму обновления в блокнот и сохраните как файл с именем UpdategramPassingNullvalues.xml.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-128">Copy the updategram above into Notepad and save it to file as UpdategramPassingNullvalues.xml.</span></span>  
  
2.  <span data-ttu-id="e5bb3-129">Подготовка тестового скрипта SQLXML 4,0 (Sqlxml4test. vbs) в [с помощью ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) для выполнения диаграмма обновления путем добавления следующих строк после `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="e5bb3-129">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value   
    cmd.Parameters.Append cmd.CreateParameter("@EmployeeID", 3, 1, 0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@ManagerID",  3, 1, 0, Null)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e5bb3-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="e5bb3-130">See Also</span></span>  
 [<span data-ttu-id="e5bb3-131">Вопросы безопасности диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e5bb3-131">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
