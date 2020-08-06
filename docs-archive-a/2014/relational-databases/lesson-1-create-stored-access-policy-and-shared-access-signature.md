---
title: Занятие 2. Создание политики в контейнере и создание ключа подписи общего доступа (SAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41674d9d-8132-4bff-be4d-85a861419f3d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab209f08d53b25a4791ef675e6fb6b78cab115f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739929"
---
# <a name="lesson-2-create-a-policy-on-container-and-generate-a-shared-access-signature-sas-key"></a><span data-ttu-id="89e06-103">Занятие 2.</span><span class="sxs-lookup"><span data-stu-id="89e06-103">Lesson 2.</span></span> <span data-ttu-id="89e06-104">Создание политики в контейнере ключа и ключа подписанного URL-адреса</span><span class="sxs-lookup"><span data-stu-id="89e06-104">Create a policy on container and generate a Shared Access Signature (SAS) key</span></span>
  <span data-ttu-id="89e06-105">На этом занятии вы узнаете, как создать политику в контейнере больших двоичных объектов, а также сформировать ключ SAS.</span><span class="sxs-lookup"><span data-stu-id="89e06-105">In this lesson, you will learn how to create a policy on the Blob container and also generate a SAS key.</span></span>  
  
 <span data-ttu-id="89e06-106">Сохраненная политика доступа предоставляет дополнительный уровень контроля над подписанными URL-адресами на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="89e06-106">A stored access policy provides an additional level of control over shared access signatures on the server side.</span></span> <span data-ttu-id="89e06-107">Подписанный URL-адрес — URI, который предоставляет ограниченные права доступа к контейнерам, большим двоичным объектам, очередям и таблицам.</span><span class="sxs-lookup"><span data-stu-id="89e06-107">A shared access signature is a URI that grants restricted access rights to containers, blobs, queues, and tables.</span></span> <span data-ttu-id="89e06-108">При использовании этого расширения необходимо создать политику в контейнере с правами на чтение, запись и перечисление.</span><span class="sxs-lookup"><span data-stu-id="89e06-108">When using this new enhancement, you need to create a policy on a container with read, write, and list rights.</span></span>  
  
 <span data-ttu-id="89e06-109">Вы можете создать политику и подписанный URL-адрес с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="89e06-109">You can create a policy and a shared access signature by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="89e06-110">Azure REST API Operations: [Создание контейнера](https://msdn.microsoft.com/library/azure/dd179468.aspx), [Настройка ACL контейнера](https://msdn.microsoft.com/library/azure/dd179391.aspx)и [Получение списка ACL контейнера](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span><span class="sxs-lookup"><span data-stu-id="89e06-110">Azure REST API operations: [Create Container](https://msdn.microsoft.com/library/azure/dd179468.aspx), [Set Container ACL](https://msdn.microsoft.com/library/azure/dd179391.aspx), and [Get Container ACL](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span></span>  
  
-   <span data-ttu-id="89e06-111">[Метод CloudBlobContainer. GetSharedAccessSignature](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) в пакете SDK для Azure.</span><span class="sxs-lookup"><span data-stu-id="89e06-111">[CloudBlobContainer.GetSharedAccessSignature Method](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) in the Azure SDK.</span></span>  
  
    ```  
  
       string signature = blob.GetSharedAccessSignature(new SharedAccessPolicy()   
        {   
            // Specify the expiration time for the signature.   
            SharedAccessExpiryTime = DateTime.Now.Years(1),   
            // Specify the permissions granted by the signature.    
            Permissions = SharedAccessPermissions.Write | SharedAccessPermissions.Read   
        });  
  
    ```  
  
-   <span data-ttu-id="89e06-112">Сторонний инструмент Azure Explorer, например [Обозреватель службы хранилища Azure](https://azurestorageexplorer.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="89e06-112">A third-party Azure explorer tool, such as [Azure Storage Explorer](https://azurestorageexplorer.codeplex.com/).</span></span>  
  
 <span data-ttu-id="89e06-113">**Следующее занятие:**</span><span class="sxs-lookup"><span data-stu-id="89e06-113">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="89e06-114">Урок 3. Создание учетных данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="89e06-114">Lesson 3: Create a SQL Server Credential</span></span>](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)  
  
