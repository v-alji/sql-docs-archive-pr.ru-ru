---
title: Назначение больших двоичных объектов Azure | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdest.f1
- sql11.dts.designer.afpblobdest.f1
ms.assetid: 820a1e7a-7182-4c7b-ab56-5b4097a7e042
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb406d38b17748e8284acee4b2849a9fd99e53ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738555"
---
# <a name="azure-blob-destination"></a><span data-ttu-id="b084f-102">Назначение больших двоичных объектов Azure</span><span class="sxs-lookup"><span data-stu-id="b084f-102">Azure Blob Destination</span></span>
  <span data-ttu-id="b084f-103">Компонент **Назначение больших двоичных объектов Azure** позволяет пакету SSIS записывать данные в BLOB-объект Azure.</span><span class="sxs-lookup"><span data-stu-id="b084f-103">The **Azure Blob Destination** component enables an SSIS package to write data to an Azure blob.</span></span> <span data-ttu-id="b084f-104">Поддерживаются следующие форматы файлов: CSV и AVRO.</span><span class="sxs-lookup"><span data-stu-id="b084f-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="b084f-105">Ддраг. Перетащите **назначение больших двоичных объектов Azure** в конструктор потока данных и дважды щелкните его, чтобы открыть редактор.</span><span class="sxs-lookup"><span data-stu-id="b084f-105">Ddrag-drop **Azure Blob Destination** to the data flow designer and double-click it to see the editor).</span></span>  
  
1.  <span data-ttu-id="b084f-106">В поле **Диспетчер подключений службы хранилища Azure** укажите существующий диспетчер подключений службы хранилища Azure или создайте новый, который ссылается на учетную запись хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="b084f-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="b084f-107">В поле **Имя контейнера больших двоичных объектов** укажите имя контейнера больших двоичных объектов, который содержит исходные файлы.</span><span class="sxs-lookup"><span data-stu-id="b084f-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="b084f-108">В поле **Имя большого двоичного объекта** укажите путь к большому двоичному объекту.</span><span class="sxs-lookup"><span data-stu-id="b084f-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="b084f-109">В поле **Формат файла большого двоичного объекта** укажите формат большого двоичного объекта, который следует использовать.</span><span class="sxs-lookup"><span data-stu-id="b084f-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="b084f-110">Если формат файла — CSV, необходимо указать значение **знака-разделителя столбцов** .</span><span class="sxs-lookup"><span data-stu-id="b084f-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="b084f-111">Также выберите **имена столбцов в первой строке данных** , если первая строка в файле содержит имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="b084f-111">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="b084f-112">После указания сведений о соединении переключитесь на страницу **Столбцы** , чтобы сопоставить столбцы источника со столбцами назначения для потока данных служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="b084f-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
