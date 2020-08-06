---
title: Источник BLOB-объекта Azure | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobsrc.f1
- sql11.dts.designer.afpblobsrc.f1
ms.assetid: 80645c5c-88c8-4fb0-8607-de1bb7bffcbb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a14c7022437c8a23f898a0f29c211bd9ae82aa0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667844"
---
# <a name="azure-blob-source"></a><span data-ttu-id="50815-102">Компонент Azure Blob Source</span><span class="sxs-lookup"><span data-stu-id="50815-102">Azure Blob Source</span></span>
 <span data-ttu-id="50815-103">Компонент **Azure Blob Source** позволяет пакету служб SSIS считывать данные из большого двоичного объекта Azure.</span><span class="sxs-lookup"><span data-stu-id="50815-103">The **Azure Blob Source** component enables an SSIS package to read data from an Azure blob.</span></span> <span data-ttu-id="50815-104">Поддерживаются следующие форматы файлов: CSV и AVRO.</span><span class="sxs-lookup"><span data-stu-id="50815-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="50815-105">Чтобы отобразить редактор источников больших двоичных объектов Azure, перетащите компонент **Azure Blob Source** в конструктор потока данных и дважды щелкните его, чтобы открыть редактор.</span><span class="sxs-lookup"><span data-stu-id="50815-105">To see the editor for the Azure Blob Source, drag and drop **Azure Blob Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
1.  <span data-ttu-id="50815-106">В поле **Диспетчер подключений службы хранилища Azure** укажите существующий диспетчер подключений службы хранилища Azure или создайте новый, который ссылается на учетную запись хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="50815-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="50815-107">В поле **Имя контейнера больших двоичных объектов** укажите имя контейнера больших двоичных объектов, который содержит исходные файлы.</span><span class="sxs-lookup"><span data-stu-id="50815-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="50815-108">В поле **Имя большого двоичного объекта** укажите путь к большому двоичному объекту.</span><span class="sxs-lookup"><span data-stu-id="50815-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="50815-109">В поле **Формат файла большого двоичного объекта** укажите формат большого двоичного объекта, который следует использовать.</span><span class="sxs-lookup"><span data-stu-id="50815-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="50815-110">Если формат файла — CSV, необходимо указать значение **знака-разделителя столбцов** .</span><span class="sxs-lookup"><span data-stu-id="50815-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="50815-111">Также выберите **Имена столбцов в первой строке данных** , если первая строка файла содержит имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="50815-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="50815-112">После указания сведений о соединении переключитесь на страницу **Столбцы** , чтобы сопоставить столбцы источника со столбцами назначения для потока данных служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="50815-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
