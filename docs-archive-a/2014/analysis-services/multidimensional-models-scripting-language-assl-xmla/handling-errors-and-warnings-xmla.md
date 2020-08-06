---
title: Обработка ошибок и предупреждений (XMLA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- inline errors [XMLA]
- SOAP faults [XML for Analysis]
- XML for Analysis, errors
- faults [XML for Analysis]
- messages [XML for Analysis]
- XMLA, errors
- warnings [XML for Analysis]
- inline warnings [XMLA]
ms.assetid: ab895282-098d-468e-9460-032598961f45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07b88d800237e5b4b06af0c1ff11cbd0af846600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658488"
---
# <a name="handling-errors-and-warnings-xmla"></a><span data-ttu-id="42516-102">Обработка ошибок и предупреждений (XMLA)</span><span class="sxs-lookup"><span data-stu-id="42516-102">Handling Errors and Warnings (XMLA)</span></span>
  <span data-ttu-id="42516-103">Обработка ошибок необходима, если вызов метода [обнаружения](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) или [выполнения](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) XML для аналитики (XMLA) не выполняется, выполняется успешно, но создает ошибки или предупреждения либо выполняется успешно, но возвращает результаты, содержащие ошибки.</span><span class="sxs-lookup"><span data-stu-id="42516-103">Error handling is required when an XML for Analysis (XMLA) [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) or [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method call does not run, runs successfully but generates errors or warnings, or runs successfully but returns results that contain errors.</span></span>  
  
|<span data-ttu-id="42516-104">Ошибка</span><span class="sxs-lookup"><span data-stu-id="42516-104">Error</span></span>|<span data-ttu-id="42516-105">Отчеты</span><span class="sxs-lookup"><span data-stu-id="42516-105">Reporting</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="42516-106">Вызов метода XMLA не запускается</span><span class="sxs-lookup"><span data-stu-id="42516-106">The XMLA method call does not run</span></span>|[!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="42516-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] возвращает сообщение об ошибке SOAP, содержащее сведения о сбое.</span><span class="sxs-lookup"><span data-stu-id="42516-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns a SOAP fault message that contains the details of the failure.</span></span><br /><br /> <span data-ttu-id="42516-108">Дополнительные сведения см. в разделе [Обработка ошибок SOAP](#handling_soap_faults).</span><span class="sxs-lookup"><span data-stu-id="42516-108">For more information, see the section, [Handling SOAP Faults](#handling_soap_faults).</span></span>|  
|<span data-ttu-id="42516-109">Ошибки или предупреждения при успешном вызове метода</span><span class="sxs-lookup"><span data-stu-id="42516-109">Errors or warnings on a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="42516-110">содержит элемент [Error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) или [warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) для каждой ошибки или предупреждения соответственно в свойстве [Messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) [корневого](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) элемента, который содержит результаты вызова метода.</span><span class="sxs-lookup"><span data-stu-id="42516-110">includes an [error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) or [warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) element for each error or warning, respectively, in the [Messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) property of the [root](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) element that contains the results of the method call.</span></span><br /><br /> <span data-ttu-id="42516-111">Дополнительные сведения см. в разделе [Обработка ошибок и предупреждений](#handling_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="42516-111">For more information, see the section, [Handling Errors and Warnings](#handling_errors_and_warnings).</span></span>|  
|<span data-ttu-id="42516-112">Ошибки в результате при успешном вызове метода</span><span class="sxs-lookup"><span data-stu-id="42516-112">Errors in the result for a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="42516-113">включает встроенный `error` `warning` элемент или для ошибки или предупреждения соответственно в соответствующую [ячейку](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) или элемент [Row](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) результатов вызова метода.</span><span class="sxs-lookup"><span data-stu-id="42516-113">includes an inline `error` or `warning` element for the error or warning, respectively, within the appropriate [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) or [row](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) element of the results of the method call.</span></span><br /><br /> <span data-ttu-id="42516-114">Дополнительные сведения см. в разделе [Обработка встроенных ошибок и предупреждений](#handling_inline_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="42516-114">For more information, see the section, [Handling Inline Errors and Warnings](#handling_inline_errors_and_warnings).</span></span>|  
  
##  <a name="handling-soap-faults"></a><a name="handling_soap_faults"></a><span data-ttu-id="42516-115">Обработка ошибок SOAP</span><span class="sxs-lookup"><span data-stu-id="42516-115">Handling SOAP Faults</span></span>  
 <span data-ttu-id="42516-116">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] возвращают сбой SOAP при возникновении следующих ситуаций.</span><span class="sxs-lookup"><span data-stu-id="42516-116">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns a SOAP fault when the following situations occur:</span></span>  
  
-   <span data-ttu-id="42516-117">Сообщение SOAP, содержащее метод XMLA, имеет неправильный формат, или экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не может провести проверку его правильности.</span><span class="sxs-lookup"><span data-stu-id="42516-117">The SOAP message that contains the XMLA method was not well-formed or could not be validated by the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="42516-118">Произошла ошибка связи или другая ошибка, касающаяся сообщения SOAP, содержащего метод XMLA.</span><span class="sxs-lookup"><span data-stu-id="42516-118">A communications or other error occurred involving the SOAP message that contains the XMLA method.</span></span>  
  
-   <span data-ttu-id="42516-119">Метод XMLA не запустился в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42516-119">The XMLA method did not run on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="42516-120">Коды сбоев SOAP для XMLA начинаются с «XMLForAnalysis», далее следуют точка и шестнадцатеричный код результата HRESULT.</span><span class="sxs-lookup"><span data-stu-id="42516-120">The SOAP fault codes for XMLstartA start with "XMLForAnalysis", followed by a period and the hexadecimal HRESULT result code.</span></span> <span data-ttu-id="42516-121">Например, код ошибки `0x80000005` форматируется как `XMLForAnalysis.0x80000005`.</span><span class="sxs-lookup"><span data-stu-id="42516-121">For example, an error code of "`0x80000005`" is formatted as "`XMLForAnalysis.0x80000005`".</span></span> <span data-ttu-id="42516-122">Дополнительные сведения о формате сбоев SOAP см. в разделе «Soap Fault» (Сбои Soap) документа «W3C Simple Object Access Protocol (SOAP) 1.1».</span><span class="sxs-lookup"><span data-stu-id="42516-122">For more information about the SOAP fault format, see Soap Fault in the W3C Simple Object Access Protocol (SOAP) 1.1.</span></span>  
  
### <a name="fault-code-information"></a><span data-ttu-id="42516-123">Сведения о кодах ошибок</span><span class="sxs-lookup"><span data-stu-id="42516-123">Fault Code Information</span></span>  
 <span data-ttu-id="42516-124">В следующей таблице приведены сведения о кодах ошибок XMLA, которые содержатся в разделе подробностей ответа SOAP.</span><span class="sxs-lookup"><span data-stu-id="42516-124">The following table shows the XMLA fault code information that is contained in the detail section of the SOAP response.</span></span> <span data-ttu-id="42516-125">Столбцы являются атрибутами ошибки в разделе подробностей сбоя SOAP.</span><span class="sxs-lookup"><span data-stu-id="42516-125">The columns are the attributes of an error in the detail section of a SOAP fault.</span></span>  
  
|<span data-ttu-id="42516-126">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="42516-126">Column name</span></span>|<span data-ttu-id="42516-127">Type</span><span class="sxs-lookup"><span data-stu-id="42516-127">Type</span></span>|<span data-ttu-id="42516-128">Описание</span><span class="sxs-lookup"><span data-stu-id="42516-128">Description</span></span>|<span data-ttu-id="42516-129">Допустимое значение NULL<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="42516-129">Null allowed<sup>1</sup></span></span>|  
|-----------------|----------|-----------------|------------------------------|  
|`ErrorCode`|`UnsignedInt`|<span data-ttu-id="42516-130">Код возврата, указывающий успешное или неудачное выполнение метода.</span><span class="sxs-lookup"><span data-stu-id="42516-130">Return code that indicates the success or failure of the method.</span></span> <span data-ttu-id="42516-131">Шестнадцатеричное значение необходимо преобразовать в значение `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="42516-131">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="42516-132">Нет</span><span class="sxs-lookup"><span data-stu-id="42516-132">No</span></span>|  
|`WarningCode`|`UnsignedInt`|<span data-ttu-id="42516-133">Код возврата, указывающий состояние предупреждения.</span><span class="sxs-lookup"><span data-stu-id="42516-133">Return code that indicates a warning condition.</span></span> <span data-ttu-id="42516-134">Шестнадцатеричное значение необходимо преобразовать в значение `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="42516-134">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="42516-135">Да</span><span class="sxs-lookup"><span data-stu-id="42516-135">Yes</span></span>|  
|`Description`|`String`|<span data-ttu-id="42516-136">Текст ошибки или предупреждения и описание, возвращаемые компонентом, сформировавшим ошибку.</span><span class="sxs-lookup"><span data-stu-id="42516-136">Error or warning text and description returned by the component that generated the error.</span></span>|<span data-ttu-id="42516-137">Да</span><span class="sxs-lookup"><span data-stu-id="42516-137">Yes</span></span>|  
|`Source`|`String`|<span data-ttu-id="42516-138">Имя компонента, сформировавшего ошибку или предупреждение.</span><span class="sxs-lookup"><span data-stu-id="42516-138">Name of the component that generated the error or warning.</span></span>|<span data-ttu-id="42516-139">Да</span><span class="sxs-lookup"><span data-stu-id="42516-139">Yes</span></span>|  
|`HelpFile`|`String`|<span data-ttu-id="42516-140">Путь или URL-адрес к файлу или разделу справки, в котором описывается ошибка или предупреждение.</span><span class="sxs-lookup"><span data-stu-id="42516-140">Path or URL to the Help file or topic that describes the error or warning.</span></span>|<span data-ttu-id="42516-141">Да</span><span class="sxs-lookup"><span data-stu-id="42516-141">Yes</span></span>|  
  
 <span data-ttu-id="42516-142"><sup>1</sup> указывает, являются ли данные обязательными и должны ли они быть возвращены, а также данные являются необязательными, если столбец не применяется.</span><span class="sxs-lookup"><span data-stu-id="42516-142"><sup>1</sup> Indicates whether the data is required and must be returned, or whether the data is optional and a null string is allowed if the column does not apply.</span></span>  
  
 <span data-ttu-id="42516-143">Далее приведен пример сбоя SOAP, произошедшего при неудачном завершении вызова метода:</span><span class="sxs-lookup"><span data-stu-id="42516-143">The following is an example of a SOAP fault that occurred when a method call failed:</span></span>  
  
```  
<?xml version="1.0"?>  
   <SOAP-ENV:Envelope  
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
   SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
      <SOAP-ENV:Fault>  
         <faultcode>XMLAnalysisError.0x80000005</faultcode>  
         <faultstring>The XML for Analysis provider encountered an error.</faultstring>  
         <faultactor>XML for Analysis Provider</faultactor>  
         <detail>  
<Error  
ErrorCode="2147483653"  
Description="An unexpected error has occurred."  
Source="XML for Analysis Provider"  
HelpFile="" />  
         </detail>  
      </SOAP-ENV:Fault>  
</SOAP-ENV:Envelope>  
```  
  
##  <a name="handling-errors-and-warnings"></a><a name="handling_errors_and_warnings"></a><span data-ttu-id="42516-144">Обработка ошибок и предупреждений</span><span class="sxs-lookup"><span data-stu-id="42516-144">Handling Errors and Warnings</span></span>  
 <span data-ttu-id="42516-145">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] возвращают свойство `Messages` в элементе `root` для команды в случае возникновения следующих ситуаций после запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="42516-145">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns the `Messages` property in the `root` element for a command if the following situations occur after that command runs:</span></span>  
  
-   <span data-ttu-id="42516-146">Сам метод выполнен успешно, но ошибка возникла в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] после успешного вызова метода.</span><span class="sxs-lookup"><span data-stu-id="42516-146">The method itself did not fail, but a failure occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the method call succeeded.</span></span>  
  
-   <span data-ttu-id="42516-147">Экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] возвращает предупреждение при успешном выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="42516-147">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance returns a warning when the command is successful.</span></span>  
  
 <span data-ttu-id="42516-148">Свойство `Messages` следует за всеми остальными свойствами, содержащимися в элементе `root`; оно может содержать один или несколько элементов `Message`.</span><span class="sxs-lookup"><span data-stu-id="42516-148">The `Messages` property follows all other properties that are contained by the `root` element, and can contain one or more `Message` elements.</span></span> <span data-ttu-id="42516-149">В свою очередь, каждый элемент `Message` может содержать один из элементов `error` или `warning`, описывающий ошибки или предупреждения соответственно, возникшие в связи с указанной командой.</span><span class="sxs-lookup"><span data-stu-id="42516-149">In turn, each `Message` element can contain either a single `error` or `warning` element describing any errors or warnings, respectively, that occurred for the specified command.</span></span>  
  
 <span data-ttu-id="42516-150">Дополнительные сведения об ошибках и предупреждениях, содержащихся в `Messages` свойстве, см. в разделе [messages &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="42516-150">For more information about errors and warnings that are contained in the `Messages` property, see [Messages Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span></span>  
  
### <a name="handling-errors-during-serialization"></a><span data-ttu-id="42516-151">Обработка ошибок во время сериализации</span><span class="sxs-lookup"><span data-stu-id="42516-151">Handling Errors During Serialization</span></span>  
 <span data-ttu-id="42516-152">Если ошибка возникает после того, как [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] экземпляр уже начал сериализацию выходных данных успешно выполненной команды, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] возвращает элемент [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) в другом пространстве имен в момент возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="42516-152">If an error occurs after the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance has already begun serializing the output of a successfully run command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) element in a different namespace at the point of the error.</span></span> <span data-ttu-id="42516-153">Затем экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] закрывает все открытые элементы с тем, чтобы XML-документ, отправляемый клиенту, был допустимым.</span><span class="sxs-lookup"><span data-stu-id="42516-153">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance then closes all open elements so that the XML document sent to the client is a valid document.</span></span> <span data-ttu-id="42516-154">Экземпляр возвращает также элемент `Messages`, содержащий описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="42516-154">The instance also returns a `Messages` element that contains the description of the error.</span></span>  
  
##  <a name="handling-inline-errors-and-warnings"></a><a name="handling_inline_errors_and_warnings"></a><span data-ttu-id="42516-155">Обработка встроенных ошибок и предупреждений</span><span class="sxs-lookup"><span data-stu-id="42516-155">Handling Inline Errors and Warnings</span></span>  
 <span data-ttu-id="42516-156">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] возвращают встроенный элемент `error` или `warning` для команды, если сам метод XMLA выполнен успешно, а ошибка, характерная для элемента данных в результатах, возвращаемых методом, возникла в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] после успешного вызова метода XMLA.</span><span class="sxs-lookup"><span data-stu-id="42516-156">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an inline `error` or `warning` for a command if the XMLA method itself did not fail, but an error specific to a data element in the results returned by the method occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the XMLA method call succeeded.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="42516-157">предоставляет встроенные `error` элементы и, `warning` Если возникают проблемы, связанные с ячейкой или другими данными, содержащимися в `root` элементе с использованием типа данных [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) , например ошибка безопасности или ошибка форматирования для ячейки.</span><span class="sxs-lookup"><span data-stu-id="42516-157">supplies inline `error` and `warning` elements if issues specific to a cell or to other data that are contained within a `root` element using the [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) data type occur, such as a security error or formatting error for a cell.</span></span> <span data-ttu-id="42516-158">В этих случаях службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] возвращают элемент `error` или `warning` в элементе `Cell` или `row`, который содержит ошибку или предупреждение соответственно.</span><span class="sxs-lookup"><span data-stu-id="42516-158">In these cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an `error` or `warning` element in the `Cell` or `row` element that contains the error or warning, respectively.</span></span>  
  
 <span data-ttu-id="42516-159">В следующем примере показан результирующий набор, содержащий ошибку в наборе строк, возвращенном из `Execute` метода с помощью команды [инструкции](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="42516-159">The following example illustrates a result set that contains an error in the rowset returned from an `Execute` method using the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command.</span></span>  
  
```  
<return>  
   ...  
   <root>  
      ...  
      <CellData>  
      ...  
         <Cell CellOrdinal="10">  
            <Value>  
               <Error>  
                  <ErrorCode>2148497527</ErrorCode>   
                  <Description>Security Error.</Description>   
               </Error>  
            </Value>  
         </Cell>  
      </CellData>  
      ...  
   </root>  
   ...  
</return>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42516-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="42516-160">See Also</span></span>  
 [<span data-ttu-id="42516-161">Разработка с использованием XMLA в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="42516-161">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
