---
title: Диалоговое окно редактора преобразования «Очистка DQS» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssdqs.designer.cleansing.f1
- SQL12.SSDQS.DESIGNER.DQCONNECTION.F1
ms.assetid: 07e79641-71ee-45d0-a9ba-ed6f9f68f333
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e97cd138bb17ce3cfe476496e5bc576875728224
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655278"
---
# <a name="dqs-cleansing-transformation-editor-dialog-box"></a><span data-ttu-id="8395e-102">Диалоговое окно редактора преобразования «Очистка DQS»</span><span class="sxs-lookup"><span data-stu-id="8395e-102">DQS Cleansing Transformation Editor Dialog Box</span></span>
  <span data-ttu-id="8395e-103">Диалоговое окно **Редактор преобразования "Очистка DQS"** служит для исправления данных с помощью служб Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="8395e-103">Use the **DQS Cleansing Transformation Editor** dialog box to correct data using Data Quality Services (DQS).</span></span> <span data-ttu-id="8395e-104">Дополнительные сведения см. в статье [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-104">For more information, see [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="8395e-105">Дополнительные сведения об этом преобразовании см. в разделе [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-105">To learn more about the transformation, see [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="8395e-106">**Выбор действия**</span><span class="sxs-lookup"><span data-stu-id="8395e-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="8395e-107">Открытие редактора преобразования «Очистка DQS»</span><span class="sxs-lookup"><span data-stu-id="8395e-107">Open the DQS Cleansing Transformation Editor</span></span>](#open)  
  
-   [<span data-ttu-id="8395e-108">Задание параметров на вкладке «Диспетчер соединений»</span><span class="sxs-lookup"><span data-stu-id="8395e-108">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="8395e-109">Задание параметров на вкладке «Сопоставление»</span><span class="sxs-lookup"><span data-stu-id="8395e-109">Set options on the Mapping tab</span></span>](#mapping)  
  
-   [<span data-ttu-id="8395e-110">Задание параметров на вкладке «Дополнительно»</span><span class="sxs-lookup"><span data-stu-id="8395e-110">Set options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="8395e-111">Задание параметров в диалоговом окне диспетчера соединений «Очистка DQS»</span><span class="sxs-lookup"><span data-stu-id="8395e-111">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>](#manager)  
  
##  <a name="open-the-dqs-cleansing-transformation-editor"></a><a name="open"></a><span data-ttu-id="8395e-112">Открытие редактора преобразования «Очистка DQS»</span><span class="sxs-lookup"><span data-stu-id="8395e-112">Open the DQS Cleansing Transformation Editor</span></span>  
  
1.  <span data-ttu-id="8395e-113">Добавьте преобразование «Очистка DQS» в пакет служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8395e-113">Add the DQS Cleansing Transformation to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="8395e-114">Щелкните правой кнопкой мыши компонент и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8395e-114">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a><span data-ttu-id="8395e-115">Задание параметров на вкладке «Диспетчер соединений»</span><span class="sxs-lookup"><span data-stu-id="8395e-115">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="8395e-116">**Диспетчер соединений DQS**</span><span class="sxs-lookup"><span data-stu-id="8395e-116">**Data quality connection manager**</span></span>  
 <span data-ttu-id="8395e-117">Выберите существующий диспетчер соединений DQS из списка или создайте новое соединение, нажав кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8395e-117">Select an existing DQS connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="8395e-118">**Создать**</span><span class="sxs-lookup"><span data-stu-id="8395e-118">**New**</span></span>  
 <span data-ttu-id="8395e-119">Создайте новый диспетчер соединений с помощью диалогового окна **Диспетчер соединений "Очистка DQS"** .</span><span class="sxs-lookup"><span data-stu-id="8395e-119">Create a new connection manager by using the **DQS Cleansing Connection Manager** dialog box.</span></span> <span data-ttu-id="8395e-120">См. раздел [Задание параметров в диалоговом окне Диспетчер соединений «Очистка DQS»](#manager) .</span><span class="sxs-lookup"><span data-stu-id="8395e-120">See [Set the options in the DQS Cleansing Connection Manager dialog box](#manager)</span></span>  
  
 <span data-ttu-id="8395e-121">**База знаний DQS**</span><span class="sxs-lookup"><span data-stu-id="8395e-121">**Data Quality Knowledge Base**</span></span>  
 <span data-ttu-id="8395e-122">Выберите существующую базу знаний DQS для подключенного источника данных.</span><span class="sxs-lookup"><span data-stu-id="8395e-122">Select an existing DQS knowledge base for the connected data source.</span></span> <span data-ttu-id="8395e-123">Дополнительные сведения о базе знаний DQS см. в разделе [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-123">For more information about the DQS knowledge base, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="8395e-124">**Шифровать соединение**</span><span class="sxs-lookup"><span data-stu-id="8395e-124">**Encrypt connection**</span></span>  
 <span data-ttu-id="8395e-125">Укажите, следует ли шифровать соединение, чтобы зашифровать обмен данными между сервером DQS и [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8395e-125">specify whether to encrypt the connection, in order to encrypt the data transfer between the DQS Server and [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8395e-126">**Доступные домены**</span><span class="sxs-lookup"><span data-stu-id="8395e-126">**Available domains**</span></span>  
 <span data-ttu-id="8395e-127">Выводит список доступных доменов для выбранной базы знаний.</span><span class="sxs-lookup"><span data-stu-id="8395e-127">Lists the available domains for the selected knowledge base.</span></span> <span data-ttu-id="8395e-128">Существует два типа доменов: одиночные и составные домены, которые содержат несколько одиночных доменов.</span><span class="sxs-lookup"><span data-stu-id="8395e-128">There are two types of domains: single domains, and composite domains that contain two or more single domains.</span></span>  
  
 <span data-ttu-id="8395e-129">Дополнительные сведения о сопоставлении столбцов с составными доменами см. в разделе [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-129">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="8395e-130">Дополнительные сведения о доменах см. в разделе [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-130">For more information about domains, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="8395e-131">**Настройка вывода ошибок**</span><span class="sxs-lookup"><span data-stu-id="8395e-131">**Configure Error Output**</span></span>  
 <span data-ttu-id="8395e-132">Укажите, как следует обрабатывать ошибки уровня строк.</span><span class="sxs-lookup"><span data-stu-id="8395e-132">Specify how to handle row-level errors.</span></span> <span data-ttu-id="8395e-133">Ошибки могут возникать при корректировке в ходе преобразования данных из подключенного источника данных из-за неожиданных значений данных или ограничений проверки.</span><span class="sxs-lookup"><span data-stu-id="8395e-133">Errors can occur when the transformation corrects data from the connected data source, due to unexpected data values or validation constraints.</span></span>  
  
 <span data-ttu-id="8395e-134">Допустимыми являются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8395e-134">The following are the valid values:</span></span>  
  
-   <span data-ttu-id="8395e-135">**Сбой компонента**указывает, что преобразование выполнить не удалось, а входные данные не были вставлены в базу данных служб Data Quality Services.</span><span class="sxs-lookup"><span data-stu-id="8395e-135">**Fail Component**, which indicates that the transformation fails and the input data is not inserted into the Data Quality Services database.</span></span> <span data-ttu-id="8395e-136">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8395e-136">This is the default value.</span></span>  
  
-   <span data-ttu-id="8395e-137">**Перенаправить строку**указывает, что входные данные не вставляются в базу данных служб Data Quality Services, а перенаправляются в поток вывода ошибок.</span><span class="sxs-lookup"><span data-stu-id="8395e-137">**Redirect Row**, which indicates that the input data is not inserted into the Data Quality Services database and is redirected to the error output.</span></span>  
  
##  <a name="set-options-on-the-mapping-tab"></a><a name="mapping"></a><span data-ttu-id="8395e-138">Задание параметров на вкладке «Сопоставление»</span><span class="sxs-lookup"><span data-stu-id="8395e-138">Set options on the Mapping tab</span></span>  
 <span data-ttu-id="8395e-139">Дополнительные сведения о сопоставлении столбцов с составными доменами см. в разделе [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-139">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="8395e-140">**Доступные входные столбцы**</span><span class="sxs-lookup"><span data-stu-id="8395e-140">**Available Input Columns**</span></span>  
 <span data-ttu-id="8395e-141">Выводит список столбцов из подключенного источника данных.</span><span class="sxs-lookup"><span data-stu-id="8395e-141">Lists the columns from the connected data source.</span></span> <span data-ttu-id="8395e-142">Выберите один или несколько столбцов, содержащих данные, которые нужно исправить.</span><span class="sxs-lookup"><span data-stu-id="8395e-142">Select one or more columns that contain data that you want to correct.</span></span>  
  
 <span data-ttu-id="8395e-143">**Входной столбец**</span><span class="sxs-lookup"><span data-stu-id="8395e-143">**Input Column**</span></span>  
 <span data-ttu-id="8395e-144">Показывает входной столбец, выбранный в области **Доступные входные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="8395e-144">Lists an input column that you selected in the **Available Input Columns** area.</span></span>  
  
 <span data-ttu-id="8395e-145">**Домен**</span><span class="sxs-lookup"><span data-stu-id="8395e-145">**Domain**</span></span>  
 <span data-ttu-id="8395e-146">Выберите домен, сопоставляемый с входным столбцом.</span><span class="sxs-lookup"><span data-stu-id="8395e-146">Select a domain to map to the input column.</span></span>  
  
 <span data-ttu-id="8395e-147">**Псевдоним источника**</span><span class="sxs-lookup"><span data-stu-id="8395e-147">**Source Alias**</span></span>  
 <span data-ttu-id="8395e-148">Выводит исходный столбец, содержащий исходное значение столбца.</span><span class="sxs-lookup"><span data-stu-id="8395e-148">Lists the source column that contains the original column value.</span></span>  
  
 <span data-ttu-id="8395e-149">Щелкните в этом поле, чтобы изменить имя столбца.</span><span class="sxs-lookup"><span data-stu-id="8395e-149">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="8395e-150">**Псевдоним вывода**</span><span class="sxs-lookup"><span data-stu-id="8395e-150">**Output Alias**</span></span>  
 <span data-ttu-id="8395e-151">Показывает столбец, который выводится **преобразованием "Очистка DQS"**.</span><span class="sxs-lookup"><span data-stu-id="8395e-151">Lists the column that is outputted by the **DQS Cleansing Transformation**.</span></span> <span data-ttu-id="8395e-152">Это столбец содержит исходное значение столбца или исправленное значение.</span><span class="sxs-lookup"><span data-stu-id="8395e-152">The column contains the original column value or the corrected value.</span></span>  
  
 <span data-ttu-id="8395e-153">Щелкните в этом поле, чтобы изменить имя столбца.</span><span class="sxs-lookup"><span data-stu-id="8395e-153">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="8395e-154">**Псевдоним состояния**</span><span class="sxs-lookup"><span data-stu-id="8395e-154">**Status Alias**</span></span>  
 <span data-ttu-id="8395e-155">Показывает столбец, содержащий сведения о состоянии для исправленных данных.</span><span class="sxs-lookup"><span data-stu-id="8395e-155">Lists the column that contains status information for the corrected data.</span></span> <span data-ttu-id="8395e-156">Щелкните в этом поле, чтобы изменить имя столбца.</span><span class="sxs-lookup"><span data-stu-id="8395e-156">Click in the field to modify the column name.</span></span>  
  
##  <a name="set-options-on-the-advanced-tab"></a><a name="advanced"></a><span data-ttu-id="8395e-157">Задание параметров на вкладке «Дополнительно»</span><span class="sxs-lookup"><span data-stu-id="8395e-157">Set options on the Advanced tab</span></span>  
 <span data-ttu-id="8395e-158">**Стандартный вывод**</span><span class="sxs-lookup"><span data-stu-id="8395e-158">**Standardize output**</span></span>  
 <span data-ttu-id="8395e-159">Показывает, будут ли данные выводиться в стандартном формате с учетом выходного формата, определенного для доменов.</span><span class="sxs-lookup"><span data-stu-id="8395e-159">Indicate whether to output the data in the standardized format based on the output format defined for domains.</span></span> <span data-ttu-id="8395e-160">Дополнительные сведения о стандартном формате см. в разделе [Очистка данных](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-160">For more information about standardized format, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="8395e-161">**Уровень**</span><span class="sxs-lookup"><span data-stu-id="8395e-161">**Confidence**</span></span>  
 <span data-ttu-id="8395e-162">Показывает, включается ли уровень достоверности для исправленных данных.</span><span class="sxs-lookup"><span data-stu-id="8395e-162">Indicate whether to include the confidence level for corrected data.</span></span> <span data-ttu-id="8395e-163">Уровень достоверности определяет степень уверенности в правильности изменений, выполненных или рекомендуемых службами DQS.</span><span class="sxs-lookup"><span data-stu-id="8395e-163">The confidence level indicates the extend of certainty of DQS for the correction or suggestion.</span></span> <span data-ttu-id="8395e-164">Дополнительные сведения об уровнях достоверности см. в разделе [Очистка данных](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-164">For more information about confidence levels, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="8395e-165">**Причина**</span><span class="sxs-lookup"><span data-stu-id="8395e-165">**Reason**</span></span>  
 <span data-ttu-id="8395e-166">Указывает, включается ли причина исправления данных.</span><span class="sxs-lookup"><span data-stu-id="8395e-166">Indicate whether to include the reason for the data correction.</span></span>  
  
 <span data-ttu-id="8395e-167">**Добавленные данные**</span><span class="sxs-lookup"><span data-stu-id="8395e-167">**Appended Data**</span></span>  
 <span data-ttu-id="8395e-168">Укажите, следует ли выводить дополнительные данные, полученные от существующего поставщика ссылочных данных.</span><span class="sxs-lookup"><span data-stu-id="8395e-168">Indicate whether to output additional data that is received from an existing reference data provider.</span></span> <span data-ttu-id="8395e-169">Дополнительные сведения см. в статье [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-169">For more information, see [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span></span>  
  
 <span data-ttu-id="8395e-170">**Схема добавленных данных**</span><span class="sxs-lookup"><span data-stu-id="8395e-170">**Appended Data Schema**</span></span>  
 <span data-ttu-id="8395e-171">Укажите, следует ли выводить схему данных.</span><span class="sxs-lookup"><span data-stu-id="8395e-171">Indicate whether to output the data schema.</span></span> <span data-ttu-id="8395e-172">Дополнительные сведения см. [в разделе Подключение домена или составного домена к ссылочным данным](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-172">For more information, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
##  <a name="set-the-options-in-the-dqs-cleansing-connection-manager-dialog-box"></a><a name="manager"></a><span data-ttu-id="8395e-173">Задание параметров в диалоговом окне диспетчера соединений «Очистка DQS»</span><span class="sxs-lookup"><span data-stu-id="8395e-173">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>  
 <span data-ttu-id="8395e-174">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="8395e-174">**Server name**</span></span>  
 <span data-ttu-id="8395e-175">Выберите или введите имя сервера DQS, к которому нужно подключиться.</span><span class="sxs-lookup"><span data-stu-id="8395e-175">Select or type the name of the DQS server that you want to connect to.</span></span> <span data-ttu-id="8395e-176">Дополнительные сведения об этом сервере см. в разделе [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span><span class="sxs-lookup"><span data-stu-id="8395e-176">For more information about the server, see [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span></span>  
  
 <span data-ttu-id="8395e-177">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="8395e-177">**Test Connection**</span></span>  
 <span data-ttu-id="8395e-178">Нажмите, чтобы убедиться в работоспособности выбранного соединения.</span><span class="sxs-lookup"><span data-stu-id="8395e-178">Click to confirm that the connection that you specified is viable.</span></span>  
  
 <span data-ttu-id="8395e-179">Также можно открыть диалоговое окно **Диспетчер соединений «Очистка DQS»** из области соединений, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8395e-179">You can also open the **DQS Cleansing Connection Manager** dialog box from the connections area, by doing the following:</span></span>  
  
1.  <span data-ttu-id="8395e-180">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте существующий проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] или создайте новый.</span><span class="sxs-lookup"><span data-stu-id="8395e-180">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or create a new one.</span></span>  
  
2.  <span data-ttu-id="8395e-181">Щелкните правой кнопкой мыши в области соединений, выберите команду **Создать соединение**, а затем выберите пункт **DQS**.</span><span class="sxs-lookup"><span data-stu-id="8395e-181">Right-click in the connections area, click **New Connection**, and then click **DQS**.</span></span>  
  
3.  <span data-ttu-id="8395e-182">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8395e-182">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8395e-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="8395e-183">See Also</span></span>  
 [<span data-ttu-id="8395e-184">Применение правил качества данных к источнику данных</span><span class="sxs-lookup"><span data-stu-id="8395e-184">Apply Data Quality Rules to Data Source</span></span>](data-flow/transformations/apply-data-quality-rules-to-data-source.md)  
  
  
