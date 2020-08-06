---
title: Представление связи (табличное) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 86a5eff8-4e07-444b-ac15-5695f09aa105
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b0a9ef87aa696292a1011a9b8d829a595eaeec2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730921"
---
# <a name="relationship-representation-tabular"></a><span data-ttu-id="ef24d-102">Представление связи (табличное)</span><span class="sxs-lookup"><span data-stu-id="ef24d-102">Relationship Representation (Tabular)</span></span>
  <span data-ttu-id="ef24d-103">Связь — это соединение между двумя таблицами данных.</span><span class="sxs-lookup"><span data-stu-id="ef24d-103">A relationship is a connection between two tables of data.</span></span> <span data-ttu-id="ef24d-104">Связь определяет, как должны соотноситься данные в двух таблицах.</span><span class="sxs-lookup"><span data-stu-id="ef24d-104">The relationship establishes how the data in the two tables should be correlated.</span></span>  
  
 <span data-ttu-id="ef24d-105">См. раздел [Relationship Representation (Tabular)](relationship-representation-tabular.md) с подробным объяснением создания представления связи и управления им.</span><span class="sxs-lookup"><span data-stu-id="ef24d-105">See [Relationship Representation (Tabular)](relationship-representation-tabular.md) for a detailed explanation on how to create and manipulate the relationship representation.</span></span>  
  
## <a name="relationship-representation"></a><span data-ttu-id="ef24d-106">Представление связи</span><span class="sxs-lookup"><span data-stu-id="ef24d-106">Relationship Representation</span></span>  
 <span data-ttu-id="ef24d-107">В табличных моделях между двумя таблицами можно определить несколько связей.</span><span class="sxs-lookup"><span data-stu-id="ef24d-107">In tabular models, multiple relationships can be defined between two tables.</span></span> <span data-ttu-id="ef24d-108">Если между двумя таблицами определено несколько связей, то в качестве связи по умолчанию для модели можно определить только одну из них. Она называется активной связью, а все остальные — неактивными.</span><span class="sxs-lookup"><span data-stu-id="ef24d-108">When multiple relationships, between two tables, are defined only one can be defined as the default relationship for the model and it is named as the Active relationship; all other relationships are named as Inactive.</span></span>  
  
### <a name="relationship-in-amo"></a><span data-ttu-id="ef24d-109">Связь в объектах AMO</span><span class="sxs-lookup"><span data-stu-id="ef24d-109">Relationship in AMO</span></span>  
 <span data-ttu-id="ef24d-110">С точки зрения объектов AMO все неактивные связи представляются в виде сопоставления «один к одному» с <xref:Microsoft.AnalysisServices.Relationship> и никакие другие объекты AMO не требуются. Для активной связи также существуют другие требования и необходимо сопоставление с <xref:Microsoft.AnalysisServices.ReferenceMeasureGroupDimension>.</span><span class="sxs-lookup"><span data-stu-id="ef24d-110">In terms of AMO objects all inactive relationships have a representation of a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Relationship> and no other main AMO objects are required; for the active relationship other requirements exist and a mapping to the <xref:Microsoft.AnalysisServices.ReferenceMeasureGroupDimension> is also required.</span></span>  
  
 <span data-ttu-id="ef24d-111">В следующих фрагментах кода показано, как создавать связи в табличных моделях, как активировать связи и как определять первичный ключ в таблице (за исключением RowNumber).</span><span class="sxs-lookup"><span data-stu-id="ef24d-111">The following code snippets show how to create a relationship in Tabular models, how to activate a relationship and how to define a primary key in a table (other than "RowNumber").</span></span> <span data-ttu-id="ef24d-112">Чтобы создать активную связь, необходимо определить первичный ключ в таблице первичного ключа PKTableName (одна из сторон связи). В представленном образце создается первичный ключ на столбце PKColumnName, если в нем не определен первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="ef24d-112">To create an active relationship a primary key need to be defined in the primary key table - PKTableName - of the relationship (the one side of the relationship), the sample shown here creates the primary key on the PKColumnName if no primary key is defined in this column.</span></span> <span data-ttu-id="ef24d-113">Неактивные связи можно создавать без первичного ключа в столбце первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="ef24d-113">Inactive relationships can be created without the need of having a primary key on the primary key column.</span></span>  
  
```cs
private Boolean createRelationship(string PKTableName, string PKColumnName, string MVTableName, string MVColumnName, AMO.Database tabularDb, string cubeName, Boolean forceActive)  
{  
    //verify input parameters  
    if(     string.IsNullOrEmpty(PKTableName) || string.IsNullOrWhiteSpace(PKTableName)  
        ||  string.IsNullOrEmpty(PKColumnName) || string.IsNullOrWhiteSpace(PKColumnName)  
        ||  string.IsNullOrEmpty(MVTableName) || string.IsNullOrWhiteSpace(MVTableName)  
        ||  string.IsNullOrEmpty(MVColumnName) || string.IsNullOrWhiteSpace(MVColumnName)  
        ||  (tabularDb == null)  
        ) return false;  
    if(!tabularDb.Dimensions.ContainsName(PKTableName) || !tabularDb.Dimensions.ContainsName(MVTableName)) return false;  
    if(!tabularDb.Dimensions[PKTableName].Attributes.ContainsName(PKColumnName) || !tabularDb.Dimensions[MVTableName].Attributes.ContainsName(MVColumnName)) return false;  
  
    //Verify underlying cube structure  
    if (!tabularDb.Cubes[cubeName].Dimensions.ContainsName(PKTableName) || !tabularDb.Cubes[cubeName].Dimensions.ContainsName(MVTableName)) return false; //Should return an exception!!  
    if (!tabularDb.Cubes[cubeName].MeasureGroups.ContainsName(PKTableName) || !tabularDb.Cubes[cubeName].MeasureGroups.ContainsName(MVTableName)) return false; //Should return an exception!!  
  
    //Make sure PKTableName.PKColumnName  is set as PK ==> <attribute>.usage == AMO.AttributeUsage.Key  
    if (tabularDb.Dimensions[PKTableName].Attributes[PKColumnName].Usage != AMO.AttributeUsage.Key)  
    {  
        //... here we are 'fixing', if there is an issue with PKTableName.PKColumnName not being the PK of the table  
        setPKColumn(tabularDb, PKTableName, PKColumnName);  
    }  
  
    //Terminology note:   
    // -   the many side of the relationship is named the From end in AMO  
    // -   the PK side of the relationship in named the To end in AMO  
    //  
    //It seems relationships flow FROM the many side of the relationship in TO the primary key side of the relationship in AMO  
    //              
    //Verify the relationship we are creating does not exist, regardless of name.  
    //if it exists, return true (no need to recreate it)  
    //if it doesn't exists it will be created after this validation  
  
    //   
    foreach (AMO.Relationship currentRelationship in tabularDb.Dimensions[MVTableName].Relationships)  
    {  
        if ((currentRelationship.FromRelationshipEnd.Attributes[0].AttributeID == MVColumnName)  
            && (currentRelationship.ToRelationshipEnd.DimensionID == PKTableName)  
            && (currentRelationship.ToRelationshipEnd.Attributes[0].AttributeID == PKColumnName))  
        {  
            if (forceActive)  
            {  
                //Activate the relationship   
                setActiveRelationship(tabularDb.Cubes[cubeName], MVTableName, MVColumnName, PKTableName, currentRelationship.ID);  
                //Update server with changes made here  
                tabularDb.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.CreateOrReplace);  
                tabularDb.Cubes[cubeName].MeasureGroups[MVTableName].Process(AMO.ProcessType.ProcessFull);  
            }  
            return true;  
        }  
    }  
  
    //A relationship like the one to be created does not exist; ergo, let's create it:  
  
    //First, create the INACTIVE relationship definitions in the MultipleValues end of the relationship  
    #region define unique name for relationship  
    string newRelationshipID = string.Format("Relationship _{0}_{1}_ to _{2}_{3}_", MVTableName, MVColumnName, PKTableName, PKColumnName);  
    int rootLen = newRelationshipID.Length;  
    for (int i = 0; tabularDb.Dimensions[MVTableName].Relationships.Contains(newRelationshipID); )  
    {  
        newRelationshipID = string.Format("{0}_{1,8:0}", newRelationshipID.Substring(0, rootLen), i);  
    }  
    #endregion  
    AMO.Relationship newRelationship = tabularDb.Dimensions[MVTableName].Relationships.Add(newRelationshipID);  
  
    newRelationship.FromRelationshipEnd.DimensionID = MVTableName;  
    newRelationship.FromRelationshipEnd.Attributes.Add(MVColumnName);  
    newRelationship.FromRelationshipEnd.Multiplicity = AMO.Multiplicity.Many;  
    newRelationship.FromRelationshipEnd.Role = string.Empty;  
    newRelationship.ToRelationshipEnd.DimensionID = PKTableName;  
    newRelationship.ToRelationshipEnd.Attributes.Add(PKColumnName);  
    newRelationship.ToRelationshipEnd.Multiplicity = AMO.Multiplicity.One;  
    newRelationship.ToRelationshipEnd.Role = string.Empty;  
  
    //Update server to create relationship  
    tabularDb.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    tabularDb.Dimensions[MVTableName].Process(AMO.ProcessType.ProcessDefault);  
    tabularDb.Dimensions[PKTableName].Process(AMO.ProcessType.ProcessDefault);  
  
    //Second, activate the relationship if relationship is to be set as the active relationship: 'forceActive==true'  
    //... an inactive relationship needs only to be created on the dimensions object  
    if (forceActive)  
    {  
        //Activate the relationship   
        setActiveRelationship(tabularDb.Cubes[cubeName], MVTableName, MVColumnName, PKTableName, newRelationshipID);                  
    }             
    return true;  
}  
  
private void setActiveRelationship(AMO.Cube currentCube, string MVTableName, string MVColumnName, string PKTableName, string relationshipID)  
{  
    if (!currentCube.MeasureGroups.Contains(MVTableName))  
    {  
        throw new AMO.AmoException(string.Format("Cube [{0}] does not contain Measure Group [{1}]\nError activating relationship [{2}]: [{4}] <--- [{1}].[{3}]"  
                                                , currentCube.Name, MVTableName, relationshipID, MVColumnName, PKTableName));  
    }  
    AMO.MeasureGroup currentMG = currentCube.MeasureGroups[MVTableName];  
  
    if (!currentMG.Dimensions.Contains(PKTableName))  
    {  
        AMO.ReferenceMeasureGroupDimension newReferenceMGDim = new AMO.ReferenceMeasureGroupDimension();  
        newReferenceMGDim.CubeDimensionID = PKTableName;  
        newReferenceMGDim.IntermediateCubeDimensionID = MVTableName;  
        newReferenceMGDim.IntermediateGranularityAttributeID = MVColumnName;  
        newReferenceMGDim.Materialization = AMO.ReferenceDimensionMaterialization.Regular;  
        newReferenceMGDim.RelationshipID = relationshipID;  
        foreach (AMO.CubeAttribute PKAttribute in currentCube.Dimensions[PKTableName].Attributes)  
        {  
            AMO.MeasureGroupAttribute PKMGAttribute = newReferenceMGDim.Attributes.Add(PKAttribute.AttributeID);  
            OleDbType PKMGAttributeType = PKAttribute.Attribute.KeyColumns[0].DataType;  
            PKMGAttribute.KeyColumns.Add(new AMO.DataItem(PKTableName, PKAttribute.AttributeID, PKMGAttributeType));  
            PKMGAttribute.KeyColumns[0].Source = new AMO.ColumnBinding(PKTableName, PKAttribute.AttributeID);  
        }  
        currentMG.Dimensions.Add(newReferenceMGDim);  
  
        AMO.ValidationErrorCollection errors = new AMO.ValidationErrorCollection();  
  
        newReferenceMGDim.Validate(errors, true);  
        if (errors.Count > 0)  
        {  
            StringBuilder errorMessages = new StringBuilder();  
            foreach (AMO.ValidationError err in errors)  
            {  
                errorMessages.AppendLine(string.Format("At {2}: # {0} : {1}", err.ErrorCode, err.FullErrorText, err.Source));  
            }  
            throw new AMO.AmoException(errorMessages.ToString());  
        }  
        //Update changes in the server  
        currentMG.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.CreateOrReplace);  
    }  
    else  
    {  
        AMO.ReferenceMeasureGroupDimension currentReferenceMGDim = (AMO.ReferenceMeasureGroupDimension)currentMG.Dimensions[PKTableName];  
        currentReferenceMGDim.RelationshipID = relationshipID;  
        currentReferenceMGDim.IntermediateGranularityAttributeID = MVColumnName;  
        //Update changes in the server  
        currentMG.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    }  
    //process MG to activate relationship  
    currentMG.Process(AMO.ProcessType.ProcessFull);  
  
}  
  
private void setPKColumn(AMO.Database tabularDb, string PKTableName, string PKColumnName)  
{  
        //Find all 'unwanted' Key attributes, remove their Key definitions and include the attributes in the ["RowNumber"].AttributeRelationships  
        foreach (AMO.DimensionAttribute currentDimAttribute in tabularDb.Dimensions[PKTableName].Attributes)  
        {  
            if ((currentDimAttribute.Usage == AMO.AttributeUsage.Key) && (currentDimAttribute.ID != PKColumnName))  
            {  
                currentDimAttribute.Usage = AMO.AttributeUsage.Regular;  
                if (currentDimAttribute.ID != "RowNumber")  
                {  
                    currentDimAttribute.KeyColumns[0].NullProcessing = AMO.NullProcessing.Preserve;  
                    currentDimAttribute.AttributeRelationships.Clear();  
                    if (!tabularDb.Dimensions[PKTableName].Attributes["RowNumber"].AttributeRelationships.ContainsName(currentDimAttribute.ID))  
                    {  
                        AMO.DimensionAttribute currentAttribute = tabularDb.Dimensions[PKTableName].Attributes[currentDimAttribute.ID];  
                        AMO.AttributeRelationship currentAttributeRelationship = tabularDb.Dimensions[PKTableName].Attributes["RowNumber"].AttributeRelationships.Add(currentAttribute.ID);  
                        currentAttributeRelationship.OverrideBehavior = AMO.OverrideBehavior.None;  
                    }  
                    tabularDb.Dimensions[PKTableName].Attributes["RowNumber"].AttributeRelationships[currentDimAttribute.ID].Cardinality = AMO.Cardinality.Many;  
                }  
            }  
        }  
  
        //Remove PKColumnName from ["RowNumber"].AttributeRelationships  
        int PKAtribRelationshipPosition = tabularDb.Dimensions[PKTableName].Attributes["RowNumber"].AttributeRelationships.IndexOf(PKColumnName);  
        if (PKAtribRelationshipPosition != -1) tabularDb.Dimensions[PKTableName].Attributes["RowNumber"].AttributeRelationships.RemoveAt(PKAtribRelationshipPosition, true);  
  
        //Define PKColumnName as Key and add ["RowNumber"] to PKColumnName.AttributeRelationships with cardinality of One  
        tabularDb.Dimensions[PKTableName].Attributes[PKColumnName].Usage = AMO.AttributeUsage.Key;  
        tabularDb.Dimensions[PKTableName].Attributes[PKColumnName].KeyColumns[0].NullProcessing = AMO.NullProcessing.Error;  
        if (!tabularDb.Dimensions[PKTableName].Attributes[PKColumnName].AttributeRelationships.ContainsName("RowNumber"))  
        {  
            AMO.DimensionAttribute currentAttribute = tabularDb.Dimensions[PKTableName].Attributes["RowNumber"];  
            AMO.AttributeRelationship currentAttributeRelationship = tabularDb.Dimensions[PKTableName].Attributes[PKColumnName].AttributeRelationships.Add(currentAttribute.ID);  
            currentAttributeRelationship.OverrideBehavior = AMO.OverrideBehavior.None;  
        }  
        tabularDb.Dimensions[PKTableName].Attributes[PKColumnName].AttributeRelationships["RowNumber"].Cardinality = AMO.Cardinality.One;  
  
        //Update Table before going creating the relationship  
        tabularDb.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
        tabularDb.Dimensions[PKTableName].Process(AMO.ProcessType.ProcessDefault);                
  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="ef24d-114">Образец AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="ef24d-114">AMO2Tabular sample</span></span>  
 <span data-ttu-id="ef24d-115">Однако, чтобы получить основные сведения об использовании объектов AMO для создания представлений связи и управления ими, ознакомьтесь с исходным кодом примера преобразования объектов AMO в табличную модель.</span><span class="sxs-lookup"><span data-stu-id="ef24d-115">However, to have an understanding on how to use AMO to create and manipulate relationship representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="ef24d-116">Этот образец доступен на сайте Codeplex.</span><span class="sxs-lookup"><span data-stu-id="ef24d-116">The sample is available at Codeplex.</span></span> <span data-ttu-id="ef24d-117">Важное примечание о коде. Код предоставляется только для иллюстрации логических концепций, поясняемых в этом разделе. Его не следует использовать в рабочей среде или для других целей, за исключением учебных.</span><span class="sxs-lookup"><span data-stu-id="ef24d-117">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
