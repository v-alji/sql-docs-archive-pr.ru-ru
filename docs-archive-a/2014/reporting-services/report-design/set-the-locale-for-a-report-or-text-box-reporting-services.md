---
title: Задание локали для отчета или текстового поля (службы Reporting Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- locales [Reporting Services]
ms.assetid: df115b01-184b-47f0-b5ec-0ad965ff9bee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb2b0cbd6e4216138520834216358ee455729386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656151"
---
# <a name="set-the-locale-for-a-report-or-text-box-reporting-services"></a><span data-ttu-id="c7358-102">Задание локали для отчета или текстового поля (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="c7358-102">Set the Locale for a Report or Text Box (Reporting Services)</span></span>
  <span data-ttu-id="c7358-103">Свойство **Язык** отчета или текстового поля содержит параметр локали, определяющий форматы по умолчанию для отображения данных отчета, зависящих от языка и региона, например даты, валюты или числовых значений.</span><span class="sxs-lookup"><span data-stu-id="c7358-103">The **Language** property on a report or a text box contains the locale setting, which determines the default formats for displaying report data that differ by language and region, for example, date, currency, or number values.</span></span> <span data-ttu-id="c7358-104">Свойство **Язык** текстового поля переопределяет свойство **Язык** отчета.</span><span class="sxs-lookup"><span data-stu-id="c7358-104">The **Language** property on a text box overrides the **Language** property on the report.</span></span> <span data-ttu-id="c7358-105">Если для свойства **Язык**не указано значения, то службы Reporting Services используют языковой стандарт операционной системы сервера отчетов для опубликованных отчетов и локаль компьютера, на котором создается отчет, при предварительном просмотре отчета.</span><span class="sxs-lookup"><span data-stu-id="c7358-105">If no value is specified for **Language**, Reporting Services uses the locale of the operating system on the report server for published reports or of the report authoring computer for report preview.</span></span>  
  
 <span data-ttu-id="c7358-106">При работе с отчетами в формате HTML значение свойства **Язык** по умолчанию можно переопределить и использовать язык, указанный в заголовке HTTP клиентского браузера, использовав встроенное поле User!Language в выражении для свойства **Язык** отчета или текстового поля.</span><span class="sxs-lookup"><span data-stu-id="c7358-106">For HTML reports, you can override the default **Language** value and use the language specified by the HTTP header of the browser client by using the built-in field User!Language in an expression for the **Language** property of a report or a text box.</span></span>  
  
 <span data-ttu-id="c7358-107">Также свойство **Язык** для отчета можно указать в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="c7358-107">You can also specify the **Language** property for a report in a URL.</span></span> <span data-ttu-id="c7358-108">Дополнительные сведения см. в статье [Задание языка для параметров отчета в URL-адресе](../set-the-language-for-report-parameters-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="c7358-108">For more information, see [Set the Language for Report Parameters in a URL](../set-the-language-for-report-parameters-in-a-url.md).</span></span>  
  
### <a name="to-set-the-locale-for-a-report"></a><span data-ttu-id="c7358-109">Назначение локали для отчета</span><span class="sxs-lookup"><span data-stu-id="c7358-109">To set the locale for a report</span></span>  
  
1.  <span data-ttu-id="c7358-110">В режиме конструктора щелкните за пределами области конструктора отчета, чтобы выбрать отчет.</span><span class="sxs-lookup"><span data-stu-id="c7358-110">In Design view, click outside the report design surface to select the report.</span></span>  
  
2.  <span data-ttu-id="c7358-111">В панели свойств для свойства **Язык** введите или выберите язык, который нужно использовать для отчета.</span><span class="sxs-lookup"><span data-stu-id="c7358-111">In the Properties pane, for the **Language** property, type or select the language that you want to use for the report.</span></span>  
  
### <a name="to-set-the-locale-for-a-text-box"></a><span data-ttu-id="c7358-112">Назначение локали для текстового поля</span><span class="sxs-lookup"><span data-stu-id="c7358-112">To set the locale for a text box</span></span>  
  
1.  <span data-ttu-id="c7358-113">В режиме конструктора выберите текстовое поле, к которому необходимо применить локаль.</span><span class="sxs-lookup"><span data-stu-id="c7358-113">In Design view, select the text box to which you want to apply the locale settings.</span></span>  
  
2.  <span data-ttu-id="c7358-114">В панели свойств выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c7358-114">In the Properties pane, do the following:</span></span>  
  
    -   <span data-ttu-id="c7358-115">Для свойства **Календарь** введите или выберите календарь, который необходимо использовать для обозначения дат.</span><span class="sxs-lookup"><span data-stu-id="c7358-115">For the **Calendar** property, type or select the calendar that you want to use for dates.</span></span>  
  
    -   <span data-ttu-id="c7358-116">Для свойства **Направление** введите или выберите направление письма.</span><span class="sxs-lookup"><span data-stu-id="c7358-116">For the **Direction** property, type or select the direction in which the text is written.</span></span>  
  
    -   <span data-ttu-id="c7358-117">Для свойства **Язык** введите или выберите язык, который необходимо использовать для текстового поля.</span><span class="sxs-lookup"><span data-stu-id="c7358-117">For the **Language** property, type or select the language that you want to use for the text box.</span></span> <span data-ttu-id="c7358-118">Это значение переопределяет свойство **Язык** отчета.</span><span class="sxs-lookup"><span data-stu-id="c7358-118">This value overrides the **Language** property for the Report.</span></span>  
  
    -   <span data-ttu-id="c7358-119">Для свойства **NumeralLanguage** введите или выберите формат для чисел в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="c7358-119">For the **NumeralLanguage** property, type or select the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="c7358-120">Для свойства **NumeralVariant** введите или выберите вариант формата для чисел в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="c7358-120">For the **NumeralVariant** property, type or select the variant of the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="c7358-121">Для свойства **UnicodeBiDi** выберите уровень внедрения разнонаправленного текста в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="c7358-121">For the **UnicodeBiDi** property, select the level of bidirectional embedding to use in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7358-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7358-122">See Also</span></span>  
 [<span data-ttu-id="c7358-123">Использование выражений в отчетах (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="c7358-123">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)  
  
  
