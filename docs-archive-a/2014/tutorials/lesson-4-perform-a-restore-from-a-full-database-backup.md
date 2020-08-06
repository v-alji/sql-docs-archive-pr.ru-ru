---
title: Занятие 4. Восстановление из полной резервной копии базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 580f76e6-9802-4abc-9043-db6de592c733
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9906ea14c2f76a49644a8f76fbd894adf8b9d500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658585"
---
# <a name="lesson-4-perform-a-restore-from-a-full-database-backup"></a><span data-ttu-id="5077f-102">Занятие 4: Восстановление базы данных из полной резервной копии</span><span class="sxs-lookup"><span data-stu-id="5077f-102">Lesson 4: Perform a Restore From a Full Database Backup</span></span>
  <span data-ttu-id="5077f-103">На этом занятии рассматривается использование инструкции TSQL для выполнения восстановления из полной резервной копии базы данных, созданной на предыдущем уроке.</span><span class="sxs-lookup"><span data-stu-id="5077f-103">This lesson demonstrates the use of a tsql statement to perform a restore from a full database backup created in the previous lesson.</span></span>  
  
## <a name="perform-a-restore-of-a-database-backup"></a><span data-ttu-id="5077f-104">Выполнение восстановления резервной копии базы данных</span><span class="sxs-lookup"><span data-stu-id="5077f-104">Perform a Restore of a Database Backup</span></span>  
 <span data-ttu-id="5077f-105">Для восстановления базы данных с помощью полной резервной копии выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5077f-105">To restore a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="5077f-106">соединение с [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)];</span><span class="sxs-lookup"><span data-stu-id="5077f-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="5077f-107">в **обозревателе объектов**установите соединение с экземпляром компонента [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)];</span><span class="sxs-lookup"><span data-stu-id="5077f-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="5077f-108">на панели меню «Стандартная» выберите пункт **Создать запрос**;</span><span class="sxs-lookup"><span data-stu-id="5077f-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="5077f-109">Скопируйте и вставьте следующий пример в окно запроса (при необходимости измените).</span><span class="sxs-lookup"><span data-stu-id="5077f-109">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks2012   
    FROM URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    WITH CREDENTIAL = 'mycredential';  
    , STATS = 5 - use this to see monitor the progress  
    GO  
  
    ```  
  
5.  <span data-ttu-id="5077f-110">Проверьте инструкцию T-SQL и нажмите кнопку " **выполнить** ".</span><span class="sxs-lookup"><span data-stu-id="5077f-110">Verify the T-SQL statement and click **Execute**</span></span>  
  
### <a name="return-to-tutorials-portal"></a><span data-ttu-id="5077f-111">Возвращение к порталу учебников</span><span class="sxs-lookup"><span data-stu-id="5077f-111">Return to Tutorials Portal</span></span>  
 <span data-ttu-id="5077f-112">[Учебник. SQL Server резервное копирование и восстановление в службе хранилища BLOB-объектов Azure](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="5077f-112">[Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span></span>  
  
  
