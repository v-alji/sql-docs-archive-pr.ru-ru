---
title: Представление секции (табличное) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: b606cd63-755c-4ac0-b19b-95b5363afbdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6a29f273a584f3e60c6cf6458751965158cf8704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738831"
---
# <a name="partition-representation-tabular"></a><span data-ttu-id="5d89e-102">Представление секции (табличное)</span><span class="sxs-lookup"><span data-stu-id="5d89e-102">Partition Representation (Tabular)</span></span>
  <span data-ttu-id="5d89e-103">В оперативных целях таблица может быть разделена на разные подмножества строк, которые, будучи объединенными, формируют таблицу; каждое из таких подмножеств является секцией таблицы.</span><span class="sxs-lookup"><span data-stu-id="5d89e-103">For operational purposes, a table can be divided in different subsets of rows that when combined together form the table; each of those subsets is a partition of the table.</span></span>  
  
## <a name="partition-representation"></a><span data-ttu-id="5d89e-104">Представление секции</span><span class="sxs-lookup"><span data-stu-id="5d89e-104">Partition Representation</span></span>  
 <span data-ttu-id="5d89e-105">С точки зрения объектов AMO представление секции имеет связь типа «один к одному» с <xref:Microsoft.AnalysisServices.Partition> и никакие другие основные объекты AMO не требуются.</span><span class="sxs-lookup"><span data-stu-id="5d89e-105">In terms of AMO objects a partition representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Partition> and no other main AMO objects are required</span></span>  
  
### <a name="partition-in-amo"></a><span data-ttu-id="5d89e-106">Секция в объектах AMO</span><span class="sxs-lookup"><span data-stu-id="5d89e-106">Partition in AMO</span></span>  
 <span data-ttu-id="5d89e-107">Если для управления секцией используются объекты AMO, нужно найти группу мер, которая представляет таблицу табличной модели, и работать с ней.</span><span class="sxs-lookup"><span data-stu-id="5d89e-107">When using AMO to manage a partition in a you need to find the measure group that represents the Tabular Model table and work from there.</span></span>  
  
 <span data-ttu-id="5d89e-108">В следующем фрагменте кода показано, как добавить секцию в существующую таблицу табличной модели.</span><span class="sxs-lookup"><span data-stu-id="5d89e-108">The following code snippet shows how to add a partition to an existing tabular model table.</span></span>  
  
```  
  
private void AddPartition(  
                     AMO.Cube modelCube  
                  ,  AMO.DataSource newDatasource  
                  ,  string mgName  
                  ,  string newPartitionName  
                  , string partitionSelectStatement  
                  , Boolean processPartition  
             )  
{  
    mgName = mgName.Trim();  
    newPartitionName = newPartitionName.Trim();  
    partitionSelectStatement = partitionSelectStatement.Trim();  
    //Validate Input  
    if (string.IsNullOrEmpty(newPartitionName) || string.IsNullOrWhiteSpace(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (modelCube.MeasureGroups[mgName].Partitions.ContainsName(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name already defined. Duplicated names are not allowed"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (string.IsNullOrEmpty(partitionSelectStatement) || string.IsNullOrWhiteSpace(partitionSelectStatement))  
    {  
        MessageBox.Show(String.Format("Select statement cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    //Input validated  
    string partitionID = newPartitionName; //Using partition name as the ID  
    AMO.Partition currentPartition = new AMO.Partition(partitionID, partitionID);  
    currentPartition.StorageMode = AMO.StorageMode.InMemory;  
    currentPartition.ProcessingMode = AMO.ProcessingMode.Regular;  
    currentPartition.Source = new AMO.QueryBinding(newDatasource.ID, partitionSelectStatement);  
    modelCube.MeasureGroups[mgName].Partitions.Add(currentPartition);  
    try  
    {  
        modelCube.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
        if (processPartition)  
        {  
            modelCube.MeasureGroups[mgName].Partitions[partitionID].Process(AMO.ProcessType.ProcessFull);  
            MessageBox.Show(String.Format("Partition successfully processed."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
        }  
  
    }  
    catch (AMO.AmoException amoXp)  
    {  
        MessageBox.Show(String.Format("AMO exception accessing the server.\nError message: {0}", amoXp.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
    catch (Exception)  
    {  
        throw;  
    }  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="5d89e-109">Образец AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="5d89e-109">AMO2Tabular sample</span></span>  
 <span data-ttu-id="5d89e-110">Однако, чтобы получить представление об использовании объектов AMO для создания представлений секции и управления ими, см. исходный код образца "Преобразование объектов AMO в табличную модель".</span><span class="sxs-lookup"><span data-stu-id="5d89e-110">However, to have an understanding on how to use AMO to create and manipulate partition representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="5d89e-111">Этот образец доступен на сайте Codeplex.</span><span class="sxs-lookup"><span data-stu-id="5d89e-111">The sample is available at Codeplex.</span></span> <span data-ttu-id="5d89e-112">Важное примечание о коде. Код предоставляется только для иллюстрации логических концепций, поясняемых в этом разделе. Его не следует использовать в рабочей среде или для других целей, за исключением учебных.</span><span class="sxs-lookup"><span data-stu-id="5d89e-112">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
