---
title: Предложение типов столбцов диалогового окна справочника по пользовательскому интерфейсу | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.suggestdatatypes.f1
ms.assetid: 8d5652e0-cf57-483f-828b-10f00c08418b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbca2a3186a58b1148eb9627825fdfddf334339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750079"
---
# <a name="suggest-column-types-dialog-box-ui-reference"></a><span data-ttu-id="2c18a-102">Предложение типов столбцов диалогового окна справочника по пользовательскому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="2c18a-102">Suggest Column Types Dialog Box UI Reference</span></span>
  <span data-ttu-id="2c18a-103">Диалоговое окно **Предлагаемые типы столбцов** используется для идентификации типа данных и длины столбцов в диспетчере соединений с неструктурированными файлами на основе содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="2c18a-103">Use the **Suggest Column Types** dialog box to identify the data type and length of columns in a Flat File Connection Manager based on a sampling of the file content.</span></span>  
  
 <span data-ttu-id="2c18a-104">Дополнительные сведения о типах данных, используемых в [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], см. в разделе [Типы данных служб Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2c18a-104">To learn more about the data types used by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2c18a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c18a-105">Options</span></span>  
 <span data-ttu-id="2c18a-106">**Число строк**</span><span class="sxs-lookup"><span data-stu-id="2c18a-106">**Number of rows**</span></span>  
 <span data-ttu-id="2c18a-107">Введите или выберите число строк в выборке, используемой алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="2c18a-107">Type or select the number of rows in the sample that the algorithm uses.</span></span>  
  
 <span data-ttu-id="2c18a-108">**Предложить наименьший тип целочисленных данных**</span><span class="sxs-lookup"><span data-stu-id="2c18a-108">**Suggest the smallest integer data type**</span></span>  
 <span data-ttu-id="2c18a-109">Снимите этот флажок, чтобы пропустить оценку.</span><span class="sxs-lookup"><span data-stu-id="2c18a-109">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="2c18a-110">Если он установлен, то определяет наименьший возможный целочисленный тип данных для столбцов, содержащих целочисленные данные.</span><span class="sxs-lookup"><span data-stu-id="2c18a-110">If selected, determines the smallest possible integer data type for columns that contain integral numeric data.</span></span>  
  
 <span data-ttu-id="2c18a-111">**Предложить наименьший тип данных с плавающей точкой**</span><span class="sxs-lookup"><span data-stu-id="2c18a-111">**Suggest the smallest real data type**</span></span>  
 <span data-ttu-id="2c18a-112">Снимите этот флажок, чтобы пропустить оценку.</span><span class="sxs-lookup"><span data-stu-id="2c18a-112">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="2c18a-113">Если он установлен, то определяет возможность использования вещественных данных наименьшего типа DT_R4 для столбцов, содержащих числовые данные вещественного типа.</span><span class="sxs-lookup"><span data-stu-id="2c18a-113">If selected, determines whether columns that contain real numeric data can use the smaller real data type, DT_R4.</span></span>  
  
 <span data-ttu-id="2c18a-114">**Определить логические столбцы по следующим значениям**</span><span class="sxs-lookup"><span data-stu-id="2c18a-114">**Identify Boolean columns using the following values**</span></span>  
 <span data-ttu-id="2c18a-115">Введите два значения, которые следует распознавать как логические значения true и false.</span><span class="sxs-lookup"><span data-stu-id="2c18a-115">Type the two values that you want to use as the Boolean values true and false.</span></span> <span data-ttu-id="2c18a-116">Значения должны быть разделены запятой, а первое из них соответствует True.</span><span class="sxs-lookup"><span data-stu-id="2c18a-116">The values must be separated by a comma, and the first value represents True.</span></span>  
  
 <span data-ttu-id="2c18a-117">**Заполнять столбцы строкового типа**</span><span class="sxs-lookup"><span data-stu-id="2c18a-117">**Pad string columns**</span></span>  
 <span data-ttu-id="2c18a-118">Выберите этот флажок, чтобы включить дополнение строк.</span><span class="sxs-lookup"><span data-stu-id="2c18a-118">Select this check box to enable string padding.</span></span>  
  
 <span data-ttu-id="2c18a-119">**Процент заполнения**</span><span class="sxs-lookup"><span data-stu-id="2c18a-119">**Percent padding**</span></span>  
 <span data-ttu-id="2c18a-120">Введите или выберите процент от длины столбцов, добавляемый к длине столбцов символьных типов данных.</span><span class="sxs-lookup"><span data-stu-id="2c18a-120">Type or select the percentage of the column lengths by which to increase the length of columns for character data types.</span></span> <span data-ttu-id="2c18a-121">Процент должен представлять собой целое число.</span><span class="sxs-lookup"><span data-stu-id="2c18a-121">The percentage must be an integer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c18a-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c18a-122">See Also</span></span>  
 <span data-ttu-id="2c18a-123">[Справочник по сообщениям об ошибках служб Integration Services](../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2c18a-123">[Integration Services Error and Message Reference](../integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="2c18a-124">Диспетчер подключений неструктурированных файлов</span><span class="sxs-lookup"><span data-stu-id="2c18a-124">Flat File Connection Manager</span></span>](file-connection-manager.md)  
  
  
