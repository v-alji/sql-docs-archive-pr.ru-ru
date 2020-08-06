---
title: Задача Hive для Azure HDInsight | Документы Майкрософт
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afphivetask.f1
- sql11.dts.designer.afphivetask.f1
ms.assetid: e1896c73-128a-4128-9814-3e01f7dfe19b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5905dee4a7a195a16d217b28b59cc10bb74dd9a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667350"
---
# <a name="azure-hdinsight-hive-task"></a><span data-ttu-id="1ae71-102">Задача Hive для Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="1ae71-102">Azure HDInsight Hive Task</span></span>
<span data-ttu-id="1ae71-103">**Задача Hive для Azure HDInsight** позволяет выполнить скрипт Hive в кластере Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="1ae71-103">Use the **Azure HDInsight Hive Task** to run Hive script on an Azure HDInsight cluster.</span></span>
     
<span data-ttu-id="1ae71-104">Чтобы добавить **задачу Hive для Azure HDInsight**, перетащите ее в конструктор SSIS, дважды щелкните или щелкните правой кнопкой мыши и выберите **Изменить** , чтобы открыть диалоговое окно **Редактор задач Hive для Azure HDInsight** .</span><span class="sxs-lookup"><span data-stu-id="1ae71-104">To add an **Azure HDInsight Hive Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Hive Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="1ae71-105">В следующем списке описаны поля этого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="1ae71-105">The following list describes fields in this dialog box.</span></span>  
  
1.  <span data-ttu-id="1ae71-106">В поле **HDInsightConnection** выберите существующий диспетчер подключений Azure HDInsight (или создайте новый), который ссылается на кластер Azure HDInsight, используемый для выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="1ae71-106">For the **HDInsightConnection** field, select an existing Azure HDInsight Connection Manager or create a new one that refers to the Azure HDInsight cluster used to execute the script.</span></span>
  
2.  <span data-ttu-id="1ae71-107">В поле **AzureStorageConnection** выберите существующий диспетчер подключений службы хранилища Azure (или создайте новый), который ссылается на учетную запись хранения Azure, связанную с кластером.</span><span class="sxs-lookup"><span data-stu-id="1ae71-107">For the **AzureStorageConnection** field, select an existing Azure Storage Connection Manager or create a new one that refers to the Azure Storage Account associated with the cluster.</span></span> <span data-ttu-id="1ae71-108">Это необходимо только в том случае, если требуется скачать выходные данные выполнения скрипта и журналы ошибок.</span><span class="sxs-lookup"><span data-stu-id="1ae71-108">This is only necessary if you want to download the script execution output and error logs.</span></span>
 
3.  <span data-ttu-id="1ae71-109">В поле **BlobContainer** укажите имя контейнера хранилища, связанного с кластером.</span><span class="sxs-lookup"><span data-stu-id="1ae71-109">For the **BlobContainer** field, specify the storage container name associated with the cluster.</span></span> <span data-ttu-id="1ae71-110">Это необходимо только в том случае, если требуется скачать выходные данные выполнения скрипта и журналы ошибок.</span><span class="sxs-lookup"><span data-stu-id="1ae71-110">This is only necessary if you want to download the script execution output and error logs.</span></span>
  
4.  <span data-ttu-id="1ae71-111">В поле **LocalLogFolder** укажите папку, в которую будут скачиваться выходные данные выполнения скрипта и журналы ошибок.</span><span class="sxs-lookup"><span data-stu-id="1ae71-111">For the **LocalLogFolder** field, specify the folder to which the script execution output and error logs will be downloaded to.</span></span> <span data-ttu-id="1ae71-112">Это необходимо только в том случае, если требуется скачать выходные данные выполнения скрипта и журналы ошибок.</span><span class="sxs-lookup"><span data-stu-id="1ae71-112">This is only necessary if you want to download the script execution output and error logs.</span></span>   
  
5.  <span data-ttu-id="1ae71-113">Существует два способа указать выполняемый скрипт Hive.</span><span class="sxs-lookup"><span data-stu-id="1ae71-113">There are two ways to specify the Hive script to execute:</span></span>
  
    1.  <span data-ttu-id="1ae71-114">**Встроенный скрипт**. Укажите значение в поле **Скрипт**, введя скрипт, который необходимо выполнить, в диалоговом окне **Введите сценарий**.</span><span class="sxs-lookup"><span data-stu-id="1ae71-114">**In-line script**: Specify the **Script** field by typing in-line the script to execute in the **Enter Script** dialog box.</span></span>
  
    2.  <span data-ttu-id="1ae71-115">**Файл скрипта**. Отправьте файл скрипта в хранилище BLOB-объектов Azure и укажите значение в поле **BlobName**.</span><span class="sxs-lookup"><span data-stu-id="1ae71-115">**Script file**: Upload the script file to Azure Blob Storage and specify the **BlobName** field.</span></span> <span data-ttu-id="1ae71-116">Если BLOB-объект не находится в используемом по умолчанию хранилище или контейнере, связанном с кластером HDInsight, нужно указать значения в полях **ExternalStorageAccountName** и **ExternalBlobContainer**.</span><span class="sxs-lookup"><span data-stu-id="1ae71-116">If the blob is not in the default storage account or container associated with the HDInsight cluster, the **ExternalStorageAccountName** and **ExternalBlobContainer** fields must be specified.</span></span> <span data-ttu-id="1ae71-117">Если используется внешний BLOB-объект, убедитесь в том, что он настроен как общедоступный.</span><span class="sxs-lookup"><span data-stu-id="1ae71-117">For an external blob, make sure that it is configured as publicly accessible.</span></span>  
  
     <span data-ttu-id="1ae71-118">Если использованы оба способа, будет задействован файл скрипта, а встроенный скрипт будет проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="1ae71-118">If both are specified, script file will be used and the in-line script will be ignored.</span></span>
