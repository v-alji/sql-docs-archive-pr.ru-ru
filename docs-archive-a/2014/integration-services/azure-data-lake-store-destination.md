---
title: Цель Azure Data Lake Store | Документы Майкрософт
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSDEST.F1
- SQL11.DTS.DESIGNER.AFPADLSDEST.F1
ms.assetid: d0e86032-2a6b-48b2-898f-e94328474fde
author: yualan
ms.author: chugu
ms.openlocfilehash: 14248d14b6a944250c33a19c8cf83ab0e0330587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740229"
---
# <a name="azure-data-lake-store-destination"></a><span data-ttu-id="c9cc5-102">Цель Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="c9cc5-102">Azure Data Lake Store Destination</span></span>
  <span data-ttu-id="c9cc5-103">Компонент **Цель Azure Data Lake Store** позволяет пакету служб SSIS записывать данные в Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-103">The **Azure Data Lake Store Destination** component enables an SSIS package to write data to an Azure Data Lake Store.</span></span> <span data-ttu-id="c9cc5-104">Поддерживаются следующие форматы файлов: текст, AVRO и ORC.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-104">The supported file formats are: Text, Avro and ORC.</span></span> 
  
## <a name="configure-the-azure-data-lake-store-destination"></a><span data-ttu-id="c9cc5-105">Настройка цели Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="c9cc5-105">Configure the Azure Data Lake Store Destination</span></span> 

1. <span data-ttu-id="c9cc5-106">Перетащите компонент **Цель Azure Data Lake Store** в конструктор потока данных и дважды щелкните его, чтобы открыть редактор.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-106">Drag-drop **Azure Data Lake Store Destination** to the data flow designer and double-click it to see the editor.</span></span>  

2.  <span data-ttu-id="c9cc5-107">В поле **Диспетчер подключений Azure Data Lake Store** укажите существующий диспетчер подключений Azure Data Lake Store или создайте новый диспетчер, который ссылается на службу Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="c9cc5-108">В поле **Путь к файлу** укажите имя файла, в который требуется записать данные.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-108">For the **File Path** field, specify the file name you want to write data to.</span></span> <span data-ttu-id="c9cc5-109">Если этот файл уже существует, его содержимое будет перезаписано.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-109">If this file already exist, its content will be overwritten.</span></span>  
  
    2.  <span data-ttu-id="c9cc5-110">В поле **Формат файла** укажите формат файла, который следует использовать.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-110">For the **File format** field, specify the file format you want to use.</span></span>  
  
        <span data-ttu-id="c9cc5-111">Если формат файла — "Текст", необходимо указать значение **символа-разделителя столбцов** .</span><span class="sxs-lookup"><span data-stu-id="c9cc5-111">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="c9cc5-112">Также выберите **имена столбцов в первой строке данных** , если первая строка в файле содержит имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-112">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  

        <span data-ttu-id="c9cc5-113">Если формат файла — ORC, вам потребуется установить JRE соответствующей платформы.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-113">If the file format is ORC, you need to install JRE of corresponding platform.</span></span> 
  
3.  <span data-ttu-id="c9cc5-114">После указания сведений о соединении переключитесь на страницу **Столбцы** , чтобы сопоставить столбцы источника со столбцами назначения для потока данных служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="c9cc5-114">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
