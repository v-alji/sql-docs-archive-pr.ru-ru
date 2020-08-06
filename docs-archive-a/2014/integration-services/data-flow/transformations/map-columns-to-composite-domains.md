---
title: Сопоставление столбцов с составными доменами | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9422412-8a3d-45ae-af7f-072c902a09ba
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a665b2096579c9da35a1b69be46c4ba6103610f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667312"
---
# <a name="map-columns-to-composite-domains"></a><span data-ttu-id="79f0b-102">Сопоставление столбцов с составными доменами</span><span class="sxs-lookup"><span data-stu-id="79f0b-102">Map Columns to Composite Domains</span></span>
  <span data-ttu-id="79f0b-103">Составной домен состоит из нескольких одиночных доменов.</span><span class="sxs-lookup"><span data-stu-id="79f0b-103">A composite domain consists of two or more single domains.</span></span> <span data-ttu-id="79f0b-104">Домену можно сопоставить несколько столбцов или один столбец с разделенными значениями.</span><span class="sxs-lookup"><span data-stu-id="79f0b-104">You can map multiple columns to the domain, or you can map a single column with delimited values to the domain.</span></span>  
  
 <span data-ttu-id="79f0b-105">При наличии нескольких столбцов столбец должен сопоставляться с каждым доменом из составного домена, чтобы применить правила составного домена к очистке данных.</span><span class="sxs-lookup"><span data-stu-id="79f0b-105">When you have multiple columns, you must map a column to each single domain in the composite domain to apply the composite domain rules to data cleansing.</span></span> <span data-ttu-id="79f0b-106">Отдельные домены, содержащиеся в составном домене, выбираются в клиенте DQS.</span><span class="sxs-lookup"><span data-stu-id="79f0b-106">You select the single domains contained in the composite domain, in the Data Quality Client.</span></span> <span data-ttu-id="79f0b-107">Дополнительные сведения см. в статье [Создание составного домена](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="79f0b-107">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
 <span data-ttu-id="79f0b-108">При наличии одного столбца с разделенными значениями его необходимо сопоставить с составным доменом.</span><span class="sxs-lookup"><span data-stu-id="79f0b-108">When you have a single column with delimited values, you must map the single column to the composite domain.</span></span> <span data-ttu-id="79f0b-109">Значение должны быть приведены в том же порядке, в котором отдельные домены находятся в составном домене.</span><span class="sxs-lookup"><span data-stu-id="79f0b-109">The values must appear in the same order as the single domains appear in the composite domain.</span></span> <span data-ttu-id="79f0b-110">В источнике данных должен использоваться такой же разделитель, который используется для синтаксического анализа значений составного домена.</span><span class="sxs-lookup"><span data-stu-id="79f0b-110">The delimiter in the data source must match the delimiter that is used to parse the composite domain values.</span></span> <span data-ttu-id="79f0b-111">Разделитель и другие свойства составного домена задаются в клиенте DQS.</span><span class="sxs-lookup"><span data-stu-id="79f0b-111">You select the delimiter for the composite domain, as well as set other properties, in the Data Quality Client.</span></span> <span data-ttu-id="79f0b-112">Дополнительные сведения см. в статье [Создание составного домена](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="79f0b-112">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
### <a name="to-map-multiple-columns-to-a-composite-domain"></a><span data-ttu-id="79f0b-113">Сопоставление нескольких столбцов с составным доменом</span><span class="sxs-lookup"><span data-stu-id="79f0b-113">To map multiple columns to a composite domain</span></span>  
  
1.  <span data-ttu-id="79f0b-114">Щелкните правой кнопкой мыши преобразование "Очистка DQS" и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="79f0b-114">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="79f0b-115">На вкладке **Диспетчер соединений** удостоверьтесь, что составной домен есть в списке доступных доменов.</span><span class="sxs-lookup"><span data-stu-id="79f0b-115">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="79f0b-116">На вкладке **Сопоставление** выберите столбцы в области **Доступные входные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="79f0b-116">On the **Mapping** tab, select the columns in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="79f0b-117">Для каждого столбца из поля **Входной столбец** выберите отдельный домен в поле **Домен** .</span><span class="sxs-lookup"><span data-stu-id="79f0b-117">For each column listed in the **Input Column** field, select a single domain in the **Domain** field.</span></span> <span data-ttu-id="79f0b-118">Выбирайте только отдельные домены, входящие в составной домен.</span><span class="sxs-lookup"><span data-stu-id="79f0b-118">Select only single domains that are in the composite domain.</span></span>  
  
5.  <span data-ttu-id="79f0b-119">Внесите необходимые изменения в имена, отображенные в полях **Псевдоним источника**, **Псевдоним вывода**и **Псевдоним состояния** .</span><span class="sxs-lookup"><span data-stu-id="79f0b-119">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="79f0b-120">Задайте необходимые свойства на вкладке **Дополнительно** . Дополнительные сведения об этих свойствах см. в разделе [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="79f0b-120">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
### <a name="to-map-a-column-with-delimited-values-to-a-composite-domain"></a><span data-ttu-id="79f0b-121">Сопоставление столбца с разделенными значениями с составным доменом</span><span class="sxs-lookup"><span data-stu-id="79f0b-121">To map a column with delimited values to a composite domain</span></span>  
  
1.  <span data-ttu-id="79f0b-122">Щелкните правой кнопкой мыши преобразование "Очистка DQS" и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="79f0b-122">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="79f0b-123">На вкладке **Диспетчер соединений** удостоверьтесь, что составной домен есть в списке доступных доменов.</span><span class="sxs-lookup"><span data-stu-id="79f0b-123">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="79f0b-124">На вкладке **Сопоставление** выберите столбец в области **Доступные входные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="79f0b-124">On the **Mapping** tab, select the column in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="79f0b-125">Для столбца из поля **Входной столбец** выберите составной домен в поле **Домен** .</span><span class="sxs-lookup"><span data-stu-id="79f0b-125">For the column listed in the **Input Column** field, select the composite domain in the **Domain** field.</span></span>  
  
5.  <span data-ttu-id="79f0b-126">Внесите необходимые изменения в имена, отображенные в полях **Псевдоним источника**, **Псевдоним вывода**и **Псевдоним состояния** .</span><span class="sxs-lookup"><span data-stu-id="79f0b-126">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="79f0b-127">Задайте необходимые свойства на вкладке **Дополнительно** . Дополнительные сведения об этих свойствах см. в разделе [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="79f0b-127">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f0b-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="79f0b-128">See Also</span></span>  
 [<span data-ttu-id="79f0b-129">Преобразование "Очистка DQS"</span><span class="sxs-lookup"><span data-stu-id="79f0b-129">DQS Cleansing Transformation</span></span>](dqs-cleansing-transformation.md)  
  
  
