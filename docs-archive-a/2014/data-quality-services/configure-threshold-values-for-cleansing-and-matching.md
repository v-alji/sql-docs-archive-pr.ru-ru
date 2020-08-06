---
title: Настройка пороговых значений для очистки и сопоставления | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.general.f1
helpviewer_keywords:
- cleansing,threshold value
- cleansing threshold values
- matching,threshold value
ms.assetid: d2305409-7115-45a4-8f60-1213c0a47368
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0faf64e96468a3a9aac0de12d3ec3acbb1e1ed85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728722"
---
# <a name="configure-threshold-values-for-cleansing-and-matching"></a><span data-ttu-id="47689-102">Настройка пороговых значений для очистки и сопоставления</span><span class="sxs-lookup"><span data-stu-id="47689-102">Configure Threshold Values for Cleansing and Matching</span></span>
  <span data-ttu-id="47689-103">В этом разделе описывается настройка пороговых значений, которые будут использоваться в ходе операций автоматизированной очистки и сопоставления в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="47689-103">This topic describes how to configure threshold values that will be used during the computer-assisted cleansing and matching activities in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="47689-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="47689-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="47689-105">безопасность</span><span class="sxs-lookup"><span data-stu-id="47689-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="47689-106">Permissions</span><span class="sxs-lookup"><span data-stu-id="47689-106">Permissions</span></span>  
 <span data-ttu-id="47689-107">Для настройки этих пороговых значений необходимо иметь роль dqs_administrator в базе данных DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="47689-107">You must have the dqs_administrator role on the DQS_MAIN database to configure these threshold values.</span></span>  
  
##  <a name="configuring-the-threshold-values"></a><a name="Configure"></a> <span data-ttu-id="47689-108">Настройка пороговых значений</span><span class="sxs-lookup"><span data-stu-id="47689-108">Configuring the Threshold Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="47689-109">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="47689-109">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="47689-110">На главном экране клиента [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] нажмите кнопку **Конфигурация**.</span><span class="sxs-lookup"><span data-stu-id="47689-110">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="47689-111">Затем перейдите на вкладку **Общие параметры** . На этой вкладке можно указать пороговые значения для очистки, а также соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="47689-111">Next, click the **General Settings** tab. This tab enables you to specify threshold values for cleansing as well as matching activities.</span></span>  
  
4.  <span data-ttu-id="47689-112">Пороговые значения для операции очистки задаются в следующих полях в области **Интерактивная очистка** :</span><span class="sxs-lookup"><span data-stu-id="47689-112">To specify threshold values for the cleansing activity, specify appropriate values in the following boxes under the **Interactive Cleansing** area:</span></span>  
  
    -   <span data-ttu-id="47689-113">**Минимальный показатель для предложений**. Минимальная оценка или уровень достоверности, которые будут использоваться службами DQS для предложения значений на замену в ходе автоматизированного процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="47689-113">**Min score for suggestions**: The minimum score or the confidence level that will be used by DQS for suggesting replacements for a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="47689-114">Введите значение в десятичной нотации для соответствующего значения в процентах.</span><span class="sxs-lookup"><span data-stu-id="47689-114">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="47689-115">Например, введите 0,75 для 75 %.</span><span class="sxs-lookup"><span data-stu-id="47689-115">For example, type 0.75 for 75%.</span></span> <span data-ttu-id="47689-116">Это значение должно быть меньше или равно значению, указанному в поле **Минимальная оценка для автоматического исправления** .</span><span class="sxs-lookup"><span data-stu-id="47689-116">This value should be less than or equal to the value specified in the **Min score for auto corrections** box.</span></span> <span data-ttu-id="47689-117">Значение по умолчанию — 0,7.</span><span class="sxs-lookup"><span data-stu-id="47689-117">The default value is 0.7.</span></span>  
  
    -   <span data-ttu-id="47689-118">**Минимальный показатель для автоматического исправления**. Минимальная оценка или уровень достоверности, которые будут использоваться службами DQS для автоматического исправления значений в ходе автоматизированного процесса очистки.</span><span class="sxs-lookup"><span data-stu-id="47689-118">**Min score for auto corrections**: The minimum score or the confidence level that will be used by DQS for automatically correcting a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="47689-119">Введите значение в десятичной нотации для соответствующего значения в процентах.</span><span class="sxs-lookup"><span data-stu-id="47689-119">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="47689-120">Например, введите 0,9 для 90 %.</span><span class="sxs-lookup"><span data-stu-id="47689-120">For example, enter 0.9 for 90%.</span></span> <span data-ttu-id="47689-121">Значение по умолчанию — 0,8.</span><span class="sxs-lookup"><span data-stu-id="47689-121">The default value is 0.8.</span></span>  
  
5.  <span data-ttu-id="47689-122">Пороговое значение для операции сопоставления задается в поле **Минимальная оценка для записи** в области **Сопоставление** .</span><span class="sxs-lookup"><span data-stu-id="47689-122">To specify threshold value for the matching activity, specify a value in the **Min record score** box under the **Matching** area.</span></span> <span data-ttu-id="47689-123">Это значение задает минимальную оценку для записи, которая позволяет считать ее соответствующей другой записи.</span><span class="sxs-lookup"><span data-stu-id="47689-123">This value signifies the minimum score for a record to be considered as a match for another record.</span></span> <span data-ttu-id="47689-124">Значение по умолчанию — 80 %.</span><span class="sxs-lookup"><span data-stu-id="47689-124">The default value is 80%.</span></span>  
  
6.  <span data-ttu-id="47689-125">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="47689-125">Click **Close**.</span></span>  
  
  
