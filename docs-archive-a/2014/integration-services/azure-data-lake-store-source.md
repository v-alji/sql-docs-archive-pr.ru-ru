---
title: Источник Azure Data Lake Store | Документы Майкрософт
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSSRC.F1
- SQL11.DTS.DESIGNER.AFPADLSSRC.F1
ms.assetid: 7d9e8457-62aa-4aea-98ee-7d1121dfae4f
author: yualan
ms.author: chugu
ms.openlocfilehash: e5bce25e303b055d734da6a00c73851f4eb0d7ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665511"
---
# <a name="azure-data-lake-store-source"></a><span data-ttu-id="d22ee-102">Источник Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="d22ee-102">Azure Data Lake Store Source</span></span>
  <span data-ttu-id="d22ee-103">Компонент **Источник Azure Data Lake Store** позволяет пакету служб SSIS считывать данные из Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="d22ee-103">The **Azure Data Lake Store Source** component enables an SSIS package to read data from an Azure Data Lake Store.</span></span> <span data-ttu-id="d22ee-104">Поддерживаются следующие форматы файлов: текст и AVRO.</span><span class="sxs-lookup"><span data-stu-id="d22ee-104">The supported file formats are: Text and Avro.</span></span>
  
## <a name="configure-the-azure-data-lake-store-source"></a><span data-ttu-id="d22ee-105">Настройка источника Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="d22ee-105">Configure the Azure Data Lake Store Source</span></span> 
  
1.  <span data-ttu-id="d22ee-106">Чтобы отобразить редактор для источника Azure Data Lake Store, перетащите компонент **Источник Azure Data Lake Store** в конструктор потока данных и дважды щелкните его, чтобы открыть редактор.</span><span class="sxs-lookup"><span data-stu-id="d22ee-106">To see the editor for the Azure Data Lake Store Source, drag and drop **Azure Data Lake Store Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
2.  <span data-ttu-id="d22ee-107">В поле **Диспетчер подключений Azure Data Lake Store** укажите существующий диспетчер подключений Azure Data Lake Store или создайте новый диспетчер, который ссылается на службу Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="d22ee-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="d22ee-108">В поле **Путь к файлу** укажите путь к исходному файлу в Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="d22ee-108">For the **File Path** field, specify the file path of the source file in Azure Data Lake Store.</span></span>   
  
    2.  <span data-ttu-id="d22ee-109">В поле **Формат файла** укажите формат исходного файла.</span><span class="sxs-lookup"><span data-stu-id="d22ee-109">For the **File format** field, specify the file format of the source file.</span></span>  
  
        <span data-ttu-id="d22ee-110">Если формат файла — "Текст", необходимо указать значение **символа-разделителя столбцов** .</span><span class="sxs-lookup"><span data-stu-id="d22ee-110">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="d22ee-111">Также выберите **Имена столбцов в первой строке данных** , если первая строка файла содержит имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="d22ee-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
3.  <span data-ttu-id="d22ee-112">После указания сведений о соединении переключитесь на страницу **Столбцы** , чтобы сопоставить столбцы источника со столбцами назначения для потока данных служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="d22ee-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
