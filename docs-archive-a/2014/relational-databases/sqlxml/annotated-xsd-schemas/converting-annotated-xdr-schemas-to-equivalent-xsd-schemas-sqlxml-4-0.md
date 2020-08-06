---
title: Преобразование схем XDR с заметками в эквивалентные схемы XSD (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XDR schemas, converting schemas
- annotated XSD schemas, converting schemas
- XDR to XSD Converter tool [SQLXML]
- XDR schemas [SQLXML], converting
- converting annotated schemas
- mapping schema [SQLXML], conversions
- XSD schemas [SQLXML], converting schemas
ms.assetid: 151c94a8-66d3-4c46-a5ff-a22df456940a
author: rothja
ms.author: jroth
ms.openlocfilehash: c36eb17aacb61a47fad0f389de9a3c216202827d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665946"
---
# <a name="converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-40"></a><span data-ttu-id="d9251-102">Преобразование схем XDR с заметками в эквивалентные схемы XSD (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d9251-102">Converting Annotated XDR Schemas to Equivalent XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="d9251-103">Язык определения схем XML (XSD) пришел на смену языку определения схем с сокращенными XML-данными (XDR).</span><span class="sxs-lookup"><span data-stu-id="d9251-103">The XML Schema Definition (XSD) language is the successor to the XML-Data Reduced (XDR) schema definition language.</span></span> <span data-ttu-id="d9251-104">После ввода в действие поддержки XSD в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 предполагается, что новые схемы с заметками должны создаваться при помощи XSD.</span><span class="sxs-lookup"><span data-stu-id="d9251-104">With the introduction of XSD support in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, it is assumed that new annotated schemas are created using XSD.</span></span> <span data-ttu-id="d9251-105">SQLXML 4.0 включает средство преобразования XDR в XSD, которое создано для предоставления помощи пользователю в преобразовании существующих схем XDR с заметками в равнозначные схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="d9251-105">SQLXML 4.0 includes an XDR to XSD converter tool that is designed to help you convert your existing annotated XDR schemas to equivalent XSD schemas.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d9251-106">Это средство рекомендуется использовать только для преобразования схем XDR в XSD в целях их применения с SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="d9251-106">Use this tool only when you want to convert annotated XDR schemas to XSD for use with SQLXML 4.0.</span></span> <span data-ttu-id="d9251-107">Это не следует считать средством преобразования XDR в XSD общего назначения.</span><span class="sxs-lookup"><span data-stu-id="d9251-107">This is not a general purpose XDR to XSD converter tool.</span></span> <span data-ttu-id="d9251-108">Преобразованные схемы XSD могут не действовать в полном соответствии с исходными схемами XDR, будучи используемыми в других средах.</span><span class="sxs-lookup"><span data-stu-id="d9251-108">The converted XSD schemas may not behave the same as the original XDR schemas when used in other environments.</span></span>  
  
 <span data-ttu-id="d9251-109">Если входной XDR-файл задает в XML-декларации кодировку, она становится кодировкой создаваемого выходного XSD-файла.</span><span class="sxs-lookup"><span data-stu-id="d9251-109">If the input XDR file specifies the encoding within the XML declaration, this becomes the encoding of the XSD output file that is generated.</span></span>  
  
 <span data-ttu-id="d9251-110">Средство преобразования (Cvtschema.exe) установлено в папке Program Files\SQLXML 4.0\bin и исполняется в командной строке.</span><span class="sxs-lookup"><span data-stu-id="d9251-110">The converter tool (Cvtschema.exe) is installed in the Program Files\SQLXML 4.0\bin folder and is executed at the command prompt.</span></span>  
  
 <span data-ttu-id="d9251-111">Далее представлен общий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d9251-111">This is the general syntax:</span></span>  
  
```  
cvtschema XDRFileName, [-y], [-w] [-?]  
```  
  
 <span data-ttu-id="d9251-112">Где:</span><span class="sxs-lookup"><span data-stu-id="d9251-112">Where:</span></span>  
  
 <span data-ttu-id="d9251-113">XDRFileName</span><span class="sxs-lookup"><span data-stu-id="d9251-113">XDRFileName</span></span>  
 <span data-ttu-id="d9251-114">Имя XDR-файла, который необходимо преобразовать в XSD.</span><span class="sxs-lookup"><span data-stu-id="d9251-114">Is the name of the XDR file that is to be converted to XSD.</span></span> <span data-ttu-id="d9251-115">Это средство читает входной XDR-файл и создает выходной XSD-файл в текущем рабочем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d9251-115">The tool reads the input XDR file and creates an XSD output file in the current working directory.</span></span> <span data-ttu-id="d9251-116">Если текущий файл имеет расширение XDR или XML, выходной XSD-файл создается с тем же именем, но с расширением XSD.</span><span class="sxs-lookup"><span data-stu-id="d9251-116">If the input file has an .xdr or .xml extension, the output XSD file is created with the same name but with an .xsd extension.</span></span> <span data-ttu-id="d9251-117">Если расширение входного файла отличается от XDR или XML (или если расширение не указано), то выходной файл создается с тем же именем и к имени входного файла присоединяется расширение XSD.</span><span class="sxs-lookup"><span data-stu-id="d9251-117">If the input file extension is other than .xml or .xdr (or if the extension is missing), the output file is created with the same name and the .xsd extension is appended to the input file name.</span></span> <span data-ttu-id="d9251-118">Например, если именем входного XDR-файла является SampleFile.abc, то полученный XSD-файл сохраняется как SampleFile.abc.xsd.</span><span class="sxs-lookup"><span data-stu-id="d9251-118">For example, if the input XDR file name is SampleFile.abc, the resulting XSD is saved as SampleFile.abc.xsd.</span></span>  
  
 <span data-ttu-id="d9251-119">-y</span><span class="sxs-lookup"><span data-stu-id="d9251-119">-y</span></span>  
 <span data-ttu-id="d9251-120">Перезаписывает существующий XSD-файл XSD-файлом, созданным средством преобразования (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d9251-120">(Optional) Overwrites the existing XSD file with the XSD file that is generated by the converter tool.</span></span> <span data-ttu-id="d9251-121">Если этот флаг не указан, в этом средстве происходит вывод приглашения для пользователя, которое позволяет указать, следует ли переписать существующий XSD-файл и изменить имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="d9251-121">If the flag is not specified, the tool prompts you to specify whether you want to overwrite the existing XSD file and gives you the option to change the output file name.</span></span>  
  
 <span data-ttu-id="d9251-122">-w</span><span class="sxs-lookup"><span data-stu-id="d9251-122">-w</span></span>  
 <span data-ttu-id="d9251-123">Возвращает некритичные предупреждения, сформированные этим средством в процессе преобразования (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d9251-123">(Optional) Returns nonfatal warnings that are generated in the conversion process by the tool.</span></span> <span data-ttu-id="d9251-124">По умолчанию это средство отображает только сообщения, относящиеся к неустранимым ошибкам.</span><span class="sxs-lookup"><span data-stu-id="d9251-124">By default, the tool displays messages only for fatal errors.</span></span>  
  
 <span data-ttu-id="d9251-125">-?</span><span class="sxs-lookup"><span data-stu-id="d9251-125">-?</span></span>  
 <span data-ttu-id="d9251-126">Возвращает список параметров, которые можно указать при помощи `cvtschema` вместе с пояснением.</span><span class="sxs-lookup"><span data-stu-id="d9251-126">Returns a list of options that you can specify with `cvtschema`, along with an explanation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9251-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9251-127">See Also</span></span>  
 <span data-ttu-id="d9251-128">[Сопоставление типов данных XSD с типами данных XPath &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="d9251-128">[Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="d9251-129">Аннотации XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d9251-129">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml-annotated-xsd-schemas-using/xsd-annotations-sqlxml-4-0.md)  
  
  
