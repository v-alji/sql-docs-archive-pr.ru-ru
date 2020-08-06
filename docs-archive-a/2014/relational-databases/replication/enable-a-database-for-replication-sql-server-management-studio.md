---
title: Разрешение применения репликации для базы данных (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server replication]
ms.assetid: 8092faa3-9cff-4f81-926c-6a0070d1ce2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 307d52e24187e35c1c30f609facd13bfad569216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655622"
---
# <a name="enable-a-database-for-replication-sql-server-management-studio"></a><span data-ttu-id="57800-102">разрешить для базы данных применение репликации (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="57800-102">Enable a Database for Replication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="57800-103">Применение репликации для базы данных неявно разрешается, когда член предопределенной роли сервера **sysadmin** создает публикацию с помощью мастера создания публикаций.</span><span class="sxs-lookup"><span data-stu-id="57800-103">A database is implicitly enabled for replication when a member of the **sysadmin** fixed server role creates a publication with the New Publication Wizard.</span></span> <span data-ttu-id="57800-104">Член предопределенной роли сервера **sysadmin** может также явно разрешить применение репликации для базы данных, чтобы член предопределенной роли базы данных **db_owner** мог создать в этой базе данных одну или несколько публикаций.</span><span class="sxs-lookup"><span data-stu-id="57800-104">A member of the **sysadmin** fixed server role can also enable a database for replication explicitly, so that a member of the **db_owner** fixed database role can create one or more publications in that database.</span></span> <span data-ttu-id="57800-105">Чтобы в явном виде включить репликацию базы данных, используйте страницу **Базы данных публикации** диалогового окна **Свойства издателя — \<Publisher>** .</span><span class="sxs-lookup"><span data-stu-id="57800-105">To enable a database explicitly, use the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box.</span></span> <span data-ttu-id="57800-106">Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="57800-106">For more information about accessing this dialog box, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
### <a name="to-enable-a-database-for-replication"></a><span data-ttu-id="57800-107">Разрешение применения репликации для базы данных</span><span class="sxs-lookup"><span data-stu-id="57800-107">To enable a database for replication</span></span>  
  
1.  <span data-ttu-id="57800-108">На странице **Базы данных публикации** диалогового окна **Свойства издателя — \<Publisher>** установите флажки **Транзакционная** и (или) **Слияние** для каждой базы данных, которую требуется реплицировать.</span><span class="sxs-lookup"><span data-stu-id="57800-108">On the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box, select the **Transactional** and/or **Merge** check box for each database you want to replicate.</span></span> <span data-ttu-id="57800-109">Установите флажок **Транзакционная** , чтобы разрешить для базы данных репликацию моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="57800-109">Select **Transactional** to enable the database for snapshot replication.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
