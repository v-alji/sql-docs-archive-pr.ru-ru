---
title: Представление вычисляемой меры (табличное) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 4cb9fea5-1616-467b-a539-d051e5833aea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6b630fa075ae07b84e4886ad8bc115611da8e2d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666750"
---
# <a name="calculated-measure-representation-tabular"></a><span data-ttu-id="b8d82-102">Представление вычисляемой меры (табличное)</span><span class="sxs-lookup"><span data-stu-id="b8d82-102">Calculated Measure Representation (Tabular)</span></span>
  <span data-ttu-id="b8d82-103">Вычисляемая мера — это именованное выражение DAX, вычисляемое при каждом использовании.</span><span class="sxs-lookup"><span data-stu-id="b8d82-103">A calculated measure is a named DAX expression evaluated every time it is used.</span></span>  
  
## <a name="calculated-measure-representation"></a><span data-ttu-id="b8d82-104">Представление вычисляемой меры</span><span class="sxs-lookup"><span data-stu-id="b8d82-104">Calculated Measure Representation</span></span>  
  
### <a name="calculated-measure-in-amo"></a><span data-ttu-id="b8d82-105">Вычисляемая мера в объектах AMO</span><span class="sxs-lookup"><span data-stu-id="b8d82-105">Calculated Measure in AMO</span></span>  
 <span data-ttu-id="b8d82-106">При использовании объектов AMO для управления вычисляемой мерой табличной модели существует соответствие «один к одному» между объектом вычисляемой меры и мерой, определенной в объекте <xref:Microsoft.AnalysisServices.Command> объекта <xref:Microsoft.AnalysisServices.MdxScript>.</span><span class="sxs-lookup"><span data-stu-id="b8d82-106">When using AMO to manage a tabular model calculated measure, there is a one-to-one match between the logical Calculated Measure object and a measure defined in a <xref:Microsoft.AnalysisServices.Command> object of the <xref:Microsoft.AnalysisServices.MdxScript> object.</span></span> <span data-ttu-id="b8d82-107">Каждая **Вычисляемая мера** определяется как `CREATE MEASURE` выражение внутри <xref:Microsoft.AnalysisServices.Command> объекта и отделяется точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="b8d82-107">Each **Calculated Measure** is defined as a `CREATE MEASURE` expression inside a <xref:Microsoft.AnalysisServices.Command> object and separated by a semicolon.</span></span> <span data-ttu-id="b8d82-108">Все вычисляемые меры в табличной модели соответствуют строке коллекции `CREATE MEASURE` в одном объекте команды из объекта <xref:Microsoft.AnalysisServices.MdxScript>.</span><span class="sxs-lookup"><span data-stu-id="b8d82-108">All calculated measures in a tabular model correspond to the collection `CREATE MEASURE` string in one command object in a <xref:Microsoft.AnalysisServices.MdxScript> object.</span></span> <span data-ttu-id="b8d82-109">Для каждой вычисляемой меры существует соответствие «один к одному» с объектом <xref:Microsoft.AnalysisServices.CalculationProperty>.</span><span class="sxs-lookup"><span data-stu-id="b8d82-109">For each calculated measure, there is one-to-one mapping with a <xref:Microsoft.AnalysisServices.CalculationProperty>.</span></span>  
  
 <span data-ttu-id="b8d82-110">В следующем фрагменте кода показано, как создать вычисляемую меру.</span><span class="sxs-lookup"><span data-stu-id="b8d82-110">The following code snippet shows how to create a calculated measure.</span></span>  
  
```  
  
private void addCalculatedMeasure(  
                   AMO.Cube modelCube  
                 , string cmTableName  
                 , string cmName  
                 , string newCalculatedMeasureExpression  
             )  
{  
    //Verify input requirements  
    if (string.IsNullOrEmpty(cmName) || string.IsNullOrWhiteSpace(cmName))  
    {  
        MessageBox.Show(String.Format("Calculated Measure name is not defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
    if (string.IsNullOrEmpty(newCalculatedMeasureExpression) || string.IsNullOrWhiteSpace(newCalculatedMeasureExpression))  
    {  
        MessageBox.Show(String.Format("Calculated Measure expression is not defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    StringBuilder measuresCommand = new StringBuilder();  
  
    AMO.MdxScript mdxScript = modelCube.MdxScripts["MdxScript"];  
  
    //ToDo: Verify if measure already exits and ask user what wants to do next  
  
    if (mdxScript.Commands.Count == 1)  
    {  
        measuresCommand.AppendLine("-------------------------------------------------------------");  
        measuresCommand.AppendLine("-- Tabular Model measures command (do not modify manually) --");  
        measuresCommand.AppendLine("-------------------------------------------------------------");  
        measuresCommand.AppendLine();  
        measuresCommand.AppendLine();  
        mdxScript.Commands.Add(new AMO.Command(measuresCommand.ToString()));  
  
    }  
    else  
    {  
        measuresCommand.Append(mdxScript.Commands[1].Text);  
    }  
    measuresCommand.AppendLine(string.Format("CREATE MEASURE '{0}'[{1}]={2};", cmTableName, cmName, newCalculatedMeasureExpression));  
  
    mdxScript.Commands[1].Text = measuresCommand.ToString();  
  
    if (!mdxScript.CalculationProperties.Contains(cmName))  
    {  
        AMO.CalculationProperty cp = new AMO.CalculationProperty(cmName, AMO.CalculationType.Member);  
        cp.FormatString = ""; // ToDo: Get formatting attributes for the member  
        cp.Visible = true;  
        mdxScript.CalculationProperties.Add(cp);  
    }  
  
    try  
    {  
        modelCube.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
        MessageBox.Show(String.Format("Calculated Measure successfully defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
    }  
    catch (AMO.OperationException amoOpXp)  
    {  
        MessageBox.Show(String.Format("Calculated Measure expression contains syntax errors, or references undefined or missspelled elements.\nError message: {0}", amoOpXp.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
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
  
  
