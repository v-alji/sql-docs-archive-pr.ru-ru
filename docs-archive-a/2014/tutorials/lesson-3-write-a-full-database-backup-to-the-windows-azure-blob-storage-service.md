---
title: Занятие 3. запись полной резервной копии базы данных в службу хранилища BLOB-объектов Azure | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 454c8296-64e9-46ed-b141-5ebfbc8a4fe2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 17e7e6b608d248a48cde52f1107bb910f06d64ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727521"
---
# <a name="lesson-3-write-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="12b9f-102">Урок 3. Запись полной резервной копии базы данных в службу хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="12b9f-102">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>
  <span data-ttu-id="12b9f-103">На этом занятии показано использование инструкции TSQL для выполнения полной резервной копии базы данных в службе хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="12b9f-103">This lesson demonstrates the use of tsql statement to perform a full database backup to Azure Blob storage service.</span></span>  
  
## <a name="perform-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="12b9f-104">Выполнение полной резервной копии базы данных в службе хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="12b9f-104">Perform a Full Database Backup to the Azure Blob Storage Service</span></span>  
 <span data-ttu-id="12b9f-105">Для создания полной резервной копии базы данных выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="12b9f-105">To create a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="12b9f-106">соединение с [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)];</span><span class="sxs-lookup"><span data-stu-id="12b9f-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="12b9f-107">в **обозревателе объектов**установите соединение с экземпляром компонента [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)];</span><span class="sxs-lookup"><span data-stu-id="12b9f-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="12b9f-108">на панели меню «Стандартная» выберите пункт **Создать запрос**;</span><span class="sxs-lookup"><span data-stu-id="12b9f-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="12b9f-109">скопируйте следующий пример в окно запроса, при необходимости измените его и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="12b9f-109">Copy and paste the following example into the query window, modify as needed, and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE[AdventureWorks2012]   
    TO URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    /* URL includes the endpoint for the BLOB service, followed by the container name, and the name of the backup file*/   
    WITH CREDENTIAL = 'mycredential';  
    /* name of the credential you created in the previous step */   
    GO  
  
    ```  
  
5.  <span data-ttu-id="12b9f-110">В обозревателе объектов подключитесь к хранилищу Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="12b9f-110">In the object explorer, connect to Azure Storage.</span></span> <span data-ttu-id="12b9f-111">Найдите папку с контейнером и только что созданными файлами резервной копии.</span><span class="sxs-lookup"><span data-stu-id="12b9f-111">Browse to find the container and the newly created backup files.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="12b9f-112">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="12b9f-112">Next Lesson</span></span>  
 <span data-ttu-id="12b9f-113">[Занятие 4. Восстановление из полной резервной копии базы данных](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span><span class="sxs-lookup"><span data-stu-id="12b9f-113">[Lesson 4: Perform a Restore From a Full Database Backup](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span></span>  
  
  
